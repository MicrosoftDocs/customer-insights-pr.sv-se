---
title: Uppdatera schemasystem
description: Schemalägg när systemet ska uppdateras
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246350"
---
# <a name="schedule-system-refresh"></a>Uppdatera schemasystem

Schemalägg automatiska uppdateringar av alla dina [inmatade datakällor](data-sources.md). Automatiska uppdateringar hjälper till att se till att uppdateringarna från dina datakällor återspeglas i dina enhetliga kundprofiler.

> [!NOTE]
> Power Query-datakällor som hanteras av dig uppdateras enligt egna scheman. Om du vill schemalägga uppdatering av dessa Power Query-datakällor konfigurerar du uppdateringsinställningarna för den specifika datakällan från sidan **Datakällor**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Inställningar för dataflödesuppdatering":::

## <a name="set-system-refresh-schedule"></a>Schemalägg uppdatering av system

1. Gå till **Admin** > **System** och välj fliken **Schema**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Fliken Schemalägg uppdatering från systemsidan.":::

1. Standardtillståndet för den schemalagda uppdateringen är **av**. För att aktivera schemalagda uppdateringar, ändra växlingsknappen överst på skärmen till **På**.

1. Välj mellan **veckovis** (standard) och **daglig** uppdatering. Om du vill schemalägga en ny veckovis uppdatering väljer du en eller flera dagar då du vill att uppdateringen ska utföras.

1. Ange din **Tidszon** och använd sedan listrutan **Tid** för att ange uppdateringstiden. Om du vill schemalägga flera uppdateringar under en och samma dag väljer du **Lägg till en annan tid**.

1. Välj **Spara** för att införa ändringarna.

[!INCLUDE [footer-include](includes/footer-banner.md)]
