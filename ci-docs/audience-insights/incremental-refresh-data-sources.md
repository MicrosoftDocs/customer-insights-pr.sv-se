---
title: Inkrementell uppdatering för Power Query-baserade datakällor
description: Uppdatera nya och uppdaterade data för stora datakällor baserat på Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 1af2e4c42dc5890556c90bb3e5ef1aeb0621fda0
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554181"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Inkrementell uppdatering för datakällor baserad Power Query

Stegvis uppdatering för datakällor har följande fördelar:

- **Snabbare uppdateringar** – endast data som har ändrats uppdateras. Du kan till exempel endast uppdatera de fem senaste dagarna av en historisk datauppsättning.
- **Ökad pålitlighet** – med mindre uppdateringar behöver du inte upprätthålla anslutningar till temporärt källsystem så länge som minskar risken för anslutningsproblem.
- **Minskad resursförbrukning** – uppdatera endast en del av dina totala dataleads till en effektivare användning av datorresurser och minskar miljöutrymme.

## <a name="configure-incremental-refresh"></a>Konfigurera stegvis uppdatering

Målgruppsinsikter möjliggör inkrementell uppdatering av datakällor som importeras via Power Query som stöder stegvis inmatning. Till exempel Azure SQL-databaser med datum- och tidsfält som anger när dataposter senast uppdaterades.

1. [Skapa en ny datakälla utifrån Power Query](connect-power-query.md).

1. Ange ett namn på datakällan.

1. Välj en datakälla som stöder inkrementell uppdatering, t.ex. Azure SQL-databas.

1. Välj de entiteter eller register som du vill samla in.

1. Slutför omvandlingsstegen och välj **nästa**.

1. I dialogrutan **Konfigurera inkrementell uppdatering** väljer du **konfigurera** för att öppna **inkrementella uppdateringsinställningar**. Om du väljer **hoppa över** kommer datakällan att uppdatera hela datauppsättningen.
   > [!TIP]
   > Du kan också tillämpa stegvis uppdatering senare genom att redigera en befintlig datakälla.

1. På **Inställningar för stegvis uppdatering**, konfigurerar du den inkrementella uppdateringen för alla entiteter du valde när du skapade datakälla.

   > [!div class="mx-imgBorder"]
   > ![Konfigurera entiteter i en datakälla för inkrementell uppdatering.](media/incremental-refresh-settings.png "Konfigurera entiteter i en datakälla för inkrementell uppdatering")

1. Välj en entitet och ange följande information:

   - **Definiera primär nyckeln**: Välj en primär nyckel för entiteten eller tabellen.
   - **Definiera senast uppdaterade fältet**: det här fältet visar endast attribut av typen datum eller tid. Välj ett attribut som anger när posterna senast uppdaterades. Den används för att identifiera poster som faller inom den inkrementella uppdateringens tidsram.
   - **sök efter uppdateringar varje**: anger hur länge du vill tidsram den inkrementella uppdateringen.

1. Klicka på **spara** för att slutföra skapandet av datakälla. Den ursprungliga datauppdateringen blir en fullständig uppdatering. Därefter sker inkrementella uppdateringen av data som har konfigurerats i föregående steg.


[!INCLUDE[footer-include](../includes/footer-banner.md)]