---
title: Exportera Customer Insights-data till HubSpot
description: Lär dig hur du konfigurerar anslutningen och exporterar till HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725376"
---
# <a name="export-segments-to-hubspot-preview"></a>Exportera segment till HubSpot (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till HubSpot och använd dem för e-post marknadsföring.

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

- Ett [HubSpot-konto](https://www.hubspot.com/) och motsvarande administratörsautentiseringsuppgifter.
- [API-nyckel](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) från HubSpot.
- [Konfigurerade segments](segments.md) i Customer Insights.

## <a name="known-limitations"></a>Kända begränsningar

- Privat länk i kombination med Ta med egen lagring (BYOS) stöds inte.
- Upp till 100 000 kundprofiler per export till HubSpot, vilket kan ta upp till 15 minuter att slutföra. Hur många kundprofiler du kan exportera till HubSpot är beroende av och begränsas av ditt kontrakt med HubSpot.
- Endast segment.

## <a name="set-up-connection-to-hubspot"></a>Upprätta anslutningen till HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **HubSpot** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange dina HubSpot-autentiseringsuppgifter när du uppmanas.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut** om du vill initiera anslutningen till HubSpot.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet HubSpot. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
