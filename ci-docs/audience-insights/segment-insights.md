---
title: Segmentinsikter för befintliga segment
description: Få insikter om befintliga segment för att se skillnader och likheter.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595356"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="2579b-103">Segmentinsikter (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="2579b-103">Segment insights (preview)</span></span>

<span data-ttu-id="2579b-104">Upptäck ytterligare information och insikter kring de befintliga segmenten.</span><span class="sxs-lookup"><span data-stu-id="2579b-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="2579b-105">Ta reda på vad som skiljer mellan två segment och vad de har gemensamt.</span><span class="sxs-lookup"><span data-stu-id="2579b-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="2579b-106">Segmentöverlappning</span><span class="sxs-lookup"><span data-stu-id="2579b-106">Segment overlap</span></span>

<span data-ttu-id="2579b-107">Analysen av segmentöverlappnings visar hur många och vilka kunder som är gemensamma för två eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="2579b-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="2579b-108">Till exempel överlappar ett segment med kunder som ofta använder ett segment som innehåller kunder som är nöjd med din tjänst eller produkt.</span><span class="sxs-lookup"><span data-stu-id="2579b-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="2579b-109">Du kan också analysera hur överlappningen ändras för vissa attribut.</span><span class="sxs-lookup"><span data-stu-id="2579b-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="2579b-110">Köra en överlappande analys</span><span class="sxs-lookup"><span data-stu-id="2579b-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="2579b-111">Gå till **segment** och välj fliken **insikter (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="2579b-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="2579b-112">Välj **Nytt** och välj alternativet **Överlappa** i fönstret **Välj insiktstyp**.</span><span class="sxs-lookup"><span data-stu-id="2579b-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="2579b-113">Välj segmentet du vill och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2579b-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="2579b-114">Alternativt kan du välja ett eller flera intresseområden för att analysera överlappningar för alla möjliga fält värden och välja **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2579b-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="2579b-115">Ange ett namn för den överlappande analysen, ett valfritt visningsnamn och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2579b-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="2579b-116">Välj **Spara** för att starta analysen.</span><span class="sxs-lookup"><span data-stu-id="2579b-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="2579b-117">Den överlappande analysen är klar när status ändras från uppdatering till lyckad.</span><span class="sxs-lookup"><span data-stu-id="2579b-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="2579b-118">Visa och optimera en överlappningsanalys</span><span class="sxs-lookup"><span data-stu-id="2579b-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="2579b-119">När du har genomfört analysen hittar du detaljerad information om den här insikten på **Segment** > **Insikter (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="2579b-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Överlappande segmentinformation om insikter":::

<span data-ttu-id="2579b-121">Välj en insikt för att se resultatet av analysen:</span><span class="sxs-lookup"><span data-stu-id="2579b-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="2579b-122">Antalet medlemmar som överlappar de segment som valts för analys.</span><span class="sxs-lookup"><span data-stu-id="2579b-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="2579b-123">Antalet medlemmar som ingår i ett av segmenten men inte i resten av segmentet.</span><span class="sxs-lookup"><span data-stu-id="2579b-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="2579b-124">Om du valde fält när du konfigurerade överlappningsanalysen hittar du dem på motsvarande flikar.</span><span class="sxs-lookup"><span data-stu-id="2579b-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="2579b-125">Du kan använda listrutan för filter för att välja en autentiseringsnivå och tabellen längst ned visar motsvarande data.</span><span class="sxs-lookup"><span data-stu-id="2579b-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="2579b-126">Differentiatorer för segment</span><span class="sxs-lookup"><span data-stu-id="2579b-126">Segment differentiators</span></span>

<span data-ttu-id="2579b-127">Segmentdifferentieringar hjälper dig att ta reda på vad som skiljer ett segment från övriga kunder eller från ett annat segment.</span><span class="sxs-lookup"><span data-stu-id="2579b-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="2579b-128">Du behöver bara välja ett segment så identifierar systemet med de profilmappar och mått som kännetecknar det valda segmentet.</span><span class="sxs-lookup"><span data-stu-id="2579b-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="2579b-129">Köra en differentieringsanalys</span><span class="sxs-lookup"><span data-stu-id="2579b-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="2579b-130">Gå till **segment** och välj fliken **insikter (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="2579b-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="2579b-131">Välj **Nytt** och välj alternativet **Överlappa** i fönstret **Välj insiktstyp**.</span><span class="sxs-lookup"><span data-stu-id="2579b-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="2579b-132">Välj det segment du vill analysera som ett **primärt segment** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2579b-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="2579b-133">Välj **Alla kunder** eller ett **sekundärt segment** för att jämföra det primära segmentet med och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2579b-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="2579b-134">Alternativt kan du välja ett eller flera intresseområden för att fokusera analysen på specifika attribut och välja **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2579b-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="2579b-135">Ange ett namn för den överlappande analysen, ett valfritt visningsnamn och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2579b-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="2579b-136">Välj **Spara** för att starta analysen.</span><span class="sxs-lookup"><span data-stu-id="2579b-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="2579b-137">Den överlappande analysen är klar när status ändras från uppdatering till lyckad.</span><span class="sxs-lookup"><span data-stu-id="2579b-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="2579b-138">Visa och optimera en differentieringsanalys</span><span class="sxs-lookup"><span data-stu-id="2579b-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="2579b-139">När du har genomfört analysen hittar du detaljerad information om den här insikten på **Segment** > **Insikter (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="2579b-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segmentdifferentieringar om insikter":::

<span data-ttu-id="2579b-141">Välj en insikt för att se resultatet av analysen.</span><span class="sxs-lookup"><span data-stu-id="2579b-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="2579b-142">En differentieringsanalys innehåller två flikar.</span><span class="sxs-lookup"><span data-stu-id="2579b-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="2579b-143">På fliken **attribut** anges de profilmappar som betraktas som differentieringar.</span><span class="sxs-lookup"><span data-stu-id="2579b-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="2579b-144">På fliken **mått** en lista över differentieringarna.</span><span class="sxs-lookup"><span data-stu-id="2579b-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="2579b-145">Varje flik innehåller följande detaljer:</span><span class="sxs-lookup"><span data-stu-id="2579b-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="2579b-146">Rangordnad lista med differentieringar sorterade efter poäng.</span><span class="sxs-lookup"><span data-stu-id="2579b-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="2579b-147">**Differenspoängen** för varje differentiering.</span><span class="sxs-lookup"><span data-stu-id="2579b-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="2579b-148">Differensenspoäng representerar graden av skillnad på ett attribut mellan två segment.</span><span class="sxs-lookup"><span data-stu-id="2579b-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="2579b-149">Ju högre differenspoängen är, desto fler attribut skiljer sig mellan de två segmenten.</span><span class="sxs-lookup"><span data-stu-id="2579b-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="2579b-150">Välj en poäng om du vill öppna fönster **differensenspoäng** med fördelningarna för de attributen.</span><span class="sxs-lookup"><span data-stu-id="2579b-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="2579b-151">Hantera segmentinsikter</span><span class="sxs-lookup"><span data-stu-id="2579b-151">Manage segment insights</span></span>

<span data-ttu-id="2579b-152">Du kan använda följande alternativ för dina insikter från kommandofältet:</span><span class="sxs-lookup"><span data-stu-id="2579b-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="2579b-153">**Tillbaka** för att returnera listan med insikter</span><span class="sxs-lookup"><span data-stu-id="2579b-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="2579b-154">**Uppdatera** om du vill köra analysen igen</span><span class="sxs-lookup"><span data-stu-id="2579b-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="2579b-155">**Ta bort** och ta bort insikt</span><span class="sxs-lookup"><span data-stu-id="2579b-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]