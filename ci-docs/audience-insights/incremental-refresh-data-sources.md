---
title: Inkrementell uppdatering för Power Query-baserade datakällor
description: Uppdatera nya och uppdaterade data för stora datakällor baserat på Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268570"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="04bda-103">Inkrementell uppdatering för datakällor baserad Power Query</span><span class="sxs-lookup"><span data-stu-id="04bda-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="04bda-104">Stegvis uppdatering för datakällor har följande fördelar:</span><span class="sxs-lookup"><span data-stu-id="04bda-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="04bda-105">**Snabbare uppdateringar** – endast data som har ändrats uppdateras.</span><span class="sxs-lookup"><span data-stu-id="04bda-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="04bda-106">Du kan till exempel endast uppdatera de fem senaste dagarna av en historisk datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="04bda-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="04bda-107">**Ökad pålitlighet** – med mindre uppdateringar behöver du inte upprätthålla anslutningar till temporärt källsystem så länge som minskar risken för anslutningsproblem.</span><span class="sxs-lookup"><span data-stu-id="04bda-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="04bda-108">**Minskad resursförbrukning** – uppdatera endast en del av dina totala dataleads till en effektivare användning av datorresurser och minskar miljöutrymme.</span><span class="sxs-lookup"><span data-stu-id="04bda-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="04bda-109">Konfigurera stegvis uppdatering</span><span class="sxs-lookup"><span data-stu-id="04bda-109">Configure incremental refresh</span></span>

<span data-ttu-id="04bda-110">Målgruppsinsikter möjliggör inkrementell uppdatering av datakällor som importeras via Power Query som stöder stegvis inmatning.</span><span class="sxs-lookup"><span data-stu-id="04bda-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="04bda-111">Till exempel Azure SQL-databaser med datum- och tidsfält som anger när dataposter senast uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="04bda-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="04bda-112">[Skapa en ny datakälla utifrån Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="04bda-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="04bda-113">Ange ett namn på datakällan.</span><span class="sxs-lookup"><span data-stu-id="04bda-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="04bda-114">Välj en datakälla som stöder inkrementell uppdatering, t.ex. Azure SQL-databas.</span><span class="sxs-lookup"><span data-stu-id="04bda-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="04bda-115">Välj de entiteter eller register som du vill samla in.</span><span class="sxs-lookup"><span data-stu-id="04bda-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="04bda-116">Slutför omvandlingsstegen och välj **nästa**.</span><span class="sxs-lookup"><span data-stu-id="04bda-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="04bda-117">I dialogrutan **Konfigurera inkrementell uppdatering** väljer du **konfigurera** för att öppna **inkrementella uppdateringsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="04bda-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="04bda-118">Om du väljer **hoppa över** kommer datakällan att uppdatera hela datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="04bda-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="04bda-119">Du kan också tillämpa stegvis uppdatering senare genom att redigera en befintlig datakälla.</span><span class="sxs-lookup"><span data-stu-id="04bda-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="04bda-120">På **Inställningar för stegvis uppdatering**, konfigurerar du den inkrementella uppdateringen för alla entiteter du valde när du skapade datakälla.</span><span class="sxs-lookup"><span data-stu-id="04bda-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="04bda-121">![konfigurera entiteter i en datakälla för inkrementell uppdatering](media/incremental-refresh-settings.png "Konfigurera entiteter i en datakälla för inkrementell uppdatering")</span><span class="sxs-lookup"><span data-stu-id="04bda-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="04bda-122">Välj en entitet och ange följande information:</span><span class="sxs-lookup"><span data-stu-id="04bda-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="04bda-123">**Definiera primär nyckeln**: Välj en primär nyckel för entiteten eller tabellen.</span><span class="sxs-lookup"><span data-stu-id="04bda-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="04bda-124">**Definiera senast uppdaterade fältet**: det här fältet visar endast attribut av typen datum eller tid.</span><span class="sxs-lookup"><span data-stu-id="04bda-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="04bda-125">Välj ett attribut som anger när posterna senast uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="04bda-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="04bda-126">Den används för att identifiera poster som faller inom den inkrementella uppdateringens tidsram.</span><span class="sxs-lookup"><span data-stu-id="04bda-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="04bda-127">**sök efter uppdateringar varje**: anger hur länge du vill tidsram den inkrementella uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="04bda-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="04bda-128">Klicka på **spara** för att slutföra skapandet av datakälla.</span><span class="sxs-lookup"><span data-stu-id="04bda-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="04bda-129">Den ursprungliga datauppdateringen blir en fullständig uppdatering.</span><span class="sxs-lookup"><span data-stu-id="04bda-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="04bda-130">Därefter sker inkrementella uppdateringen av data som har konfigurerats i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="04bda-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]