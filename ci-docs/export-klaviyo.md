---
title: Exportera segment till Klaviyo (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724655"
---
# <a name="export-segments-to-klaviyo-preview"></a>Exportera segment till Klaviyo (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Klaviyo och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Klaviyo-konto](https://www.klaviyo.com/) och motsvarande autentiseringsuppgifter för administratör.
- En [Kluseyo-API-nyckel](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- Ett [Klaviyo list-ID](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Privat länk i kombination med Ta med egen lagring (BYOS) stöds inte.
- Upp till 1 miljon kundprofiler per export till Klaviyo, vilket kan ta upp till 20 minuter att slutföra. Hur många kundprofiler du kan exportera till Klaviyo är beroende av ditt kontrakt med Klaviyo.
- Endast segment.

## <a name="set-up-connection-to-klaviyo"></a>Upprätta anslutningen till Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Klaviyo**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll din Klaviyo API-nyckel för att fortsätta logga in.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Autentisera med Klaviyo** och ange dina administratörsautentiseringsuppgifter för Klaviyo.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet Klaviyo. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange ditt **List-ID för Klaviyo**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
