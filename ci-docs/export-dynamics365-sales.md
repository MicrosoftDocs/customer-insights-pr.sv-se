---
title: Exportera segment till Dynamics 365 Sales (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196003"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportera segment till Dynamics 365 Sales (förhandsgranskning)

Använd dina kunddata för att skapa marknadsföringslistor, följa upp arbetsflöden och skicka ut reklamkampanjer med Dynamics 365 Sales.

## <a name="prerequisites"></a>Förutsättningar

Kontaktposter måste finnas i Dynamics 365 Sales innan du kan exportera ett segment från Customer Insights till Sales. Läs mer om hur du använder kontakter från [Dynamics 365 Sales med Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Om du exporterar segment från Customer Insights till Sales skapas inga nya kontaktposter i Sales-instanserna. Kontaktposterna från Sales måste innehålla Customer Insights och användas som en datakälla. De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.

## <a name="known-limitations"></a>Kända begränsningar

Exporter till Dynamics 365 Sales är begränsad till 100 000 per segment, vilket kan ta upp till 3 timmar att slutföra.

## <a name="set-up-connection-to-sales"></a>Upprätta anslutningen till Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Dynamics 365 Sales**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange organisationens Sales-URL i fältet **Serveradress**.

1. I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Sales-konto.

1. Mappa ett kund-ID-fält till Dynamics 365 Contact ID.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Dynamics 365 Sales. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj fältet Kontakt-ID i entiteten Kund som matchar Dynamics 365 Kontakt-ID.

1. Välj de segment som du vill exportera.

1. Välj **Spara**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
