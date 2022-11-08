---
title: Exportera segment till Marketo (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724962"
---
# <a name="export-segments-to-marketo-preview"></a>Exportera segment till Marketo (förhandsgranskning)

Exportera segment av enhetliga kundprofiler för att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Marketo.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Marketo-konto](https://login.marketo.com/) och motsvarande administratörsautentiseringsuppgifter.
- En [Marketo klient-ID, klienthemlighet och slutpunktsvärdnamnet för REST](https://developers.marketo.com/rest-api/authentication/).
- [Befintliga listor i Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) och motsvarande ID.
- [Konfigurerat segment](segments.md).
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Privat länk i kombination med Ta med egen lagring (BYOS) stöds inte.
- Upp till 1 miljon kundprofiler per export till Marketo, vilket kan ta upp till 3 timmar. Hur många kundprofiler du kan exportera till Marketo är beroende av ditt kontrakt med Marketo.
- Endast segment.

## <a name="set-up-connection-to-marketo"></a>Upprätta anslutningen till Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Marketo**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt **klient-ID för Marketo, din klienthemlighet och slutpunktsvärdnamnet för REST**. Endast slutpunktsvärdnamn för REST utan https://. Exempel: xyz-abc-123.mktorest.com.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Marketo. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange ditt **ID för Marketo-lista**. List-ID:t är ett endast numeriskt värde. Om ditt Marketo-list-ID är ST12345A7 tar du bort tecknet före och efter numeriska tecken och anger *12345*.

1. I avsnittet **Datamatchning** väljer du minst ett fält som representerar en kunds e-postadress eller en kunds Marketo-ID.

1. Alternativt kan du exportera **Förnamn**, **Efternamn**, **Ort**, **Delstat** och **Land/Region** för att skapa mer anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I Marketo kan du hitta dina segment under [Marketo-listor](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
