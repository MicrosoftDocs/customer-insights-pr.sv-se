---
title: Exempelguide för förutsägelse om transaktionell omsättning
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om transaktionell omsättning.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609707"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Exempelguide för förutsägelse om transaktionell omsättning

Den här guiden ger dig ett komplett exempel på förutsägelse av transaktionell omsättning med exempeldata. Vi rekommenderar att du provar denna prediktion [i en ny miljö](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso är ett företag som tillverkar kaffe och kaffeautomater av hög kvalitet. De säljer produkterna via Contoso Coffees webbplats. Deras mål är att veta vilka kunder som vanligtvis köper deras produkter regelbundet kommer att sluta vara aktiva kunder under de närmaste 60 dagarna. Att veta vilka av deras kunder som **sannolikt kommer att omsättas** kan hjälpa dem att spara marknadsföringsinsatser genom att fokusera på att behålla dem.

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md).

## <a name="task-1---ingest-data"></a>Uppgift 1 – Mata in data

Läs artiklarna [om datainmatning](data-sources.md) och [ansluta till en Power Query datakälla](connect-power-query.md). Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Mata in kunddata från e-handelsplattformen

1. Skapa en datakälla med namnet **eCommerce** och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasscontacts.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Tid/Zon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Omvandla födelsedatum till datum.":::

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla till **eCommerceContacts**

1. Spara datakällan.

### <a name="ingest-online-purchase-data"></a>Mata in inköpsdata online

1. Lägg till ytterligare en datauppsättning till samma **e-handelskälla**. Välj anslutningsprogrammet **Text/CSV** igen.

1. Ange URL för information om onlineköp https://aka.ms/ciadclassonline.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **PurchasedOn**: Datum/tid
   - **TotalPrice**: Valuta

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla till **eCommercePurchases**.

1. Spara datakällan.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Mata in kunddata från lojalitetsschema

1. Skapa en datakälla med namnet **LoyaltyScheme** och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasscustomerloyalty.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **DateOfBirth**: Datum
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Datum/Tid

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla till **loyCustomers**.

1. Spara datakällan.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Uppgift 4 – Konfigurera förutsägelsen om transaktionell omsättning

Med enhetliga kundprofiler på plats och aktivitet kör prediktion för transaktionsomsättning.

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på **Kundomsättningsmodell**.

1. Välj **transaktionell** för typen av omsättning och **Kom igång**.

1. Namnge modellen **OOB förutsägelse om transaktionell omsättning inom e-handel** och utdataentiteten **OOBeCommerceChurnPrediction**.

1. Välj **Nästa**.

1. Definiera modellinställningar:

   - **Prediktionsfönster**: **60** dagar för att definiera hur långt in i framtiden vi vill förutsäga kundomsättning.

   - **Omsättningsdefinition**: **60** dagar för att ange varaktigheten utan köp efter vilken en kund anses vara omsättning.

     :::image type="content" source="media/model-levers.PNG" alt-text="Välj modellens inställning av förutsägelsefönster och omsättningsdefinition.":::

1. Välj **Nästa**.

1. Välj **Inköpshistorik (obligatoriskt)** och välj **Lägg till data** för inköpshistorik.

1. Välj **SalesOrderLine** och entitet eCommercePurchases och välj **Nästa**. Data som krävs fylls i automatiskt från aktiviteten. Välj **Spara** och välj sedan **Nästa**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Anslut e-handelsentiteter.":::

1. Hoppa över steget **Ytterligare data (valfritt)**.

1. I steget **Datauppdateringar** välj **Månadsvis** för modellschemat.

1. När du har granskat alla detaljer väljer du **Spara och kör**.

## <a name="task-5---review-model-results-and-explanations"></a>Uppgift 5 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Granska förklaring av omsättningsmodell. Mer information finns i [Visa förutsägelseresultat](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Uppgift 6 – Skapa ett segment med kunder med hög omsättningsrisk

Om du kör produktionsmodellen skapas en ny entitet som visas på **Data** > **Entiteter**. Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.

1. Välj på resultatsidan **Skapa segment**.

1. Skapa en regel med entitet **OOBeCommerceChurnPrediction** och definiera segmentet:
   - **Fält**: ChurnScore
   - **Operatör**: är större än
   - **Värde**: 0,6

1. Välj **Spara** och **Kör** segmentet.

Nu har du ett segment som uppdateras dynamiskt och som identifierar kunder med hög risk. Mer information finns i [Skapa och hantera segment](segments.md).

> [!TIP]
> Du kan också skapa ett segment för en prediktionsmodell från **Segment** genom att välja **Nytt** och **Skapa från** > **Intelligens**. För mer information, se [Skapa ett nytt segment med snabba segment](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
