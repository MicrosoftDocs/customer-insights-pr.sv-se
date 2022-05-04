---
title: Inkrementell uppdatering för Power Query-baserade datakällor
description: Uppdatera nya och uppdaterade data för stordatakällor baserat på Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647867"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Inkrementell uppdatering för datakällor baserade på Power Query

I den här artikeln beskrivs hur du konfigurerar inkrementella uppdateringar datakällor som är baserade på Power Query.

Stegvis uppdatering för datakällor har följande fördelar:

- **Snabbare uppdateringar** – endast data som har ändrats uppdateras. Du kan till exempel endast uppdatera de fem senaste dagarna av en historisk datauppsättning.
- **Ökad pålitlighet** – med mindre uppdateringar behöver du inte upprätthålla anslutningar till temporärt källsystem så länge som minskar risken för anslutningsproblem.
- **Minskad resursförbrukning** – uppdatera endast en del av dina totala dataleads till en effektivare användning av datorresurser och minskar miljöutrymme.

## <a name="configure-incremental-refresh"></a>Konfigurera inkrementell uppdatering

Customer Insights gör det möjligt att göra inkrementella uppdateringar för datakällor som importeras genom Power Query som stöder inkrementell inmatning. Till exempel Azure SQL-databaser med datum- och tidsfält som anger när dataposter senast uppdaterades.

1. [Skapa en ny datakälla som är baserad på Power Query](connect-power-query.md).

1. Ange ett **namn** på datakällan.

1. Välj en datakälla som stöder inkrementell uppdatering, t.ex. [Azure SQL-databas.](/power-query/connectors/azuresqldatabase).

1. Välj de entiteter eller register som du vill samla in.

1. Slutför omvandlingsstegen och välj **nästa**.

1. I dialogrutan **Konfigurera inkrementell uppdatering** väljer du **konfigurera** för att öppna **inkrementella uppdateringsinställningar**. Om du väljer **hoppa över** kommer datakällan att uppdatera hela datauppsättningen.
   > [!TIP]
   > Du kan också tillämpa stegvis uppdatering senare genom att redigera en befintlig datakälla.

1. På **Inställningar för stegvis uppdatering**, konfigurerar du den inkrementella uppdateringen för alla entiteter du valde när du skapade datakälla.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurera entiteter i en datakälla för inkrementell uppdatering.":::

1. Välj en entitet och ange följande information:

   - **Definiera primär nyckeln**: Välj en primär nyckel för entiteten eller tabellen.
   - **Definiera senast uppdaterade fältet**: det här fältet visar endast attribut av typen datum eller tid. Välj ett attribut som anger när posterna senast uppdaterades. Den används för att identifiera poster som faller inom den inkrementella uppdateringens tidsram.
   - **sök efter uppdateringar varje**: anger hur länge du vill tidsram den inkrementella uppdateringen.

1. Klicka på **spara** för att slutföra skapandet av datakälla. Den ursprungliga datauppdateringen blir en fullständig uppdatering. Därefter sker inkrementella uppdateringen av data som har konfigurerats i föregående steg.


[!INCLUDE [footer-include](includes/footer-banner.md)]
