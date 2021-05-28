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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085552"
---
# <a name="data-sources-overview"></a><span data-ttu-id="299cb-103">Översikt över datakällor</span><span class="sxs-lookup"><span data-stu-id="299cb-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="299cb-104">Kapaciteten för målgruppsinsikter i Dynamics 365 Customer Insights ansluter till data från en bred uppsättning källor.</span><span class="sxs-lookup"><span data-stu-id="299cb-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="299cb-105">Anslutning till en datakälla kallas ofta för *datainmatning*.</span><span class="sxs-lookup"><span data-stu-id="299cb-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="299cb-106">När du har inmatat dina data kan du [ena](data-unification.md) och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="299cb-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="299cb-107">Lägg till en datakälla</span><span class="sxs-lookup"><span data-stu-id="299cb-107">Add a data source</span></span>

<span data-ttu-id="299cb-108">Se de detaljerade artiklarna om hur du lägger till en datakälla beroende på vilket alternativ du väljer.</span><span class="sxs-lookup"><span data-stu-id="299cb-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="299cb-109">Du kan lägga till en datakälla på tre huvudsakliga sätt:</span><span class="sxs-lookup"><span data-stu-id="299cb-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="299cb-110">Efter dussintals Power Query-anslutningar</span><span class="sxs-lookup"><span data-stu-id="299cb-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="299cb-111">Från en Common Data Model-mapp</span><span class="sxs-lookup"><span data-stu-id="299cb-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="299cb-112">Från din egen Common Data Service sjö</span><span class="sxs-lookup"><span data-stu-id="299cb-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="299cb-113">Lägga till data lokala datakällor</span><span class="sxs-lookup"><span data-stu-id="299cb-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="299cb-114">Det finns stöd för lokala datakällor i målgruppinsikter bygger på Power Platform-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="299cb-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="299cb-115">Dataflöden kan aktiveras i Customer Insights av [ange Microsoft Dataverse miljö-URL](manage-environments.md#create-an-environment-in-an-existing-organization) när du ställer in miljön.</span><span class="sxs-lookup"><span data-stu-id="299cb-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="299cb-116">Datakällor som skapas efter att ha associerat en Dataverse-miljö med Customer Insights kommer att använda [Power Platform dataflöden](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span><span class="sxs-lookup"><span data-stu-id="299cb-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="299cb-117">Dataflöden stöder lokal anslutning med datagateway.</span><span class="sxs-lookup"><span data-stu-id="299cb-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="299cb-118">Ta bort och återskapa datakällor som fanns innan en Dataverse-miljö associerades för att [använda lokal datagateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="299cb-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="299cb-119">Datagateways från en befintlig Power BI eller Power Apps-miljö kommer att synas och du kan återanvända i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="299cb-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="299cb-120">På sidan för datakällor visas länkar som går till den Power Platform-miljö där du kan visa och konfigurera lokal datagateways.</span><span class="sxs-lookup"><span data-stu-id="299cb-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="299cb-121">Granska inmatade data</span><span class="sxs-lookup"><span data-stu-id="299cb-121">Review ingested data</span></span>

<span data-ttu-id="299cb-122">Du ser namnet på varje inmatad datakälla, dess status och sista gången data uppdaterades för källan.</span><span class="sxs-lookup"><span data-stu-id="299cb-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="299cb-123">Du kan sortera listan över datakällor efter varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="299cb-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="299cb-124">![Tillagd datakälla](media/configure-data-datasource-added.png "Tillagd datakälla")</span><span class="sxs-lookup"><span data-stu-id="299cb-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="299cb-125">Status</span><span class="sxs-lookup"><span data-stu-id="299cb-125">Status</span></span>  |<span data-ttu-id="299cb-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="299cb-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="299cb-127">Lyckades</span><span class="sxs-lookup"><span data-stu-id="299cb-127">Successful</span></span>   |<span data-ttu-id="299cb-128">Datakälla har matats in om en tidpunkt nämns i kolumnen **Uppdaterad**.</span><span class="sxs-lookup"><span data-stu-id="299cb-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="299cb-129">Inte startad</span><span class="sxs-lookup"><span data-stu-id="299cb-129">Not started</span></span>   |<span data-ttu-id="299cb-130">Datakällan har inga inmatade data än eller är fortfarande i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="299cb-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="299cb-131">Uppdaterar</span><span class="sxs-lookup"><span data-stu-id="299cb-131">Refreshing</span></span>    |<span data-ttu-id="299cb-132">Datainmatning pågår.</span><span class="sxs-lookup"><span data-stu-id="299cb-132">Data ingestion is in progress.</span></span> <span data-ttu-id="299cb-133">Du kan avbryta åtgärden genom att välja **Avbryt uppdatering** i kolumnen **åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="299cb-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="299cb-134">Om du stoppar uppdateringen av en datakälla återställs den till dess senaste uppdateringstillstånd.</span><span class="sxs-lookup"><span data-stu-id="299cb-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="299cb-135">Misslyckad</span><span class="sxs-lookup"><span data-stu-id="299cb-135">Failed</span></span>     |<span data-ttu-id="299cb-136">Datahämtning har stött på fel.</span><span class="sxs-lookup"><span data-stu-id="299cb-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="299cb-137">Välj värdet i kolumnen **Status** för en datakälla för att se mer information.</span><span class="sxs-lookup"><span data-stu-id="299cb-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="299cb-138">I rutan **Förloppsinformation** visar du **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="299cb-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="299cb-139">Välj **Se information** för mer information om uppdateringsstatusen, inklusive felinformation och uppdateringar om nedströmsprocesser.</span><span class="sxs-lookup"><span data-stu-id="299cb-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="299cb-140">Inläsning av data kan ta en stund.</span><span class="sxs-lookup"><span data-stu-id="299cb-140">Loading data can take some time.</span></span> <span data-ttu-id="299cb-141">Efter en lyckad uppdatering kan hämtade data granskas från sidan **entiteter**.</span><span class="sxs-lookup"><span data-stu-id="299cb-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="299cb-142">Mer information finns i [Entiteter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="299cb-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="299cb-143">Uppdatera en datakälla</span><span class="sxs-lookup"><span data-stu-id="299cb-143">Refresh a data source</span></span>

<span data-ttu-id="299cb-144">Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran.</span><span class="sxs-lookup"><span data-stu-id="299cb-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="299cb-145">Gå till **Admin** > **System** > [**Schema**](system.md#schedule-tab) för att konfigurera schemalagda uppdateringar av alla dina inmatade datakällor.</span><span class="sxs-lookup"><span data-stu-id="299cb-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="299cb-146">Uppdatera en datakälla på begäran så här:</span><span class="sxs-lookup"><span data-stu-id="299cb-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="299cb-147">I målgruppsinsikter går du till **Data** > **Datakällor**</span><span class="sxs-lookup"><span data-stu-id="299cb-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="299cb-148">Välj den lodräta ellipsen bredvid den datakälla som du vill uppdatera och välj **Uppdatera** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="299cb-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="299cb-149">Datakällan aktiveras nu för en manuell uppdatering.</span><span class="sxs-lookup"><span data-stu-id="299cb-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="299cb-150">Om du uppdaterar datakälla uppdateras både entitetsschemat och data för alla entiteter som anges i datakälla.</span><span class="sxs-lookup"><span data-stu-id="299cb-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="299cb-151">Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="299cb-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="299cb-152">Ta bort datakällan</span><span class="sxs-lookup"><span data-stu-id="299cb-152">Delete a data source</span></span>

1. <span data-ttu-id="299cb-153">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="299cb-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="299cb-154">Markera den lodräta ellipsen bredvid datakällan du vill ta bort och välj **ta bort** i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="299cb-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="299cb-155">Bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="299cb-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
