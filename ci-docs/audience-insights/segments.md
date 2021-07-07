---
title: Segments i målgruppsinsikter
description: Översikt över segment och hur du skapar och hanterar dem.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306279"
---
# <a name="segments-overview"></a><span data-ttu-id="ba09d-103">Segment – översikt</span><span class="sxs-lookup"><span data-stu-id="ba09d-103">Segments overview</span></span>

<span data-ttu-id="ba09d-104">Med segment kan du gruppera dina kunder baserat på demografiska attribut, transaktionella eller beteendemässiga attribut.</span><span class="sxs-lookup"><span data-stu-id="ba09d-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="ba09d-105">Du kan använda segment för att rikta reklamkampanjer, säljaktiviteter och kundsupport för att uppnå dina affärsmål.</span><span class="sxs-lookup"><span data-stu-id="ba09d-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="ba09d-106">Kundprofiler som överensstämmer med filter för en segmentdefinition kallas *medlemmar* i ett segment.</span><span class="sxs-lookup"><span data-stu-id="ba09d-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="ba09d-107">Vissa [servicegränser](service-limits.md) gäller.</span><span class="sxs-lookup"><span data-stu-id="ba09d-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="ba09d-108">Skapa ett nytt segment</span><span class="sxs-lookup"><span data-stu-id="ba09d-108">Create a new segment</span></span>

<span data-ttu-id="ba09d-109">Du kan skapa ett nytt segment på flera sätt:</span><span class="sxs-lookup"><span data-stu-id="ba09d-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="ba09d-110">Komplext segment med segmentverktyget: [Tomt segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="ba09d-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="ba09d-111">Enkla segment med en operator: [Snabbsegment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="ba09d-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="ba09d-112">AI-drivet sätt att hitta liknande kunder: [Liknande kunder](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="ba09d-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="ba09d-113">AI-drivna förslag baserade på mått eller attribut: [Förslag på segment för att förbättra åtgärder](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="ba09d-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="ba09d-114">Förslag utifrån aktiviteter: [Förslag på segment utifrån kundaktivitet](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="ba09d-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="ba09d-115">Hantera befintliga segment</span><span class="sxs-lookup"><span data-stu-id="ba09d-115">Manage existing segments</span></span>

<span data-ttu-id="ba09d-116">Gå till sidan **Segment** om du vill visa alla sparade segment och hantera dem.</span><span class="sxs-lookup"><span data-stu-id="ba09d-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="ba09d-117">Varje segment representeras av en rad som innehåller ytterligare information om segmentet.</span><span class="sxs-lookup"><span data-stu-id="ba09d-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valt segment med alternativlistrutan och tillgängliga alternativ.":::

<span data-ttu-id="ba09d-119">Följande åtgärd är tillgänglig när du väljer ett segment:</span><span class="sxs-lookup"><span data-stu-id="ba09d-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="ba09d-120">**Visa** information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="ba09d-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="ba09d-121">**Redigera** segmentet om du vill ändra dess egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ba09d-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="ba09d-122">**Skapa dubblett** av ett segment.</span><span class="sxs-lookup"><span data-stu-id="ba09d-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="ba09d-123">Du kan välja att redigera egenskaperna direkt eller bara spara dubbletten.</span><span class="sxs-lookup"><span data-stu-id="ba09d-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="ba09d-124">**Uppdatera** segmentet så att det omfattar senaste data.</span><span class="sxs-lookup"><span data-stu-id="ba09d-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="ba09d-125">**Aktivera** eller **Inaktivera** segmentet.</span><span class="sxs-lookup"><span data-stu-id="ba09d-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="ba09d-126">Segment har två möjliga tillstånd - aktiva eller inaktiva.</span><span class="sxs-lookup"><span data-stu-id="ba09d-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="ba09d-127">Dessa tillstånd har praktiskt taget när de redigerar ett segment.</span><span class="sxs-lookup"><span data-stu-id="ba09d-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="ba09d-128">För inaktiva segment finns segmentdefinitionen, men den innehåller inga kunder ännu.</span><span class="sxs-lookup"><span data-stu-id="ba09d-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="ba09d-129">När du aktiverar ett segment ändras dess status från "inaktivt" till "aktivt" och sökningen börjar söka efter kunder som matchar segmentdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="ba09d-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="ba09d-130">Om en [schemalagd uppdatering](system.md#schedule-tab) har konfigurerats har inaktiva segment **Status** anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats.</span><span class="sxs-lookup"><span data-stu-id="ba09d-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="ba09d-131">När ett inaktivt segment aktiveras uppdateras och tas med i schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="ba09d-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="ba09d-132">Du kan också använda funktionen **Schemalägg senare** i listrutan **Aktivera/inaktivera** för att ange ett framtida datum och tid för aktivering och inaktivering av ett visst segment.</span><span class="sxs-lookup"><span data-stu-id="ba09d-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="ba09d-133">**Byt namn** på segment.</span><span class="sxs-lookup"><span data-stu-id="ba09d-133">**Rename** the segment.</span></span>
- <span data-ttu-id="ba09d-134">**Hämta** listan över medlemmar som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="ba09d-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="ba09d-135">**Hantera export** för att se exportrelaterade segment och hantera dem.</span><span class="sxs-lookup"><span data-stu-id="ba09d-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="ba09d-136">Läs mer om exporter.</span><span class="sxs-lookup"><span data-stu-id="ba09d-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="ba09d-137">**Ta bort** segment.</span><span class="sxs-lookup"><span data-stu-id="ba09d-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="ba09d-138">Uppdatera segment</span><span class="sxs-lookup"><span data-stu-id="ba09d-138">Refresh segments</span></span>

<span data-ttu-id="ba09d-139">Du kan uppdatera alla segment på en gång genom att markera **Uppdatera alla** på sidan **Segment**, eller också kan du uppdatera ett eller flera segment när du markerar dem och väljer **Uppdatera** bland alternativen.</span><span class="sxs-lookup"><span data-stu-id="ba09d-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="ba09d-140">Du kan även konfigurera en återkommande uppdatering på **Administratör** > **System** > **Schemalägg**.</span><span class="sxs-lookup"><span data-stu-id="ba09d-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="ba09d-141">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="ba09d-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ba09d-142">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ba09d-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ba09d-143">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="ba09d-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ba09d-144">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="ba09d-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="ba09d-145">Exportera segment</span><span class="sxs-lookup"><span data-stu-id="ba09d-145">Export segments</span></span>

<span data-ttu-id="ba09d-146">Du kan exportera ett segment från segmentsidan eller [exportsidan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ba09d-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="ba09d-147">Gå till sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="ba09d-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="ba09d-148">Välj **Visa mer [...]** för det segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="ba09d-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="ba09d-149">Välj **Hantera exporter** i listrutan Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ba09d-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="ba09d-150">Sidan **Exporter (förhandsversion) för segment** öppnas.</span><span class="sxs-lookup"><span data-stu-id="ba09d-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="ba09d-151">Du kan se alla konfigurerade exporter grupperade efter export som innehåller det aktuella segmentet eller inte innehåller det.</span><span class="sxs-lookup"><span data-stu-id="ba09d-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="ba09d-152">Om du vill lägga till det valda segmentet i en export markerar du exporten i listan och väljer **Lägg till segment**.</span><span class="sxs-lookup"><span data-stu-id="ba09d-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="ba09d-153">Om du vill skapa en ny export med det markerade segmentet väljer du **Lägg till export**.</span><span class="sxs-lookup"><span data-stu-id="ba09d-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="ba09d-154">Mer information om hur du skapar export finns i [Konfigurera en ny export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ba09d-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ba09d-155">Välj **Tillbaka** för att gå tillbaka till huvudsidan för segment.</span><span class="sxs-lookup"><span data-stu-id="ba09d-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="ba09d-156">Visa historik- och segmentmedlemmar för bearbetning</span><span class="sxs-lookup"><span data-stu-id="ba09d-156">View processing history and segment members</span></span>

<span data-ttu-id="ba09d-157">Du kan visa konsoliderade data om ett segment genom att granska dess detaljer.</span><span class="sxs-lookup"><span data-stu-id="ba09d-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="ba09d-158">På sidan **Segment**, välj det segment du vill granska.</span><span class="sxs-lookup"><span data-stu-id="ba09d-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="ba09d-159">Den övre delen av sidan innehåller ett trenddiagram som visualiserar ändringar i medlemsantal.</span><span class="sxs-lookup"><span data-stu-id="ba09d-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="ba09d-160">Hovra över datapunkter om du vill visa antal medlemmar för ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="ba09d-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="ba09d-161">Du kan uppdatera visualiseringens tidsram.</span><span class="sxs-lookup"><span data-stu-id="ba09d-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba09d-162">![Tidsintervall för segment](media/segment-time-range.png "Tidsintervall för segment")</span><span class="sxs-lookup"><span data-stu-id="ba09d-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="ba09d-163">Den nedre delen innehåller en lista över segmentets medlemmar.</span><span class="sxs-lookup"><span data-stu-id="ba09d-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="ba09d-164">Fält som visas i listan bygger på attributen för segmentets entiteter.</span><span class="sxs-lookup"><span data-stu-id="ba09d-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="ba09d-165">Listan är en förhandsgranskning av de matchande segmentmedlemmarna och visar de första 100 posterna för ditt segment så att du snabbt kan utvärdera den och granska dess definitioner om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ba09d-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="ba09d-166">Om du vill visa alla matchande poster måste du [exportera segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ba09d-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
