---
title: Skapa och hantera segment.
description: Skapa segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597083"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="f3920-103">Skapa och hantera segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-103">Create and manage segments</span></span>

<span data-ttu-id="f3920-104">Med segment kan du gruppera dina kunder baserat på demografiska attribut, transaktionella eller beteendemässiga attribut.</span><span class="sxs-lookup"><span data-stu-id="f3920-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="f3920-105">Du kan använda segment för att rikta reklamkampanjer, säljaktiviteter och kundsupport för att uppnå dina affärsmål.</span><span class="sxs-lookup"><span data-stu-id="f3920-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="f3920-106">Du kan definiera komplexa filter runt entiteten kundprofil och dess relaterade entiteter.</span><span class="sxs-lookup"><span data-stu-id="f3920-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="f3920-107">Varje segment skapar en uppsättning kundposter efter bearbetning som du kan exportera och utföra åtgärder på.</span><span class="sxs-lookup"><span data-stu-id="f3920-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="f3920-108">Vissa [servicegränser](service-limits.md) gäller.</span><span class="sxs-lookup"><span data-stu-id="f3920-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="f3920-109">Om inget annat anges är alla segment **Dynamiska segment**, som uppdateras enligt ett återkommande schema.</span><span class="sxs-lookup"><span data-stu-id="f3920-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="f3920-110">Följande exempel illustrerar segmenteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="f3920-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="f3920-111">Vi har definierat ett segment för kunder som beställde minst 500 $ av varor under de senaste 90 dagarna *och* som var inblandade i ett kundtjänstsamtal som har eskalerats.</span><span class="sxs-lookup"><span data-stu-id="f3920-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3920-112">![Flera grupper](media/segmentation-group1-2.png "Flera grupper")</span><span class="sxs-lookup"><span data-stu-id="f3920-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="f3920-113">Skapa ett nytt segment</span><span class="sxs-lookup"><span data-stu-id="f3920-113">Create a new segment</span></span>

<span data-ttu-id="f3920-114">Segment hanteras på sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="f3920-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="f3920-115">I målgruppsinsikter går du till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="f3920-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="f3920-116">Välj **nytt** > **tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="f3920-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="f3920-117">I rutan **Nytt segment** välj en segmenttyp och ange ett **namn**.</span><span class="sxs-lookup"><span data-stu-id="f3920-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="f3920-118">Om du vill kan du ange en visningsnamn och en beskrivning som hjälper till att identifiera segmentet.</span><span class="sxs-lookup"><span data-stu-id="f3920-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="f3920-119">Välj **nästa** om du vill komma till sidan **segmentverktyget** där du definierar en grupp.</span><span class="sxs-lookup"><span data-stu-id="f3920-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="f3920-120">En grupp är en uppsättning kunder.</span><span class="sxs-lookup"><span data-stu-id="f3920-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="f3920-121">Välj den enhet som innehåller attributet du vill segmentera efter.</span><span class="sxs-lookup"><span data-stu-id="f3920-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="f3920-122">Välj det attribut du vill segmentera efter.</span><span class="sxs-lookup"><span data-stu-id="f3920-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="f3920-123">Attributet kan ha en av fyra värdetyper: numerisk, sträng, datum eller boolesk.</span><span class="sxs-lookup"><span data-stu-id="f3920-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="f3920-124">Välj en operator och ett värde för det valda attributet.</span><span class="sxs-lookup"><span data-stu-id="f3920-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3920-125">![Anpassat gruppfilter](media/customer-group-numbers.png "Kundgruppfilter")</span><span class="sxs-lookup"><span data-stu-id="f3920-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="f3920-126">Antal</span><span class="sxs-lookup"><span data-stu-id="f3920-126">Number</span></span> |<span data-ttu-id="f3920-127">Definition</span><span class="sxs-lookup"><span data-stu-id="f3920-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="f3920-128">1</span><span class="sxs-lookup"><span data-stu-id="f3920-128">1</span></span>     |<span data-ttu-id="f3920-129">Entity</span><span class="sxs-lookup"><span data-stu-id="f3920-129">Entity</span></span>          |
   |<span data-ttu-id="f3920-130">2</span><span class="sxs-lookup"><span data-stu-id="f3920-130">2</span></span>     |<span data-ttu-id="f3920-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="f3920-131">Attribute</span></span>          |
   |<span data-ttu-id="f3920-132">3</span><span class="sxs-lookup"><span data-stu-id="f3920-132">3</span></span>    |<span data-ttu-id="f3920-133">Operator</span><span class="sxs-lookup"><span data-stu-id="f3920-133">Operator</span></span>         |
   |<span data-ttu-id="f3920-134">4</span><span class="sxs-lookup"><span data-stu-id="f3920-134">4</span></span>    |<span data-ttu-id="f3920-135">Värde</span><span class="sxs-lookup"><span data-stu-id="f3920-135">Value</span></span>         |

8. <span data-ttu-id="f3920-136">Om entiteten är kopplad till den enhetliga kundentiteten via [Relationer](relationships.md) måste du definiera relationssökvägen för att skapa ett giltigt segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="f3920-137">Lägg till entiteterna från relationssökvägen tills du kan välja entiteten **kund: CustomerInsights** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f3920-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="f3920-138">Välj sedan **alla poster** för varje villkor.</span><span class="sxs-lookup"><span data-stu-id="f3920-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3920-139">![Relationssökväg under skapande av segment](media/segments-multiple-relationships.png "Relationssökväg under skapande av segment")</span><span class="sxs-lookup"><span data-stu-id="f3920-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="f3920-140">Som standard genererar segment en utdataentitet som innehåller alla attribut i kundprofiler som matchar de definierade filtren.</span><span class="sxs-lookup"><span data-stu-id="f3920-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="f3920-141">Om ett segment bygger på andra entiteter än entiteten *Kund* kan du lägga till fler attribut från dessa entiteter i utdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="f3920-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="f3920-142">Välj **Projektattribut** om du vill välja vilka attribut som ska läggas till i utdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="f3920-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="f3920-143">Exempel: Ett segment bygger på en entitet som innehåller kundaktivitetsdata som relaterar till entiteten *Kund*.</span><span class="sxs-lookup"><span data-stu-id="f3920-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="f3920-144">I segmenten söker du efter alla kunder som har ringt supporten de senaste 60 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f3920-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="f3920-145">Du kan välja att lägga till samtalslängden och antalet anrop till alla matchande kundposter i utdataentiteten.</span><span class="sxs-lookup"><span data-stu-id="f3920-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="f3920-146">Den här informationen kan vara användbar om du vill skicka ett e-postmeddelande med länkar till hjälpartiklar online och vanliga frågor och svar till kunder som ofta ringt.</span><span class="sxs-lookup"><span data-stu-id="f3920-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="f3920-147">Välj **Spara** för att spara dina segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="f3920-148">Segmentet sparas och bearbetas om alla krav är validerade.</span><span class="sxs-lookup"><span data-stu-id="f3920-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="f3920-149">Annars sparas den som ett utkast.</span><span class="sxs-lookup"><span data-stu-id="f3920-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="f3920-150">Klicka på **Tillbaka till segment** för att gå tillbaka till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="f3920-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="f3920-151">Hantera befintliga segment</span><span class="sxs-lookup"><span data-stu-id="f3920-151">Manage existing segments</span></span>

<span data-ttu-id="f3920-152">På sidan **segment** kan du visa alla dina sparade segment och hantera dem.</span><span class="sxs-lookup"><span data-stu-id="f3920-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="f3920-153">Varje segment representeras av en rad som innehåller ytterligare information om segmentet.</span><span class="sxs-lookup"><span data-stu-id="f3920-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="f3920-154">Du kan sortera segmenten i en kolumn genom att markera kolumnrubriken.</span><span class="sxs-lookup"><span data-stu-id="f3920-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="f3920-155">Använd rutan **Sök** i det övre högra hörnet för att filtrera segmenten.</span><span class="sxs-lookup"><span data-stu-id="f3920-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3920-156">![Alternativ för att hantera ett befintligt segment](media/segments-selected-segment.png "Alternativ för att hantera ett befintligt segment")</span><span class="sxs-lookup"><span data-stu-id="f3920-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="f3920-157">Följande åtgärd är tillgänglig när du väljer ett segment:</span><span class="sxs-lookup"><span data-stu-id="f3920-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="f3920-158">**Visa** information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="f3920-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="f3920-159">**Redigera** segmentet om du vill ändra dess egenskaper.</span><span class="sxs-lookup"><span data-stu-id="f3920-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="f3920-160">**Skapa dubblett** av ett segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="f3920-161">Du kan välja att redigera egenskaperna direkt eller bara spara dubbletten.</span><span class="sxs-lookup"><span data-stu-id="f3920-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="f3920-162">**Uppdatera** segmentet så att det omfattar senaste data.</span><span class="sxs-lookup"><span data-stu-id="f3920-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="f3920-163">**Aktivera** eller **Inaktivera** segmentet.</span><span class="sxs-lookup"><span data-stu-id="f3920-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="f3920-164">Segment har två möjliga tillstånd - aktiva eller inaktiva.</span><span class="sxs-lookup"><span data-stu-id="f3920-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="f3920-165">Dessa tillstånd har praktiskt taget när de redigerar ett segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="f3920-166">För inaktiva segment finns segmentdefinitionen, men den innehåller inga kunder ännu.</span><span class="sxs-lookup"><span data-stu-id="f3920-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="f3920-167">När du aktiverar ett segment ändras dess status från "inaktivt" till "aktivt" och sökningen börjar söka efter kunder som matchar segmentdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="f3920-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="f3920-168">Om en [schemalagd uppdatering](system.md#schedule-tab) har konfigurerats har inaktiva segment **Status** anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats.</span><span class="sxs-lookup"><span data-stu-id="f3920-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="f3920-169">När ett inaktivt segment aktiveras uppdateras och tas med i schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="f3920-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="f3920-170">Du kan också använda funktionen **Schemalägg senare** i listrutan **Aktivera/inaktivera** för att ange ett framtida datum och tid för aktivering och inaktivering av ett visst segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="f3920-171">**Byt namn** på segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-171">**Rename** the segment.</span></span>
- <span data-ttu-id="f3920-172">**Hämta** listan över medlemmar som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="f3920-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="f3920-173">Alternativet **Lägg till** skickar listan med kund-ID i segmentet för bearbetning i ett annat program.</span><span class="sxs-lookup"><span data-stu-id="f3920-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="f3920-174">**Ta bort** segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="f3920-175">Uppdatera segment</span><span class="sxs-lookup"><span data-stu-id="f3920-175">Refresh segments</span></span>

<span data-ttu-id="f3920-176">Du kan uppdatera alla segment på en gång genom att markera **Uppdatera alla** på sidan **Segment**, eller också kan du uppdatera ett eller flera segment när du markerar dem och väljer **Uppdatera** bland alternativen.</span><span class="sxs-lookup"><span data-stu-id="f3920-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="f3920-177">Du kan även konfigurera en återkommande uppdatering på **Administratör** > **System** > **Schemalägg**.</span><span class="sxs-lookup"><span data-stu-id="f3920-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="f3920-178">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="f3920-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f3920-179">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f3920-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f3920-180">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="f3920-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f3920-181">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="f3920-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="f3920-182">Ladda ned och exportera segment</span><span class="sxs-lookup"><span data-stu-id="f3920-182">Download and export segments</span></span>

<span data-ttu-id="f3920-183">Du kan hämta segmenten till en CSV-fil eller exportera dem till Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="f3920-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="f3920-184">Ladda ned segment till en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="f3920-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="f3920-185">I målgruppsinsikter går du till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="f3920-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="f3920-186">Välj en ellips på en specifik segmentpanel.</span><span class="sxs-lookup"><span data-stu-id="f3920-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="f3920-187">Välj **Hämta som CSV** i listrutan för åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f3920-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="f3920-188">Exportera segment till Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="f3920-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="f3920-189">Innan du exporterar segment till Dynamics 365 Sales måste en administratör [skapa exportmålet](export-destinations.md) för Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="f3920-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="f3920-190">I målgruppsinsikter går du till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="f3920-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="f3920-191">Välj en ellips på en specifik segmentpanel.</span><span class="sxs-lookup"><span data-stu-id="f3920-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="f3920-192">Välj **Lägg till** från listrutan åtgärder och välj det exportmål som du vill skicka data till.</span><span class="sxs-lookup"><span data-stu-id="f3920-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="f3920-193">Utkastläge för segment</span><span class="sxs-lookup"><span data-stu-id="f3920-193">Draft mode for segments</span></span>

<span data-ttu-id="f3920-194">Om inte alla krav för att bearbeta ett segment uppfylls kan du spara segmentet som ett utkast och komma åt det från sidan **segment**.</span><span class="sxs-lookup"><span data-stu-id="f3920-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="f3920-195">Det sparas som ett inaktivt segment och kan inte aktiveras förrän det är giltigt.</span><span class="sxs-lookup"><span data-stu-id="f3920-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="f3920-196">Lägga till fler villkor i en grupp</span><span class="sxs-lookup"><span data-stu-id="f3920-196">Add more conditions to a group</span></span>

<span data-ttu-id="f3920-197">Om du vill lägga till villkor i en grupp kan du använda två logiska operatorer:</span><span class="sxs-lookup"><span data-stu-id="f3920-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="f3920-198">**OCH** operatör: båda villkoren måste uppfyllas som en del av segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f3920-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="f3920-199">Det här alternativet är mest användbart när du definierar villkor för olika entiteter.</span><span class="sxs-lookup"><span data-stu-id="f3920-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="f3920-200">**ELLER** operatör: ett av villkoren behöver uppfyllas som en del av segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f3920-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="f3920-201">Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.</span><span class="sxs-lookup"><span data-stu-id="f3920-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3920-202">![ELLER operatör där något av villkoren behöver uppfyllas](media/segmentation-either-condition.png "ELLER operatör där något av villkoren behöver uppfyllas")</span><span class="sxs-lookup"><span data-stu-id="f3920-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="f3920-203">Det går för närvarande att kapsla en **ELLER**-operatör under **OCH**-operatör, men inte tvärtom.</span><span class="sxs-lookup"><span data-stu-id="f3920-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="f3920-204">Kombinera flera grupper</span><span class="sxs-lookup"><span data-stu-id="f3920-204">Combine multiple groups</span></span>

<span data-ttu-id="f3920-205">Varje grupp skapar en specifik uppsättning kunder.</span><span class="sxs-lookup"><span data-stu-id="f3920-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="f3920-206">Du kan kombinera grupperna så att de omfattar de kunder som krävs för affärsärendet.</span><span class="sxs-lookup"><span data-stu-id="f3920-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="f3920-207">I målgruppsinsikter går du till sidan **Segment** och väljer ett segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="f3920-208">Markera **Lägg till grupp**.</span><span class="sxs-lookup"><span data-stu-id="f3920-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3920-209">![Lägg till grupp för kundgrupp](media/customer-group-add-group.png "Lägg till grupp för kundgrupp")</span><span class="sxs-lookup"><span data-stu-id="f3920-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="f3920-210">Välj en av följande uppsättningar med operatorer: **förbindelse**, **överlappa** eller **förutom**.</span><span class="sxs-lookup"><span data-stu-id="f3920-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3920-211">![Lägg till sammanförande för kundgrupp](media/customer-group-union.png "Lägg till sammanförande för kundgrupp")</span><span class="sxs-lookup"><span data-stu-id="f3920-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="f3920-212">Välj en uppsättnings operatör kan du definiera en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="f3920-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="f3920-213">Spara olika grupper för att fastställa vilka data som ska behållas:</span><span class="sxs-lookup"><span data-stu-id="f3920-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="f3920-214">**Sammanförande** sammanför de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="f3920-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="f3920-215">**Överlappande** överlappar de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="f3920-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="f3920-216">Endast data som *är gemensamma* för båda grupperna behålls i den enhetliga gruppen.</span><span class="sxs-lookup"><span data-stu-id="f3920-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="f3920-217">**Förutom** kombinerar de två grupperna.</span><span class="sxs-lookup"><span data-stu-id="f3920-217">**Except** combines the two groups.</span></span> <span data-ttu-id="f3920-218">Endast data i grupp A som *inte är samma* som data i grupp B behålls.</span><span class="sxs-lookup"><span data-stu-id="f3920-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="f3920-219">Visa historik- och segmentmedlemmar för bearbetning</span><span class="sxs-lookup"><span data-stu-id="f3920-219">View processing history and segment members</span></span>

<span data-ttu-id="f3920-220">Du kan visa konsoliderade data om ett segment genom att granska dess detaljer.</span><span class="sxs-lookup"><span data-stu-id="f3920-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="f3920-221">På sidan **Segment**, välj det segment du vill granska.</span><span class="sxs-lookup"><span data-stu-id="f3920-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="f3920-222">Den övre delen av sidan innehåller ett trenddiagram som visualiserar ändringar i medlemsantal.</span><span class="sxs-lookup"><span data-stu-id="f3920-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="f3920-223">Hovra över datapunkter om du vill visa antal medlemmar för ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="f3920-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="f3920-224">Du kan uppdatera visualiseringens tidsram.</span><span class="sxs-lookup"><span data-stu-id="f3920-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3920-225">![Tidsintervall för segment](media/segment-time-range.png "Tidsintervall för segment")</span><span class="sxs-lookup"><span data-stu-id="f3920-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="f3920-226">Den nedre delen innehåller en lista över segmentets medlemmar.</span><span class="sxs-lookup"><span data-stu-id="f3920-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="f3920-227">Fält som visas i listan bygger på attributen för segmentets entiteter.</span><span class="sxs-lookup"><span data-stu-id="f3920-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="f3920-228">Listan är en förhandsgranskning av de matchande segmentmedlemmarna och visar de första 100 posterna för ditt segment så att du snabbt kan utvärdera den och granska dess definitioner om det behövs.</span><span class="sxs-lookup"><span data-stu-id="f3920-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="f3920-229">Om du vill visa alla matchande poster måste du [exportera segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f3920-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="f3920-230">Snabbsegment</span><span class="sxs-lookup"><span data-stu-id="f3920-230">Quick segments</span></span>

<span data-ttu-id="f3920-231">Förutom segmentbyggaren finns det en annan väg för att skapa segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="f3920-232">Med hjälp av snabbsegment kan du snabbt skapa enkla segment (med en enskild operator) och med omedelbara insikter.</span><span class="sxs-lookup"><span data-stu-id="f3920-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="f3920-233">På sidan **Segment** välj **Ny** > **Snabbskapa från**.</span><span class="sxs-lookup"><span data-stu-id="f3920-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="f3920-234">Välj alternativet **profiler** för att skapa ett segment som baseras på entiteten för den enhetliga kunden.</span><span class="sxs-lookup"><span data-stu-id="f3920-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="f3920-235">Välj alternativet **mått** för att skapa ett segment runt varje kundattribut av typen av mått som du redan har skapat på sidan **mått**.</span><span class="sxs-lookup"><span data-stu-id="f3920-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="f3920-236">Markera alternativet **Intelligens** om du vill skapa ett segment runt en av de utdataentiteter som du skapade med funktionerna **prediktioner** eller **anpassade modeller**.</span><span class="sxs-lookup"><span data-stu-id="f3920-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="f3920-237">I dialogrutan **Nytt snabbsegment**, välj ett attribut i listrutan **Fält**.</span><span class="sxs-lookup"><span data-stu-id="f3920-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="f3920-238">Systemet tillhandahåller ytterligare insikter som hjälper dig att skapa bättre segment av dina kunder.</span><span class="sxs-lookup"><span data-stu-id="f3920-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="f3920-239">För kategorifält visas tio populära kundräkningar.</span><span class="sxs-lookup"><span data-stu-id="f3920-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="f3920-240">Välj ett **Värde** och välj **Granska**.</span><span class="sxs-lookup"><span data-stu-id="f3920-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="f3920-241">För ett numeriskt attribut visar systemet vilket attributvärde som faller under varje kunds percentil.</span><span class="sxs-lookup"><span data-stu-id="f3920-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="f3920-242">Välj en **operatör** och ett **värde** och välj sedan **granska**.</span><span class="sxs-lookup"><span data-stu-id="f3920-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="f3920-243">Systemet tillhandahåller en **uppskattad segmentstorlek**.</span><span class="sxs-lookup"><span data-stu-id="f3920-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="f3920-244">Du kan välja om du vill skapa ett segment som du har definierat eller om du först vill ha en annan segmentstorlek.</span><span class="sxs-lookup"><span data-stu-id="f3920-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f3920-245">![Namn och uppskattning för ett snabbsegment](media/quick-segment-name.png "Namn och uppskattning för ett snabbsegment")</span><span class="sxs-lookup"><span data-stu-id="f3920-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="f3920-246">Ange ett **namn** för ditt segment.</span><span class="sxs-lookup"><span data-stu-id="f3920-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="f3920-247">Eventuellt ge en **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="f3920-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="f3920-248">Välj **Spara** för att skapa segmentet.</span><span class="sxs-lookup"><span data-stu-id="f3920-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="f3920-249">När segmentet har bearbetat klart kan du visa det på samma sätt som andra segment som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="f3920-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="f3920-250">För följande scenarier rekommenderar vi att du använder segmentbyggare i stället för de rekommenderade segmenten:</span><span class="sxs-lookup"><span data-stu-id="f3920-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="f3920-251">Skapa segment med filter för kategorifält där operatorn är annorlunda än operatorn **Är**</span><span class="sxs-lookup"><span data-stu-id="f3920-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="f3920-252">Skapa segment med filter för numeriska fält där operatorn är annorlunda än operatorerna **Mellan**, **Större än** och **Mindre än**</span><span class="sxs-lookup"><span data-stu-id="f3920-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="f3920-253">Skapa segment med filter för datumtypfält</span><span class="sxs-lookup"><span data-stu-id="f3920-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="f3920-254">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f3920-254">Next steps</span></span>

<span data-ttu-id="f3920-255">[Exportera ett segment](export-destinations.md) och utforska [kundkortet](customer-card-add-in.md) och [kontakterna](export-power-bi.md) för att komma igång med kundnivån.</span><span class="sxs-lookup"><span data-stu-id="f3920-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]