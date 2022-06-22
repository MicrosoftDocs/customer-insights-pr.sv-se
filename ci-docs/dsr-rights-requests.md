---
title: Registrerades begäran (DSR) under GDPR | Microsoft Docs
description: Besvara registrerades begäran för Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c71305ab835b0f4f75adcce716e795959f898e47
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947390"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Registrerades begäran (DSR) under GDPR

Den allmänna dataskyddsordningen (GDPR) har funnits sedan den 25 maj 2018. Den ger viktiga rättigheter till enskilda personer när det gäller deras data. GDPR handlar om att skydda och möjliggöra enskilda personers rätt till sekretess. Du kan läsa mer om Microsoft säkerhets- och regelefterlevnad på [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Vi är engagerade i att hjälpa våra kunder att uppfylla sina GDPR-krav. Den omfattar rätten att ta bort och exportera data som innehåller personlig information som användar-ID, telefonnummer och e-postadresser. Administratörer kan implementera användarförfrågningar om att ta bort eller exportera personliga data.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Svara på GDPR registrerades begäran för att ta bort data från Dynamics 365 Customer Insights

Rätten att ta bort personuppgifter från en organisations kunddata är ett viktigt skydd i allmänna dataskyddsförordningen (GDPR). Om du tar bort personuppgifter tas även alla personuppgifter och systemgenererade loggar bort, förutom granskningslogginformationen.

#### <a name="manage-data-subject-delete-requests"></a>Hantera registrerades begäran för att ta bort data

Customer Insights erbjuder följande produkterfarenheter för borttagning av personliga data för en specifik kund eller användare:

- **Hantera rader för borttagning av kunddata**: kunddata i Customer Insights inkommer från ursprungliga datakällor som är externa till Customer Insights. Alla GDPR begäran för att ta bort data måste utföras i original datakälla.
- **Hantera begäranden om borttagning av data för Customer Insights-kund**: Data för användare skapas av Customer Insights. Alla GDPR begäran för att ta bort data måste utföras i Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Hantera begäran om att ta bort kunddata

En administratör för Customer Insights kan följa stegen nedan för att ta bort kunddata som tagits bort i datakällan:

1. Logga in på Dynamics 365 Customer Insights.
2. Gå till **Data** > **Datakällor**
3. För respektive datakälla i listan som innehåller borttagna kunduppgifter:
   1. Markera den stående ellipsen (&vellip;) och välj sedan **Uppdatera**.
   2. Kontrollera status för datakälla under **Status**. En bockmarkering betyder att uppdateringen har slutförts. En varningstriangel betyder att något har gått fel. Om en varningstriangel visas kontaktar du D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Hantera GDPR-begäran för att ta bort kunddata](media/gdpr-data-sources.png "Hantera GDPR begäran för att ta bort kunddata")

##### <a name="manage-delete-requests-for-user-data"></a>Hantera begäranden om att ta bort användardata

En Customer Insights-administratör kan följa stegen nedan för att ta bort Customer Insights-användardata:

1. Logga in på Dynamics 365 Customer Insights.
2. Gå till **Administratör** > **Säkerhet** > **Behörigheter**.
3. Markera kryssrutan för den användare du vill ta bort.
4. Välj **Ta bort**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Svara på GDPR registrerades begäran för att exportera data

Som en del av vårt engagemang i vår strävan efter att resa till allmän dataskyddsförordning (GDPR) har vi utvecklat dokumentation som hjälper dig att svara på förfrågningar från registrerade.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]