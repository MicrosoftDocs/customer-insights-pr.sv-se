---
title: Mata in data via ett Power Query-anslutningsprogram
description: Anslutningar för datakällor baserade på Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407085"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="34948-103">Ansluta till en Power Query-datakälla</span><span class="sxs-lookup"><span data-stu-id="34948-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="34948-104">Power Query erbjuder ett stort antal kontakter för att samla in data.</span><span class="sxs-lookup"><span data-stu-id="34948-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="34948-105">De flesta av dessa anslutningar stöds av Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34948-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="34948-106">Att lägga till datakällor baserade på Power Query-anslutningar följer i allmänhet de steg som beskrivs i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="34948-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="34948-107">Beroende på vilken anslutning du använder krävs emellertid olika uppgifter.</span><span class="sxs-lookup"><span data-stu-id="34948-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="34948-108">Mer information finns i dokumentationen om enskilda anslutningar i [Power Query anslutningsreferens](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="34948-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="34948-109">Skapa en ny datakälla</span><span class="sxs-lookup"><span data-stu-id="34948-109">Create a new data source</span></span>

1. <span data-ttu-id="34948-110">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="34948-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="34948-111">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="34948-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="34948-112">Välj metoden **Importera data** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34948-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="34948-113">Ange ett **namn** på datakälla och välj **nästa** om du vill skapa datakälla.</span><span class="sxs-lookup"><span data-stu-id="34948-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="34948-114">Välj ett av [tillgängliga anslutningsprogram](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="34948-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="34948-115">I det här exemplet väljer du anslutningen **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="34948-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="34948-116">Ange obligatoriska uppgifter i **anslutningsinställningar** för den valda anslutningen och välj **Nästa** om du vill visa en förhandsgranskning av informationen.</span><span class="sxs-lookup"><span data-stu-id="34948-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="34948-117">Välj **Transformera data**.</span><span class="sxs-lookup"><span data-stu-id="34948-117">Select **Transform data**.</span></span> <span data-ttu-id="34948-118">I det här steget lägger du till entiteter i datakälla.</span><span class="sxs-lookup"><span data-stu-id="34948-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="34948-119">Entiteter är datauppsättningar.</span><span class="sxs-lookup"><span data-stu-id="34948-119">Entities are datasets.</span></span> <span data-ttu-id="34948-120">Om du har en databas som innehåller flera datauppsättningar är varje datauppsättning en egen entitet.</span><span class="sxs-lookup"><span data-stu-id="34948-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="34948-121">Dialogrutan **Power Query - redigera frågor** låter dig granska och förfina data.</span><span class="sxs-lookup"><span data-stu-id="34948-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="34948-122">De entiteter som identifieras i den valda datakälla visas i den vänstra rutan.</span><span class="sxs-lookup"><span data-stu-id="34948-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34948-123">![Dialogrutan Redigera frågor](media/data-manager-configure-edit-queries.png "Dialogrutan Redigera frågor")</span><span class="sxs-lookup"><span data-stu-id="34948-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="34948-124">Du kan även omvandla dina data.</span><span class="sxs-lookup"><span data-stu-id="34948-124">You can also transform your data.</span></span> <span data-ttu-id="34948-125">Välj en entitet att redigera eller omvandla.</span><span class="sxs-lookup"><span data-stu-id="34948-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="34948-126">Använd alternativen i fönstret Power Query för att tillämpa omvandlingar.</span><span class="sxs-lookup"><span data-stu-id="34948-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="34948-127">Varje omvandling visas under **tillämpade steg**.</span><span class="sxs-lookup"><span data-stu-id="34948-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="34948-128">Power Query innehåller flera fördefinierade omvandlingsalternativ.</span><span class="sxs-lookup"><span data-stu-id="34948-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="34948-129">Mer information finns i [Power Query omvandlingar](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="34948-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="34948-130">Du kan lägga till ytterligare entiteter till din datakälla genom att markera **Hämta data** i dialogrutan **Redigera frågor**.</span><span class="sxs-lookup"><span data-stu-id="34948-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="34948-131">Dessa omvandlingar rekommenderas högt:</span><span class="sxs-lookup"><span data-stu-id="34948-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="34948-132">Om du samlar in data från en CSV-fil innehåller den första raden ofta rubriker.</span><span class="sxs-lookup"><span data-stu-id="34948-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="34948-133">Gå till **Omvandla tabell** och välj **Använd rubriker som första rad**.</span><span class="sxs-lookup"><span data-stu-id="34948-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="34948-134">Kontrollera att datatypen har definierats korrekt.</span><span class="sxs-lookup"><span data-stu-id="34948-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="34948-135">Välj **Spara** längst ned av Power Query-fönstret för att spara omvandlingarna.</span><span class="sxs-lookup"><span data-stu-id="34948-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="34948-136">När du har sparat informationen hittar du datakälla på **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="34948-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="34948-137">På sidan **Datakällor** kommer du att lägga märke till att den nya datakälla är i status **uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="34948-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="34948-138">Tillgängliga Power Query datakällor</span><span class="sxs-lookup"><span data-stu-id="34948-138">Available Power Query data sources</span></span>

<span data-ttu-id="34948-139">Se [Power Query anslutningsreferens](https://docs.microsoft.com/power-query/connectors/) för en aktuell lista över anslutningar som du kan välja för att importera data till Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34948-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="34948-140">Anslutningar med en bockmarkering i kolumnen **Customer Insights (dataflöden)** är tillgängliga för att skapa nya datakällor utifrån Power Query.</span><span class="sxs-lookup"><span data-stu-id="34948-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="34948-141">Läs dokumentationen för en specifik kontakt om du vill ha mer information om dess krav, begränsningar och annan information.</span><span class="sxs-lookup"><span data-stu-id="34948-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="34948-142">Redigera Power Query datakällor</span><span class="sxs-lookup"><span data-stu-id="34948-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="34948-143">Det kanske inte går att göra ändringar i datakällor som för närvarande används i någon av appens processer (*segmentering*, *matchning* eller *koppling*).</span><span class="sxs-lookup"><span data-stu-id="34948-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="34948-144">På sidan **inställningar** kan du följa upp förloppet för varje aktiv process.</span><span class="sxs-lookup"><span data-stu-id="34948-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="34948-145">När en process har slutförts kan du gå tillbaka till sidan **datakällor** och göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="34948-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="34948-146">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="34948-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="34948-147">Markera den lodräta ellipsen bredvid datakällan du vill ändra och välj **redigera** i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="34948-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34948-148">![Redigera alternativ](media/edit-option-data-sources.png "Redigera alternativ")</span><span class="sxs-lookup"><span data-stu-id="34948-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="34948-149">Tillämpa ändringarna och omvandlingarna i dialogrutan **Power Query - redigera frågor** som beskrivs i avsnittet [Skapa en ny datakälla](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="34948-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="34948-150">Välj **Spara** i Power Query när du har slutfört redigeringarna och vill spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="34948-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
