---
title: Exportera Customer Insights-data till Dynamics 365 Sales
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643840"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Koppling för Dynamics 365 Sales (förhandsversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Använd dina kunddata för att skapa marknadsföringslistor, följa upp arbetsflöden och skicka ut reklamkampanjer med Dynamics 365 Sales.

## <a name="prerequisite"></a>Förutsättningar

Kontaktposter [från Dynamics 365 Sales matade in med Common Data Service](connect-power-query.md).

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
