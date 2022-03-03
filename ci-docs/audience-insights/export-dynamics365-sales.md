---
title: Exportera Customer Insights-data till Dynamics 365 Sales
description: Lär dig hur du konfigurerar anslutningen och exporterar till Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: cf680c21c55c71d99728be79fe68111dc89a79ec
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355051"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Använd segment i Dynamics 365 Sales (förhandsvisning)



Använd dina kunddata för att skapa marknadsföringslistor, följa upp arbetsflöden och skicka ut reklamkampanjer med Dynamics 365 Sales.

## <a name="known-limitations"></a>Kända begränsningar

- Export till Dynamics 365 Sales är begränsad till 100 000 medlemmar per segment.
- Segmentexporten till Dynamics 365 Sales kan ta upp till 3 timmar att slutföra. 

## <a name="prerequisite-for-connection"></a>Krav för anslutning

1. Kontaktposter måste finnas i Dynamics 365 Sales innan du kan exportera ett segment från Customer Insights till Sales. Läs mer om hur du matar in kontakter i [Dynamics 365 Sales med Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > Om du exporterar segment från målgruppsinsikter till Sales skapas inte nya kontaktposter i Sales-instanserna. Kontaktposterna från Sales måste matas in i målgruppsinsikter och användas som en datakälla. De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.

## <a name="set-up-the-connection-to-sales"></a>Upprätta anslutningen till Sales

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Dynamics 365 Sales** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange organisationens Sales-URL i fältet **Serveradress**.

1. I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Sales-konto.

1. Mappa ett kund-ID-fält till Dynamics 365 Contact ID.

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Dynamics 365 Sales. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Välj ett eller flera segment.

1. Välj **Spara**

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
