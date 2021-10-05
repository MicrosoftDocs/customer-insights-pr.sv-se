---
title: Skapa en länk mellan målgruppsinsikter och engagemangsinsikter
description: Skapa en aktiv länk mellan målgruppsinsikter och engagemangsinsikter för att möjliggöra dubbelriktad datadelning.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d93a49a29c29103e189a6d4a42294c18dc28abd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7559040"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Skapa en länk mellan målgruppsinsikter och engagemangsinsikter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integreringen mellan insikter om publik insikter länkar miljöer från båda funktionerna och gör att data kan delas dubbelriktat mellan dem.

Använd enhetliga profiler och segment från olika målgruppsinsikter för fler analysalternativ i insikter om åtaganden. Exportera händelser med ett högt affärsvärde från engagemangsinsikter. Använd dessa händelser om du vill lägga till data i enhetliga profiler målgruppsinsikter.

## <a name="prerequisites"></a>Förutsättningar

- Målgruppens insiktsprofiler måste lagras i en Azure Data Lake Storage konto som du äger eller i en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;hanterad datasjö. 
- Din miljö med målgruppsinsikter bör ha en associerad Dataverse-miljö. Och om den miljön också använder Dataverse för datalagring bör du kontrollera alternativet **Aktivera datadelning** bland målgruppsinsikterna. Mer information finns i [Skapa och konfigurera en betalmiljö bland målgruppsinsikterna](../audience-insights/get-started-paid.md).
- Du måste ha administratörabehörigheter för både engagemangsinsikter och målgruppsinsikter.
- Länkade miljöer måste finnas i samma geografiska område.

> [!NOTE]
> - Om din prenumeration på målgruppsinsikter är en utvärderingsversion som använder en internt hanterad datasjöv för målgruppsinsikter kontaktar du [pirequest@microsoft.com](mailto:pirequest@microsoft.com) för hjälp. 
> - Om din miljö med målgruppsinsikter använder din egen Azure Data Lake Storage för att lagra data, måste du lägga till ett Azure-huvudkonto för tjänsten för engagemangsinsikter i ditt lagringskonto. Mer information finns i [Ansluta till ett Azure Data Lake Storage konto med ett Azure-huvudkonto för tjänsten för målgruppsinsikter](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Skapa en miljölänk

Du kan skapa en miljölänk genom att uppdatera inställningarna för **Admin** > **Miljö** i engagemangsinsikter.

**För att etablera en aktiv länk mellan målgruppsinsikter och engagemangsinsikter**

1. På sidan **Miljöadministratör** välj fliken **Länkmiljöer**.

    :::image type="content" source="media/integrate1.png" alt-text="Ställ in en miljö.":::

1. Välj **installationsmiljöer** längst upp till vänster eller längst ned på skärmen.

     :::image type="content" source="media/integrate2.png" alt-text="Välj miljö för målgruppinsikter.":::

1. Välj en miljö med målgruppsinsikt och välj sedan ***Nästa** för att avsluta. Nu kan du välja valfria funktioner för de länkade miljöerna.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Aktivera målgruppsinsikter, enhetliga profilattribut och segment

Efter länkning av miljöer kan du välja valfria funktioner för de länkade miljöerna. Dessa funktioner möjliggör enhetliga profilattribut och segment från målgruppsinsikter för interaktiv analys på kunddata.

> [!IMPORTANT]
> För segment med målgruppsinsikter att visa i engagemangsinsikter måste du först [köra kopplade och nedströmsprocesser ](../audience-insights/merge-entities.md). Processer nedströms är viktiga eftersom de genererar en unik tabell som förbereder segment av målgruppsinsikter som ska delas med engagemangsinsikter. (Om en systemuppdatering schemaläggs inkluderas processer nedströms automatiskt.)

**Analysera webbdata i insikter om interaktion**

1. På sidan **Miljöadministratör** aktivera växla **Dela data från målgruppinsikter med engagemangsinsikter** och välj **Nästa**.

    :::image type="content" source="media/integrate4.png" alt-text="Välj funktioner.":::

1. Välj attributen för de enhetliga profilerna som ska bli till mått i engagemangsinsikter. (Alla attribut är inte användbara mått. Till exempel är det inte troligt att du behöver det **förnamn** eller **efternamn** som attribut för analys av webbplatshändelserna.)

    :::image type="content" source="media/integrate5.png" alt-text="Moderera dimensioner.":::

   >[!NOTE]
   > Alla profilattribut för målgruppsinsikter som representerar identifierare (t.ex. **ID** och **alternativt ID**) filtreras bort från de tillgängliga attributen och blir dimensioner i engagemangsinsikter.

1. När du är klar med att välja attribut väljer du **Nästa**.
1. Lägg till användare som kan visa målgruppinsikter profilmått och segment i engagemangsinsikter.

    :::image type="content" source="media/integrate6.png" alt-text="Hantera åtkomst till kunddata.":::

   > [!IMPORTANT]
   > Om du inte uttryckligen lägger till användare i det här steget döljs data för användare i engagemangsinsikter.
   > För segment med målgruppsinsikter att visa i engagemangsinsikter måste du först [köra kopplade och nedströmsprocesser ](../audience-insights/merge-entities.md). Processer nedströms är viktiga eftersom de genererar en unik tabell som förbereder segment av målgruppsinsikter som ska delas med engagemangsinsikter. (Om en systemuppdatering schemaläggs inkluderas processer nedströms automatiskt.)

1. Gå igenom valen och klicka därefter på **Slutför**.

    :::image type="content" source="media/integrate7.png" alt-text="Granska inställningarna för kunddata.":::

## <a name="export-refined-events-to-audience-insights"></a>Exportera dina förfinade händelse till målgruppinsikter

När du har skapat en länk mellan miljöer kan du exportera viktiga händelser från insikter om målgruppsinsikter och hitta dem som en datakälla. 

Mer information finns i [Integrera webbdata från kontaktinsikter med målgruppsinsikter](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
