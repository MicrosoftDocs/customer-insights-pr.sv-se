---
title: Exportera Customer Insights-data till Campaign Monitor
description: Lär dig hur du konfigurerar anslutningen och exporterar till Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647587"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportera segment till Campaign Monitor (förhandsversion)

Exportera segment med enhetliga kundprofiler till Campaign Monitor och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Campaign Monitor-konto](https://www.campaignmonitor.com/) och motsvarande autentiseringsuppgifter för administratör.
-   Du har [konfigurerade segments](segments.md) i Customer Insights.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till 1 miljon kundprofiler per export till Campaign Monitor.
- Export till Campaign Monitor är begränsad till segment.
- Det kan ta upp till 20 minuter innan du exporterar upp till 1 miljon kundprofiler till Campaign Monitor. 
- Hur många kundprofiler du kan exportera till Campaign Monitor är beroende av och begränsas av ditt kontrakt med Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurera anslutning till Campaign Monitor 

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Campaign Monitor** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Campaign Monitor.

1. Välj **Autentisera med Campaign Monitor** och ange dina administratörsuppgifter för Campaign Monitor.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Campaign Monitor. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange [**Campaign Monitor list-ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Generera API-nyckeln](https://www.campaignmonitor.com/api/getting-started/) från **Kontoinställningar** i Campaign Monitor  först för att visa API-list-ID:t.  

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Det krävs att exportera segment till Campaign Monitor.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Campaign Monitor, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Campaign Monitor uppfyller alla eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
