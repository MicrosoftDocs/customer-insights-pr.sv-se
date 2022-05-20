---
title: Exempelguide för förutsägelse av produktrekommendationer
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om produktrekommendation.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762708"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Exempelguide för förutsägelse av produktrekommendationer

Vi ger dig ett komplett exempel på förutsägelse av produktrekommendation med hjälp av de exempeldata som anges nedan.

## <a name="scenario"></a>Scenario

Contoso är ett företag som producerar kaffe och kaffemaskiner av hög kvalitet, som de säljer via Contoso Coffee-webbplatsen. Målet är att förstå vilka produkter de ska rekommendera till sina återkommande kunder. Om du vet vilka kunder som **sannolikt kommer att köpa**, kan du göra besparingar på marknadsföring genom att fokusera på specifika objekt.

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.
- Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).

## <a name="task-1---ingest-data"></a>Uppgift 1 – Mata in data

Läs specifikt artiklarna [om datainmatning](data-sources.md) och [import av datakällor med hjälp av Power Query-anslutningar](connect-power-query.md). Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Mata in kunddata från e-handelsplattformen

1. Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för eCommerce: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Tid/Zon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformera födelsedatum till datum.":::

1. I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **eCommerceContacts**

1. **Spara** datakällan.

### <a name="ingest-online-purchase-data"></a>Mata in inköpsdata online

1. Lägg till ytterligare en datauppsättning till samma **e-handelskälla**. Välj anslutningsprogrammet **Text/CSV** igen.

1. Ange URL för **Onlineköp** data [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **PurchasedOn**: Datum/tid
   - **TotalPrice**: Valuta

1. I fältet **Namn** i sidofönstret byter du namn på din datakälla från **Fråga** till **eCommercePurchases**.

1. **Spara** datakällan.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Mata in kunddata från lojalitetsschema

1. Skapa en datakälla med namnet **LoyaltyScheme**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Datum/Tid

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **loyCustomers**.

1. **Spara** datakällan.

## <a name="task-2---data-unification"></a>Uppgift 2 – Dataförening

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Uppgift 3 – Konfigurera förutsägelse av produktrekommendation

Med Unified customer profile på plats kan vi nu köra produktrekommendationen prediktion.

1. Gå till **Intelligens** > **Förutsägelse** välj **Produktrekommendation**.

1. Välj **Komma igång**.

1. Namnge modellen **OOB modellförutsägelse av produktrekommendation** och utdataentiteten **OOBProductRecommendationModelPrediction**.

1. Definiera tre villkor för modellen:

   - **Antal produkter**: Sätt detta värde på **5**. Den här inställningen anger hur många produkter du vill rekommendera till kunderna.

   - **Upprepade köp förväntas**: Välj **Ja** för att ange att du vill inkludera produkter i rekommendationen som dina kunder har köpt tidigare.

   - **Fönstret Titta bakåt:** Välj minst **365 dagar**. Den här inställningen definierar hur långt bak i tiden som modellen tittar på kundens aktivitet för att använda den som indata i rekommendationerna.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinställningar för produktrekommendationsmodellen.":::

1. I **Lägg till obligatoriska data**, välj **Lägg till data**.

1. I fönstret **Lägg till data**, välj **SalesOrderLine** som entitet för inköpshistorik. Så här dags är det troligen inte konfigurerat ännu. Öppna länken i fönstret om du vill skapa aktiviteten med följande steg:
   1. Ange ett **Aktivitetsnamn** och välj *eCommercePurchases:eCommerce* som **Entiteten aktivitet**. Den **primära nyckeln** är *PurchaseId*.
   1. Definiera och namnge relationen till *eCommerceContacts:eCommerce entity* och välj **ContactId** som utländsk nyckel.
   1. För Aktivitetssammanslagning, ställ in **Händelseaktivitet** som *TotalPrice* och tidsstämpel till *PurchasedOn*. Du kan ange fler fält enligt beskrivningen i [kundaktiviteter](activities.md).
   1. För **aktivitetstyp**, välj *SalesOrderLine*. Mappa följande aktivitetsfält:
      - Orderrad-ID: PurchaseId
      - Inköpsorder-ID: PurchaseId
      - Orderdata: PurchasedOn
      - Produkt-ID: ProductId
      - Summa: TotalPrice
   1. Granska och slutför aktiviteten innan du går tillbaka till modellkonfigurationen.

1. Tillbaka i steget **Välj aktiviteter**, välj den nyligen skapade aktiviteten i avsnittet **Aktiviteter**. Välj **Nästa** så fylls attributmappningen i. Välj **Spara**.

1. I denna exempelguide hoppar vi över ange **Lägg till produktinformation** och **Produktfilter** eftersom det inte finns några produktinformationsdata.

1. I steget **Datauppdateringar**, ange modellschemat.

   Modellen måste träna regelbundet för att lära sig nya mönster när det finns nya data inmatade. För det här exemplet väljer du **Månadsvis**.

1. När du har granskat alla detaljer väljer du **Spara och kör**. Det tar några minuter att köra modellen första gången.

## <a name="task-4---review-model-results-and-explanations"></a>Uppgift 4 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Du kan nu granska förklaringar av modellen för produktrekommendationer. Mer information finns i [Granska en förutsägelsestatus och resultat](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Uppgift 5 – Skapa ett segment med ofta köpta produkter

Om du kör produktionsmodellen skapas en ny entitet som du kan se i **Data** > **Entiteter**.

Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.

1. Gå till **Segment**. Välj **Nytt** och välj **Skapa från Intelligens**.

   ![Skapa ett segment med modellutdata.](media/segment-intelligence.png)

1. Välj slutpunkten **OOBProductRecommendationModelPrediction** och definiera segmentet:

   - Fält: Produkt-ID
   - Värde: Välj de tre översta produkt-ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Skapa ett segment utifrån modellresultatet.":::

Nu har du ett segment som uppdateras dynamiskt och identifierar de kunder som kan vara intresserade av att köpa de tre mest rekommenderade produkterna.

Mer information finns i [Skapa och hantera segment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
