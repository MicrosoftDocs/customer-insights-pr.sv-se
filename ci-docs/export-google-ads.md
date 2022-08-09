---
title: Exportera segment till Google Ads (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196600"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportera segment till Google Ads (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till en Google Ads-målgruppslista och använd dem för att annonsera på Google Search, Gmail, YouTube och Google Display Network.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Google Ads-konto](https://ads.google.com/) och motsvarande administratörsautentiseringsuppgifter.
- En [Google Ads kund-ID](https://support.google.com/google-ads/answer/1704344).
- Du uppfyller kraven i [policyn för Customer Match](https://support.google.com/adspolicy/answer/6299717).
- Du uppfyller kraven i [storlekar för återmarknadsföringslista](https://support.google.com/google-ads/answer/7558048).
- [Konfigurerat segment](segments.md).
- Enhetliga kundprofiler i de exporterade segmenten innehåller fält som representerar e-postadress, telefonnummer, ID för mobilannonsör, användar-ID för tredje part, samt adress.

## <a name="known-limitations"></a>Kända begränsningar

- Exportera upp till 1 miljon kundprofiler per export till Google Ads, vilket kan ta upp till 30 minuter att slutföra på grund av begränsningar på leverantörssidan.
- Endast segment.
- Matchningen i Google Ads kan ta upp till 48 timmar.

## <a name="set-up-connection-to-google-ads"></a>Konfigurera anslutningen Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Google Ads**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt kund-ID för Google Ads.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Autentisera med Google Ads** och ange dina Google Ads-autentiseringsuppgifter.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Google Ads. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj om du vill använda en befintlig målgrupp eller skapa en ny:
   - Om du vill uppdatera en befintlig Google Ads-målgrupp anger du ditt [målgrupps-ID för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Om du vill skapa en ny målgrupp låter du fältet ID för Google-målgrupp vara tomt. Customer Insights skapar automatiskt en ny målgrupp på ditt Google Ads-konto och använder namnet på det exporterade segmentet.

1. I avsnittet **Datamatchning** väljer du ett eller flera datafält som ska exporteras, och markerar sedan det fält som representerar motsvarande datafält i Customer Insights.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
