---
title: Exempelguide för förutsägelse av produktrekommendationer
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om produktrekommendation.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270538"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Exempelguide för förutsägelse av produktrekommendationer (förhandsversion)

Vi ger dig ett komplett exempel på förutsägelse av produktrekommendation med hjälp av de exempeldata som anges nedan.

## <a name="scenario"></a>Scenario

Contoso är ett företag som producerar kaffe och kaffemaskiner av hög kvalitet, som de säljer via Contoso Coffee-webbplatsen. Målet är att förstå vilka produkter de ska rekommendera till sina återkommande kunder. Om du vet vilka kunder som **sannolikt kommer att köpa**, kan du göra besparingar på marknadsföring genom att fokusera på specifika objekt.

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.
- Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).

## <a name="task-1---ingest-data"></a>Uppgift 1 – Mata in data

Granska artiklarna [om datainmatning](data-sources.md) och [import av datakällor med hjälp av Power Query-anslutningsprogram](connect-power-query.md) specifikt. Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Mata in kunddata från e-handelsplattformen

1. Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasscontacts.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Tid/Zon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformera födelsedatum till datum.":::

5. I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **eCommerceContacts**

6. **Spara** datakällan.

### <a name="ingest-online-purchase-data"></a>Mata in inköpsdata online

1. Lägg till ytterligare en datauppsättning till samma **e-handelskälla**. Välj anslutningsprogrammet **Text/CSV** igen.

1. Ange URL för **Onlineköpsdata** https://aka.ms/ciadclassonline.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **PurchasedOn**: Datum/tid
   - **TotalPrice**: Valuta

1. I fältet **Namn** i sidofönstret byter du namn på din datakälla från **Fråga** till **eCommercePurchases**.

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

2. Välj de entiteter som representerar kundprofilen – **eCommerceContacts** och **loyCustomers**.

   ![förena e-handels- och lojalitetsdatakällor.](media/unify-ecommerce-loyalty.png)

3. Välj **ContactId** som primärnyckel för **eCommerceContacts** och **LoyaltyID** som primärnyckel för **loyCustomers**.

   ![Förena LoyaltyId som primärnyckel.](media/unify-loyaltyid.png)

### <a name="match"></a>Matchning

1. Gå till fliken **Matcha** och välj **Ange ordning**.

2. I listrutan **Primär** väljer du **eCommerceContacts: e-handel** som primär källa och inkluderar alla poster.

3. I listrutan **Entitet 2** väljer du **loyCustomers: LoyaltyScheme** och inkluderar alla poster.

   ![Förena matchande e-handel och lojalitet.](media/unify-match-order.png)

4. Välj **Skapa en ny regel**

5. Lägg till ditt första villkor med hjälp av FullName.

   - För eCommerceContacts välj **FullName** i listrutan.
   - För loyCustomers välj **FullName** i listrutan.
   - Välj listrutan **Normalisera** och välj **Typ (telefon, namn, adress ...)**.
   - Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.

6. Ange namnet **FullName, E-post** för den nya regeln.

   - Lägg till ett andra villkor för e-postadress genom att välja **Lägg till villkor**
   - För entitet eCommerceContacts väljer du **EMail** i listrutan.
   - För entitet loyCustomers väljer du **EMail** i listrutan.
   - Lämna Normalisera tomt.
   - Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.

   ![Förena matchningsregel för namn och e-post.](media/unify-match-rule.png)

7. Välj **Spara** och **Kör**.

### <a name="merge"></a>Slå ihop

1. Gå till fliken **Sammanslå**.

1. På **ContactId** för entiteten **loyCustomers** ändrar du visningsnamnet till **ContactIdLOYALTY** för att särskilja den från andra inmatade ID.

   ![byta namn på contactid från lojalitets-id.](media/unify-merge-contactid.png)

1. Välj **Spara** och **Kör** för att starta sammanslagningsprocessen.

## <a name="task-3---configure-product-recommendation-prediction"></a>Uppgift 3 – Konfigurera förutsägelse av produktrekommendation

Med de enhetliga kundprofilerna på plats kan vi nu köra förutsägelsen om prenumerationsomsättning.

1. Gå till **Intelligens** > **Förutsägelse** välj **Produktrekommendation**.

1. Välj **Komma igång**.

1. Namnge modellen **OOB modellförutsägelse av produktrekommendation** och utdataentiteten **OOBProductRecommendationModelPrediction**.

1. Definiera tre villkor för modellen:

   - **Antal produkter**: Sätt detta värde på **5**. Den här inställningen anger hur många produkter du vill rekommendera till kunderna.

   - **Föreslå produkter som kunder nyligen har köpt?**: Välj **Ja** för att ange att du vill inkludera produkter i rekommendationen som dina kunder har köpt tidigare.

   - **Fönstret Titta bakåt:** Välj minst **365 dagar**. Den här inställningen definierar hur långt bak i tiden som modellen tittar på kundens aktivitet för att använda den som indata i rekommendationerna.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinställningar för produktrekommendationsmodellen.":::

1. Välj **Data som krävs** och välj **Lägg till data** för köphistorik.

1. Lägg till entiteten **eCommercePurchases: e-handel** och mappa fälten från e-handel till motsvarande fält som krävs av modellen.

1. Anslut till entiteten **eCommercePurchases: e-handel** med **eCommerceContacts: e-handel**.

   ![Anslut e-handelsentiteter.](media/model-purchase-join.png)

1. Välj **Nästa** för att ange modellschemat.

   Modellen måste träna regelbundet för att lära sig nya mönster när det finns nya data inmatade. För det här exemplet väljer du **Månadsvis**.

1. När du har granskat alla detaljer väljer du **Spara och kör**.


## <a name="task-4---review-model-results-and-explanations"></a>Uppgift 4 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Du kan nu granska förklaringar av modellen för produktrekommendationer. Mer information finns i [Granska en förutsägelsestatus och resultat](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Uppgift 5 – Skapa ett segment med ofta köpta produkter

Om du kör produktionsmodellen skapas en ny entitet som du kan se i **Data** > **Entiteter**.

Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.

1. Gå till **Segment**. Välj **Nytt** och välj **Skapa från** > **Intelligens**.

   ![Skapa ett segment med modellutdata.](media/segment-intelligence.png)

1. Välj slutpunkten **OOBProductRecommendationModelPrediction** och definiera segmentet:

   - Fält: Produkt-ID
   - Operator: Värde
   - Värde: Välj de tre översta produkt-ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Skapa ett segment utifrån modellresultatet.":::

Nu har du ett segment som uppdateras dynamiskt och identifierar de kunder som är mer villiga att köpa de tre mest rekommenderade produkterna 

Mer information finns i [Skapa och hantera segment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]