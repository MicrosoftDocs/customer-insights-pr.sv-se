---
title: Exportera segment till ActiveCampaign
description: Lär dig hur du konfigurerar anslutningen och exporterar till ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195590"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportera segment till ActiveCampaign (förhandsversion)

Exportera segment med enhetliga kundprofiler till ActiveCampaign och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

- Ett [ActiveCampaign-konto](https://www.activecampaign.com/) och motsvarande autentiseringsuppgifter för administratör.
- En [ActiveCampaign list-ID](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- En [ActiveCampaign API-nyckel](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) och värdnamn för REST-slutpunkt.
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljon kundprofiler per export till ActiveCampaign, vilket kan ta upp till 90 minuter att slutföra. Hur många kundprofiler du kan exportera till ActiveCampaign är beroende av ditt kontrakt med ActiveCampaign.
- Endast segment.

## <a name="set-up-connection-to-activecampaign"></a>Upprätta anslutning till ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **ActiveCampaign**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange din API-nyckel för ActiveCampaign och ditt värdnamn för REST-slutpunkt. Endast slutpunktsvärdnamn för REST utan https://.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet ActiveCampaign. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange ditt **List-ID för ActiveCampaign**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Alternativt kan du exportera **Förnamn**, **Efternamn** och **Telefonnummer** om du vill skapa mer anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
