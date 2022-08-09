---
title: Exportera segment till Mailchimp (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196876"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportera segment till Mailchimp (förhandsversion)

Exportera segment av enhetliga kundprofiler till Mailchimp för att skapa nyhetsbrev och e-postkampanjer.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Mailchimp-konto](https://mailchimp.com/) och motsvarande administratörsautentiseringsuppgifter.
- [Befintliga målgrupper i Mailchimp](https://mailchimp.com/help/create-audience/) och motsvarande [målgrupps-ID](https://mailchimp.com/help/find-audience-id/).
- [Konfigurerat segment](segments.md).
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljon kundprofiler per export till Mailchimp, vilket kan ta upp till 3 timmar. Hur många kundprofiler du kan exportera till Mailchimp är beroende av ditt kontrakt med Mailchimp.
- Endast segment.

## <a name="set-up-connection-to-mailchimp"></a>Konfigurera anslutningen Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Mailchimp**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Autentisera med Mailchimp** och ange dina Mailchimp-autentiseringsuppgifter.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Mailchimp. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange din **Målgrupps-ID för Mailchimp**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Alternativt kan du exportera **Förnamn** och **Efternamn** för att skapa mer anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
