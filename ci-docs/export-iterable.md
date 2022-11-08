---
title: Exportera segment till Iterable (förhandsgranskning)
description: Lär dig att konfigurera anslutningen och exporten till Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724626"
---
# <a name="export-segments-to-iterable-preview"></a>Exportera segment till Iterable (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Iterable och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Iterable-konto](https://iterable.com/) och motsvarande administratörsbehörigheter.
- En [Iterable API-nyckel](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Privat länk i kombination med Ta med egen lagring (BYOS) stöds inte.
- 1 miljon kundprofiler till Iterable, vilket kan ta upp till 30 minuter att slutföra. Hur många kundprofiler du kan exportera till Iterable är beroende av ditt kontrakt med Iterable.
- Endast segment.

## <a name="set-up-connection-to-iterable"></a>Upprätta anslutningen till Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Iterable**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll din Iterable API-nyckel för att fortsätta logga in.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från Iterable-avsnittet. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Listan som skapas i Iterable får exakt samma namn som segmentnamnet i Dynamics 365 Customer Insights.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
