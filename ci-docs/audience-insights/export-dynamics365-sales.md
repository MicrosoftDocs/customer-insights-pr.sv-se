---
title: Exportera Customer Insights-data till Dynamics 365 Sales
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269030"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Koppling för Dynamics 365 Sales (förhandsversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Använd dina kunddata för att skapa marknadsföringslistor, följa upp arbetsflöden och skicka ut reklamkampanjer med Dynamics 365 Sales.

## <a name="prerequisite"></a>Förutsättningar

1. Kontaktposter måste finnas i Dynamics 365 Sales innan du kan exportera ett segment från Customer Insights till Sales. Läs mer om hur du matar in kontakter i [Dynamics 365 Sales med Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Om du exporterar segment från målgruppsinsikter till Sales skapas inte nya kontaktposter i Sales-instanserna. Kontaktposterna från Sales måste matas in i målgruppsinsikter och användas som en datakälla. De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.

## <a name="configure-the-connector-for-sales"></a>Konfigurera koppling för Sales

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. Under **Dynamics 365 Sales**, välj **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

1. Ange organisationens Sales-URL i fältet **Serveradress**.

1. I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Sales-konto.

1. Mappa ett kund-ID-fält till Dynamics 365 Contact ID.

1. Välj **Nästa**.

1. Välj ett eller flera segment.

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]