---
title: Registrerades begäran (DSR) under GDPR | Microsoft Docs
description: Besvara registrerades begäran om funktionen målgruppsinsikter i Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350291"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Registrerades begäran (DSR) under GDPR

Den allmänna dataskyddsordningen (GDPR) har funnits sedan den 25 maj 2018. Den ger viktiga rättigheter till enskilda personer när det gäller deras data. GDPR handlar om att skydda och möjliggöra enskilda personers rätt till sekretess. Du kan läsa mer om Microsoft säkerhets- och regelefterlevnad på [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Vi är engagerade i att hjälpa våra kunder att uppfylla sina GDPR-krav. Den omfattar rätten att ta bort och exportera data som innehåller personlig information som användar-ID, telefonnummer och e-postadresser. Administratörer kan implementera användarförfrågningar om att ta bort eller exportera personliga data.

## <a name="audience-insights"></a>Målgruppsinsikter

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Besvara GDPR registrerades begäran om borttagning av funktionen målgruppsinsikter i Dynamics 365 Customer Insights

Rätten att ta bort personuppgifter från en organisations kunddata är ett viktigt skydd i allmänna dataskyddsförordningen (GDPR). Om du tar bort personuppgifter tas även alla personuppgifter och systemgenererade loggar bort, förutom granskningslogginformationen.

#### <a name="manage-data-subject-delete-requests"></a>Hantera registrerades begäran för att ta bort data

Målgruppsinsikter erbjuder följande produktupplevelser för borttagning av personuppgifter för en specifik kund eller användare:

- **Hantera rader för borttagning av kunddata**: kunddata i Customer Insights inkommer från ursprungliga datakällor som är externa till Customer Insights. Alla GDPR begäran för att ta bort data måste utföras i original datakälla.
- **Hantera begäranden om borttagning av data för Customer Insights-kund**: Data för användare skapas av Customer Insights. Alla GDPR begäran för att ta bort data måste utföras i Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Hantera begäran om att ta bort kunddata

En administratör för Customer Insights kan följa stegen nedan för att ta bort kunddata som tagits bort i datakällan:

1. Logga in på Dynamics 365 Customer Insights.
2. I målgruppsinsikter går du till **Data** > **Datakällor**
3. För respektive datakälla i listan som innehåller borttagna kunduppgifter:
   1. Välj (…) och sedan **Uppdatera**.
   2. Kontrollera status för datakälla under **Status**. En bockmarkering betyder att uppdateringen har slutförts. En varningstriangel betyder att något har gått fel. Om en varningstriangel visas kontaktar du D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Hantera GDPR-begäran för att ta bort kunddata](audience-insights/media/gdpr-data-sources.png "Hantera GDPR begäran för att ta bort kunddata")

##### <a name="manage-delete-requests-for-user-data"></a>Hantera begäranden om att ta bort användardata

En Customer Insights-administratör kan följa stegen nedan för att ta bort Customer Insights-användardata:

1. Logga in på Dynamics 365 Customer Insights.
2. I målgruppsinsikter går du till **Admin** > **Behörigheter**.
3. Markera kryssrutan för den användare du vill ta bort.
4. Välj **Ta bort**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Svara på GDPR registrerades begäran för att exportera data

Som en del av vårt engagemang i vår strävan efter att resa till allmän dataskyddsförordning (GDPR) har vi utvecklat dokumentation som hjälper dig att förbereda dig. I den här dokumentationen beskrivs vad du kan göra i dag för att stödja GDPR-efterlevnad när du använder målgruppsinsikter.

#### <a name="manage-export-and-view-requests"></a>Hantera export och visa förfrågningar

Rätten till dataportabilitet kan användas av registrerade för att begära en kopia av deras personuppgifter i elektroniskt format (ett strukturerat, vanligt förekommande, maskinläsbart och driftskompatibelt format) som kan överföras till en annan personuppgiftsansvarig.

##### <a name="export-customer-data-tenant-admin"></a>Exportera kunddata (klientorganisationens administratör).

Klientorganisationens administratör följer de här stegen för att exportera data:

1. Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange kundens e-postadress i förfrågan. Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.
2. Bekräfta bekräftelsen av att exportera data för den begärda kunden.
3. Ta emot exporterade data via e-postadressen för innehavaradministration.

##### <a name="export-user-data-tenant-admin"></a>Exportera användardata (klientorganisationens administratör)

1. Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange användarens e-postadress i förfrågan. Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.
2. Bekräfta bekräftelsen av att exportera data för den begärda användaren.
3. Ta emot exporterade data via e-postadressen för innehavaradministration.

## <a name="consent-management-preview"></a>Samtyckeshantering (förhandsversion)

Med funktionen för samtyckeshantering samlas inte användardata in direkt. Den importerar och bearbetar endast samtyckesdata som tillhandahålls av användare i andra program.

Ta bort samtyckesdata om specifika användare genom att ta bort dem i datakällorna som inte har funktioner för samtyckeshantering. När du har datakälla informationen tas även de bort i Samtyckescenter. Program som använder samtyckesentiteten tar även bort data som har tagits bort på källan efter en [uppdatering](audience-insights/system.md#refresh-processes). Vi rekommenderar att du uppdaterar datakällor snabbt när du har besvarat en förfrågan om dataämne för att ta bort användarens data från alla andra processer och program.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]