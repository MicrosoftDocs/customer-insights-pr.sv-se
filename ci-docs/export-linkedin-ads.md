---
title: Exportera segment till LinkedIn Ads (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196830"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportera segment till LinkedIn Ads (förhandsversion)

Exportera segment med enhetliga kundprofiler till LinkedIn Ads för att skapa matchade målgrupper. Använd de matchade målgrupperna för företagsinriktning och kontaktinriktning.

## <a name="prerequisites"></a>Förutsättningar

- Ett [LinkedIn Campaign Manager konto](https://business.linkedin.com/marketing-solutions/ads) och motsvarande administratörsbehörigheter.
- Ett [LinkedIn Campaign Manager konto-ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 100 000 miljon kundprofiler per export till LinkedIn Ads, vilket kan ta upp till 10 minuter att slutföra.
- Endast segment. Ett segment måste innehålla minst 300 unika profiler.

## <a name="set-up-connection-to-linkedin-ads"></a>Upprätta anslutningen till LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **LinkedIn Ads**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange LinkedIn Campaign Manager konto-ID.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Autentisera med LinkedIn** och tillhandahåll dina administratörsautentiseringsuppgifter för LinkedIn Campaign Manager.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet LinkedIn Ads. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj om du vill exportera data för att göra [kontaktinriktning](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [företagsinriktning](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn.

1. I avsnittet **Datamatchning** väljer du minst ett fält som representerar en kunds e-postadress, Apple Ad ID, Googles Ad ID, Google användar-ID, förnamn och efternamn. Om du väljer företagsanpassning väljer du minst ett fält som representerar ett företagsnamn, en e-postdomän, LinkedIn-sidans URL, lagersymbol eller webbplats.

1. Lägg eventuellt till fält för att ytterligare definiera din export. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera. De matchade målgrupperna i LinkedIn Campaign Manager skapas automatiskt med namnet på de segment som du har valt att exportera. Varje segment resulterar i en separat matchad målgrupp.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
