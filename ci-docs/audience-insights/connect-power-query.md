---
title: Mata in data via ett Power Query-anslutningsprogram
description: Anslutningar för datakällor baserade på Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596935"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="b93eb-103">Ansluta till en Power Query-datakälla</span><span class="sxs-lookup"><span data-stu-id="b93eb-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="b93eb-104">Power Query erbjuder ett stort antal kontakter för att samla in data.</span><span class="sxs-lookup"><span data-stu-id="b93eb-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="b93eb-105">De flesta av dessa anslutningar stöds av Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b93eb-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="b93eb-106">Att lägga till datakällor baserade på Power Query-anslutningar följer i allmänhet de steg som beskrivs i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b93eb-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="b93eb-107">Beroende på vilken anslutning du använder krävs emellertid olika uppgifter.</span><span class="sxs-lookup"><span data-stu-id="b93eb-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="b93eb-108">Mer information finns i dokumentationen om enskilda anslutningar i [Power Query anslutningsreferens](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="b93eb-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="b93eb-109">Skapa en ny datakälla</span><span class="sxs-lookup"><span data-stu-id="b93eb-109">Create a new data source</span></span>

1. <span data-ttu-id="b93eb-110">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="b93eb-111">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="b93eb-112">Välj metoden **Importera data** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="b93eb-113">Ange ett **namn** på datakälla och välj **nästa** om du vill skapa datakälla.</span><span class="sxs-lookup"><span data-stu-id="b93eb-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="b93eb-114">Namnge riktlinjer:</span><span class="sxs-lookup"><span data-stu-id="b93eb-114">Name guidelines:</span></span> 
   - <span data-ttu-id="b93eb-115">Inled med en bokstav.</span><span class="sxs-lookup"><span data-stu-id="b93eb-115">Start with a letter.</span></span>
   - <span data-ttu-id="b93eb-116">Använd endast bokstäver och siffror.</span><span class="sxs-lookup"><span data-stu-id="b93eb-116">Use letters and numbers only.</span></span> <span data-ttu-id="b93eb-117">Specialtecken och blanksteg är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="b93eb-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="b93eb-118">Använd mellan 3 och 64 tecken.</span><span class="sxs-lookup"><span data-stu-id="b93eb-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="b93eb-119">Välj ett av [tillgängliga anslutningsprogram](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="b93eb-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="b93eb-120">I det här exemplet väljer du anslutningen **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b93eb-121">Ange obligatoriska uppgifter i **anslutningsinställningar** för den valda anslutningen och välj **Nästa** om du vill visa en förhandsgranskning av informationen.</span><span class="sxs-lookup"><span data-stu-id="b93eb-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="b93eb-122">Välj **Transformera data**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-122">Select **Transform data**.</span></span> <span data-ttu-id="b93eb-123">I det här steget lägger du till entiteter i datakälla.</span><span class="sxs-lookup"><span data-stu-id="b93eb-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="b93eb-124">Entiteter är datauppsättningar.</span><span class="sxs-lookup"><span data-stu-id="b93eb-124">Entities are datasets.</span></span> <span data-ttu-id="b93eb-125">Om du har en databas som innehåller flera datauppsättningar är varje datauppsättning en egen entitet.</span><span class="sxs-lookup"><span data-stu-id="b93eb-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="b93eb-126">Dialogrutan **Power Query - redigera frågor** låter dig granska och förfina data.</span><span class="sxs-lookup"><span data-stu-id="b93eb-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="b93eb-127">De entiteter som identifieras i den valda datakälla visas i den vänstra rutan.</span><span class="sxs-lookup"><span data-stu-id="b93eb-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b93eb-128">![Dialogrutan Redigera frågor](media/data-manager-configure-edit-queries.png "Dialogrutan Redigera frågor")</span><span class="sxs-lookup"><span data-stu-id="b93eb-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="b93eb-129">Du kan även omvandla dina data.</span><span class="sxs-lookup"><span data-stu-id="b93eb-129">You can also transform your data.</span></span> <span data-ttu-id="b93eb-130">Välj en entitet att redigera eller omvandla.</span><span class="sxs-lookup"><span data-stu-id="b93eb-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="b93eb-131">Använd alternativen i fönstret Power Query för att tillämpa omvandlingar.</span><span class="sxs-lookup"><span data-stu-id="b93eb-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="b93eb-132">Varje omvandling visas under **tillämpade steg**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="b93eb-133">Power Query innehåller flera fördefinierade omvandlingsalternativ.</span><span class="sxs-lookup"><span data-stu-id="b93eb-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="b93eb-134">Mer information finns i [Power Query omvandlingar](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="b93eb-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="b93eb-135">Du kan lägga till ytterligare entiteter till din datakälla genom att markera **Hämta data** i dialogrutan **Redigera frågor**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="b93eb-136">Dessa omvandlingar rekommenderas högt:</span><span class="sxs-lookup"><span data-stu-id="b93eb-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="b93eb-137">Om du samlar in data från en CSV-fil innehåller den första raden ofta rubriker.</span><span class="sxs-lookup"><span data-stu-id="b93eb-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="b93eb-138">Gå till **Omvandla tabell** och välj **Använd rubriker som första rad**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="b93eb-139">Kontrollera att datatypen har definierats korrekt.</span><span class="sxs-lookup"><span data-stu-id="b93eb-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="b93eb-140">Välj **Spara** längst ned av Power Query-fönstret för att spara omvandlingarna.</span><span class="sxs-lookup"><span data-stu-id="b93eb-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="b93eb-141">När du har sparat informationen hittar du datakälla på **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="b93eb-142">På sidan **Datakällor** kommer du att lägga märke till att den nya datakälla är i status **uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="b93eb-143">Tillgängliga Power Query datakällor</span><span class="sxs-lookup"><span data-stu-id="b93eb-143">Available Power Query data sources</span></span>

<span data-ttu-id="b93eb-144">Se [Power Query anslutningsreferens](/power-query/connectors/) för en aktuell lista över anslutningar som du kan välja för att importera data till Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b93eb-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="b93eb-145">Anslutningar med en bockmarkering i kolumnen **Customer Insights (dataflöden)** är tillgängliga för att skapa nya datakällor utifrån Power Query.</span><span class="sxs-lookup"><span data-stu-id="b93eb-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="b93eb-146">Läs dokumentationen för en specifik kontakt om du vill ha mer information om dess krav, begränsningar och annan information.</span><span class="sxs-lookup"><span data-stu-id="b93eb-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="b93eb-147">Redigera Power Query datakällor</span><span class="sxs-lookup"><span data-stu-id="b93eb-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="b93eb-148">Det kanske inte går att göra ändringar i datakällor som för närvarande används i någon av appens processer (*segmentering*, *matchning* eller *koppling*).</span><span class="sxs-lookup"><span data-stu-id="b93eb-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="b93eb-149">På sidan **inställningar** kan du följa upp förloppet för varje aktiv process.</span><span class="sxs-lookup"><span data-stu-id="b93eb-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="b93eb-150">När en process har slutförts kan du gå tillbaka till sidan **datakällor** och göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="b93eb-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="b93eb-151">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="b93eb-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b93eb-152">Markera den lodräta ellipsen bredvid datakällan du vill ändra och välj **redigera** i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="b93eb-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b93eb-153">![Redigera alternativ](media/edit-option-data-sources.png "Redigera alternativ")</span><span class="sxs-lookup"><span data-stu-id="b93eb-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="b93eb-154">Tillämpa ändringarna och omvandlingarna i dialogrutan **Power Query - redigera frågor** som beskrivs i avsnittet [Skapa en ny datakälla](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="b93eb-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="b93eb-155">Välj **Spara** i Power Query när du har slutfört redigeringarna och vill spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b93eb-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]