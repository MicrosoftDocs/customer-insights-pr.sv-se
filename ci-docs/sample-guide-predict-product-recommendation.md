---
title: Exempelguide för förutsägelse av produktrekommendationer
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om produktrekommendation.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610166"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Exempelguide för förutsägelse av produktrekommendationer

Guiden leder dig genom komplett exempel på förutsägelse av produktrekommendation med hjälp av de exempeldata. Vi rekommenderar att du provar denna prediktion [i en ny miljö](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso är ett företag som tillverkar kaffe och kaffeautomater av hög kvalitet. De säljer produkterna via Contoso Coffees webbplats. Målet är att förstå vilka produkter de ska rekommendera till sina återkommande kunder. Om du vet vilka kunder som **sannolikt kommer att köpa**, kan du göra besparingar på marknadsföring genom att fokusera på specifika objekt.

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.

## <a name="task-1---ingest-data"></a>Uppgift 1 – Mata in data

Läs artiklarna [om datainmatning](data-sources.md) och [ansluta till en Power Query datakälla](connect-power-query.md). Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Mata in kunddata från e-handelsplattformen

1. Skapa en Power Query datakälla med namnet **eCommerce** och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter: https://aka.ms/ciadclasscontacts.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Tid/Zon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformera födelsedatum till datum.":::

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla till **eCommerceContacts**.

1. **Spara** datakällan.

### <a name="ingest-online-purchase-data"></a>Mata in inköpsdata online

1. Lägg till ytterligare en datauppsättning till samma **e-handelskälla**. Välj anslutningsprogrammet **Text/CSV** igen.

1. Ange URL för information om onlineköp https://aka.ms/ciadclassonline.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **PurchasedOn**: Datum/tid
   - **TotalPrice**: Valuta

1. I fältet **Namn** i sidofönstret byter du namn på din datakälla från **eCommercePurchases**.

1. **Spara** datakällan.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Mata in kunddata från lojalitetsschema

1. Skapa en datakälla med namnet **LoyaltyScheme** och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL:en för lojalitetskunder https://aka.ms/ciadclasscustomerloyalty.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Datum/Tid

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla till **loyCustomers**.

1. **Spara** datakällan.

## <a name="task-2---data-unification"></a>Uppgift 2 – Dataförening

Granska artikeln [om datasamordning](data-unification.md). Följande information förutsätter att du bekantat dig med datasamordning i allmänhet.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Uppgift 3 – Skapa transaktionshistorik aktivitet

Läs artikeln [om kundaktiviteter](activities.md). Följande information förutsätter att du bekantat dig med skapa aktiviteter i allmänhet.

1. Skapa en aktivitet med namnet **eCommercePurchases** med entiteten *eCommercePurchases:eCommerce* och dess primära nyckel **PurchaseId**.

1. Skapa en relation mellan *eCommercePurchases:eCommerce* och *eCommerceContacts:eCommerce* med **ContactID** som främmande nyckel för att ansluta de två enheterna.

1. Välj **TotalPrice** för **EventActivity** och **PurchasedOn** för **TimeStamp**.

1. Välj **SalesOrderLine** för **aktivitetstyp** och semantiskt kartlägga aktivitetsdata.

1. Kör aktiviteten.

## <a name="task-4---configure-product-recommendation-prediction"></a>Uppgift 4 – Konfigurera förutsägelse av produktrekommendation

Med enhetlig kundprofiler på plats och skapad aktivitet köra produktrekommendationen prediktion.

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Produktrekommendationsmodell (förhandsversion)**.

1. Välj **Komma igång**.

1. Namnge modellen **OOB modellförutsägelse av produktrekommendation** och utdataentiteten **OOBProductRecommendationModelPrediction**.

1. Välj **Nästa**.

1. Definiera modellinställningar:
   - **Antal produkter**: **5** för att definiera hur många produkter du vill rekommendera till dina kunder.
   - **Återkommande köp förväntas**: **Ja** till att ta med tidigare köpta produkter i rekommendationen.
   - **Titta bakåt i fönstret:** **365 dagar** för att definiera hur långt modellen kommer att se tillbaka innan du rekommenderar en produkt igen.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinställningar för produktrekommendationsmodellen.":::

1. Välj **Nästa**.

1. I **Lägg till inköpshistorik**, välj **Lägg till data**.

1. Välj **SalesOrderLine** och entitet eCommercePurchases och välj **Nästa**. Data som krävs fylls i automatiskt från aktiviteten. Välj **Spara** och välj sedan **Nästa**.

1. Hoppa över steg **Lägg till produktinformation** och **Produktfilter** eftersom det inte finns några produktinformationsdata.

1. I steget **Datauppdateringar** välj **Månadsvis** för modellschemat.

1. Välj **Nästa**.

1. När du har granskat alla detaljer väljer du **Spara och kör**.

## <a name="task-5---review-model-results-and-explanations"></a>Uppgift 5 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Granska [förklaringar av modellen för produktrekommendationer](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Uppgift 6 – Skapa ett segment med ofta köpta produkter

Om du kör modellen skapas en ny entitet som visas på **Data** > **Entiteter**. Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.

1. Välj på resultatsidan **Skapa segment**.

1. Skapa en regel med entitet **OOBProductRecommendationModelPrediction** och definiera segmentet:
   - **Fält**: ProductID
   - **Värde**: Välj de tre översta produkt-ID

1. Välj **Spara** och **Kör** segmentet.

Nu har du ett segment som uppdateras dynamiskt och identifierar de kunder som kan vara intresserade av att köpa de fem mest rekommenderade produkterna. Mer information finns i [Skapa och hantera segment](segments.md).

> [!TIP]
> Du kan också skapa ett segment för en prediktionsmodell från **Segment** genom att välja **Nytt** och **Skapa från** > **Intelligens**. För mer information, se [Skapa ett nytt segment med snabba segment](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
