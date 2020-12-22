---
title: Slå samman entiteter i datasammanslutningen
description: Slå samman entiteter för att skapa enhetliga kundprofiler.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407101"
---
# <a name="merge-entities"></a><span data-ttu-id="c1960-103">Slå samman entiteter</span><span class="sxs-lookup"><span data-stu-id="c1960-103">Merge entities</span></span>

<span data-ttu-id="c1960-104">Sammanslagningsfasen är den sista fasen i föreningsprocessen för data.</span><span class="sxs-lookup"><span data-stu-id="c1960-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="c1960-105">Dess syfte avstäms av motstridiga data.</span><span class="sxs-lookup"><span data-stu-id="c1960-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="c1960-106">Exempel på data som är i konflikt kan vara ett kundnamn som finns i två av dina datauppsättningar, men som visar lite annorlunda i varje (“Grant Marshall” jämfört med “Grant Marshal”), eller ett telefonnummer som skiljer sig från formatet (617-803-091X jämfört med 617803091X).</span><span class="sxs-lookup"><span data-stu-id="c1960-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="c1960-107">Sammanfoga dessa motstridiga datapunkter görs på ett attribut till attributbasis.</span><span class="sxs-lookup"><span data-stu-id="c1960-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="c1960-108">Efter att ha avslutat [matchningsfasen](match-entities.md) kan du starta sammanslagningsfasen genom att välja panelen **Sammanslagning** på sidan **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="c1960-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="c1960-109">Granska systemrekommendationer</span><span class="sxs-lookup"><span data-stu-id="c1960-109">Review system recommendations</span></span>

<span data-ttu-id="c1960-110">På sidan **Sammanslå** kan du välja och exkludera attribut som ska slås samman i entiteten enhetlig kundprofil (resultatet av konfigurationsprocessen).</span><span class="sxs-lookup"><span data-stu-id="c1960-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="c1960-111">Vissa attribut slås samman automatiskt av systemet.</span><span class="sxs-lookup"><span data-stu-id="c1960-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="c1960-112">Visa sammankopplade attribut</span><span class="sxs-lookup"><span data-stu-id="c1960-112">View merged attributes</span></span>

<span data-ttu-id="c1960-113">Om du vill visa de attribut som är inkluderade i ett av de automatiskt sammankopplade attributen markerar du det sammankopplade attributet.</span><span class="sxs-lookup"><span data-stu-id="c1960-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="c1960-114">De två attributen som utgör det sammankopplade attributet visas i två nya rader under det sammankopplade attributet.</span><span class="sxs-lookup"><span data-stu-id="c1960-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c1960-115">![Välj sammankopplade attribut](media/configure-data-merge-profile-attributes.png "Välj sammankopplade attribut")</span><span class="sxs-lookup"><span data-stu-id="c1960-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="c1960-116">Separata sammankopplade attribut</span><span class="sxs-lookup"><span data-stu-id="c1960-116">Separate merged attributes</span></span>

<span data-ttu-id="c1960-117">Om du vill separera eller ta isär de automatiskt sammankopplade attributen kan du söka efter attributet i tabellen i **profilattribut**.</span><span class="sxs-lookup"><span data-stu-id="c1960-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="c1960-118">Markera ellips-knappen (...) .</span><span class="sxs-lookup"><span data-stu-id="c1960-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="c1960-119">Välj i listrutan **Separata fält**.</span><span class="sxs-lookup"><span data-stu-id="c1960-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="c1960-120">Ta bort sammankopplade attribut</span><span class="sxs-lookup"><span data-stu-id="c1960-120">Remove merged attributes</span></span>

<span data-ttu-id="c1960-121">Om du vill utesluta ett attribut från den slutgiltiga entiteten för kundprofilen söker du efter **Profilattribut**.</span><span class="sxs-lookup"><span data-stu-id="c1960-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="c1960-122">Markera ellips-knappen (...) .</span><span class="sxs-lookup"><span data-stu-id="c1960-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="c1960-123">Välj i listrutan **Koppla inte**.</span><span class="sxs-lookup"><span data-stu-id="c1960-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="c1960-124">Attributet flyttas till avsnittet **borttaget från kundpost**.</span><span class="sxs-lookup"><span data-stu-id="c1960-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="c1960-125">Lägg till ett sammankopplat attribut manuellt</span><span class="sxs-lookup"><span data-stu-id="c1960-125">Manually add a merged attribute</span></span>

<span data-ttu-id="c1960-126">Om du vill lägga till ett kopplar attribut går du till sidan **Koppla**.</span><span class="sxs-lookup"><span data-stu-id="c1960-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="c1960-127">Välj **Lägg till sammankopplade attribut**.</span><span class="sxs-lookup"><span data-stu-id="c1960-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="c1960-128">Ange ett **namn** för att identifiera det på sidan **Koppla** senare.</span><span class="sxs-lookup"><span data-stu-id="c1960-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="c1960-129">Alternativt kan du ange ett **visningsnamn** som ska visas i entiteten för den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="c1960-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="c1960-130">Konfigurera **Markera dubblettattribut** för att välja de attribut som du vill koppla från de matchade entiteterna.</span><span class="sxs-lookup"><span data-stu-id="c1960-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="c1960-131">Du kan även söka efter attribut.</span><span class="sxs-lookup"><span data-stu-id="c1960-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="c1960-132">Ange **rangordna efter prioritet** om du vill prioritera ett attribut ovanför de övriga.</span><span class="sxs-lookup"><span data-stu-id="c1960-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="c1960-133">Till exempel om entiteten *WebAccountCSV* innehåller den mest exakta informationen om attributet *fullständigt namn* kan du prioritera den här entiteten *ContactCSV* genom att välja *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="c1960-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="c1960-134">Detta innebär att *WebAccountCSV* flyttar till den första prioriteten medan *ContactCSV* flyttar till den andra prioriteten när de hämtar värden för attributet *fullständigt namn*.</span><span class="sxs-lookup"><span data-stu-id="c1960-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="c1960-135">Kör din koppling</span><span class="sxs-lookup"><span data-stu-id="c1960-135">Run your merge</span></span>

<span data-ttu-id="c1960-136">Oavsett om du kopplar attribut manuellt eller låter systemet koppla ihop dem kan du alltid köra kopplingen.</span><span class="sxs-lookup"><span data-stu-id="c1960-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="c1960-137">Välj **Kör** på sidan **Koppla** för att starta processen.</span><span class="sxs-lookup"><span data-stu-id="c1960-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c1960-138">![Datakoppling Spara och kör](media/configure-data-merge-save-run.png "Datakoppling Spara och kör")</span><span class="sxs-lookup"><span data-stu-id="c1960-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="c1960-139">Om du vill göra ytterligare ändringar och köra steget igen kan du avbryta en pågående koppling.</span><span class="sxs-lookup"><span data-stu-id="c1960-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="c1960-140">Välj **Uppdatera...** och välj **Avbryt jobb** i sidorutan som visas.</span><span class="sxs-lookup"><span data-stu-id="c1960-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="c1960-141">Efter att texten **Uppdaterar...** ändras till **Lyckad**, men sammanslagning har slutfört och löst motstridig information i enlighet med de principer du angav.</span><span class="sxs-lookup"><span data-stu-id="c1960-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="c1960-142">Sammanslagna och inte sammanslagna attribut ingår i entiteten Enhetliga profiler.</span><span class="sxs-lookup"><span data-stu-id="c1960-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="c1960-143">Utelämnade attribut ingår inte i entiteten Enhetliga profiler.</span><span class="sxs-lookup"><span data-stu-id="c1960-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="c1960-144">Om det inte var första gången som du körde en sammanslagning, kommer alla efterföljande processer, inklusive berikning, segmentering och mått att köras igen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c1960-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="c1960-145">När alla efterföljande processer har körts igen återspeglas de ändringar du har gjort i kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="c1960-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="c1960-146">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="c1960-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c1960-147">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c1960-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c1960-148">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="c1960-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c1960-149">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="c1960-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="c1960-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c1960-150">Next Step</span></span>

<span data-ttu-id="c1960-151">Konfigurera [aktiviteter](activities.md), [berikning](enrichment-microsoft-graph.md)eller [relationer](relationships.md) till mer information om kunderna.</span><span class="sxs-lookup"><span data-stu-id="c1960-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="c1960-152">Om du redan har konfigurerat aktiviteter, berikning eller relationer eller om du har definierat segment, bearbetas de automatiskt så att de senaste kunddata används.</span><span class="sxs-lookup"><span data-stu-id="c1960-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


