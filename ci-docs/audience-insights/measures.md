---
title: Skapa och hantera mått
description: Definiera mått som ska analyseras och reflektera företagets resultat.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654754"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="fd408-103">Definiera och hantera mått</span><span class="sxs-lookup"><span data-stu-id="fd408-103">Define and manage measures</span></span>

<span data-ttu-id="fd408-104">Med hjälp av mått kan du få en bättre förståelse för kundbeteenden och affärsresultat genom att hämta relevanta värden från [enhetliga profiler](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fd408-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="fd408-105">Ett företag vill till exempel se den *totala kostnaden per kund* för att förstå enskilda kunders köphistorik.</span><span class="sxs-lookup"><span data-stu-id="fd408-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="fd408-106">Eller mäta *total försäljning för företaget* för att förstå den aggregerade nivån av intäkt i hela verksamheten.</span><span class="sxs-lookup"><span data-stu-id="fd408-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="fd408-107">Mått skapas med måttverktyget, en datafrågeställningsplattform med olika operatörer och enkla mappningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="fd408-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="fd408-108">Du kan filtrera data, gruppera resultat, identifiera [entitetsrelationssökvägar](relationships.md) och förhandsgranska utdata.</span><span class="sxs-lookup"><span data-stu-id="fd408-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="fd408-109">Använd måttverktyget om du vill planera affärsaktiviteter genom att fråga efter kunddata och extrahera insikter.</span><span class="sxs-lookup"><span data-stu-id="fd408-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="fd408-110">Om du till exempel skapar ett mått på *totalsumma per kund* och *total intäkt per kund* kan du identifiera en grupp av kunder som spenderar mycket men ger höga intäkter.</span><span class="sxs-lookup"><span data-stu-id="fd408-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="fd408-111">Du kan [skapa ett segment](segments.md) för att driva på nästa bästa åtgärd.</span><span class="sxs-lookup"><span data-stu-id="fd408-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="fd408-112">Skapa ett mått</span><span class="sxs-lookup"><span data-stu-id="fd408-112">Create a measure</span></span>

<span data-ttu-id="fd408-113">Det här avsnittet innehåller information om hur du skapar ett nytt mått från grunden.</span><span class="sxs-lookup"><span data-stu-id="fd408-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="fd408-114">Du kan skapa ett mått med dataattribut från dataentiteter som har en relation som är konfigurerad för att ansluta till entiteten Kund.</span><span class="sxs-lookup"><span data-stu-id="fd408-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="fd408-115">I målgruppsinsikter går du till **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="fd408-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="fd408-116">Välj **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="fd408-116">Select **New**.</span></span>

1. <span data-ttu-id="fd408-117">Välj **Redigera namn** och tillhandahåll ett **namn** för måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="fd408-118">Om den nya måttkonfigurationen endast har två fält, till exempel Kund-ID och en beräkning, läggs utdatan till som en ny kolumn i den systemgenererade entiteten Kundmått.</span><span class="sxs-lookup"><span data-stu-id="fd408-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="fd408-119">Dessutom kan du se måttens värde i den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="fd408-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="fd408-120">Andra mått genererar egna entiteter.</span><span class="sxs-lookup"><span data-stu-id="fd408-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="fd408-121">I konfigurationsområdet väljer du sammansättningsfunktionen från listrutan **Välj funktion**.</span><span class="sxs-lookup"><span data-stu-id="fd408-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="fd408-122">Sammansättningsfunktioner omfattar:</span><span class="sxs-lookup"><span data-stu-id="fd408-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="fd408-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="fd408-123">**Sum**</span></span>
   - <span data-ttu-id="fd408-124">**Medel**</span><span class="sxs-lookup"><span data-stu-id="fd408-124">**Average**</span></span>
   - <span data-ttu-id="fd408-125">**Antal**</span><span class="sxs-lookup"><span data-stu-id="fd408-125">**Count**</span></span>
   - <span data-ttu-id="fd408-126">**Antal unika**</span><span class="sxs-lookup"><span data-stu-id="fd408-126">**Count Unique**</span></span>
   - <span data-ttu-id="fd408-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="fd408-127">**Max**</span></span>
   - <span data-ttu-id="fd408-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="fd408-128">**Min**</span></span>
   - <span data-ttu-id="fd408-129">**Först**: tar det första värdet i dataposten</span><span class="sxs-lookup"><span data-stu-id="fd408-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="fd408-130">**Sist:** tar det sista värdet som lades till i dataposten</span><span class="sxs-lookup"><span data-stu-id="fd408-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatörer för måttberäkningar.":::

1. <span data-ttu-id="fd408-132">Välj **Lägg till attribut** för att välja de data du behöver för att skapa måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="fd408-133">Välj fliken **Attribut**.</span><span class="sxs-lookup"><span data-stu-id="fd408-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="fd408-134">Dataentitet: Välj den entitet som innehåller attributet du vill mäta.</span><span class="sxs-lookup"><span data-stu-id="fd408-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="fd408-135">Dataattribut: Välj det attribut som du vill använda i sammansättningsfunktionen för att beräkna måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="fd408-136">Du kan bara välja ett attribut åt gången.</span><span class="sxs-lookup"><span data-stu-id="fd408-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="fd408-137">Du kan också välja ett dataattribut från ett befintligt mått genom att välja fliken **Mått**. Du kan också söka efter ett entitets- eller måttnamn.</span><span class="sxs-lookup"><span data-stu-id="fd408-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="fd408-138">Välj **Lägg till** för att lägga till det valda attributet till måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Välj ett attribut som ska användas i beräkningarna.":::

1. <span data-ttu-id="fd408-140">Om du vill skapa mer komplexa mått kan du lägga till fler attribut eller använda olika operatörer i måttfunktionen.</span><span class="sxs-lookup"><span data-stu-id="fd408-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Skapa ett komplext mått med matematikoperatörer.":::

1. <span data-ttu-id="fd408-142">Om du vill lägga till filter väljer du **Filter** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="fd408-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="fd408-143">I avsnittet **Lägg till attribut** i rutan **Filter** väljer du det attribut som du vill använda för att skapa filter.</span><span class="sxs-lookup"><span data-stu-id="fd408-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="fd408-144">Ange filteroperatörerna så att filtret definieras för varje markerat attribut.</span><span class="sxs-lookup"><span data-stu-id="fd408-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="fd408-145">Välj **Tillämpa** för att lägga till filtren till måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="fd408-146">Om du vill lägga till dimensioner väljer du **Dimension** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="fd408-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="fd408-147">Dimensioner visas som kolumner i måttutdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="fd408-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="fd408-148">Välj **Redigera dimensioner** för att lägga till dataattribut som du vill gruppera måttvärdena efter.</span><span class="sxs-lookup"><span data-stu-id="fd408-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="fd408-149">Till exempel ort eller kön.</span><span class="sxs-lookup"><span data-stu-id="fd408-149">For example, city or gender.</span></span> <span data-ttu-id="fd408-150">Som standard väljs dimensionen *Kund-ID* för att skapa *mått på kundnivå*.</span><span class="sxs-lookup"><span data-stu-id="fd408-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="fd408-151">Du kan ta bort standarddimensionen om du vill skapa *mått på företagsnivå*.</span><span class="sxs-lookup"><span data-stu-id="fd408-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="fd408-152">Välj **Klart** för att lägga till dimensionerna till måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="fd408-153">Om det finns flera sökvägar mellan den dataentitet du mappade och entiteten *Kund* måste du välja någon av de identifierade [entitetsrelationssökvägarna](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="fd408-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="fd408-154">Resultaten av måtten kan variera beroende på den valda sökvägen.</span><span class="sxs-lookup"><span data-stu-id="fd408-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="fd408-155">Välj **Datainställningar** och välj den entitetssökväg som ska användas för att identifiera måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="fd408-156">Om det bara finns en enskild sökväg till entiteten *Kund* visas inte den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="fd408-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="fd408-157">Välj **Klart** för att tillämpa dina val.</span><span class="sxs-lookup"><span data-stu-id="fd408-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Välj entitetssökvägen för måttet.":::

1. <span data-ttu-id="fd408-159">Om du vill lägga till fler beräkningar för måttet väljer du **Ny beräkning**.</span><span class="sxs-lookup"><span data-stu-id="fd408-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="fd408-160">Du kan endast använda entiteter på samma entitetssökväg för nya beräkningar.</span><span class="sxs-lookup"><span data-stu-id="fd408-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="fd408-161">Fler beräkningar visas som nya kolumner i måttutdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="fd408-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="fd408-162">Välj **...** i beräkningen för att **duplicera**, **byta namn på** eller **ta bort** en beräkning från ett mått.</span><span class="sxs-lookup"><span data-stu-id="fd408-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="fd408-163">I området **Förhandsgranskning** ser du dataschemat för måttutdataentiteten, inklusive filter och dimensioner.</span><span class="sxs-lookup"><span data-stu-id="fd408-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="fd408-164">Förhandsgranskningen reagerar dynamiskt på ändringar i konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="fd408-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="fd408-165">Välj **Kör** för att beräkna resultaten för det konfigurerade måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="fd408-166">Välj **Spara och stäng** om du vill behålla den aktuella konfigurationen och köra måttet senare.</span><span class="sxs-lookup"><span data-stu-id="fd408-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="fd408-167">Gå till **Mått** för att se det nyskapade måttet i listan.</span><span class="sxs-lookup"><span data-stu-id="fd408-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="fd408-168">Hantera dina mått</span><span class="sxs-lookup"><span data-stu-id="fd408-168">Manage your measures</span></span>

<span data-ttu-id="fd408-169">När du har [skapat ett mått](#create-a-measure) visas en lista med mått på sidan **Mått**.</span><span class="sxs-lookup"><span data-stu-id="fd408-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="fd408-170">Här finns information om måttypen, den som skapade den, datumet då den skapades, statusen och tillståndet.</span><span class="sxs-lookup"><span data-stu-id="fd408-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="fd408-171">När du väljer ett mått i listan kan du förhandsgranska utdata och hämta en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="fd408-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="fd408-172">Om du vill uppdatera alla dina åtgärder samtidigt markerar du **Uppdatera allt** utan att välja ett specifikt mått.</span><span class="sxs-lookup"><span data-stu-id="fd408-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fd408-173">![Åtgärder för att hantera enskilda mått](media/measure-actions.png "Åtgärder för att hantera enskilda mått")</span><span class="sxs-lookup"><span data-stu-id="fd408-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="fd408-174">Välj ett mått i listan för följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="fd408-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="fd408-175">Markera måttets namn om du vill se detaljerna.</span><span class="sxs-lookup"><span data-stu-id="fd408-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="fd408-176">**Redigera** måttets konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fd408-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="fd408-177">**Uppdatera** måttet baserat på senaste data.</span><span class="sxs-lookup"><span data-stu-id="fd408-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="fd408-178">**Byt namn** på mått.</span><span class="sxs-lookup"><span data-stu-id="fd408-178">**Rename** the measure.</span></span>
- <span data-ttu-id="fd408-179">**Ta bort** måttet.</span><span class="sxs-lookup"><span data-stu-id="fd408-179">**Delete** the measure.</span></span>
- <span data-ttu-id="fd408-180">**Aktivera** eller **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="fd408-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="fd408-181">Inaktiva mått uppdateras inte vid en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fd408-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="fd408-182">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="fd408-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fd408-183">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fd408-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fd408-184">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="fd408-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fd408-185">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="fd408-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="fd408-186">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fd408-186">Next step</span></span>

<span data-ttu-id="fd408-187">Du kan använda befintliga mått för att skapa [ett kundsegment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fd408-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]