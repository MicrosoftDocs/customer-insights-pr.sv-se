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
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304718"
---
# <a name="data-sources-overview"></a><span data-ttu-id="d35f4-103">Översikt över datakällor</span><span class="sxs-lookup"><span data-stu-id="d35f4-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d35f4-104">Kapaciteten för målgruppsinsikter i Dynamics 365 Customer Insights ansluter till data från en bred uppsättning källor.</span><span class="sxs-lookup"><span data-stu-id="d35f4-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="d35f4-105">Anslutning till en datakälla kallas ofta för *datainmatning*.</span><span class="sxs-lookup"><span data-stu-id="d35f4-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="d35f4-106">När du har inmatat dina data kan du [ena](data-unification.md) och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d35f4-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="d35f4-107">Lägg till en datakälla</span><span class="sxs-lookup"><span data-stu-id="d35f4-107">Add a data source</span></span>

<span data-ttu-id="d35f4-108">Se de detaljerade artiklarna om hur du lägger till en datakälla beroende på vilket alternativ du väljer.</span><span class="sxs-lookup"><span data-stu-id="d35f4-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="d35f4-109">Du kan lägga till en datakälla på tre huvudsakliga sätt:</span><span class="sxs-lookup"><span data-stu-id="d35f4-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="d35f4-110">Efter dussintals Power Query-anslutningar</span><span class="sxs-lookup"><span data-stu-id="d35f4-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="d35f4-111">Från en Common Data Model-mapp</span><span class="sxs-lookup"><span data-stu-id="d35f4-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="d35f4-112">Från din egen Microsoft Dataverse sjö</span><span class="sxs-lookup"><span data-stu-id="d35f4-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="d35f4-113">Lägga till data lokala datakällor</span><span class="sxs-lookup"><span data-stu-id="d35f4-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="d35f4-114">Inmatning av data från lokala datakällor i målgruppinsikter stöds baserat på Microsoft Power Platform-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="d35f4-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="d35f4-115">Dataflöden kan aktiveras i Customer Insights av [ange Microsoft Dataverse miljö-URL](manage-environments.md#create-an-environment-in-an-existing-organization) när du ställer in miljön.</span><span class="sxs-lookup"><span data-stu-id="d35f4-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="d35f4-116">Datakällor som skapas efter att ha associerat en Dataverse-miljö med Customer Insights kommer att använda [Power Platform dataflöden](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span><span class="sxs-lookup"><span data-stu-id="d35f4-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="d35f4-117">Dataflöden stöder lokal anslutning med datagateway.</span><span class="sxs-lookup"><span data-stu-id="d35f4-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="d35f4-118">Ta bort och återskapa datakällor som fanns innan en Dataverse-miljö associerades för att [använda lokal datagateways](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="d35f4-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="d35f4-119">Datagateways från en befintlig Power BI eller Power Apps-miljö kommer att synas och du kan återanvända i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d35f4-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="d35f4-120">På sidan för datakällor visas länkar som går till den Microsoft Power Platform-miljö där du kan visa och konfigurera lokal data-gateways.</span><span class="sxs-lookup"><span data-stu-id="d35f4-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="d35f4-121">Granska inmatade data</span><span class="sxs-lookup"><span data-stu-id="d35f4-121">Review ingested data</span></span>

<span data-ttu-id="d35f4-122">Du ser namnet på varje inmatad datakälla, dess status och sista gången data uppdaterades för källan.</span><span class="sxs-lookup"><span data-stu-id="d35f4-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="d35f4-123">Du kan sortera listan över datakällor efter varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="d35f4-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d35f4-124">![Tillagd datakälla](media/configure-data-datasource-added.png "Tillagd datakälla")</span><span class="sxs-lookup"><span data-stu-id="d35f4-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="d35f4-125">Status</span><span class="sxs-lookup"><span data-stu-id="d35f4-125">Status</span></span>  |<span data-ttu-id="d35f4-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d35f4-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d35f4-127">Lyckades</span><span class="sxs-lookup"><span data-stu-id="d35f4-127">Successful</span></span>   |<span data-ttu-id="d35f4-128">Datakälla har matats in om en tidpunkt nämns i kolumnen **Uppdaterad**.</span><span class="sxs-lookup"><span data-stu-id="d35f4-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="d35f4-129">Inte startad</span><span class="sxs-lookup"><span data-stu-id="d35f4-129">Not started</span></span>   |<span data-ttu-id="d35f4-130">Datakällan har inga inmatade data än eller är fortfarande i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="d35f4-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="d35f4-131">Uppdaterar</span><span class="sxs-lookup"><span data-stu-id="d35f4-131">Refreshing</span></span>    |<span data-ttu-id="d35f4-132">Datainmatning pågår.</span><span class="sxs-lookup"><span data-stu-id="d35f4-132">Data ingestion is in progress.</span></span> <span data-ttu-id="d35f4-133">Du kan avbryta åtgärden genom att välja **Avbryt uppdatering** i kolumnen **åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="d35f4-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="d35f4-134">Om du stoppar uppdateringen av en datakälla återställs den till dess senaste uppdateringstillstånd.</span><span class="sxs-lookup"><span data-stu-id="d35f4-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="d35f4-135">Misslyckad</span><span class="sxs-lookup"><span data-stu-id="d35f4-135">Failed</span></span>     |<span data-ttu-id="d35f4-136">Datahämtning har stött på fel.</span><span class="sxs-lookup"><span data-stu-id="d35f4-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="d35f4-137">Välj värdet i kolumnen **Status** för en datakälla för att se mer information.</span><span class="sxs-lookup"><span data-stu-id="d35f4-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="d35f4-138">I rutan **Förloppsinformation** visar du **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="d35f4-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="d35f4-139">Välj **Se information** för mer information om uppdateringsstatusen, inklusive felinformation och uppdateringar om nedströmsprocesser.</span><span class="sxs-lookup"><span data-stu-id="d35f4-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="d35f4-140">Det kan ta lång tid att läsa in data.</span><span class="sxs-lookup"><span data-stu-id="d35f4-140">Loading data can take time.</span></span> <span data-ttu-id="d35f4-141">Efter en lyckad uppdatering kan hämtade data granskas från sidan **entiteter**.</span><span class="sxs-lookup"><span data-stu-id="d35f4-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="d35f4-142">Mer information finns i [Entiteter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="d35f4-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="d35f4-143">Uppdatera en datakälla</span><span class="sxs-lookup"><span data-stu-id="d35f4-143">Refresh a data source</span></span>

<span data-ttu-id="d35f4-144">Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran.</span><span class="sxs-lookup"><span data-stu-id="d35f4-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="d35f4-145">Gå till **Admin** > **System** > [**Schema**](system.md#schedule-tab) för att konfigurera schemalagda uppdateringar av alla dina inmatade datakällor.</span><span class="sxs-lookup"><span data-stu-id="d35f4-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="d35f4-146">Uppdatera en datakälla på begäran så här:</span><span class="sxs-lookup"><span data-stu-id="d35f4-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="d35f4-147">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="d35f4-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d35f4-148">Välj den stående ellipsen bredvid den datakälla du vill uppdatera och välj sedan **Uppdatera** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="d35f4-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="d35f4-149">Datakällan aktiveras nu för en manuell uppdatering.</span><span class="sxs-lookup"><span data-stu-id="d35f4-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="d35f4-150">Om du uppdaterar datakälla uppdateras både entitetsschemat och data för alla entiteter som anges i datakälla.</span><span class="sxs-lookup"><span data-stu-id="d35f4-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="d35f4-151">Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="d35f4-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="d35f4-152">Ta bort datakällan</span><span class="sxs-lookup"><span data-stu-id="d35f4-152">Delete a data source</span></span>

1. <span data-ttu-id="d35f4-153">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="d35f4-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d35f4-154">Välj den stående ellipsen bredvid den datakälla du vill ta bort och välj sedan **Ta bort** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="d35f4-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="d35f4-155">Bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="d35f4-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
