---
title: Exempelguide för förutsägelse om transaktionell omsättning
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om transaktionell omsättning.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741341"
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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Uppgift 3 – Konfigurera förutsägelsen om transaktionell omsättning

Med Unified customer profile på plats kan vi nu köra prediktion för transaktionsomsättning. Detaljerade anvisningar finns i artikeln [prediktion för transaktionsomsättning](predict-transactional-churn.md). 

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

Låt modellen slutföra träningen och bedömningen av data. Nu kan du se vilken omsättningsmodell som används. Mer information finns i [Granska en förutsägelsestatus och resultat](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Uppgift 5 – Skapa ett segment med kunder med hög omsättningsrisk

Om du kör produktionsmodellen skapas en ny entitet som du kan se i **Data** > **Entiteter**.   

Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.

1.  Gå till **Segment**. Välj **Nytt** och välj **Skapa från** > **Intelligens**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Skapa ett segment med modellutdata.":::

1. Välj slutpunkten **OOBeCommerceChurnPrediction** ch definiera segmentet: 
   - Fält: ChurnScore
   - Operatör: större än
   - Värde: 0,6

Nu har du ett segment som uppdateras dynamiskt och som identifierar kunder med hög risk.

Mer information finns i [Skapa och hantera segment](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
