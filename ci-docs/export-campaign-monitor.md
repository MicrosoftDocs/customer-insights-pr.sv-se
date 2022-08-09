---
title: Exportera segment till Campaign Monitor (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196324"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportera segment till Campaign Monitor (förhandsversion)

Exportera segment med enhetliga kundprofiler till Campaign Monitor och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

- [Campaign Monitor-konto](https://www.campaignmonitor.com/) och motsvarande autentiseringsuppgifter för administratör.
- En [Campaign Monitor list-ID](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- En [generera API-nyckeln](https://www.campaignmonitor.com/api/getting-started/) från **Kontoinställningar** i Campaign Monitor för att hämta API-list-ID:t.
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Det kan ta upp till 20 minuter innan du exporterar upp till 1 miljon kundprofiler till Campaign Monitor. Hur många kundprofiler du kan exportera till Campaign Monitor är beroende av ditt kontrakt med Campaign Monitor.
- Endast segment.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurera anslutning till Campaign Monitor 

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Campaign Monitor**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen till Campaign Monitor.

1. Välj **Autentisera med Campaign Monitor** och ange dina administratörsuppgifter för Campaign Monitor.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Campaign Monitor. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange **Campaign Monitor list-ID**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Det krävs att exportera segment till Campaign Monitor.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
