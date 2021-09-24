---
title: Registrerades begäran (DSR) under GDPR | Microsoft Docs
description: Besvara registrerades begäran om funktionen målgruppsinsikter i Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483712"
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

## <a name="engagement-insights"></a>Engagemangsinsikter

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Ta bort och exportera händelsedata som innehåller identifierbar användarinformation

I följande avsnitt beskrivs hur du tar bort och exporterar händelsedata som kan innehålla personliga data.

Att ta bort eller exportera data:

1. Tagga händelseegenskaper som innehåller data med personlig information.
2. Ta bort eller exportera data som är associerade med specifika värden (till exempel: ett angivet användar-ID).

#### <a name="tag-and-update-event-properties"></a>Tagga och uppdatera händelseegenskaper

Personliga data taggas på egenskapsnivå för en händelse. Först taggar du de egenskaper som ska tas bort eller exporteras.

Om du vill tagga en händelseegenskap som innehåller personlig information gör du följande:

1. Öppna arbetsytan som innehåller händelsen.

1. Gå till **Data** > **Händelser** om du vill visa listan med händelser på den valda arbetsytan.
  
1. Välj den händelse du vill tagga.

1. Välj **Redigera egenskaper** om du vill öppna fönstret med alla egenskaper för den markerade händelsen.
     
1. Välj **…** och välj sedan **Redigera** för att nå dialogrutan **Uppdatera egenskap** dialog.

   ![Redigera händelse.](engagement-insights/media/edit-event.png "Redigera händelse")

1. I fönstret **Uppdatera egenskap**, välj **…** längst upp till höger och välj rutan **Innehåller EUII**. Välj **Uppdatera** för att spara ändringarna.

   ![Spara dina ändringar.](engagement-insights/media/update-property.png "Spara dina ändringar")

   > [!NOTE]
   > Varje gång händelseschemat ändras eller du skapar en ny händelse bör du utvärdera de associerade händelseegenskaperna och tagga eller avtagga dem som innehåller personliga data om det behövs.

#### <a name="delete-or-export-tagged-event-data"></a>Ta bort eller exportera taggade händelsedata

Om alla händelseegenskaper har taggats korrekt enligt beskrivningen i föregående steg kan en miljöadministratör utfärda en borttagningsbegäran för taggade händelsedata.

Hantera förfrågningar om borttagning eller export av EUII

1. Gå till **Administratör** > **Miljö** > **Inställningar**.

1. I avsnittet **Hantera slutanvändarens identifierbara information (EUII)**, välj **Hantera EUII**.

##### <a name="deletion"></a>Borttagning

För borttagning kan du ange en lista med kommaavgränsade användar-ID i avsnittet **Ta bort slutanvändarens identifierbara information (EUII)**. Dessa ID jämförs sedan med alla taggade händelseegenskaper för alla projekt i den aktuella miljön via exakt strängmatchning. 

Om ett egenskapsvärde matchar ett av de medföljande ID:na tas den associerade händelsen bort permanent. På grund av att åtgärden är fel måste du bekräfta borttagningen efter att du har valt **Ta bort**.

##### <a name="export"></a>Export

Exportprocessen är identisk med borttagningsprocessen när det gäller att definiera händelseegenskapsvärden i avsnittet **Exportera slutanvändarens identifierbara information (EUII)** section. Dessutom måste du ange en **Azure blobblagrings-URL** för att ange exportmålet. Azures blobb-URL måste innehålla en [signatur för delad åtkomst (SAS)](/azure/storage/common/storage-sas-overview).

När du har valt **Exportera** exporteras alla händelser för det aktuella teamet som innehåller matchande taggade egenskaper i CSV-format till exportmålet.

### <a name="good-practices"></a>Bra lösningar

* Försök att undvika att skicka händelser som innehåller personliga data.
* Om du behöver skicka händelser som innehåller EUII-data begränsar du antalet händelser och händelseegenskaper som innehåller EUII-data. Då begränsar du dig själv till en sådan händelse.
* Se till att så få personer som möjligt har tillgång till de skickade personuppgifterna.
* Vid händelser som innehåller personliga data bör du ange att en egenskap ska innehålla en unik identifierare som enkelt kan länkas till en viss användare (till exempel ett användar-ID). Det gör det enklare att separera data och att exportera eller ta bort rätt data.
* Tagga endast en egenskap per händelse som innehåller personliga data. En som endast innehåller en unik identifierare.
* Tagga inte egenskaper som innehåller utförlig värden (till exempel hela begärandetexten). För engagemangsinsikter används exakt strängmatchning när du bestämmer vilka händelser som ska tas bort eller exporteras.

[!INCLUDE[footer-include](includes/footer-banner.md)]