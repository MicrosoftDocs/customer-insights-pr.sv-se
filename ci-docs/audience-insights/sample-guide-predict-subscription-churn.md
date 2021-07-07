---
title: Exempelguide för förutsägelse om prenumerationsomsättning
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om prenumerationsomsättning.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306325"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Exempelguide för förutsägelse om prenumerationsomsättning (förhandsversion)

Vi ger dig ett komplett exempel på förutsägelse av prenumerationsomsättning med hjälp av de exempeldata som anges nedan. 

## <a name="scenario"></a>Scenario

Contoso är ett företag som producerar högkvalitativt kaffe och kaffemaskiner, som de säljer via sin Contoso Coffee-webbplats. De startade nyligen ett prenumerationsalternativ för sina kunder för att med jämna mellanrum få kaffe. Deras mål är att förstå vilka prenumererande kunder som kan komma att säga upp prenumerationen inom de kommande månaderna. Att veta vilka av deras kunder som **sannolikt kommer att omsättas** kan hjälpa dem att spara marknadsföringsinsatser genom att fokusera på att behålla dem.

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

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **eCommerceContacts**

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

### <a name="ingest-subscription-information"></a>Mata in prenumerationsinformation

1. Skapa en datakälla med namnet **SubscriptionHistory**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadchurnsubscriptionhistory.

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

1. I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **SubscriptionHistory**.

1. Spara datakällan.

### <a name="ingest-customer-data-from-website-reviews"></a>Mata in kunddata från webbplatsens recensioner

1. Skapa en datakälla med namnet **Website**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.

1. Ange URL för e-handelskontakter https://aka.ms/ciadclasswebsite.

1. Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.

1. Uppdatera datatypen för kolumnerna som anges nedan:

   - **ReviewRating**: Hela numret
   - **ReviewDate**: Datum

1. I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **webReviews**.

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


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Uppgift 3 – Konfigurera förutsägelsen om prenumerationsomsättning

Med de enhetliga kundprofilerna på plats kan vi nu köra förutsägelsen om prenumerationsomsättning. Detaljerade steg finns i artikeln [Förutsägelse om prenumerationsomsättning (förhandsversion)](predict-subscription-churn.md). 

1. Gå till **Intelligens** > **Utforska** och välj att använda **modellen Kundomsättning**.

1. Välj alternativet **Prenumeration** och välj **Kom igång**.

1. Namnge modellen **OOB förutsägelse om prenumerationsomsättning** och utdataentiteten **OOBSubscriptionChurnPrediction**.

1. Definiera två villkor för omsättningsmodellen:

   * **Dagar sedan prenumerationen avslutades**: **minst 60** dagar. Om en kund inte förnyar prenumerationen under den här tidsperioden efter att prenumerationen avslutades, anses de vara omsatta. 

   * **Omsättningsdefinition**: **minst 93** dagar. Den tidsperiod inom vilken modellen förutser att kunden kan komma att omsättas. Ju längre in i framtiden du tittar, desto mindre exakta blir resultaten.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Välj modellens förutsägelsefönster och omsättningsdefinition.":::

1. Välj **Lägg till obligatoriska data** och välj **Lägg till data** för prenumerationshistorik.

1. Lägg till entiteten **Prenumeration: SubscriptionHistory** och mappa fälten från e-handel till motsvarande fält som krävs av modellen.

1. Anslut entiteten **Prenumeration: SubscriptionHistory** med **eCommerceContacts: e-handel**, namnge relationen **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Anslut e-handelsentiteter.":::

1. Under Kundaktiviteter lägger du till entiteten **webReviews: Webbplats** och mappar fälten från webReviews till motsvarande fält som krävs av modellen. 
   - Primär nyckel: ReviewId
   - Tidsstämpel: ReviewDate
   - Händelse: ReviewRating

1. Konfigurera en aktivitet för recensioner av webbplatsen. Välj aktiviteten **Recension** och anslut entiteten **webReviews : Webbplats** till **eCommerceContacts : e-handel**.

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