---
title: Slå samman entiteter i datasammanslutningen
description: Slå samman entiteter för att skapa enhetliga kundprofiler.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305677"
---
# <a name="merge-entities"></a><span data-ttu-id="07488-103">Slå samman entiteter</span><span class="sxs-lookup"><span data-stu-id="07488-103">Merge entities</span></span>

<span data-ttu-id="07488-104">Sammanslagningsfasen är den sista fasen i föreningsprocessen för data.</span><span class="sxs-lookup"><span data-stu-id="07488-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="07488-105">Dess syfte avstäms av motstridiga data.</span><span class="sxs-lookup"><span data-stu-id="07488-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="07488-106">Exempel på data som är i konflikt kan vara ett kundnamn som finns i två av dina datauppsättningar, men som visar lite annorlunda i varje (“Grant Marshall” jämfört med “Grant Marshal”), eller ett telefonnummer som skiljer sig från formatet (617-803-091X jämfört med 617803091X).</span><span class="sxs-lookup"><span data-stu-id="07488-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="07488-107">Sammanfoga dessa motstridiga datapunkter görs på ett attribut till attributbasis.</span><span class="sxs-lookup"><span data-stu-id="07488-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Sammanslå sida i dataförlopp som visar tabell med kopplade fält som definierar den enhetliga kundprofilen.":::

<span data-ttu-id="07488-109">Efter att ha avslutat [matchningsfasen](match-entities.md) kan du starta sammanslagningsfasen genom att välja panelen **Sammanslagning** på sidan **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="07488-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="07488-110">Granska systemrekommendationer</span><span class="sxs-lookup"><span data-stu-id="07488-110">Review system recommendations</span></span>

<span data-ttu-id="07488-111">I **Data** > **Förena** > **Slå samman** väljer du och utesluter attribut att slå samman inom din enhetliga kundprofilenhet.</span><span class="sxs-lookup"><span data-stu-id="07488-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="07488-112">Den enhetliga kundprofilen är resultatet av dataföreningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="07488-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="07488-113">Vissa attribut slås samman automatiskt av systemet.</span><span class="sxs-lookup"><span data-stu-id="07488-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="07488-114">Om du vill visa attributen som ingår i ett av dina automatiskt kopplade attribut väljer du det kopplade attributet på fliken **Kundfält** i tabellen.</span><span class="sxs-lookup"><span data-stu-id="07488-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="07488-115">Attributen som utgör det sammankopplade attributet visas i två nya rader under det sammankopplade attributet.</span><span class="sxs-lookup"><span data-stu-id="07488-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="07488-116">Separera, byta namn på, utesluta och redigera kopplade fält</span><span class="sxs-lookup"><span data-stu-id="07488-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="07488-117">Du kan ändra hur systemet bearbetar kopplade attribut för att skapa en enhetlig kundprofil.</span><span class="sxs-lookup"><span data-stu-id="07488-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="07488-118">Välj **Visa fler** och välj vad du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="07488-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Alternativ i listrutan Visa fler för att hantera kopplade attribut.":::

<span data-ttu-id="07488-120">Mer information finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="07488-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="07488-121">Separera sammanslagna fält</span><span class="sxs-lookup"><span data-stu-id="07488-121">Separate merged fields</span></span>

<span data-ttu-id="07488-122">Om du vill separera sammanslagna fält hittar du attributet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="07488-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="07488-123">Separerade fält visas som enskilda datapunkter i den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="07488-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="07488-124">Välj det sammanslagna fältet.</span><span class="sxs-lookup"><span data-stu-id="07488-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="07488-125">Välj **Visa fler** och välj **Separata fält**.</span><span class="sxs-lookup"><span data-stu-id="07488-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="07488-126">Bekräfta separationen.</span><span class="sxs-lookup"><span data-stu-id="07488-126">Confirm the separation.</span></span>

1. <span data-ttu-id="07488-127">Välj **Spara** och **Kör** för att bearbeta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="07488-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="07488-128">Byta namn på kopplade fält</span><span class="sxs-lookup"><span data-stu-id="07488-128">Rename merged fields</span></span>

<span data-ttu-id="07488-129">Ändra visningsnamn kopplade attribut.</span><span class="sxs-lookup"><span data-stu-id="07488-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="07488-130">Du kan inte ändra namn på utdataentitet.</span><span class="sxs-lookup"><span data-stu-id="07488-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="07488-131">Välj det sammanslagna fältet.</span><span class="sxs-lookup"><span data-stu-id="07488-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="07488-132">Välj **Visa fler** och välj **Byt namn**.</span><span class="sxs-lookup"><span data-stu-id="07488-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="07488-133">Bekräfta det ändrade visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="07488-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="07488-134">Välj **Spara** och **Kör** för att bearbeta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="07488-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="07488-135">Utelämna sammanslagna fält</span><span class="sxs-lookup"><span data-stu-id="07488-135">Exclude merged fields</span></span>

<span data-ttu-id="07488-136">Utelämna ett attribut från den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="07488-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="07488-137">Om fältet används i andra processer, till exempel i ett segment, tar du bort det från dessa processer innan du utesluter det från kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="07488-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="07488-138">Välj det sammanslagna fältet.</span><span class="sxs-lookup"><span data-stu-id="07488-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="07488-139">Välj **Visa fler** och välj **Uteslut**.</span><span class="sxs-lookup"><span data-stu-id="07488-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="07488-140">Bekräfta uteslutningen.</span><span class="sxs-lookup"><span data-stu-id="07488-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="07488-141">Välj **Spara** och **Kör** för att bearbeta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="07488-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="07488-142">På sidan **Sammanslå**, välj **Uteslutna fält** om du vill visa listan över alla uteslutna fält.</span><span class="sxs-lookup"><span data-stu-id="07488-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="07488-143">I den här rutan kan du lägga till uteslutna fält bakåt.</span><span class="sxs-lookup"><span data-stu-id="07488-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="07488-144">Kombinera fält manuellt</span><span class="sxs-lookup"><span data-stu-id="07488-144">Manually combine fields</span></span>

<span data-ttu-id="07488-145">Ange ett kopplat attribut manuellt.</span><span class="sxs-lookup"><span data-stu-id="07488-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="07488-146">På sidan **Sammanslå**, välj **Kombinera fält**.</span><span class="sxs-lookup"><span data-stu-id="07488-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="07488-147">Ange ett **Namn** och ett **Utdatafältsnamn**.</span><span class="sxs-lookup"><span data-stu-id="07488-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="07488-148">Välj ett fält att lägga till.</span><span class="sxs-lookup"><span data-stu-id="07488-148">Choose a field to add.</span></span> <span data-ttu-id="07488-149">Välj **Lägg till fält** för att kombinera fler fält.</span><span class="sxs-lookup"><span data-stu-id="07488-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="07488-150">Bekräfta uteslutningen.</span><span class="sxs-lookup"><span data-stu-id="07488-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="07488-151">Välj **Spara** och **Kör** för att bearbeta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="07488-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="07488-152">Ändra ordning på fält</span><span class="sxs-lookup"><span data-stu-id="07488-152">Change the order of fields</span></span>

<span data-ttu-id="07488-153">Vissa entiteter innehåller mer information än andra.</span><span class="sxs-lookup"><span data-stu-id="07488-153">Some entities contain more details than others.</span></span> <span data-ttu-id="07488-154">Om en entitet innehåller de senaste data om ett fält kan du prioritera den framför andra entiteter när du kopplar samman värden.</span><span class="sxs-lookup"><span data-stu-id="07488-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="07488-155">Välj det sammanslagna fältet.</span><span class="sxs-lookup"><span data-stu-id="07488-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="07488-156">Välj **Visa fler** och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="07488-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="07488-157">I rutan **Kombinera fält**, välj **Flytta upp/ned** för att ange ordning eller dra och släpp dem i önskad position.</span><span class="sxs-lookup"><span data-stu-id="07488-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="07488-158">Bekräfta ändringen.</span><span class="sxs-lookup"><span data-stu-id="07488-158">Confirm the change.</span></span>

1. <span data-ttu-id="07488-159">Välj **Spara** och **Kör** för att bearbeta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="07488-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="07488-160">Kör din koppling</span><span class="sxs-lookup"><span data-stu-id="07488-160">Run your merge</span></span>

<span data-ttu-id="07488-161">Oavsett om du kopplar attribut manuellt eller låter systemet koppla ihop dem kan du alltid köra kopplingen.</span><span class="sxs-lookup"><span data-stu-id="07488-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="07488-162">Välj **Kör** på sidan **Koppla** för att starta processen.</span><span class="sxs-lookup"><span data-stu-id="07488-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="07488-163">![Datakoppling Spara och kör](media/configure-data-merge-save-run.png "Datakoppling Spara och kör")</span><span class="sxs-lookup"><span data-stu-id="07488-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="07488-164">Välj **Kör endast sammanslagning** om du bara vill visa utdata som reflekteras i entiteten för en enhetlig kund.</span><span class="sxs-lookup"><span data-stu-id="07488-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="07488-165">Processer nedströms uppdateras enligt vad som [definieras i uppdateringsschemat](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="07488-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="07488-166">Välj **Kör sammanslagnings- och nedströmsprocesser** om du vill uppdatera systemet med ändringarna.</span><span class="sxs-lookup"><span data-stu-id="07488-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="07488-167">Alla processer, inklusive berikning, segment och åtgärder, körs om automatiskt.</span><span class="sxs-lookup"><span data-stu-id="07488-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="07488-168">När alla processer nedströms har slutförts återspeglar kundprofilerna alla ändringar du har gjort.</span><span class="sxs-lookup"><span data-stu-id="07488-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="07488-169">Om du vill göra fler ändringar och köra steget igen kan du avbryta en pågående koppling.</span><span class="sxs-lookup"><span data-stu-id="07488-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="07488-170">Välj **Uppdatera...** och välj **Avbryt jobb** i sidorutan som visas.</span><span class="sxs-lookup"><span data-stu-id="07488-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="07488-171">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="07488-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="07488-172">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="07488-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="07488-173">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="07488-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="07488-174">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="07488-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="07488-175">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="07488-175">Next Step</span></span>

<span data-ttu-id="07488-176">Konfigurera [aktiviteter](activities.md), [berikning](enrichment-hub.md)eller [relationer](relationships.md) till mer information om kunderna.</span><span class="sxs-lookup"><span data-stu-id="07488-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="07488-177">Om du redan har konfigurerat aktiviteter, utökar eller segment, bearbetas de automatiskt för att använda de senaste kunddata.</span><span class="sxs-lookup"><span data-stu-id="07488-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
