---
title: Exportera Customer Insights-data till Dynamics 365 Marketing
description: Lär dig hur du konfigurerar anslutningen och exporterar till Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bd8189f8daee1a6aea75e75e116186f62a360ba4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692503"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Använd segment i Dynamics 365 Marketing (förhandsvisning)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med Dynamics 365 Marketing. Mer information finns i [Använda segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>Krav för anslutning

- Kontaktposter måste finnas i Dynamics 365 Marketing innan du kan exportera ett segment från Customer Insights till Marketing. Läs mer om hur du matar in kontakter i [Dynamics 365 Marketing med Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Om du exporterar segment från målgruppsinsikter till Marketing skapas inte nya kontaktposter i Marketing-instanserna. Kontaktposterna från Marketing måste matas in i målgruppsinsikter och användas som en datakälla. De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.

## <a name="set-up-connection-to-marketing"></a>Upprätta anslutningen till Marketing

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Dynamics 365 Marketing** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange organisationens marknadsförings-URL i fältet **Serveradress**.

1. I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.

1. Mappa ett kund-ID-fält till Dynamics 365 Contact ID.

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Dynamics 365 Marketing. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Välj ett eller flera segment.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
