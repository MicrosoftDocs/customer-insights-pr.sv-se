---
title: Exportera segment till Snapchat (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195404"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportera segment till Snapchat (förhandsversion)

Exportera segment med enhetliga kundprofiler till Snapchat och använd dem för annonser.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Snapchat företagskonto](https://business.snapchat.com/), en [Snapchat-annonskonto](https://ads.snapchat.com/) och motsvarande administratörsuppgifter. Du måste minst vara medlem i ett organisationskonto och en datahanterare för ett specifikt annonskonto.
- Du har minst en målgrupp i Snapchat Audience Manager av typen SAM (Snap Audience Match).
- [Snapchat-segment/målgrupps-ID](https://businesshelp.snapchat.com/s/article/custom-audiences). ID:t för publik finns i URL:en när du har valt publik i Snapchat Audience Manager.
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Det kan ta upp till 15 minuter att exportera upp till 1 miljon kundprofiler.
- Endast segment.

## <a name="set-up-connection-to-snapchat"></a>Konfigurera anslutningen Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Snapchat**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Autentisera med Snapchat** och ange dina administratörsuppgifter för Snapchat.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Snapchat. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange **Snapchat segment/målgrupps-ID**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
