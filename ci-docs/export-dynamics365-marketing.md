---
title: Exportera segment till Dynamics 365 Marketing (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196646"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exportera segment till Dynamics 365 Marketing (förhandsgranskning)

Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Om du använder de nya funktionerna i Dynamics 365 Marketing för kundens färd i realtid i en Dataverse organisation behöver du inte skapa en standardexport till Dynamics 365 Marketing. Kontakter och segment från Customer Insights är tillgängliga direkt i Dynamics 365 Marketing efter att ha anslutit Marketing och Customer Insights. Innan du tar bort befintlig export bör du läsa dokumentationen för [hur du ansluter Customer Insights och Dynamics 365 Marketing strukturera kundens färd](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Förutsättningar

Kontaktposter måste finnas i Dynamics 365 Marketing innan du kan exportera ett segment från Customer Insights till Marketing. Läs mer om hur du matar in kontakter i [Dynamics 365 Marketing med Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Om du exporterar segment från Customer Insights till Marketing skapas inga nya kontaktposter i Marketing-instanserna. Kontaktposterna från Marketing måste innehålla Customer Insights och användas som en datakälla. De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.

## <a name="set-up-connection-to-marketing"></a>Upprätta anslutningen till Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Dynamics 365 Marketing**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange organisationens marknadsförings-URL i fältet **Serveradress**.

1. I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.

1. Mappa fältet Kontakt-ID i entiteten Kund till Dynamics 365 Kontakt-ID.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Dynamics 365 Marketing. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj fältet Kontakt-ID i entiteten Kund som matchar Dynamics 365 Kontakt-ID.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
