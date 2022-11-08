---
title: Exportera segment till Sendinblue (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724916"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportera segment till Sendinblue (förhandsversion)

Exportera segment från enhetliga kundprofiler i syfte att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Sendinblue.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Sendinblue-konto](https://www.sendinblue.com/) och motsvarande autentiseringsuppgifter för administratör.
- En [SendinBlue API-nyckel](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Befintliga listor i Sendinblue och motsvarande ID.
- [Konfigurerat segment](segments.md).
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Privat länk i kombination med Ta med egen lagring (BYOS) stöds inte.
- Upp till 1 miljon kundprofiler per export till Sendinblue, vilket kan ta upp till 90 minuter att slutföra. Hur många kundprofiler du kan exportera till Sendinblue är beroende av ditt kontrakt med Sendinblue.
- Endast segment.

## <a name="set-up-connection-to-sendinblue"></a>Konfigurera anslutning till Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Sendinblue**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange din **SendinBlue API-nyckel**.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet Sendinblue. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange ditt **List-ID för Sendinblue**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Alternativt kan du exportera **Förnamn**, **Efternamn** och **Telefonnummer** om du vill skapa mer anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
