---
title: Använd datakällor för att mata in data
description: Lär dig hur du importerar data från olika källor.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887916"
---
# <a name="data-sources-overview"></a><span data-ttu-id="f6210-103">Översikt över datakällor</span><span class="sxs-lookup"><span data-stu-id="f6210-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f6210-104">Kapaciteten för målgruppsinsikter i Dynamics 365 Customer Insights ansluter till data från en bred uppsättning källor.</span><span class="sxs-lookup"><span data-stu-id="f6210-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="f6210-105">Anslutning till en datakälla kallas ofta för *datainmatning*.</span><span class="sxs-lookup"><span data-stu-id="f6210-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="f6210-106">När du har inmatat dina data kan du [ena](data-unification.md) och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f6210-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="f6210-107">Lägg till en datakälla</span><span class="sxs-lookup"><span data-stu-id="f6210-107">Add a data source</span></span>

<span data-ttu-id="f6210-108">Se de detaljerade artiklarna om hur du lägger till en datakälla beroende på vilket alternativ du väljer.</span><span class="sxs-lookup"><span data-stu-id="f6210-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="f6210-109">Du kan lägga till en datakälla på tre huvudsakliga sätt:</span><span class="sxs-lookup"><span data-stu-id="f6210-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="f6210-110">Efter dussintals Power Query-anslutningar</span><span class="sxs-lookup"><span data-stu-id="f6210-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="f6210-111">Från en Common Data Model-mapp</span><span class="sxs-lookup"><span data-stu-id="f6210-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="f6210-112">Från din egen Common Data Service sjö</span><span class="sxs-lookup"><span data-stu-id="f6210-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="f6210-113">Lägga till data lokala datakällor</span><span class="sxs-lookup"><span data-stu-id="f6210-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="f6210-114">Det finns stöd för lokala datakällor i målgruppinsikter bygger på Power Platform-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="f6210-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="f6210-115">Dataflöden kan aktiveras i Customer Insights av [ange Microsoft Dataverse miljö-URL](manage-environments.md#create-an-environment-in-an-existing-organization) när du ställer in miljön.</span><span class="sxs-lookup"><span data-stu-id="f6210-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="f6210-116">Datakällor som skapas efter att ha associerat en Dataverse-miljö med Customer Insights kommer att använda [Power Platform dataflöden](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span><span class="sxs-lookup"><span data-stu-id="f6210-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="f6210-117">Dataflöden stöder lokal anslutning med datagateways.</span><span class="sxs-lookup"><span data-stu-id="f6210-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="f6210-118">Ta bort och återskapa datakällor som fanns innan en Dataverse-miljö associerades för att använda lokal datagateways.</span><span class="sxs-lookup"><span data-stu-id="f6210-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="f6210-119">Datagateways från en befintlig Power BI eller Power Apps-miljö kommer att synas och du kan återanvända i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f6210-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="f6210-120">På sidan för datakällor visas länkar som går till den Power Platform-miljö där du kan visa och konfigurera lokal datagateways.</span><span class="sxs-lookup"><span data-stu-id="f6210-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Skärmbild på sidan med datakällor som visar länkar som pekar till Power Platform-miljön.":::

## <a name="review-ingested-data"></a><span data-ttu-id="f6210-122">Granska inmatade data</span><span class="sxs-lookup"><span data-stu-id="f6210-122">Review ingested data</span></span>

<span data-ttu-id="f6210-123">Du ser namnet på varje inmatad datakälla, dess status och sista gången data uppdaterades för källan.</span><span class="sxs-lookup"><span data-stu-id="f6210-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="f6210-124">Du kan sortera listan över datakällor efter varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="f6210-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6210-125">![Tillagd datakälla](media/configure-data-datasource-added.png "Tillagd datakälla")</span><span class="sxs-lookup"><span data-stu-id="f6210-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="f6210-126">Status</span><span class="sxs-lookup"><span data-stu-id="f6210-126">Status</span></span>  |<span data-ttu-id="f6210-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f6210-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f6210-128">Lyckades</span><span class="sxs-lookup"><span data-stu-id="f6210-128">Successful</span></span>   |<span data-ttu-id="f6210-129">Datakälla har matats in om en tidpunkt nämns i kolumnen **Uppdaterad**.</span><span class="sxs-lookup"><span data-stu-id="f6210-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="f6210-130">Inte startad</span><span class="sxs-lookup"><span data-stu-id="f6210-130">Not started</span></span>   |<span data-ttu-id="f6210-131">Datakällan har inga inmatade data än eller är fortfarande i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="f6210-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="f6210-132">Uppdaterar</span><span class="sxs-lookup"><span data-stu-id="f6210-132">Refreshing</span></span>    |<span data-ttu-id="f6210-133">Datainmatning pågår.</span><span class="sxs-lookup"><span data-stu-id="f6210-133">Data ingestion is in progress.</span></span> <span data-ttu-id="f6210-134">Du kan avbryta åtgärden genom att välja **Avbryt uppdatering** i kolumnen **åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="f6210-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="f6210-135">Om du stoppar uppdateringen av en datakälla återställs den till dess senaste uppdateringstillstånd.</span><span class="sxs-lookup"><span data-stu-id="f6210-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="f6210-136">Misslyckad</span><span class="sxs-lookup"><span data-stu-id="f6210-136">Failed</span></span>     |<span data-ttu-id="f6210-137">Datahämtning har stött på fel.</span><span class="sxs-lookup"><span data-stu-id="f6210-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="f6210-138">Välj värdet i kolumnen **Status** för en datakälla för att se mer information.</span><span class="sxs-lookup"><span data-stu-id="f6210-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="f6210-139">I rutan **Förloppsinformation** visar du **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="f6210-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="f6210-140">Välj **Se information** för mer information om uppdateringsstatusen, inklusive felinformation och uppdateringar om nedströmsprocesser.</span><span class="sxs-lookup"><span data-stu-id="f6210-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="f6210-141">Inläsning av data kan ta en stund.</span><span class="sxs-lookup"><span data-stu-id="f6210-141">Loading data can take some time.</span></span> <span data-ttu-id="f6210-142">Efter en lyckad uppdatering kan hämtade data granskas från sidan **entiteter**.</span><span class="sxs-lookup"><span data-stu-id="f6210-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="f6210-143">Mer information finns i [Entiteter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="f6210-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="f6210-144">Uppdatera en datakälla</span><span class="sxs-lookup"><span data-stu-id="f6210-144">Refresh a data source</span></span>

<span data-ttu-id="f6210-145">Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran.</span><span class="sxs-lookup"><span data-stu-id="f6210-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="f6210-146">Gå till **Admin** > **System** > [**Schema**](system.md#schedule-tab) för att konfigurera schemalagda uppdateringar av alla dina inmatade datakällor.</span><span class="sxs-lookup"><span data-stu-id="f6210-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="f6210-147">Uppdatera en datakälla på begäran så här:</span><span class="sxs-lookup"><span data-stu-id="f6210-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="f6210-148">I målgruppsinsikter går du till **Data** > **Datakällor**</span><span class="sxs-lookup"><span data-stu-id="f6210-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="f6210-149">Välj den lodräta ellipsen bredvid den datakälla som du vill uppdatera och välj **Uppdatera** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="f6210-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="f6210-150">Datakällan aktiveras nu för en manuell uppdatering.</span><span class="sxs-lookup"><span data-stu-id="f6210-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="f6210-151">Om du uppdaterar datakälla uppdateras både entitetsschemat och data för alla entiteter som anges i datakälla.</span><span class="sxs-lookup"><span data-stu-id="f6210-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="f6210-152">Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="f6210-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="f6210-153">Ta bort datakällan</span><span class="sxs-lookup"><span data-stu-id="f6210-153">Delete a data source</span></span>

1. <span data-ttu-id="f6210-154">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="f6210-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f6210-155">Markera den lodräta ellipsen bredvid datakällan du vill ta bort och välj **ta bort** i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="f6210-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="f6210-156">Bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="f6210-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
