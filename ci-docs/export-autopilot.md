---
title: Exportera segment till Autopilot (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724824"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportera segment till Autopilot (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Autopilot och använd dem för e-postmarknadsföring i Autopilot.

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

- Ett [Autopilot-konto](https://www.autopilothq.com/) och motsvarande administratörsautentiseringsuppgifter.
- En [Autopilot API-nyckel](https://autopilot.docs.apiary.io/#)
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Privat länk i kombination med Ta med egen lagring (BYOS) stöds inte.
- Det kan ta upp till några timmar innan du exporterar upp till 100 000 kundprofiler till Autopilot. Hur många kundprofiler du kan exportera till Autopilot är beroende av ditt kontrakt med Autopilot.
- Endast segment.

## <a name="set-up-connection-to-autopilot"></a>Upprätta anslutningen till Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Autopilot**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange din Autopilot API-nyckel.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Autopilot. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Du kan även exportera andra fält **förnamn** och **efternamn**.

1. Välj de segment du vill exportera med de kända begränsningarna.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
