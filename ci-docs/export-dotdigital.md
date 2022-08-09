---
title: Exportera segment till DotDigital (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196094"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportera segment till DotDigital (förhandsversion)

Exportera segment med enhetliga kundprofiler till DotDigital-adressböcker och använd dem för kampanjer, skicka marknadsföring via e-post och skapa kundsegment med DotDigital.

## <a name="prerequisites"></a>Förutsättningar

- Ett [DotDigital-konto](https://dotdigital.com/) och en [API-användare](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Ett DotDigital ID från en [ny](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) eller befintlig adressbok i DotDigital. ID hittar du i URL-adressen när du väljer och öppnar en adressbok.
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljon kundprofiler per export till DotDigital, vilket kan ta upp till tre timmar att slutföra på grund av begränsningar på leverantörssidan. Hur många kundprofiler du kan exportera till DotDigital är beroende av ditt kontrakt med DotDigital.
- Endast segment.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurera anslutningen DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **DotDigital**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt **användarnamn och lösenord för DotDigital API**.

1. Ange ditt **ID till DotDigital-adressboken**.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet DotDigital. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Du kan även exportera **förnamn**, **efternamn**, **fullständigt namn**, **kön** och **postnummer**.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I DotDigital kan du nu hitta segment i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
