---
title: Använd datakällor för att mata in data
description: Lär dig hur du importerar data från olika källor.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643975"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="43f6e-103">Översikt över datakällor</span><span class="sxs-lookup"><span data-stu-id="43f6e-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="43f6e-104">Kapaciteten för målgruppsinsikter i Dynamics 365 Customer Insights ansluter till data från en bred uppsättning källor.</span><span class="sxs-lookup"><span data-stu-id="43f6e-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="43f6e-105">Anslutning till en datakälla kallas ofta för *datainmatning*.</span><span class="sxs-lookup"><span data-stu-id="43f6e-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="43f6e-106">När du har inmatat dina data kan du [ena](data-unification.md) och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="43f6e-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="43f6e-107">Lägg till en datakälla</span><span class="sxs-lookup"><span data-stu-id="43f6e-107">Add a data source</span></span>

<span data-ttu-id="43f6e-108">Se de detaljerade artiklarna om hur du lägger till en datakälla beroende på vilket alternativ du väljer.</span><span class="sxs-lookup"><span data-stu-id="43f6e-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="43f6e-109">Du kan lägga till en datakälla på tre huvudsakliga sätt:</span><span class="sxs-lookup"><span data-stu-id="43f6e-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="43f6e-110">Efter dussintals Power Query-anslutningar</span><span class="sxs-lookup"><span data-stu-id="43f6e-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="43f6e-111">Från en Common Data Model-mapp</span><span class="sxs-lookup"><span data-stu-id="43f6e-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="43f6e-112">Från din egen Common Data Service sjö</span><span class="sxs-lookup"><span data-stu-id="43f6e-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="43f6e-113">Du kan inte lägga till data från lokala datakällor ännu.</span><span class="sxs-lookup"><span data-stu-id="43f6e-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="43f6e-114">Granska inmatade data</span><span class="sxs-lookup"><span data-stu-id="43f6e-114">Review ingested data</span></span>

<span data-ttu-id="43f6e-115">Du ser namnet på varje inmatad datakälla, dess status och sista gången data uppdaterades för källan.</span><span class="sxs-lookup"><span data-stu-id="43f6e-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="43f6e-116">Du kan sortera listan över datakällor efter varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="43f6e-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43f6e-117">![Tillagd datakälla](media/configure-data-datasource-added.png "Tillagd datakälla")</span><span class="sxs-lookup"><span data-stu-id="43f6e-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="43f6e-118">Status</span><span class="sxs-lookup"><span data-stu-id="43f6e-118">Status</span></span>  |<span data-ttu-id="43f6e-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="43f6e-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="43f6e-120">Lyckades</span><span class="sxs-lookup"><span data-stu-id="43f6e-120">Successful</span></span>   |<span data-ttu-id="43f6e-121">Datakälla har matats in om en tidpunkt nämns i kolumnen **Uppdaterad**.</span><span class="sxs-lookup"><span data-stu-id="43f6e-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="43f6e-122">Inte startad</span><span class="sxs-lookup"><span data-stu-id="43f6e-122">Not started</span></span>   |<span data-ttu-id="43f6e-123">Datakällan har inga inmatade data än eller är fortfarande i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="43f6e-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="43f6e-124">Uppdaterar</span><span class="sxs-lookup"><span data-stu-id="43f6e-124">Refreshing</span></span>    |<span data-ttu-id="43f6e-125">Datainmatning pågår.</span><span class="sxs-lookup"><span data-stu-id="43f6e-125">Data ingestion is in progress.</span></span> <span data-ttu-id="43f6e-126">Du kan avbryta åtgärden genom att välja **Avbryt uppdatering** i kolumnen **åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="43f6e-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="43f6e-127">Om du stoppar uppdateringen av en datakälla återställs den till dess senaste uppdateringstillstånd.</span><span class="sxs-lookup"><span data-stu-id="43f6e-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="43f6e-128">Misslyckad</span><span class="sxs-lookup"><span data-stu-id="43f6e-128">Failed</span></span>     |<span data-ttu-id="43f6e-129">Datahämtning har stött på fel.</span><span class="sxs-lookup"><span data-stu-id="43f6e-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="43f6e-130">Välj **Uppdatera status** för att se mer information om uppdateringsstatusen, inklusive information om fel och uppdateringar om processer nedströms.</span><span class="sxs-lookup"><span data-stu-id="43f6e-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="43f6e-131">Inläsning av data kan ta en stund.</span><span class="sxs-lookup"><span data-stu-id="43f6e-131">Loading data can take some time.</span></span> <span data-ttu-id="43f6e-132">Efter en lyckad uppdatering kan hämtade data granskas från sidan **entiteter**.</span><span class="sxs-lookup"><span data-stu-id="43f6e-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="43f6e-133">Mer information finns i [Entiteter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="43f6e-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="43f6e-134">Uppdatera en datakälla</span><span class="sxs-lookup"><span data-stu-id="43f6e-134">Refresh a data source</span></span>

<span data-ttu-id="43f6e-135">Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran.</span><span class="sxs-lookup"><span data-stu-id="43f6e-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="43f6e-136">Gå till **Admin** > **System** > [**Schema**](system.md#schedule-tab) för att konfigurera schemalagda uppdateringar av alla dina inmatade datakällor.</span><span class="sxs-lookup"><span data-stu-id="43f6e-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="43f6e-137">Uppdatera en datakälla på begäran så här:</span><span class="sxs-lookup"><span data-stu-id="43f6e-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="43f6e-138">I målgruppsinsikter går du till **Data** > **Datakällor**</span><span class="sxs-lookup"><span data-stu-id="43f6e-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="43f6e-139">Välj den lodräta ellipsen bredvid den datakälla som du vill uppdatera och välj **Uppdatera** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="43f6e-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="43f6e-140">Datakällan aktiveras nu för en manuell uppdatering.</span><span class="sxs-lookup"><span data-stu-id="43f6e-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="43f6e-141">Att uppdatera en datakälla uppdaterar både entitetsschemat och data för alla entiteter som specificerats i datakällan.</span><span class="sxs-lookup"><span data-stu-id="43f6e-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="43f6e-142">Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="43f6e-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="43f6e-143">Ta bort datakällan</span><span class="sxs-lookup"><span data-stu-id="43f6e-143">Delete a data source</span></span>

1. <span data-ttu-id="43f6e-144">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="43f6e-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="43f6e-145">Markera den lodräta ellipsen bredvid datakällan du vill ta bort och välj **ta bort** i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="43f6e-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="43f6e-146">Bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="43f6e-146">Confirm your deletion.</span></span>
