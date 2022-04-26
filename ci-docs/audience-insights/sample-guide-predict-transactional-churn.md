---
title: Exempelguide för förutsägelse om transaktionell omsättning
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om transaktionell omsättning.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d3465b7eaa17a24e2926b8ea432b33e705931b88
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555381"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Exempelguide för förutsägelse om transaktionell omsättning

Den här guiden ger dig ett komplett exempel på förutsägelse av transaktionell omsättning i Customer Insights med hjälp av de data som anges nedan. Inga data som används i den här guiden är riktiga kunddata och är en del av Contoso-datauppsättningen som finns i miljön *Demo* i din Customer Insights-prenumeration.

## <a name="scenario"></a>Scenario

Contoso är ett företag som producerar kaffe och kaffemaskiner av hög kvalitet, som de säljer via Contoso Coffee-webbplatsen. Deras mål är att veta vilka kunder som vanligtvis köper deras produkter regelbundet kommer att sluta vara aktiva kunder under de närmaste 60 dagarna. Att veta vilka av deras kunder som **sannolikt kommer att omsättas** kan hjälpa dem att spara marknadsföringsinsatser genom att fokusera på att behålla dem.

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.
- Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).

## <a name="task-1---ingest-data"></a>Uppgift 1 – Mata in data

Läs specifikt artiklarna [om datainmatning](data-sources.md) och [import av datakällor med hjälp av Power Query-anslutningar](connect-power-query.md). Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Mata in kunddata från e-handelsplattformen

1. Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasscontacts.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Tid/Zon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Omvandla födelsedatum till datum.":::

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **eCommerceContacts**

1. Spara datakällan.

### <a name="ingest-online-purchase-data"></a>Mata in inköpsdata online

1. Lägg till ytterligare en datauppsättning till samma **e-handelskälla**. Välj anslutningsprogrammet **Text/CSV** igen.

1. Ange URL för **Onlineköpsdata** https://aka.ms/ciadclassonline.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **PurchasedOn**: Datum/tid
   - **TotalPrice**: Valuta
   
1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **eCommercePurchases**.

1. Spara datakällan.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Mata in kunddata från lojalitetsschema

1. Skapa en datakälla med namnet **LoyaltyScheme**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasscustomerloyalty.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **DateOfBirth**: Datum
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Datum/Tid

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **loyCustomers**.

1. Spara datakällan.


## <a name="task-2---data-unification"></a>Uppgift 2 – Dataförening

Efter inmatning av datan börjar vi nu processen **mappa, matcha, slå samman** för att skapa en enhetlig kundprofil. Mer information finns i [Dataförening](data-unification.md).

### <a name="map"></a>Mappa

1. Efter inmatande av data mappar du kontakter från e-handels- och lojalitetsdata till vanliga datatyper. Gå till **Data** > **Förena** > **Mappa**.

1. Välj de entiteter som representerar kundprofilen – **eCommerceContacts** och **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="förena e-handels- och lojalitetsdatakällor.":::

1. Välj **ContactId** som primärnyckel för **eCommerceContacts** och **LoyaltyID** som primärnyckel för **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Förena LoyaltyId som primärnyckel.":::

### <a name="match"></a>Matchning

1. Gå till fliken **Matcha** och välj **Ange ordning**.

1. I listrutan **Primär** väljer du **eCommerceContacts : eCommerce** som primär källa och inkluderar samtliga poster.

1. I listrutan **Entitet 2** väljer du **loyCustomers : LoyaltyScheme** och inkluderar alla poster.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Förena matchande e-handel och lojalitet.":::

1. Välj **Skapa en ny regel**

1. Lägg till ditt första villkor med hjälp av FullName.

   * För eCommerceContacts väljer du **FullName** i listrutan.
   * För loyCustomers väljer du **FullName** i listrutan.
   * Välj listrutan **Normalisera** och välj **Typ (telefon, namn, adress ...)**.
   * Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.

1. Ange namnet **FullName, E-post** för den nya regeln.

   * Lägg till ett andra villkor för e-postadress genom att välja **Lägg till villkor**
   * För entiteten eCommerceContacts väljer du **EMail** i listrutan.
   * För entiteten loyCustomers väljer du **EMail** i listrutan. 
   * Lämna Normalisera tomt. 
   * Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Förena matchningsregel för namn och e-post.":::

7. Välj **Spara** och **Kör**.

### <a name="merge"></a>Slå ihop

1. Gå till fliken **Sammanslå**.

1. På **ContactId** för entiteten **loyCustomers** ändrar du visningsnamnet till **ContactIdLOYALTY** för att särskilja den från andra inmatade ID.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="byta namn på contactid från lojalitets-id.":::

1. Välj **Spara** och **Kör** för att starta sammanslagningsprocessen.



## <a name="task-3---configure-transaction-churn-prediction"></a>Uppgift 3 – Konfigurera förutsägelsen om transaktionell omsättning

Med de enhetliga kundprofilerna på plats kan vi nu köra förutsägelsen om prenumerationsomsättning. Detaljerade anvisningar finns i artikeln [Förutsägelse av prenumerationsomsättning](predict-subscription-churn.md). 

1. Gå till **Intelligens** > **Utforska** och välj att använda **modellen Kundomsättning**.

1. Välj alternativet **Transaktionell** och välj **Kom igång**.

1. Namnge modellen **OOB förutsägelse om transaktionell omsättning inom e-handel** och utdataentiteten **OOBeCommerceChurnPrediction**.

1. Definiera två villkor för omsättningsmodellen:

   * **Fönsstret Förutsägelse**: **minst 60** dagar. Den här inställningen definierar hur långt in i framtiden vi vill förutsäga kundomsättning.

   * **Omsättningsdefinition**: **minst 60** dagar. Tidsperiod utan köp varefter en kund anses vara omsatt.

     :::image type="content" source="media/model-levers.PNG" alt-text="Välj modellens förutsägelsefönster och omsättningsdefinition.":::

1. Välj **Inköpshistorik (obligatoriskt)** och välj **Lägg till data** för inköpshistorik.

1. Lägg till entiteten **eCommercePurchases: e-handel** och mappa fälten från e-handel till motsvarande fält som krävs av modellen.

1. Anslut till entiteten **eCommercePurchases: e-handel** med **eCommerceContacts: e-handel**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Anslut e-handelsentiteter.":::

1. Välj **Nästa** för att ange modellschemat.

   Modellen måste träna regelbundet för att lära sig nya mönster när det finns nya data inmatade. För det här exemplet väljer du **Månadsvis**.

1. När du har granskat alla detaljer väljer du **Spara och kör**.

## <a name="task-4---review-model-results-and-explanations"></a>Uppgift 4 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Du kan nu granska förklaringar av modellen för prenumerationsomsättning. Mer information finns i [Granska en förutsägelsestatus och resultat](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Uppgift 5 – Skapa ett segment med kunder med hög omsättningsrisk

Om du kör produktionsmodellen skapas en ny entitet som du kan se i **Data** > **Entiteter**.   

Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.

1.  Gå till **Segment**. Välj **Nytt** och välj **Skapa från** > **Intelligens**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Skapa ett segment med modellutdata.":::

1. Välj slutpunkten **OOBSubscriptionChurnPrediction** och definiera segmentet: 
   - Fält: ChurnScore
   - Operatör: större än
   - Värde: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Konfigurera segment för prenumerationsomsättning.":::

Du har nu ett segment som uppdateras dynamiskt som identifierar kunder med hög omsättningsrisk för den här prenumerationsverksamheten.

Mer information finns i [Skapa och hantera segment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
