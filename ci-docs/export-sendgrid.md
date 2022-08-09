---
title: Exportera segment till SendGrid (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197014"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportera segment till SendGrid (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till SendGrid-kontaktlistor och använd dem för kampanjer och e-postmarknadsföring i SendGrid.

## <a name="prerequisites"></a>Förutsättningar

- [SendGrid-konto](https://sendgrid.com/) och motsvarande administratörsautentiseringsuppgifter.
- [Befintliga kontaktlistor i SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) och motsvarande ID.
- [SendGrid API-nyckel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Det kan ta upp till några timmar innan du exporterar upp till 100 000 kundprofiler till SendGrid. Hur många kundprofiler du kan exportera till SendGrid är beroende av ditt kontrakt med SendGrid.
- Endast segment.

## <a name="set-up-connection-to-sendgrid"></a>Konfigurera anslutningen SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **SendGrid**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange din **SendGrid API-nyckel**.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet SendGrid. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange ditt **ID för SendGrid-lista**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress.

1. Välj valfritt fält som t.ex. **Förnamn**, **Efternamn**, **Land/region**, **Delstat**, **Stad** och **Postnummer**.

1. Välj de segment du vill exportera med de kända begränsningarna.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
