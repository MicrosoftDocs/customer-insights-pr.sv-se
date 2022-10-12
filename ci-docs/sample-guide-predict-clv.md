---
title: Kundens livstidsvärde (CLV) prediktion exempelguide
description: Använd den här exempelguiden för att testa kundens livstidsvärde prediktionsmodellen.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609660"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Kundens livstidsvärde (CLV) prediktion exempelguide

Den här guiden förklarar för dig ett slutexempel på CLV-prediktion i Customer Insights med hjälp av exempeldata. Vi rekommenderar att du provar denna prediktion [i en ny miljö](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso är ett företag som tillverkar kaffe och kaffeautomater av hög kvalitet. De säljer produkterna via Contoso Coffees webbplats. Företaget vill förstå värdet (intäkterna) som deras kunder kan generera under de kommande 12 månaderna. Att veta det förväntade värdet på sina kunder under de kommande 12 månaderna kommer att hjälpa dem att styra sina marknadsföringsinsatser på kunder med högt värde.

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md).

## <a name="task-1---ingest-data"></a>Uppgift 1 – Mata in data

Läs artiklarna [om datainmatning](data-sources.md) och [ansluta till en Power Query datakälla](connect-power-query.md). Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Mata in kunddata från e-handelsplattformen

1. Skapa en Power Query datakälla med namnet **eCommerce** och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasscontacts.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Tid/Zon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformera födelsedatum till datum.":::

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla till **eCommerceContacts**

1. **Spara** datakällan.

### <a name="ingest-online-purchase-data"></a>Mata in inköpsdata online

1. Lägg till ytterligare en datauppsättning till samma **e-handelskälla**. Välj anslutningsprogrammet **Text/CSV** igen.

1. Ange URL för **Onlineköpsdata** https://aka.ms/ciadclassonline.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Mata in kunddata från webbplatsens recensioner

1. Skapa en datakälla med namnet **Webbplats** och välj anslutningsprogrammet **Text/CSV**.

1. Ange webbadressen för webbplatsrecensioner https://aka.ms/CI-ILT/WebReviews.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **ReviewRating**: Decimaltal
   - **ReviewDate**: Datum

1. I fältet **Namn** i den högra rutan byter du namn på din datakälla till **Recensioner**.

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

1. Lägg till en aktivitet och mappa fältnamnen till motsvarande fält:
   - **Aktivitetsentitet**: Recensioner: Webbplats
   - **Primär nyckel**: ReviewId
   - **Tidsstämpel**: ReviewDate
   - **Händelseaktivitet**: ActivityTypeDisplay
   - **Ytterligare information**: ReviewRating
   - **Aktivitetstyp**: Granska

1. Kör aktiviteten.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Uppgift 4 – Konfigurera kundens livstidsvärdesprediktion

Med de enhetliga kundprofilerna på plats kan och skapad aktivitet köra kundens livstidsvärdesprediktion (CLV). Detaljerade steg finns i [Förutsägelse av Kundlivstidsvärde](predict-customer-lifetime-value.md).

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Kundens livstidsvärde**.

1. Välj **Komma igång**.

1. Namnge modellen **OOB eCommerce CLV prediktion** och utdataentiteten **OOBeCommerceCLVPrediction**.

1. Definiera modellinställningar:
   - **Tidsperiod för förutsägelse**: **12 månad eller 1 år** för att definiera hur långt in i framtiden man ska förutsäga CLV.
   - **Aktiva kunder**: **Låt modellen beräkna inköpsintervall** som tidsramen inom vilken en kund måste ha minst en transaktion för att anses vara aktiv.
   - **Kund med högt värde**: manuellt definiera högt värde kunder som **topp 30 % av aktiva kunder**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Inställningssteg i den guidade upplevelsen för CLV-modellen.":::

1. Välj **Nästa**.

1. I steget **Obligatoriska data** väljer du **Lägg till data** för att tillhandahålla transaktionshistorikdata.

    :::image type="content" source="media/clv-model-required.png" alt-text="Lägg till datasteg krävs i den guidade upplevelsen för CLV-modellen.":::

1. Välj **SalesOrderLine** och entitet eCommercePurchases och välj **Nästa**. Data som krävs fylls i automatiskt från aktiviteten. Välj **Spara** och välj sedan **Nästa**.

1. Med steget **Ytterligare data (valfritt)** kan du lägga till mer data om kundaktivitet för att få fler insikter för kundinteraktioner. I det här exemplet väljer du **Lägg till data** och lägger till webbgranskningsaktiviteten.

1. Välj **Nästa**.

1. I steget **Datauppdateringar** välj **Månadsvis** för modellschemat.

1. Välj **Nästa**.

1. När du har granskat alla detaljer väljer du **Spara och kör**.

## <a name="task-5---review-model-results-and-explanations"></a>Uppgift 5 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Granska [CLV modellresultat och förklaringar](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Uppgift 6 - Skapa ett segment med kunder med högt värde

Om du kör modellen skapas en ny entitet som visas på **Data** > **Entiteter**. Du kan skapa ett nytt kundsegment baserat på den entitet som skapas av modellen.

1. Välj på resultatsidan **Skapa segment**.

1. Skapa en regel med entitet **OOBeCommerceCLVPrediction** och definiera segmentet:
   - **Fält**: CLVScore
   - **Operatör**: är större än
   - **Värde**: 1500

1. Välj **Spara** och **Kör** segmentet.

Du har nu ett segment som identifierar kunder som förväntas generera mer än 1 500 dollar i intäkter under de kommande 12 månaderna. Det här segmentet uppdateras dynamiskt om mer data matas in. Mer information finns i [Skapa och hantera segment](segments.md).

> [!TIP]
> Du kan också skapa ett segment för en prediktionsmodell från **Segment** genom att välja **Nytt** och **Skapa från** > **Intelligens**. För mer information, se [Skapa ett nytt segment med snabba segment](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
