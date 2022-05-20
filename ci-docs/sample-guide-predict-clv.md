---
title: Kundens livstidsvärde prediktion exempelguide
description: Använd den här exempelguiden för att testa kundens livstidsvärde prediktionsmodellen.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 351946c734f5a1054eb3769b2d9cced3bed48e15
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740833"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Kundens livstidsvärde (CLV) prediktion exempelguide

Den här guiden förklarar för dig ett slutexempel på CLV-prediktion i Customer Insights med hjälp av exempeldata.

## <a name="scenario"></a>Scenario

Contoso är ett företag som tillverkar kaffe och kaffeautomater av hög kvalitet. De säljer produkterna via Contoso Coffees webbplats. Företaget vill förstå värdet (intäkterna) som deras kunder kan generera under de kommande 12 månaderna. Att veta det förväntade värdet på sina kunder under de kommande 12 månaderna kommer att hjälpa dem att styra sina marknadsföringsinsatser på kunder med högt värde.

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.
- Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).

## <a name="task-1---ingest-data"></a>Uppgift 1 – Mata in data

Läs artiklarna [om datainmatning](data-sources.md) och [import av datakällor med hjälp av Power Query-anslutningar](connect-power-query.md). Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Mata in kunddata från e-handelsplattformen

1. Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Tid/Zon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformera födelsedatum till datum.":::

1. I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **eCommerceContacts**

1. **Spara** datakällan.

### <a name="ingest-online-purchase-data"></a>Mata in inköpsdata online

1. Lägg till ytterligare en datauppsättning till samma **e-handelskälla**. Välj anslutningsprogrammet **Text/CSV** igen.

1. Ange URL för **Onlineköpsdata** https://aka.ms/ciadclassonline.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **PurchasedOn**: Datum/tid
   - **TotalPrice**: Valuta

1. I fältet **Namn** i sidofönstret byter du namn på din datakälla från **Fråga** till **eCommercePurchases**.

1. **Spara** datakällan.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Mata in kunddata från lojalitetsschema

1. Skapa en datakälla med namnet **LoyaltyScheme**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasscustomerloyalty.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Datum/Tid

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **loyCustomers**.

1. **Spara** datakällan.

### <a name="ingest-customer-data-from-website-reviews"></a>Mata in kunddata från webbplatsens recensioner

1. Skapa en datakälla med namnet **Website**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/CI-ILT/WebReviews.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **ReviewRating**: Decimaltal
   - **ReviewDate**: Datum

1. I fältet Namn i den högra rutan byter du namn på din datakälla från **Fråga** till **Recensioner**.

1. **Spara** datakällan.

## <a name="task-2---data-unification"></a>Uppgift 2 – Dataförening

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Uppgift 3 – Konfigurera kundens livstidsvärdesprediktion

Med de enhetliga kundprofilerna på plats kan vi nu köra kundens livstidsvärdesprediktion. Detaljerade steg finns i [Förutsägelse av Kundlivstidsvärde](predict-customer-lifetime-value.md).

1. Gå till **Intelligens**  > **Förutsägelser** och välj **Kundens livstidsvärdesmodell**.

1. Gå igenom informationen i sidorutan och välj **Kom igång**.

1. Namnge modellen **OOB eCommerce CLV prediktion** och utdataentiteten **OOBeCommerceCLVPrediction**.

1. Definiera modellinställningar för CLV-modellen:
   - **Prediktionstidsperiod**: **12 månader eller 1 år**. Den här inställningen definierar hur långt in i framtiden som kundens livstidsvärde ska förutsägas.
   - **Aktiva kunder**: Ange vad aktiva kunder betyder för ditt företag. Ange den historiska tidsram där en kund måste ha haft minst en transaktion som ska betraktas som aktiv. Modellen förutser endast kundens livstid för aktiva kunder. Välj mellan att låta modellen beräkna tidsperioden baserat på historiska transaktionsdata eller ange en specifik tidsram. I den här exempelguiden **låter vi modellen beräkna inköpsintervall**, vilket är standardalternativet.
   - **Kunder med högt värde**: Definiera kunder med högt värde som en percentil av toppbetalande kunder. Modellen använder den här indata för att ge resultat som passar din affärsdefinition av kunder med högt värde. Du kan välja att låta modellen definiera kunder med högt värde. Den använder en heuristisk regel som härleder percentilen. Du kan också definiera kunder med högt värde som en percentil av framtida toppbetalande kunder. I den här exempelguiden definierar vi manuellt kunder med högt värde som **topp 30 % av aktiva betalande kunder** och väljer **Nästa**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Inställningssteg i den guidade upplevelsen för CLV-modellen.":::

1. I steget **Obligatoriska data** väljer du **Lägg till data** för att tillhandahålla transaktionshistorikdata.

1. Lägg till entiteten **eCommercePurchases: e-handel** och mappa de attribut som krävs av modellen:
   - Transaktions-ID: eCommerce.eCommercePurchases.PurchaseId
   - Transaktionsdatum: eCommerce.eCommercePurchases.PurchasedOn
   - Transaktionsbelopp: eCommerce.eCommercePurchases.TotalPrice
   - Produkt-ID: eCommerce.eCommercePurchases.ProductId

1. Välj **Nästa**.

1. Ställ in förhållandet mellan entiteten **eCommercePurchases: e-handel** och **eCommerceContacts: e-handel**.

1. Med steget **Ytterligare data (valfritt)** kan du lägga till mer data om kundaktivitet. Dessa data kan hjälpa till att få fler insikter för kundinteraktioner med ditt företag, vilket kan bidra till CLV. Att lägga till viktiga kundinteraktioner som webbloggar, kundtjänstloggar eller belöningsprogramhistorik kan förbättra förutsägelsernas noggrannhet. Välj **Lägg till data** för att inkludera mer data om kundaktivitet.

1. Lägg till entiteten för kundaktivitet och mappa fältnamnen till motsvarande fält som krävs enligt modellen:
   - Kundaktivitetsenhet: Recensioner:Webbplats
   - Primärnyckel: Website.Reviews.ReviewId
   - Tidsstämpel: Website.Reviews.ReviewDate
   - Händelse (aktivitetsnamn): Website.Reviews.ActivityTypeDisplay
   - Information (belopp eller värde): Website.Reviews.ReviewRating

1. Välj **Nästa** och konfigurera aktiviteten och relationen mellan transaktionsdata och kunddata:  
   - Aktivitetstyp: Välj befintlig
   - Aktivitetsetikett: Recension
   - Motsvarande etikett: Website.Reviews.UserId
   - Kundenhet: eCommerceContacts:e-handel
   - Relation: Webbplatsrecensioner

1. Välj **Nästa** för att ange modellschemat.

   Modellen måste träna regelbundet för att lära sig nya mönster när nya data matas in. I det här exemplet väljer du **Månadsvis**.

1. När du har granskat alla detaljer väljer du **Spara och kör**.

## <a name="task-4---review-model-results-and-explanations"></a>Uppgift 4 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Därefter kan du granska CLV-modellens resultat och förklaringar. Mer information finns i [Granska en förutsägelsestatus och resultat](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Uppgift 5 - Skapa ett segment med kunder med högt värde

Om du kör modellen skapas en ny entitet som visas på **Data** > **Entiteter**. Du kan skapa ett nytt kundsegment baserat på den entitet som skapas av modellen.

1. Gå till **Segment**. 

1. Välj **Nytt** och välj **Skapa från** > **Intelligens**.

   ![Skapa ett segment med modellutdata.](media/segment-intelligence.png)

1. Välj entiteten **OOBeCommerceCLVPrediction** och definiera segmentet:
  - Fält: CLVScore
  - Operatör: större än
  - Värde: 1500

1. Välj **Granska** och **Spara** segmentet.

Du har nu ett segment som identifierar kunder som förväntas generera mer än 1 500 dollar i intäkter under de kommande 12 månaderna. Det här segmentet uppdateras dynamiskt om mer data matas in.

Mer information finns i [Skapa och hantera segment](segments.md).
