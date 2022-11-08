---
title: Exportera segment till AdRoll (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724734"
---
# <a name="export-segments-to-adroll-preview"></a>Exportera segment till AdRoll (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till AdRoll och använd dem för annonsering.

## <a name="prerequisites"></a>Förutsättningar

- Ett [AdRoll-konto](https://www.adroll.com/) och motsvarande administratörsautentiseringsuppgifter.
- Ett [AdRoll annonsörs-ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Privat länk i kombination med Ta med egen lagring (BYOS) stöds inte.
- Det kan ta upp till 10 minuter innan du exporterar upp till 250 000 kundprofiler till AdRoll. Hur många kundprofiler du kan exportera till AdRoll är beroende av ditt kontrakt med AdRoll.
- Endast segment. Ett segment måste innehålla minst 100 kundprofiler.

## <a name="set-up-connection-to-adroll"></a>Upprätta anslutningen till AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **AdRoll**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Autentisera med AdRoll** och ange dina autentiseringsuppgifter som administratör för AdRoll.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet AdRoll. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange ditt **Annonsörs-ID för AdRoll**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
