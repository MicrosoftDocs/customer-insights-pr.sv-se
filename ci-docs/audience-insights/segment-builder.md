---
title: Skapa och hantera segment.
description: Skapa segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064959"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="5c59e-103">Skapa och hantera segment.</span><span class="sxs-lookup"><span data-stu-id="5c59e-103">Create and manage segments</span></span>

<span data-ttu-id="5c59e-104">Definiera komplexa filter runt den enhetliga kundentiteten och det är relaterade entiteter.</span><span class="sxs-lookup"><span data-stu-id="5c59e-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="5c59e-105">Varje segment skapar en uppsättning kundposter efter bearbetning som du kan exportera och utföra åtgärder på.</span><span class="sxs-lookup"><span data-stu-id="5c59e-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="5c59e-106">Segment hanteras på sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="5c59e-107">Följande exempel illustrerar segmenteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5c59e-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="5c59e-108">Vi har definierat ett segment för kunder som beställde minst 500 $ av varor under de senaste 90 dagarna *och* som var inblandade i ett kundtjänstsamtal som har eskalerats.</span><span class="sxs-lookup"><span data-stu-id="5c59e-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Skärmbild av användargränssnittet för segmentverktyget med två grupper som anger ett kundsegment.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="5c59e-110">Skapa ett nytt segment</span><span class="sxs-lookup"><span data-stu-id="5c59e-110">Create a new segment</span></span>

<span data-ttu-id="5c59e-111">Du kan skapa ett nytt segment på flera sätt.</span><span class="sxs-lookup"><span data-stu-id="5c59e-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="5c59e-112">I det här avsnittet beskrivs hur du skapar ett *tomt segment* från grunden.</span><span class="sxs-lookup"><span data-stu-id="5c59e-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="5c59e-113">Du kan också skapa ett *snabbsegment* som bygger på befintliga entiteter eller använda maskininlärning för att få *förslag på segment*.</span><span class="sxs-lookup"><span data-stu-id="5c59e-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="5c59e-114">Mer information: [Segmentöversikt](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5c59e-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="5c59e-115">När du skapar ett segment kan du spara ett utkast.</span><span class="sxs-lookup"><span data-stu-id="5c59e-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="5c59e-116">Den sparas som ett inaktivt segment och kan inte aktiveras och avslutas med en giltig konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5c59e-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="5c59e-117">Gå till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="5c59e-118">Välj **nytt** > **tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="5c59e-119">I rutan **Nytt segment**, välj en segment typ:</span><span class="sxs-lookup"><span data-stu-id="5c59e-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="5c59e-120">**Dynamiska segment** [uppdateras](segments.md#refresh-segments) enligt ett återkommande schema.</span><span class="sxs-lookup"><span data-stu-id="5c59e-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="5c59e-121">**Statiska segment** körs en gång när du skapar det.</span><span class="sxs-lookup"><span data-stu-id="5c59e-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="5c59e-122">Ange **Utdataentitetens namn** för segment.</span><span class="sxs-lookup"><span data-stu-id="5c59e-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="5c59e-123">Om du vill kan du ange en visningsnamn och en beskrivning som hjälper till att identifiera segmentet.</span><span class="sxs-lookup"><span data-stu-id="5c59e-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="5c59e-124">Välj **nästa** om du vill komma till sidan **segmentverktyget** där du definierar en grupp.</span><span class="sxs-lookup"><span data-stu-id="5c59e-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="5c59e-125">En grupp är en uppsättning kunder.</span><span class="sxs-lookup"><span data-stu-id="5c59e-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="5c59e-126">Välj den enhet som innehåller attributet du vill segmentera efter.</span><span class="sxs-lookup"><span data-stu-id="5c59e-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="5c59e-127">Välj det attribut du vill segmentera efter.</span><span class="sxs-lookup"><span data-stu-id="5c59e-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="5c59e-128">Attributet kan ha en av fyra värdetyper: numerisk, sträng, datum eller boolesk.</span><span class="sxs-lookup"><span data-stu-id="5c59e-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="5c59e-129">Välj en operator och ett värde för det valda attributet.</span><span class="sxs-lookup"><span data-stu-id="5c59e-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c59e-130">![Anpassat gruppfilter](media/customer-group-numbers.png "Kundgruppfilter")</span><span class="sxs-lookup"><span data-stu-id="5c59e-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="5c59e-131">Antal</span><span class="sxs-lookup"><span data-stu-id="5c59e-131">Number</span></span> |<span data-ttu-id="5c59e-132">Definition</span><span class="sxs-lookup"><span data-stu-id="5c59e-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="5c59e-133">1</span><span class="sxs-lookup"><span data-stu-id="5c59e-133">1</span></span>     |<span data-ttu-id="5c59e-134">Entity</span><span class="sxs-lookup"><span data-stu-id="5c59e-134">Entity</span></span>          |
   |<span data-ttu-id="5c59e-135">2</span><span class="sxs-lookup"><span data-stu-id="5c59e-135">2</span></span>     |<span data-ttu-id="5c59e-136">Attribut</span><span class="sxs-lookup"><span data-stu-id="5c59e-136">Attribute</span></span>          |
   |<span data-ttu-id="5c59e-137">3</span><span class="sxs-lookup"><span data-stu-id="5c59e-137">3</span></span>    |<span data-ttu-id="5c59e-138">Operator</span><span class="sxs-lookup"><span data-stu-id="5c59e-138">Operator</span></span>         |
   |<span data-ttu-id="5c59e-139">4</span><span class="sxs-lookup"><span data-stu-id="5c59e-139">4</span></span>    |<span data-ttu-id="5c59e-140">Värde</span><span class="sxs-lookup"><span data-stu-id="5c59e-140">Value</span></span>         |

   1. <span data-ttu-id="5c59e-141">Om du vill lägga till villkor i en grupp kan du använda två logiska operatorer:</span><span class="sxs-lookup"><span data-stu-id="5c59e-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="5c59e-142">**OCH** operatör: båda villkoren måste uppfyllas som en del av segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5c59e-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="5c59e-143">Det här alternativet är mest användbart när du definierar villkor för olika entiteter.</span><span class="sxs-lookup"><span data-stu-id="5c59e-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="5c59e-144">**ELLER** operatör: ett av villkoren behöver uppfyllas som en del av segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5c59e-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="5c59e-145">Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.</span><span class="sxs-lookup"><span data-stu-id="5c59e-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="5c59e-146">![ELLER operatör där något av villkoren behöver uppfyllas](media/segmentation-either-condition.png "ELLER operatör där något av villkoren behöver uppfyllas")</span><span class="sxs-lookup"><span data-stu-id="5c59e-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="5c59e-147">Det går för närvarande att kapsla en **ELLER**-operatör under **OCH**-operatör, men inte tvärtom.</span><span class="sxs-lookup"><span data-stu-id="5c59e-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="5c59e-148">Varje grupp matchar en uppsättning kunder.</span><span class="sxs-lookup"><span data-stu-id="5c59e-148">Each group matches set of customers.</span></span> <span data-ttu-id="5c59e-149">Du kan kombinera grupper så att de kunder som krävs för ditt affärsfall inkluderas.</span><span class="sxs-lookup"><span data-stu-id="5c59e-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="5c59e-150">Markera **Lägg till grupp**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="5c59e-151">![Lägg till grupp för kundgrupp](media/customer-group-add-group.png "Lägg till grupp för kundgrupp")</span><span class="sxs-lookup"><span data-stu-id="5c59e-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="5c59e-152">Välj en av uppsättningsoperatorerna: **Union**, **Skärning** eller **Förutom**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c59e-153">![Lägg till sammanförande för kundgrupp](media/customer-group-union.png "Lägg till sammanförande för kundgrupp")</span><span class="sxs-lookup"><span data-stu-id="5c59e-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="5c59e-154">**Sammanförande** sammanför de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="5c59e-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="5c59e-155">**Överlappande** överlappar de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="5c59e-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="5c59e-156">Endast data som *är gemensamma* för båda grupperna behålls i den enhetliga gruppen.</span><span class="sxs-lookup"><span data-stu-id="5c59e-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="5c59e-157">**Förutom** kombinerar de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="5c59e-157">**Except** combines the two groups.</span></span> <span data-ttu-id="5c59e-158">Endast data i grupp A som *inte är samma* som data i grupp B behålls.</span><span class="sxs-lookup"><span data-stu-id="5c59e-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="5c59e-159">Om entiteten är kopplad till den enhetliga kundentiteten via [Relationer](relationships.md) måste du definiera relationssökvägen för att skapa ett giltigt segment.</span><span class="sxs-lookup"><span data-stu-id="5c59e-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="5c59e-160">Lägg till entiteterna från relationssökvägen tills du kan välja entiteten **kund: CustomerInsights** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="5c59e-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="5c59e-161">Välj sedan **Alla poster** för varje steg.</span><span class="sxs-lookup"><span data-stu-id="5c59e-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c59e-162">![Relationssökväg under skapande av segment](media/segments-multiple-relationships.png "Relationssökväg under skapande av segment")</span><span class="sxs-lookup"><span data-stu-id="5c59e-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="5c59e-163">Som standard genererar segment en utdataentitet som innehåller alla attribut i kundprofiler som matchar de definierade filtren.</span><span class="sxs-lookup"><span data-stu-id="5c59e-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="5c59e-164">Om ett segment bygger på andra entiteter än entiteten *Kund* kan du lägga till fler attribut från dessa entiteter i utdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="5c59e-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="5c59e-165">Välj **Projektattribut** om du vill välja vilka attribut som ska läggas till i utdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="5c59e-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="5c59e-166">Exempel: Ett segment bygger på en entitet som innehåller kundaktivitetsdata som relaterar till entiteten *Kund*.</span><span class="sxs-lookup"><span data-stu-id="5c59e-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="5c59e-167">I segmenten söker du efter alla kunder som har ringt supporten de senaste 60 dagarna.</span><span class="sxs-lookup"><span data-stu-id="5c59e-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="5c59e-168">Du kan välja att lägga till samtalslängden och antalet anrop till alla matchande kundposter i utdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="5c59e-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="5c59e-169">Den här informationen kan vara användbar om du vill skicka ett e-postmeddelande med länkar till hjälpartiklar online och vanliga frågor och svar till kunder som ofta ringt.</span><span class="sxs-lookup"><span data-stu-id="5c59e-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="5c59e-170">Projekterade attribut fungerar endast för entiteter som har en till flera-relation med kundentiteten.</span><span class="sxs-lookup"><span data-stu-id="5c59e-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="5c59e-171">En kund kan till exempel ha flera prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="5c59e-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="5c59e-172">Du kan endast ha projektattribut från en entitet som används i varje grupp med segmentfrågor som du skapar.</span><span class="sxs-lookup"><span data-stu-id="5c59e-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="5c59e-173">Projekterade attribut räknas in när du använder uppsättningsoperatorer.</span><span class="sxs-lookup"><span data-stu-id="5c59e-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="5c59e-174">Välj **Spara** för att spara dina segment.</span><span class="sxs-lookup"><span data-stu-id="5c59e-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="5c59e-175">Segmentet sparas och bearbetas om alla krav är validerade.</span><span class="sxs-lookup"><span data-stu-id="5c59e-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="5c59e-176">Annars sparas den som ett utkast.</span><span class="sxs-lookup"><span data-stu-id="5c59e-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="5c59e-177">Klicka på **Tillbaka till segment** för att gå tillbaka till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="5c59e-178">Snabbsegment</span><span class="sxs-lookup"><span data-stu-id="5c59e-178">Quick segments</span></span>

<span data-ttu-id="5c59e-179">Med snabbsegment kan du bygga enkla segment med en enda operator snabbt för snabbare insikter.</span><span class="sxs-lookup"><span data-stu-id="5c59e-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="5c59e-180">På sidan **Segment**, välj **Ny** > **Skapa från**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="5c59e-181">Välj alternativet **profiler** för att skapa ett segment som baseras på entiteten för den *enhetliga kunden*.</span><span class="sxs-lookup"><span data-stu-id="5c59e-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="5c59e-182">Välj alternativet **Mått** om du vill skapa ett segment kring mått som du har skapat tidigare.</span><span class="sxs-lookup"><span data-stu-id="5c59e-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="5c59e-183">Markera alternativet **Intelligens** om du vill skapa ett segment runt en av de utdataentiteter som du skapade med funktionerna **prediktioner** eller **anpassade modeller**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="5c59e-184">I dialogrutan **Nytt snabbsegment**, välj ett attribut i listrutan **Fält**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="5c59e-185">Systemet tillhandahåller ytterligare insikter som hjälper dig att skapa bättre segment av dina kunder.</span><span class="sxs-lookup"><span data-stu-id="5c59e-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="5c59e-186">För kategorifält visas tio populära kundräkningar.</span><span class="sxs-lookup"><span data-stu-id="5c59e-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="5c59e-187">Välj ett **Värde** och välj **Granska**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="5c59e-188">För ett numeriskt attribut visar systemet vilket attributvärde som faller under varje kunds percentil.</span><span class="sxs-lookup"><span data-stu-id="5c59e-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="5c59e-189">Välj en **operatör** och ett **värde** och välj sedan **granska**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="5c59e-190">Systemet tillhandahåller en **uppskattad segmentstorlek**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="5c59e-191">Du kan välja om du vill skapa ett segment som du har definierat eller om du först vill ha en annan segmentstorlek.</span><span class="sxs-lookup"><span data-stu-id="5c59e-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5c59e-192">![Namn och uppskattning för ett snabbsegment](media/quick-segment-name.png "Namn och uppskattning för ett snabbsegment")</span><span class="sxs-lookup"><span data-stu-id="5c59e-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="5c59e-193">Ange ett **namn** för ditt segment.</span><span class="sxs-lookup"><span data-stu-id="5c59e-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="5c59e-194">Eventuellt ge en **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="5c59e-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="5c59e-195">Välj **Spara** för att skapa segmentet.</span><span class="sxs-lookup"><span data-stu-id="5c59e-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="5c59e-196">När segmentet har bearbetat klart kan du visa det på samma sätt som andra segment som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="5c59e-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c59e-197">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5c59e-197">Next steps</span></span>

<span data-ttu-id="5c59e-198">[Exportera ett segment](export-destinations.md) och utforska [kundkortet](customer-card-add-in.md) och [kontakterna](export-power-bi.md) för att komma igång med kundnivån.</span><span class="sxs-lookup"><span data-stu-id="5c59e-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
