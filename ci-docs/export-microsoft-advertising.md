---
title: Exportera segment till Microsoft Advertising (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196554"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportera segment till Microsoft Advertising (förhandsversion)

Exportera Customer Insights-segment till Microsoft Advertising för att skapa Customer Match-målgrupper. Använd dessa målgrupper för dina annonskampanjer.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Microsoft Advertising-konto](https://ads.microsoft.com/) och motsvarande autentiseringsuppgifter för administratör.
- Microsoft Advertising kund-ID och konto-ID. Du hittar kund-ID (`cid`) och konto-ID (`aid`) i parametrarna för webbadressen när du är inloggad på Microsoft Advertising.
- Du har accepterat användarvillkoren för Customer Match.
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 500 000 kundprofiler per export till Microsoft Advertising, vilket kan ta upp till 10 minuter.
- Endast segment.

## <a name="set-up-connection-to-microsoft-advertising"></a>Upprätta anslutningen till Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Microsoft Advertising**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Standardinställningen är administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Microsoft Advertising kund-ID**.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Autentisera med Microsoft Advertising** och ange dina administratörsuppgifter för Microsoft Advertising.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Microsoft Advertising. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj de segment som ska exporteras. Customer Match-målgrupperna i Microsoft Advertising skapas automatiskt med namnet på de segment som valts för export. Varje segment resulterar i en separat Customer Match-målgrupp.

1. Ange ditt **kund-ID och konto-ID för Microsoft Advertising**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet med en kunds e-postadress.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
