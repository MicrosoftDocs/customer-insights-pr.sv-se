---
title: Skapa och hantera segment.
description: Skapa segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270378"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="870cc-103">Skapa och hantera segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-103">Create and manage segments</span></span>

<span data-ttu-id="870cc-104">Med segment kan du gruppera dina kunder baserat på demografiska attribut, transaktionella eller beteendemässiga attribut.</span><span class="sxs-lookup"><span data-stu-id="870cc-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="870cc-105">Du kan använda segment för att rikta reklamkampanjer, säljaktiviteter och kundsupport för att uppnå dina affärsmål.</span><span class="sxs-lookup"><span data-stu-id="870cc-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="870cc-106">Du kan definiera komplexa filter runt entiteten kundprofil och dess relaterade entiteter.</span><span class="sxs-lookup"><span data-stu-id="870cc-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="870cc-107">Varje segment skapar en uppsättning kundposter efter bearbetning som du kan exportera och utföra åtgärder på.</span><span class="sxs-lookup"><span data-stu-id="870cc-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="870cc-108">Vissa [servicegränser](service-limits.md) gäller.</span><span class="sxs-lookup"><span data-stu-id="870cc-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="870cc-109">Om inget annat anges är alla segment **Dynamiska segment**, som uppdateras enligt ett återkommande schema.</span><span class="sxs-lookup"><span data-stu-id="870cc-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="870cc-110">Följande exempel illustrerar segmenteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="870cc-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="870cc-111">Vi har definierat ett segment för kunder som beställde minst 500 $ av varor under de senaste 90 dagarna *och* som var inblandade i ett kundtjänstsamtal som har eskalerats.</span><span class="sxs-lookup"><span data-stu-id="870cc-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="870cc-112">![Flera grupper](media/segmentation-group1-2.png "Flera grupper")</span><span class="sxs-lookup"><span data-stu-id="870cc-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="870cc-113">Skapa ett nytt segment</span><span class="sxs-lookup"><span data-stu-id="870cc-113">Create a new segment</span></span>

<span data-ttu-id="870cc-114">Segment hanteras på sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="870cc-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="870cc-115">I målgruppsinsikter går du till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="870cc-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="870cc-116">Välj **nytt** > **tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="870cc-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="870cc-117">I rutan **Nytt segment** välj en segmenttyp och ange ett **namn**.</span><span class="sxs-lookup"><span data-stu-id="870cc-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="870cc-118">Om du vill kan du ange en visningsnamn och en beskrivning som hjälper till att identifiera segmentet.</span><span class="sxs-lookup"><span data-stu-id="870cc-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="870cc-119">Välj **nästa** om du vill komma till sidan **segmentverktyget** där du definierar en grupp.</span><span class="sxs-lookup"><span data-stu-id="870cc-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="870cc-120">En grupp är en uppsättning kunder.</span><span class="sxs-lookup"><span data-stu-id="870cc-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="870cc-121">Välj den enhet som innehåller attributet du vill segmentera efter.</span><span class="sxs-lookup"><span data-stu-id="870cc-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="870cc-122">Välj det attribut du vill segmentera efter.</span><span class="sxs-lookup"><span data-stu-id="870cc-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="870cc-123">Attributet kan ha en av fyra värdetyper: numerisk, sträng, datum eller boolesk.</span><span class="sxs-lookup"><span data-stu-id="870cc-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="870cc-124">Välj en operator och ett värde för det valda attributet.</span><span class="sxs-lookup"><span data-stu-id="870cc-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="870cc-125">![Anpassat gruppfilter](media/customer-group-numbers.png "Kundgruppfilter")</span><span class="sxs-lookup"><span data-stu-id="870cc-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="870cc-126">Antal</span><span class="sxs-lookup"><span data-stu-id="870cc-126">Number</span></span> |<span data-ttu-id="870cc-127">Definition</span><span class="sxs-lookup"><span data-stu-id="870cc-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="870cc-128">1</span><span class="sxs-lookup"><span data-stu-id="870cc-128">1</span></span>     |<span data-ttu-id="870cc-129">Entity</span><span class="sxs-lookup"><span data-stu-id="870cc-129">Entity</span></span>          |
   |<span data-ttu-id="870cc-130">2</span><span class="sxs-lookup"><span data-stu-id="870cc-130">2</span></span>     |<span data-ttu-id="870cc-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="870cc-131">Attribute</span></span>          |
   |<span data-ttu-id="870cc-132">3</span><span class="sxs-lookup"><span data-stu-id="870cc-132">3</span></span>    |<span data-ttu-id="870cc-133">Operator</span><span class="sxs-lookup"><span data-stu-id="870cc-133">Operator</span></span>         |
   |<span data-ttu-id="870cc-134">4</span><span class="sxs-lookup"><span data-stu-id="870cc-134">4</span></span>    |<span data-ttu-id="870cc-135">Värde</span><span class="sxs-lookup"><span data-stu-id="870cc-135">Value</span></span>         |

8. <span data-ttu-id="870cc-136">Om entiteten är kopplad till den enhetliga kundentiteten via [Relationer](relationships.md) måste du definiera relationssökvägen för att skapa ett giltigt segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="870cc-137">Lägg till entiteterna från relationssökvägen tills du kan välja entiteten **kund: CustomerInsights** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="870cc-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="870cc-138">Välj sedan **alla poster** för varje villkor.</span><span class="sxs-lookup"><span data-stu-id="870cc-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="870cc-139">![Relationssökväg under skapande av segment](media/segments-multiple-relationships.png "Relationssökväg under skapande av segment")</span><span class="sxs-lookup"><span data-stu-id="870cc-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="870cc-140">Välj **Spara** för att spara dina segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="870cc-141">Segmentet sparas och bearbetas om alla krav är validerade.</span><span class="sxs-lookup"><span data-stu-id="870cc-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="870cc-142">Annars sparas den som ett utkast.</span><span class="sxs-lookup"><span data-stu-id="870cc-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="870cc-143">Klicka på **Tillbaka till segment** för att gå tillbaka till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="870cc-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="870cc-144">Hantera befintliga segment</span><span class="sxs-lookup"><span data-stu-id="870cc-144">Manage existing segments</span></span>

<span data-ttu-id="870cc-145">På sidan **segment** kan du visa alla dina sparade segment och hantera dem.</span><span class="sxs-lookup"><span data-stu-id="870cc-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="870cc-146">Varje segment representeras av en rad som innehåller ytterligare information om segmentet.</span><span class="sxs-lookup"><span data-stu-id="870cc-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="870cc-147">Du kan sortera segmenten i en kolumn genom att markera kolumnrubriken.</span><span class="sxs-lookup"><span data-stu-id="870cc-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="870cc-148">Använd rutan **Sök** i det övre högra hörnet för att filtrera segmenten.</span><span class="sxs-lookup"><span data-stu-id="870cc-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="870cc-149">![Alternativ för att hantera ett befintligt segment](media/segments-selected-segment.png "Alternativ för att hantera ett befintligt segment")</span><span class="sxs-lookup"><span data-stu-id="870cc-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="870cc-150">Följande åtgärd är tillgänglig när du väljer ett segment:</span><span class="sxs-lookup"><span data-stu-id="870cc-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="870cc-151">**Visa** information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="870cc-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="870cc-152">**Redigera** segmentet om du vill ändra dess egenskaper.</span><span class="sxs-lookup"><span data-stu-id="870cc-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="870cc-153">**Uppdatera** segmentet så att det omfattar senaste data.</span><span class="sxs-lookup"><span data-stu-id="870cc-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="870cc-154">**Aktivera** eller **Inaktivera** segmentet.</span><span class="sxs-lookup"><span data-stu-id="870cc-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="870cc-155">Segment har två möjliga tillstånd - aktiva eller inaktiva.</span><span class="sxs-lookup"><span data-stu-id="870cc-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="870cc-156">Dessa tillstånd har praktiskt taget när de redigerar ett segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="870cc-157">För inaktiva segment finns segmentdefinitionen, men den innehåller inga kunder ännu.</span><span class="sxs-lookup"><span data-stu-id="870cc-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="870cc-158">När du aktiverar ett segment ändras dess status från "inaktivt" till "aktivt" och sökningen börjar söka efter kunder som matchar segmentdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="870cc-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="870cc-159">Om en [schemalagd uppdatering](system.md#schedule-tab) har konfigurerats har inaktiva segment **Status** anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats.</span><span class="sxs-lookup"><span data-stu-id="870cc-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="870cc-160">När ett inaktivt segment aktiveras uppdateras och tas med i schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="870cc-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="870cc-161">Du kan också använda funktionen **Schemalägg senare** i listrutan **Aktivera/inaktivera** för att ange ett framtida datum och tid för aktivering och inaktivering av ett visst segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="870cc-162">**Byt namn** på segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-162">**Rename** the segment.</span></span>
- <span data-ttu-id="870cc-163">**Hämta** listan över medlemmar som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="870cc-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="870cc-164">Alternativet **Lägg till** skickar listan med kund-ID i segmentet för bearbetning i ett annat program.</span><span class="sxs-lookup"><span data-stu-id="870cc-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="870cc-165">**Ta bort** segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="870cc-166">Uppdatera segment</span><span class="sxs-lookup"><span data-stu-id="870cc-166">Refresh segments</span></span>

<span data-ttu-id="870cc-167">Du kan uppdatera alla segment på en gång genom att markera **Uppdatera alla** på sidan **Segment**, eller också kan du uppdatera ett eller flera segment när du markerar dem och väljer **Uppdatera** bland alternativen.</span><span class="sxs-lookup"><span data-stu-id="870cc-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="870cc-168">Du kan även konfigurera en återkommande uppdatering på **Administratör** > **System** > **Schemalägg**.</span><span class="sxs-lookup"><span data-stu-id="870cc-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="870cc-169">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="870cc-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="870cc-170">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="870cc-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="870cc-171">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="870cc-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="870cc-172">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="870cc-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="870cc-173">Ladda ned och exportera segment</span><span class="sxs-lookup"><span data-stu-id="870cc-173">Download and export segments</span></span>

<span data-ttu-id="870cc-174">Du kan hämta segmenten till en CSV-fil eller exportera dem till Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="870cc-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="870cc-175">Ladda ned segment till en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="870cc-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="870cc-176">I målgruppsinsikter går du till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="870cc-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="870cc-177">Välj en ellips på en specifik segmentpanel.</span><span class="sxs-lookup"><span data-stu-id="870cc-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="870cc-178">Välj **Hämta som CSV** i listrutan för åtgärder.</span><span class="sxs-lookup"><span data-stu-id="870cc-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="870cc-179">Exportera segment till Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="870cc-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="870cc-180">Innan du exporterar segment till Dynamics 365 Sales måste en administratör [skapa exportmålet](export-destinations.md) för Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="870cc-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="870cc-181">I målgruppsinsikter går du till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="870cc-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="870cc-182">Välj en ellips på en specifik segmentpanel.</span><span class="sxs-lookup"><span data-stu-id="870cc-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="870cc-183">Välj **Lägg till** från listrutan åtgärder och välj det exportmål som du vill skicka data till.</span><span class="sxs-lookup"><span data-stu-id="870cc-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="870cc-184">Utkastläge för segment</span><span class="sxs-lookup"><span data-stu-id="870cc-184">Draft mode for segments</span></span>

<span data-ttu-id="870cc-185">Om inte alla krav för att bearbeta ett segment uppfylls kan du spara segmentet som ett utkast och komma åt det från sidan **segment**.</span><span class="sxs-lookup"><span data-stu-id="870cc-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="870cc-186">Det sparas som ett inaktivt segment och kan inte aktiveras förrän det är giltigt.</span><span class="sxs-lookup"><span data-stu-id="870cc-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="870cc-187">Lägga till fler villkor i en grupp</span><span class="sxs-lookup"><span data-stu-id="870cc-187">Add more conditions to a group</span></span>

<span data-ttu-id="870cc-188">Om du vill lägga till villkor i en grupp kan du använda två logiska operatorer:</span><span class="sxs-lookup"><span data-stu-id="870cc-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="870cc-189">**OCH** operatör: båda villkoren måste uppfyllas som en del av segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="870cc-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="870cc-190">Det här alternativet är mest användbart när du definierar villkor för olika entiteter.</span><span class="sxs-lookup"><span data-stu-id="870cc-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="870cc-191">**ELLER** operatör: ett av villkoren behöver uppfyllas som en del av segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="870cc-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="870cc-192">Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.</span><span class="sxs-lookup"><span data-stu-id="870cc-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="870cc-193">![ELLER operatör där något av villkoren behöver uppfyllas](media/segmentation-either-condition.png "ELLER operatör där något av villkoren behöver uppfyllas")</span><span class="sxs-lookup"><span data-stu-id="870cc-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="870cc-194">Det går för närvarande att kapsla en **ELLER**-operatör under **OCH**-operatör, men inte tvärtom.</span><span class="sxs-lookup"><span data-stu-id="870cc-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="870cc-195">Kombinera flera grupper</span><span class="sxs-lookup"><span data-stu-id="870cc-195">Combine multiple groups</span></span>

<span data-ttu-id="870cc-196">Varje grupp skapar en specifik uppsättning kunder.</span><span class="sxs-lookup"><span data-stu-id="870cc-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="870cc-197">Du kan kombinera grupperna så att de omfattar de kunder som krävs för affärsärendet.</span><span class="sxs-lookup"><span data-stu-id="870cc-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="870cc-198">I målgruppsinsikter går du till sidan **Segment** och väljer ett segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="870cc-199">Markera **Lägg till grupp**.</span><span class="sxs-lookup"><span data-stu-id="870cc-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="870cc-200">![Lägg till grupp för kundgrupp](media/customer-group-add-group.png "Lägg till grupp för kundgrupp")</span><span class="sxs-lookup"><span data-stu-id="870cc-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="870cc-201">Välj en av följande uppsättningar med operatorer: **förbindelse**, **överlappa** eller **förutom**.</span><span class="sxs-lookup"><span data-stu-id="870cc-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="870cc-202">![Lägg till sammanförande för kundgrupp](media/customer-group-union.png "Lägg till sammanförande för kundgrupp")</span><span class="sxs-lookup"><span data-stu-id="870cc-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="870cc-203">Välj en uppsättnings operatör kan du definiera en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="870cc-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="870cc-204">Spara olika grupper för att fastställa vilka data som ska behållas:</span><span class="sxs-lookup"><span data-stu-id="870cc-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="870cc-205">**Sammanförande** sammanför de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="870cc-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="870cc-206">**Överlappande** överlappar de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="870cc-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="870cc-207">Endast data som *är gemensamma* för båda grupperna behålls i den enhetliga gruppen.</span><span class="sxs-lookup"><span data-stu-id="870cc-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="870cc-208">**Förutom** kombinerar de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="870cc-208">**Except** combines the two groups.</span></span> <span data-ttu-id="870cc-209">Endast data i grupp A som *inte är samma* som data i grupp B behålls.</span><span class="sxs-lookup"><span data-stu-id="870cc-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="870cc-210">Visa historik- och segmentmedlemmar för bearbetning</span><span class="sxs-lookup"><span data-stu-id="870cc-210">View processing history and segment members</span></span>

<span data-ttu-id="870cc-211">Du kan visa konsoliderade data om ett segment genom att granska dess detaljer.</span><span class="sxs-lookup"><span data-stu-id="870cc-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="870cc-212">På sidan **Segment**, välj det segment du vill granska.</span><span class="sxs-lookup"><span data-stu-id="870cc-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="870cc-213">Den övre delen av sidan innehåller ett trenddiagram som visualiserar ändringar i medlemsantal.</span><span class="sxs-lookup"><span data-stu-id="870cc-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="870cc-214">Hovra över datapunkter om du vill visa antal medlemmar för ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="870cc-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="870cc-215">Du kan uppdatera visualiseringens tidsram.</span><span class="sxs-lookup"><span data-stu-id="870cc-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="870cc-216">![Tidsintervall för segment](media/segment-time-range.png "Tidsintervall för segment")</span><span class="sxs-lookup"><span data-stu-id="870cc-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="870cc-217">Den nedre delen innehåller en lista över segmentets medlemmar.</span><span class="sxs-lookup"><span data-stu-id="870cc-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="870cc-218">Fält som visas i listan bygger på attributen för segmentets entiteter.</span><span class="sxs-lookup"><span data-stu-id="870cc-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="870cc-219">Listan är en förhandsgranskning av de matchande segmentmedlemmarna och visar de första 100 posterna för ditt segment så att du snabbt kan utvärdera den och granska dess definitioner om det behövs.</span><span class="sxs-lookup"><span data-stu-id="870cc-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="870cc-220">Om du vill visa alla matchande poster måste du [exportera segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="870cc-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="870cc-221">Snabbsegment</span><span class="sxs-lookup"><span data-stu-id="870cc-221">Quick segments</span></span>

<span data-ttu-id="870cc-222">Förutom segmentbyggaren finns det en annan väg för att skapa segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="870cc-223">Med hjälp av snabbsegment kan du snabbt skapa enkla segment (med en enskild operator) och med omedelbara insikter.</span><span class="sxs-lookup"><span data-stu-id="870cc-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="870cc-224">På sidan **Segment** välj **Ny** > **Snabbskapa från**.</span><span class="sxs-lookup"><span data-stu-id="870cc-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="870cc-225">Välj alternativet **profiler** för att skapa ett segment som baseras på entiteten för den enhetliga kunden.</span><span class="sxs-lookup"><span data-stu-id="870cc-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="870cc-226">Välj alternativet **mått** för att skapa ett segment runt varje kundattribut av typen av mått som du redan har skapat på sidan **mått**.</span><span class="sxs-lookup"><span data-stu-id="870cc-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="870cc-227">Markera alternativet **Intelligens** om du vill skapa ett segment runt en av de utdataentiteter som du skapade med funktionerna **prediktioner** eller **anpassade modeller**.</span><span class="sxs-lookup"><span data-stu-id="870cc-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="870cc-228">I dialogrutan **Nytt snabbsegment**, välj ett attribut i listrutan **Fält**.</span><span class="sxs-lookup"><span data-stu-id="870cc-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="870cc-229">Systemet tillhandahåller ytterligare insikter som hjälper dig att skapa bättre segment av dina kunder.</span><span class="sxs-lookup"><span data-stu-id="870cc-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="870cc-230">För kategorifält visas tio populära kundräkningar.</span><span class="sxs-lookup"><span data-stu-id="870cc-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="870cc-231">Välj ett **Värde** och välj **Granska**.</span><span class="sxs-lookup"><span data-stu-id="870cc-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="870cc-232">För ett numeriskt attribut visar systemet vilket attributvärde som faller under varje kunds percentil.</span><span class="sxs-lookup"><span data-stu-id="870cc-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="870cc-233">Välj en **operatör** och ett **värde** och välj sedan **granska**.</span><span class="sxs-lookup"><span data-stu-id="870cc-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="870cc-234">Systemet tillhandahåller en **uppskattad segmentstorlek**.</span><span class="sxs-lookup"><span data-stu-id="870cc-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="870cc-235">Du kan välja om du vill skapa ett segment som du har definierat eller om du först vill ha en annan segmentstorlek.</span><span class="sxs-lookup"><span data-stu-id="870cc-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="870cc-236">![Namn och uppskattning för ett snabbsegment](media/quick-segment-name.png "Namn och uppskattning för ett snabbsegment")</span><span class="sxs-lookup"><span data-stu-id="870cc-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="870cc-237">Ange ett **namn** för ditt segment.</span><span class="sxs-lookup"><span data-stu-id="870cc-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="870cc-238">Eventuellt ge en **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="870cc-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="870cc-239">Välj **Spara** för att skapa segmentet.</span><span class="sxs-lookup"><span data-stu-id="870cc-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="870cc-240">När segmentet har bearbetat klart kan du visa det på samma sätt som andra segment som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="870cc-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="870cc-241">För följande scenarier rekommenderar vi att du använder segmentbyggare i stället för de rekommenderade segmenten:</span><span class="sxs-lookup"><span data-stu-id="870cc-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="870cc-242">Skapa segment med filter för kategorifält där operatorn är annorlunda än operatorn **Är**</span><span class="sxs-lookup"><span data-stu-id="870cc-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="870cc-243">Skapa segment med filter för numeriska fält där operatorn är annorlunda än operatorerna **Mellan**, **Större än** och **Mindre än**</span><span class="sxs-lookup"><span data-stu-id="870cc-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="870cc-244">Skapa segment med filter för datumtypfält</span><span class="sxs-lookup"><span data-stu-id="870cc-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="870cc-245">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="870cc-245">Next steps</span></span>

<span data-ttu-id="870cc-246">[Exportera ett segment](export-destinations.md) och utforska [kundkortet](customer-card-add-in.md) och [kontakterna](export-power-bi.md) för att komma igång med kundnivån.</span><span class="sxs-lookup"><span data-stu-id="870cc-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]