---
title: Skapa och hantera mått
description: Definiera mått som ska analyseras och reflektera företagets resultat.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304829"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="cff76-103">Definiera och hantera mått</span><span class="sxs-lookup"><span data-stu-id="cff76-103">Define and manage measures</span></span>

<span data-ttu-id="cff76-104">Åtgärder hjälper dig att få en bättre förståelse av kundbeteenden och affärsresultat.</span><span class="sxs-lookup"><span data-stu-id="cff76-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="cff76-105">De tittar på relevanta värden från [enhetliga profiler](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="cff76-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="cff76-106">Ett företag vill till exempel se den *totala kostnaden per kund* för att förstå en enskild kunds köphistorik eller mäta företagets *totala försäljning* för att förstå den sammanlagda omsättningen för hela verksamheten.</span><span class="sxs-lookup"><span data-stu-id="cff76-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="cff76-107">Mått skapas med måttverktyget, en datafrågeställningsplattform med olika operatörer och enkla mappningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="cff76-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="cff76-108">Du kan filtrera data, gruppera resultat, identifiera [entitetsrelationssökvägar](relationships.md) och förhandsgranska utdata.</span><span class="sxs-lookup"><span data-stu-id="cff76-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="cff76-109">Använd måttverktyget om du vill planera affärsaktiviteter genom att fråga efter kunddata och extrahera insikter.</span><span class="sxs-lookup"><span data-stu-id="cff76-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="cff76-110">Om du till exempel skapar ett mått på *totalsumma per kund* och *total intäkt per kund* kan du identifiera en grupp av kunder som spenderar mycket men ger höga intäkter.</span><span class="sxs-lookup"><span data-stu-id="cff76-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="cff76-111">Du kan [skapa ett segment](segments.md) för att driva på nästa bästa åtgärd.</span><span class="sxs-lookup"><span data-stu-id="cff76-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="cff76-112">Bygg upp ditt eget mått från början</span><span class="sxs-lookup"><span data-stu-id="cff76-112">Build your own measure from scratch</span></span>

<span data-ttu-id="cff76-113">Det här avsnittet innehåller information om hur du skapar ett nytt mått från grunden.</span><span class="sxs-lookup"><span data-stu-id="cff76-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="cff76-114">Du kan skapa ett mått med dataattribut från dataentiteter som har en relation som är konfigurerad för att ansluta till entiteten Kund.</span><span class="sxs-lookup"><span data-stu-id="cff76-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="cff76-115">I målgruppsinsikter går du till **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="cff76-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="cff76-116">Välj **Ny** och välj **Skapa din egen**.</span><span class="sxs-lookup"><span data-stu-id="cff76-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="cff76-117">Välj **Redigera namn** och tillhandahåll ett **namn** för måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="cff76-118">Om den nya måttkonfigurationen endast innehåller två fält, till exempel kund-ID och en beräkning, läggs utdatan till som en ny kolumn i den systemgenererade entiteten Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="cff76-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="cff76-119">Dessutom kan du se måttens värde i den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="cff76-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="cff76-120">Andra mått genererar egna entiteter.</span><span class="sxs-lookup"><span data-stu-id="cff76-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="cff76-121">Välj en sammansättningsfunktion i listrutan **Välj funktion** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="cff76-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="cff76-122">Sammansättningsfunktioner omfattar:</span><span class="sxs-lookup"><span data-stu-id="cff76-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="cff76-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="cff76-123">**Sum**</span></span>
   - <span data-ttu-id="cff76-124">**Medel**</span><span class="sxs-lookup"><span data-stu-id="cff76-124">**Average**</span></span>
   - <span data-ttu-id="cff76-125">**Antal**</span><span class="sxs-lookup"><span data-stu-id="cff76-125">**Count**</span></span>
   - <span data-ttu-id="cff76-126">**Antal unika**</span><span class="sxs-lookup"><span data-stu-id="cff76-126">**Count Unique**</span></span>
   - <span data-ttu-id="cff76-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="cff76-127">**Max**</span></span>
   - <span data-ttu-id="cff76-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="cff76-128">**Min**</span></span>
   - <span data-ttu-id="cff76-129">**Först**: tar det första värdet i dataposten</span><span class="sxs-lookup"><span data-stu-id="cff76-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="cff76-130">**Sist:** tar det sista värdet som lades till i dataposten</span><span class="sxs-lookup"><span data-stu-id="cff76-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatörer för måttberäkningar.":::

1. <span data-ttu-id="cff76-132">Välj **Lägg till attribut** för att välja de data du behöver för att skapa måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="cff76-133">Välj fliken **Attribut**.</span><span class="sxs-lookup"><span data-stu-id="cff76-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="cff76-134">Dataentitet: Välj den entitet som innehåller attributet du vill mäta.</span><span class="sxs-lookup"><span data-stu-id="cff76-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="cff76-135">Dataattribut: Välj det attribut som du vill använda i sammansättningsfunktionen för att beräkna måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="cff76-136">Du kan bara välja ett attribut åt gången.</span><span class="sxs-lookup"><span data-stu-id="cff76-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="cff76-137">Du kan också välja ett dataattribut från ett befintligt mått genom att välja fliken **Mått**. Du kan också söka efter ett entitets- eller måttnamn.</span><span class="sxs-lookup"><span data-stu-id="cff76-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="cff76-138">Välj **Lägg till** för att lägga till det valda attributet till måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Välj ett attribut som ska användas i beräkningarna.":::

1. <span data-ttu-id="cff76-140">Om du vill skapa mer komplexa mått kan du lägga till fler attribut eller använda olika operatörer i måttfunktionen.</span><span class="sxs-lookup"><span data-stu-id="cff76-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Skapa ett komplext mått med matematikoperatörer.":::

1. <span data-ttu-id="cff76-142">Om du vill lägga till filter väljer du **Filter** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="cff76-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="cff76-143">I avsnittet **Lägg till attribut** i fönstret **Filter** väljer du det attribut som du vill använda för att skapa filter.</span><span class="sxs-lookup"><span data-stu-id="cff76-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="cff76-144">Ange filteroperatörerna så att filtret definieras för varje markerat attribut.</span><span class="sxs-lookup"><span data-stu-id="cff76-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="cff76-145">Välj **Tillämpa** för att lägga till filtren till måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="cff76-146">Om du vill lägga till dimensioner väljer du **Dimension** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="cff76-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="cff76-147">Dimensioner visas som kolumner i måttutdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="cff76-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="cff76-148">Välj **Redigera dimensioner** för att lägga till dataattribut som du vill gruppera måttvärdena efter.</span><span class="sxs-lookup"><span data-stu-id="cff76-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="cff76-149">Till exempel ort eller kön.</span><span class="sxs-lookup"><span data-stu-id="cff76-149">For example, city or gender.</span></span> <span data-ttu-id="cff76-150">Som standard väljs dimensionen *Kund-ID* för att skapa *mått på kundnivå*.</span><span class="sxs-lookup"><span data-stu-id="cff76-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="cff76-151">Du kan ta bort standarddimensionen om du vill skapa *mått på företagsnivå*.</span><span class="sxs-lookup"><span data-stu-id="cff76-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="cff76-152">Välj **Klart** för att lägga till dimensionerna till måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="cff76-153">Om det finns värden i dina data som du behöver ersätta med ett heltal - till exempel ersätta *null* med *0* - väljer du **Regler**.</span><span class="sxs-lookup"><span data-stu-id="cff76-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="cff76-154">Konfigurera regeln och se till att du endast väljer heltal som ersättare.</span><span class="sxs-lookup"><span data-stu-id="cff76-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="cff76-155">Om det finns flera sökvägar mellan den dataentitet du mappade och entiteten *Kund* måste du välja någon av de identifierade [entitetsrelationssökvägarna](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="cff76-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="cff76-156">Resultaten av måtten kan variera beroende på den valda sökvägen.</span><span class="sxs-lookup"><span data-stu-id="cff76-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="cff76-157">Välj **Datainställningar** och välj den entitetssökväg som ska användas för att identifiera måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="cff76-158">Om det bara finns en enskild sökväg till entiteten *Kund* visas inte den här kontrollen.</span><span class="sxs-lookup"><span data-stu-id="cff76-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="cff76-159">Välj **Klart** för att tillämpa dina val.</span><span class="sxs-lookup"><span data-stu-id="cff76-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Välj entitetssökvägen för måttet.":::

1. <span data-ttu-id="cff76-161">Om du vill lägga till fler beräkningar för måttet väljer du **Ny beräkning**.</span><span class="sxs-lookup"><span data-stu-id="cff76-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="cff76-162">Du kan endast använda entiteter på samma entitetssökväg för nya beräkningar.</span><span class="sxs-lookup"><span data-stu-id="cff76-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="cff76-163">Fler beräkningar visas som nya kolumner i måttutdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="cff76-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="cff76-164">Välj **...** i beräkningen för att **duplicera**, **byta namn på** eller **ta bort** en beräkning från ett mått.</span><span class="sxs-lookup"><span data-stu-id="cff76-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="cff76-165">I området **Förhandsgranskning** ser du dataschemat för måttutdataentiteten, inklusive filter och dimensioner.</span><span class="sxs-lookup"><span data-stu-id="cff76-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="cff76-166">Förhandsgranskningen reagerar dynamiskt på ändringar i konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="cff76-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="cff76-167">Välj **Kör** för att beräkna resultaten för det konfigurerade måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="cff76-168">Välj **Spara och stäng** om du vill behålla den aktuella konfigurationen och köra måttet senare.</span><span class="sxs-lookup"><span data-stu-id="cff76-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="cff76-169">Gå till **Mått** för att se det nyskapade måttet i listan.</span><span class="sxs-lookup"><span data-stu-id="cff76-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="cff76-170">Skapa ett mått med hjälp av en mall</span><span class="sxs-lookup"><span data-stu-id="cff76-170">Use a template to build a measure</span></span>

<span data-ttu-id="cff76-171">Du kan använda fördefinierade mallar med vanliga åtgärder för att skapa dem.</span><span class="sxs-lookup"><span data-stu-id="cff76-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="cff76-172">Detaljerade beskrivningar av mallarna och en guidad upplevelse hjälper dig att skapa effektiva mått.</span><span class="sxs-lookup"><span data-stu-id="cff76-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="cff76-173">Mallar bygger på mappade data från entiteten *Enhetlig aktivitet*.</span><span class="sxs-lookup"><span data-stu-id="cff76-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="cff76-174">Kontrollera därför att du har konfigurerat [kundaktiviteter](activities.md) innan du skapar ett mått från en mall.</span><span class="sxs-lookup"><span data-stu-id="cff76-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="cff76-175">Tillgängliga mätmallar:</span><span class="sxs-lookup"><span data-stu-id="cff76-175">Available measure templates:</span></span> 
- <span data-ttu-id="cff76-176">Genomsnittligt transaktionsvärde</span><span class="sxs-lookup"><span data-stu-id="cff76-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="cff76-177">Totalt transaktionsvärde</span><span class="sxs-lookup"><span data-stu-id="cff76-177">Total transaction value</span></span>
- <span data-ttu-id="cff76-178">Genomsnittlig daglig intäkt</span><span class="sxs-lookup"><span data-stu-id="cff76-178">Average daily revenue</span></span>
- <span data-ttu-id="cff76-179">Genomsnittlig årlig intäkt</span><span class="sxs-lookup"><span data-stu-id="cff76-179">Average yearly revenue</span></span>
- <span data-ttu-id="cff76-180">Transaktionsantal</span><span class="sxs-lookup"><span data-stu-id="cff76-180">Transaction count</span></span>
- <span data-ttu-id="cff76-181">Intjänade lojalitetspoäng</span><span class="sxs-lookup"><span data-stu-id="cff76-181">Loyalty points earned</span></span>
- <span data-ttu-id="cff76-182">Inlösta lojalitetspoäng</span><span class="sxs-lookup"><span data-stu-id="cff76-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="cff76-183">Saldo för lojalitetspoäng</span><span class="sxs-lookup"><span data-stu-id="cff76-183">Loyalty points balance</span></span>
- <span data-ttu-id="cff76-184">Livslängd för aktiv kund</span><span class="sxs-lookup"><span data-stu-id="cff76-184">Active customer lifespan</span></span>
- <span data-ttu-id="cff76-185">Lojalitetsmedlemskapets varaktighet</span><span class="sxs-lookup"><span data-stu-id="cff76-185">Loyalty membership duration</span></span>
- <span data-ttu-id="cff76-186">Tid sedan senaste inköpet</span><span class="sxs-lookup"><span data-stu-id="cff76-186">Time since last purchase</span></span>

<span data-ttu-id="cff76-187">I följande procedur beskrivs stegen för att skapa ett nytt mått med hjälp av en mall.</span><span class="sxs-lookup"><span data-stu-id="cff76-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="cff76-188">I målgruppsinsikter går du till **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="cff76-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="cff76-189">Välj **Ny** och markera **Välj en mall**.</span><span class="sxs-lookup"><span data-stu-id="cff76-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Skärmbild på listrutan när du skapar ett nytt mått med markering i mallen.":::

1. <span data-ttu-id="cff76-191">Hitta den mall som passar dina behov och välj **Välj mall**.</span><span class="sxs-lookup"><span data-stu-id="cff76-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="cff76-192">Granska de data som krävs och välj **Kom igång** om alla data är på plats.</span><span class="sxs-lookup"><span data-stu-id="cff76-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="cff76-193">I rutan **Redigera namn** ange namn för måttet och utdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="cff76-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="cff76-194">Välj **Utfört**.</span><span class="sxs-lookup"><span data-stu-id="cff76-194">Select **Done**.</span></span>

1. <span data-ttu-id="cff76-195">I avsnittet **Ange tidsperiod** definierar du tidsram för de data som ska användas.</span><span class="sxs-lookup"><span data-stu-id="cff76-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="cff76-196">Välj om du vill att det nya måttet ska täcka hela datauppsättningen genom att välja **Hela tiden** eller att måttet ska fokusera på en **Speficik tidsperiod**.</span><span class="sxs-lookup"><span data-stu-id="cff76-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skärmbild som visar avsnittet tidsperiod när du konfigurerar ett mått från en mall.":::

1. <span data-ttu-id="cff76-198">Välj **Lägg till data** i nästa avsnitt om du vill välja aktiviteter och mappa motsvarande data från entiteten *Enhetlig aktivitet*.</span><span class="sxs-lookup"><span data-stu-id="cff76-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="cff76-199">Steg 1 av 2: Under **Aktivitetstyp** väljer du vilken typ av entitet du vill använda.</span><span class="sxs-lookup"><span data-stu-id="cff76-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="cff76-200">Välj de **Aktiviteter** väljer du de entiteter du vill mappa.</span><span class="sxs-lookup"><span data-stu-id="cff76-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="cff76-201">Steg 2 av 2: Välj attributet från entiteten *Enhetlig aktivitet* för den komponent som krävs av formeln.</span><span class="sxs-lookup"><span data-stu-id="cff76-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="cff76-202">För genomsnittstransaktionsvärdet är det till exempel attributet som representerar transaktionsvärdet.</span><span class="sxs-lookup"><span data-stu-id="cff76-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="cff76-203">För **tidsstämpeln för aktivitet** väljer du attributet från entiteten Enhetlig aktivitet som representerar datum och tid för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="cff76-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="cff76-204">När datamappningen är klar kan du se statusen **Slutförd** och namnet på de mappade aktiviteterna och attributen.</span><span class="sxs-lookup"><span data-stu-id="cff76-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Skärmbild av en slutförd måttmallskonfiguration.":::

1. <span data-ttu-id="cff76-206">Nu kan du välja **Kör** för att beräkna resultatet av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="cff76-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="cff76-207">Om du vill förfina den senare markerar du **Spara utkast**.</span><span class="sxs-lookup"><span data-stu-id="cff76-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="cff76-208">Hantera dina mått</span><span class="sxs-lookup"><span data-stu-id="cff76-208">Manage your measures</span></span>

<span data-ttu-id="cff76-209">Listan med åtgärder finns på sidan **Mått**.</span><span class="sxs-lookup"><span data-stu-id="cff76-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="cff76-210">Här finns information om måttypen, den som skapade den, datumet då den skapades, statusen och tillståndet.</span><span class="sxs-lookup"><span data-stu-id="cff76-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="cff76-211">När du väljer ett mått i listan kan du förhandsgranska utdatan och hämta en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="cff76-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="cff76-212">Om du vill uppdatera alla dina åtgärder samtidigt markerar du **Uppdatera allt** utan att välja ett specifikt mått.</span><span class="sxs-lookup"><span data-stu-id="cff76-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cff76-213">![Åtgärder för att hantera enskilda mått.](media/measure-actions.png "Åtgärder för att hantera enskilda mått.")</span><span class="sxs-lookup"><span data-stu-id="cff76-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="cff76-214">Välj ett mått i listan för följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="cff76-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="cff76-215">Markera måttets namn om du vill se detaljerna.</span><span class="sxs-lookup"><span data-stu-id="cff76-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="cff76-216">**Redigera** måttets konfiguration.</span><span class="sxs-lookup"><span data-stu-id="cff76-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="cff76-217">**Uppdatera** måttet baserat på senaste data.</span><span class="sxs-lookup"><span data-stu-id="cff76-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="cff76-218">**Byt namn** på mått.</span><span class="sxs-lookup"><span data-stu-id="cff76-218">**Rename** the measure.</span></span>
- <span data-ttu-id="cff76-219">**Ta bort** måttet.</span><span class="sxs-lookup"><span data-stu-id="cff76-219">**Delete** the measure.</span></span>
- <span data-ttu-id="cff76-220">**Aktivera** eller **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="cff76-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="cff76-221">Inaktiva mått uppdateras inte vid en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cff76-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="cff76-222">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="cff76-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cff76-223">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="cff76-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cff76-224">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="cff76-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cff76-225">När du har valt **Visa detaljerad information** för en av uppgifterna för jobbet hittar du ytterligare information: bearbetningstid, senaste bearbetningsdatum samt alla fel och varningar som hör till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="cff76-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="cff76-226">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="cff76-226">Next step</span></span>

<span data-ttu-id="cff76-227">Du kan använda befintliga åtgärder för att skapa [ett kundsegment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cff76-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
