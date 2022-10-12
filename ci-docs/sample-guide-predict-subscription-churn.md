---
title: Exempelguide för förutsägelse om prenumerationsomsättning
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om prenumerationsomsättning.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610028"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Exempelguide för förutsägelse om prenumerationsomsättning

Den här guiden ger dig ett komplett exempel på förutsägelse av prenumeration omsättning med exempeldata. Vi rekommenderar att du provar denna prediktion [i en ny miljö](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso är ett företag som tillverkar kaffe och kaffeautomater av hög kvalitet. De säljer produkterna via Contoso Coffees webbplats. De startade nyligen ett prenumerationsalternativ för sina kunder för att med jämna mellanrum få kaffe. Deras mål är att förstå vilka prenumererande kunder som kan komma att säga upp prenumerationen inom de kommande månaderna. Att veta vilka av deras kunder som **sannolikt kommer att omsättas** kan hjälpa dem att spara marknadsföringsinsatser genom att fokusera på att behålla dem.

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.

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

1. Spara datakällan.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Mata in kunddata från lojalitetsschema

1. Skapa en datakälla med namnet **LoyaltyScheme** och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL:en för lojalitetskunder https://aka.ms/ciadclasscustomerloyalty.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Datum/Tid

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla till **loyCustomers**.

1. Spara datakällan.

### <a name="ingest-subscription-information"></a>Mata in prenumerationsinformation

1. Skapa en datakälla med namnet **SubscriptionHistory** och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för prenumerationer https://aka.ms/ciadchurnsubscriptionhistory.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **SubscriptioID**: Hela numret
   - **SubscriptionAmount**: Valuta
   - **SubscriptionEndDate**: Datum/tid
   - **SubscriptionStartDate**: Datum/tid
   - **TransactionDate**: Datum/tid
   - **IsRecurring**: Sant/falskt
   - **Is_auto_renew**: Sant/falskt
   - **RecurringFrequencyInMonths**: Hela numret

1. I fältet **Namn** i den högra rutan byter du namn på din datakälla till **SubscriptionHistory**.

1. Spara datakällan.

### <a name="ingest-customer-data-from-website-reviews"></a>Mata in kunddata från webbplatsens recensioner

1. Skapa en datakälla med namnet **Webbplats** och välj anslutningsprogrammet **Text/CSV**.

1. Ange webbadressen för webbplatsrecensioner https://aka.ms/ciadclasswebsite.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:
   - **ReviewRating**: Hela numret
   - **ReviewDate**: Datum

1. I fältet **Namn** i den högra rutan byter du namn på din datakälla till **webReviews**.

## <a name="task-2---data-unification"></a>Uppgift 2 – Dataförening

Granska artikeln [om datasamordning](data-unification.md). Följande information förutsätter att du bekantat dig med datasamordning i allmänhet.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Uppgift 3 – Skapa transaktionshistorik aktivitet

Läs artikeln [om kundaktiviteter](activities.md). Följande information förutsätter att du bekantat dig med skapa aktiviteter i allmänhet.

1. Skapa en aktivitet med namnet **SubscriptionHistory** med entiteten *prenumeration* och dess primära nyckel **CustomerId**.

1. Skapa en relation mellan *SubscriptionHistory:Subscription* och *eCommerceContacts:eCommerce* med **CustomerID** som främmande nyckel för att ansluta de två enheterna.

1. Välj **SubscriptionType** för **EventActivity** och **SubscriptionEndDate** för **TimeStamp**.

1. Välj **prenumeration** för **aktivitetstyp** och semantiskt kartlägga aktivitetsdata.

1. Kör aktiviteten.

1. Lägg till en aktivitet och mappa fältnamnen till motsvarande fält:
   - Kundaktivitetsenhet: Recensioner:Webbplats
   - Primärnyckel: Website.Reviews.ReviewId
   - Tidsstämpel: Website.Reviews.ReviewDate
   - Händelse (aktivitetsnamn): Website.Reviews.ActivityTypeDisplay
   - Information (belopp eller värde): Website.Reviews.ReviewRating

1. Kör aktiviteten.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Uppgift 4 – Konfigurera förutsägelsen om prenumerationsomsättning

Med de enhetliga kundprofilerna på plats och aktiviteten som skapas kan vi nu köra förutsägelsen om prenumerationsomsättning. Detaljerade anvisningar finns i [Förutsägelse av prenumerationsomsättning](predict-subscription-churn.md).

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Kundomsättningsmodell**.

1. Välj **prenumeration** för typen av omsättning och **Kom igång**.

1. Namnge modellen **OOB förutsägelse om prenumerationsomsättning** och utdataentiteten **OOBSubscriptionChurnPrediction**.

1. Definiera modellinställningar:
   - **Dagar sedan prenumerationen upphörde**: **60** dagar för att visa att en kund betraktas som omsättning om de inte förnyar prenumerationen under den här perioden efter det att prenumerationen upphört.
   - **Antal dagar i framtiden att förutsäga omsättningen för**: **93** dagar, vilket är den varaktighet modellen förutsäger att kunden kan omsätta. Ju längre in i framtiden du tittar, desto mindre exakta blir resultaten.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Välj modellens inställning och omsättningsdefinition.":::

1. Välj **Nästa**.

1. I steget **Obligatoriska data** väljer du **Lägg till data** för att tillhandahålla prenumerationshistorik.

1. Välj **Prenumeration** och entiteten SubscriptionHistory och välj **Nästa**. Data som krävs fylls i automatiskt från aktiviteten. Välj **Spara**.

1. Under Kundaktiviteter väljer du **Lägg till data**.

1. I det här exemplet lägger du till webbgranskningsaktiviteten.

1. Välj **Nästa**.

1. I steget **Datauppdateringar** välj **Månadsvis** för modellschemat.

1. När du har granskat alla detaljer väljer du **Spara och kör**.

## <a name="task-5---review-model-results-and-explanations"></a>Uppgift 5 – Granska modellresultat och förklaringar

Låt modellen slutföra träningen och bedömningen av data. Granska förklaring för omsättningsmodell för prenumeration. Mer information finns i [Visa förutsägelseresultat](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Uppgift 6 – Skapa ett segment med kunder med hög omsättningsrisk

Om du kör modellen skapas en ny entitet som visas på **Data** > **Entiteter**. Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.

1. Välj på resultatsidan **Skapa segment**.

1. Skapa en regel med entitet **OOBSubscriptionChurnPrediction** och definiera segmentet:
   - **Fält**: ChurnScore
   - **Operatör**: är större än
   - **Värde**: 0,6

1. Välj **Spara** och **Kör** segmentet.

Du har nu ett segment som uppdateras dynamiskt som identifierar kunder med hög omsättningsrisk för den här prenumerationsverksamheten. Mer information finns i [Skapa och hantera segment](segments.md).

> [!TIP]
> Du kan också skapa ett segment för en prediktionsmodell från **Segment** genom att välja **Nytt** och **Skapa från** > **Intelligens**. För mer information, se [Skapa ett nytt segment med snabba segment](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
