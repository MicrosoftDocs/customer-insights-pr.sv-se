---
title: Exportera Customer Insights-data till Dynamics 365 Marketing
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597625"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Koppling för Dynamics 365 Marketing (förhandsversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med Dynamics 365 Marketing. Mer information finns i [Använda segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Förutsättningar

- Kontaktposter måste finnas i Dynamics 365 Marketing innan du kan exportera ett segment från Customer Insights till Marketing. Läs mer om hur du matar in kontakter i [Dynamics 365 Marketing med Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Om du exporterar segment från målgruppsinsikter till Marketing skapas inte nya kontaktposter i Marketing-instanserna. Kontaktposterna från Marketing måste matas in i målgruppsinsikter och användas som en datakälla. De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.

## <a name="configure-the-connector-for-marketing"></a>Konfigurera koppling för marknadsföring

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. Under **Dynamics 365 Marketing**, välj **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

1. Ange organisationens marknadsförings-URL i fältet **Serveradress**.

1. I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.

1. Mappa ett kund-ID-fält till Dynamics 365 Contact ID.

1. Välj **Nästa**.

1. Välj ett eller flera segment.

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]