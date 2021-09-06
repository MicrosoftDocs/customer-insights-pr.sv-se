---
title: Exportera Customer Insights-data till Autopilot
description: Lär dig hur du konfigurerar anslutningen och exporterar till Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9ada8a6f4e4546990a1360567b400033050119c4c4c9a3df1af8fcaab75e157
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032047"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportera segment till Autopilot (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Autopilot och använd dem för e-postmarknadsföring i Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [Autopilot-konto](https://www.autopilothq.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till totalt 100 000 profiler till Autopilot.
- Export till Autopilot är begränsad till segment.
- Att exportera upp till 100 000 profiler till Autopilot kan ta upp till några timmar att genomföra. 
- Antalet profiler som du kan exportera till Autopilot är beroende av och begränsat enligt ditt kontrakt med Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Upprätta anslutningen till Autopilot

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Autopilot** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

3. Ange din [Autopilot API-nyckel](https://autopilot.docs.apiary.io/#).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Autopilot.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Autopilot. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

3. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**.

1. Välj de segment som du vill exportera. Vi rekommenderar **starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till Autopilot. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Autopilot tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Autopilot uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
