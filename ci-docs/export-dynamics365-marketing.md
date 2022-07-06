---
title: Exportera segment till Dynamics 365 Marketing (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054638"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exportera segment till Dynamics 365 Marketing (förhandsgranskning)

Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med Dynamics 365 Marketing. Mer information finns i [Använda segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Om du använder de nya funktionerna i Dynamics 365 Marketing för kundens färd i realtid i en Dataverse organisation behöver du inte skapa en standardexport till Dynamics 365 Marketing. Kontakter och segment från Customer Insights är tillgängliga direkt i Dynamics 365 Marketing efter att ha anslutit Marketing och Customer Insights. Innan du tar bort befintlig export bör du läsa dokumentationen för [hur du ansluter Customer Insights och Dynamics 365 Marketing strukturera kundens färd](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Krav för anslutning

- Kontaktposter måste finnas i Dynamics 365 Marketing innan du kan exportera ett segment från Customer Insights till Marketing. Läs mer om hur du matar in kontakter i [Dynamics 365 Marketing med Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Om du exporterar segment från Customer Insights till Marketing skapas inga nya kontaktposter i Marketing-instanserna. Kontaktposterna från Marketing måste innehålla Customer Insights och användas som en datakälla. De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.

## <a name="set-up-connection-to-marketing"></a>Upprätta anslutningen till Marketing

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Dynamics 365 Marketing** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange organisationens marknadsförings-URL i fältet **Serveradress**.

1. I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.

1. Mappa fältet Kontakt-ID i entiteten Kund till Dynamics 365 Kontakt-ID.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]