---
title: Registrerades begäran (DSR) under GDPR | Microsoft Docs
description: Besvara registrerades begäran för Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387133"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Registrerades begäran (DSR) under GDPR

Den allmänna dataskyddsordningen (GDPR) har funnits sedan den 25 maj 2018. Den ger viktiga rättigheter till enskilda personer när det gäller deras data. GDPR handlar om att skydda och möjliggöra enskilda personers rätt till sekretess. Läs mer om Microsoft säkerhets- och regelefterlevnad på [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Vi är engagerade i att hjälpa våra kunder att uppfylla sina GDPR-krav. Den omfattar rätten att ta bort och exportera data som innehåller personlig information som användar-ID, telefonnummer och e-postadresser. Administratörer kan implementera användarförfrågningar om att ta bort eller exportera personliga data.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Besvara GDPR registrerades begäran om borttagning av Customer Insights

Rätten att ta bort personuppgifter från en organisations kunddata är ett viktigt skydd i allmänna dataskyddsförordningen (GDPR). Om du tar bort personuppgifter tas även alla personuppgifter och systemgenererade loggar bort, förutom granskningslogginformationen.

### <a name="manage-data-subject-delete-requests"></a>Hantera registrerades begäran för att ta bort data

Customer Insights erbjuder följande produkterfarenheter för borttagning av personliga data för en specifik kund eller användare:

- **Hantera rader för borttagning av kunddata**: kunddata i Customer Insights inkommer från ursprungliga datakällor som är externa till Customer Insights. Utför GDPR-borttagningsbegäranden i den ursprungliga datakällan först.
- **Hantera begäranden om borttagning av data för Customer Insights-kund**: Data för användare skapas av Customer Insights. Utför alla GDPR begäran för att ta bort data i Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Hantera begäran om att ta bort kunddata

Som administratör för Customer Insights, ta bort Customer Insights kunddata som tagits bort i datakällan. Verifiera de GDPR begäran för att ta bort data som utfördes i original datakälla.

1. Logga in på Dynamics 365 Customer Insights.

1. Gå till **Data** > **Datakällor**.

1. För respektive datakälla i listan som innehåller borttagna kunduppgifter:
   1. Markera datakällan och välj sedan **Uppdatera**.
   1. Kontrollera status för datakälla under **Status**. En bockmarkering betyder att uppdateringen har slutförts. En varningstriangel betyder att något har gått fel. Om en varningstriangel visas kontaktar du D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Hantera GDPR-begäran för att ta bort kunddata":::

1. När alla datakällor har uppdaterats kör du även de nedströmsuppdateringarna. Särskilt om du inte har en återkommande fullständig uppdatering av Customer Insights schemalagda.

   > [!IMPORTANT]
   > Statiska segment ingår inte i en fullständig uppdatering eller körs nedströmsuppdateringar efter en borttagningsbegäran. Se också till att kunddata tas bort från statiska segment genom att skapa de statiska segmenten med uppdaterade källdata.

#### <a name="manage-delete-requests-for-user-data"></a>Hantera begäranden om att ta bort användardata

Som Customer Insights-administratör, ta bort Customer Insights-användardata.

1. Logga in på Dynamics 365 Customer Insights.

1. Gå till **Admin** > **Säkerhet** > och välj fliken **Användare**.

1. Markera kryssrutan för de användare du vill ta bort.

1. Välj **Ta bort**.

1. Bekräfta borttagningen.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Svara på GDPR registrerades begäran för att exportera data

Rätten till dataportabilitet kan användas av registrerade för att begära en kopia av deras personuppgifter i elektroniskt format (ett strukturerat, vanligt förekommande, maskinläsbart och driftskompatibelt format) som kan överföras till en annan personuppgiftsansvarig.

### <a name="manage-export-and-view-requests"></a>Hantera export och visa förfrågningar

Hantera begäran om att exportera kund- eller användardata.

#### <a name="export-customer-data-tenant-admin"></a>Exportera kunddata (klientorganisationens administratör).

Som klientorganisationens administratör, exportera kunddata.

1. Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange kundens e-postadress i förfrågan. Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.
2. Bekräfta bekräftelsen av att exportera data för den begärda kunden.
3. Ta emot exporterade data via e-postadressen för innehavaradministration.

#### <a name="export-user-data-tenant-admin"></a>Exportera användardata (klientorganisationens administratör)

Som klientorganisationens administratör, exportera användardata.

1. Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange användarens e-postadress i förfrågan. Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.
1. Bekräfta bekräftelsen av att exportera data för den begärda användaren.
1. Ta emot exporterade data via e-postadressen för innehavaradministration.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Hantering av databorttagning i Dynamics 365 Customer Insights

Data tas bort (datapartitioner och dataögonblicksbilder) om datapartitionerna och dataögonblicksbilderna är inaktiva i mer än 30 dagar, vilket innebär att de har ersatts av en ny datapartition och ögonblicksbild genom en uppdatering av datakällor.

Alla data och ögonblicksbilder tas inte bort. Den senaste datapartitionen och dataögonblicksbilden är aktiva eftersom de används i Customer Insights. För de senaste data spelar det ingen roll om datakällorna inte har uppdaterats under de senaste 30 dagarna.

[!INCLUDE [footer-include](includes/footer-banner.md)]
