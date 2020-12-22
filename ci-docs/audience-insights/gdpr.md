---
title: Registrerades begäran (DSR) under GDPR | Microsoft Docs
description: Besvara registrerades begäran om funktionen målgruppsinsikter i Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407092"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Registrerades begäran (DSR) under GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Besvara GDPR registrerades begäran om borttagning av funktionen målgruppsinsikter i Dynamics 365 Customer Insights

Rätten att ta bort personuppgifter från en organisations kunddata är ett viktigt skydd i allmänna dataskyddsförordningen (GDPR). Om du tar bort personuppgifter tas även alla personuppgifter och systemgenererade loggar bort, förutom granskningslogginformationen.

### <a name="manage-data-subject-delete-requests"></a>Hantera registrerades begäran för att ta bort data

Målgruppsinsikter erbjuder följande produktupplevelser för borttagning av personuppgifter för en specifik kund eller användare:

- **Hantera rader för borttagning av kunddata**: kunddata i Customer Insights inkommer från ursprungliga datakällor som är externa till Customer Insights. Alla GDPR begäran för att ta bort data måste utföras i original datakälla.
- **Hantera begäranden om borttagning av data för Customer Insights-kund**: Data för användare skapas av Customer Insights. Alla GDPR begäran för att ta bort data måste utföras i Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Hantera begäran för att ta bort kunddata

En administratör för Customer Insights kan följa stegen nedan för att ta bort kunddata som tagits bort i datakällan:

1. Logga in på Dynamics 365 Customer Insights.
2. I målgruppsinsikter går du till **Data** > **Datakällor**
3. För respektive datakälla i listan som innehåller borttagna kunduppgifter:
   1. Välj (...) och sedan **Uppdatera**.
   2. Kontrollera status för datakälla under **Status**. En bockmarkering betyder att uppdateringen har slutförts. En varningstriangel betyder att något har gått fel. Om en varningstriangel visas kontaktar du D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Hantera GDPR begäran för att ta bort kunddata](media/gdpr-data-sources.png "Hantera GDPR begäran för att ta bort kunddata")

#### <a name="manage-delete-requests-for-user-data"></a>Hantera begäranden om att ta bort användardata

En Customer Insights-administratör kan följa stegen nedan för att ta bort Customer Insights-användardata:

1. Logga in på Dynamics 365 Customer Insights.
2. I målgruppsinsikter går du till **Admin** > **Behörigheter**.
3. Markera kryssrutan för den användare du vill ta bort.
4. Välj **Ta bort**.

> [!div class="mx-imgBorder"]
> ![Hantera GDPR och begäranden om att ta bort användardata](media/gdpr-permissions.png "Hantera GDPR och begäranden om att ta bort användardata")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Svara på GDPR registrerades begäran för att exportera data

Som en del av vårt engagemang i vår strävan efter att resa till allmän dataskyddsförordning (GDPR) har vi utvecklat dokumentation som hjälper dig att förbereda dig. I den här dokumentationen beskrivs vad du kan göra i dag för att stödja GDPR-efterlevnad när du använder målgruppsinsikter.

### <a name="manage-export-and-view-requests"></a>Hantera export och visa förfrågningar

Rätten till dataportabilitet kan användas av registrerade för att begära en kopia av deras personuppgifter i elektroniskt format (ett strukturerat, vanligt förekommande, maskinläsbart och driftskompatibelt format) som kan överföras till en annan personuppgiftsansvarig.

#### <a name="export-customer-data-tenant-admin"></a>Exportera kunddata (klientorganisationens administratör).

Klientorganisationens administratör följer de här stegen för att exportera data:

1. Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange kundens e-postadress i förfrågan. Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.
2. Bekräfta bekräftelsen av att exportera data för den begärda kunden.
3. Ta emot exporterade data via e-postadressen för innehavaradministration.

#### <a name="export-user-data-tenant-admin"></a>Exportera användardata (klientorganisationens administratör)

1. Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange användarens e-postadress i förfrågan. Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.
2. Bekräfta bekräftelsen av att exportera data för den begärda användaren.
3. Ta emot exporterade data via e-postadressen för innehavaradministration.
