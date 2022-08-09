---
title: Exportera segment till MoEngage
description: Lär dig att konfigurera anslutningen och exporten till MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199150"
---
# <a name="export-segments-to-moengage-preview"></a>Exportera segment till MoEngage (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till MoEngage och använd dem för e-postmarknadsföring i MoEngage.

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

- [MoEngage-konto](https://www.moengage.com/) och motsvarande administratörsbehörigheter.
- MoEngage API-nyckel från Inställningar > API i MoEngage.
- [Konfigurerade segments](segments.md) i Customer Insights.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 100 000 kundprofiler per export till MoEngage, vilket kan ta upp till 15 minuter. Hur många kundprofiler du kan exportera till MoEngage är beroende av ditt kontrakt med MoEngage.
- Endast segment.

## <a name="set-up-connection-to-moengage"></a>Konfigurera anslutningen MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **MoEngage** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange din [MoEngage Data API ID och API-nyckel](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen till MoEngage.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet MoEngage. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält.

1. Välj de segment som du vill exportera. Vi skapar ett eller flera segment med samma namn som de valda segmenten i MoEngage under **Segment** > **Anpassade segment**.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
