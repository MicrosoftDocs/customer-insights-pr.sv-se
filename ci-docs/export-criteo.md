---
title: Exportera segment till Criteo (förhandsgranskning)
description: Lär dig att konfigurera anslutningen och exporten till Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760048"
---
# <a name="export-segments-to-criteo-preview"></a>Exportera segment till Criteo (förhandsgranskning)

Exportera segment för enhetliga kundprofiler för att generera kampanjer, tillhandahålla e-postmarknadsföring och utnyttja specifika kundgrupper med Criteo.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Criteo Dynamics Retargeting-konto](https://www.criteo.com/login/) och motsvarande administratörsbehörigheter.
- [Konfigurerat segment](segments.md).
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljon kundprofiler per export till Criteo, vilket kan ta upp till 30 minuter att slutföra. Hur många kundprofiler du kan exportera till Criteo är beroende av ditt kontrakt med Criteo.
- Endast segment.

## <a name="set-up-connection-to-criteo"></a>Upprätta anslutningen till Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Criteo**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Autentisera med Criteo** och ange ditt administratörsanvändarnamn och dina autentiseringsuppgifter för Criteo.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från Criteo-avsnittet. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
