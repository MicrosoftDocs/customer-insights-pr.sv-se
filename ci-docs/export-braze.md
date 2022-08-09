---
title: Exportera segment till Braze (förhandsgranskning)
description: Lär dig att konfigurera anslutningen och exporten till Braze.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195129"
---
# <a name="export-segments-to-braze-preview"></a>Exportera segment till Braze (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Braze och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Braze-konto](https://www.braze.com/) och motsvarande administratörsbehörigheter.
- En [Braze API-nyckel](https://www.braze.com/docs/api/basics/)
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress och ett Braze-kund-ID.

## <a name="known-limitations"></a>Kända begränsningar

- Det kan ta upp till 40 minuter att exportera upp till 1 miljon kundprofiler till Braze. Hur många kundprofiler du kan exportera till Braze är beroende av ditt kontrakt med Braze.
- Endast segment.

## <a name="set-up-connection-to-braze"></a>Upprätta anslutningen till Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Braze**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll din Braze API-nyckel för att fortsätta logga in.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från Braze-avsnittet. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. I fältet **Kund-ID**, välj fältet som representerar kundens Braze ID. Segmenten i Braze skapas med samma namn på segmenten som i Dynamics 365 Customer Insights. Du kan välja ytterligare valfria fält för matchande data.

1. Markera de entiteter eller segment, som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
