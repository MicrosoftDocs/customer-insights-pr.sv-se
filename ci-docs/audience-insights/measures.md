---
title: Skapa och redigera åtgärder
description: Definiera kundrelaterade åtgärder för att analysera och avspegla resultat för vissa affärsområden.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407104"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="458d3-103">Definiera och hantera mått</span><span class="sxs-lookup"><span data-stu-id="458d3-103">Define and manage measures</span></span>

<span data-ttu-id="458d3-104">**Mått** representerar KPI:er som avspeglar prestanda och hälsa för specifika affärsområden.</span><span class="sxs-lookup"><span data-stu-id="458d3-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="458d3-105">Målgruppsinsikter ger en intuitiv upplevelse för att bygga olika typer av åtgärder, med hjälp av en frågebyggare som inte kräver att du kodar eller validerar dina åtgärder manuellt.</span><span class="sxs-lookup"><span data-stu-id="458d3-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="458d3-106">**Du kan spåra dina affärsmått på startsidan**, visa mått för specifika kunder på **kundkortet** och använda mått för att definiera kundsegment på sidan **segment**.</span><span class="sxs-lookup"><span data-stu-id="458d3-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="458d3-107">Skapa ett mått</span><span class="sxs-lookup"><span data-stu-id="458d3-107">Create a measure</span></span>

<span data-ttu-id="458d3-108">Det här avsnittet innehåller stegvisa anvisningar om hur du skapar ett mått från grunden.</span><span class="sxs-lookup"><span data-stu-id="458d3-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="458d3-109">Du kan skapa mått med data från flera datakällor som är anslutna via entiteten kund.</span><span class="sxs-lookup"><span data-stu-id="458d3-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="458d3-110">Vissa [servicegränser](service-limits.md) gäller.</span><span class="sxs-lookup"><span data-stu-id="458d3-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="458d3-111">I målgruppsinsikter går du till **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="458d3-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="458d3-112">Välj **nytt mått**.</span><span class="sxs-lookup"><span data-stu-id="458d3-112">Select **New measure**.</span></span>

3. <span data-ttu-id="458d3-113">Välj en mått **typ**:</span><span class="sxs-lookup"><span data-stu-id="458d3-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="458d3-114">**Kundattribut**: ett enskilt fält per kund som visar poäng, värde eller tillstånd för kunden.</span><span class="sxs-lookup"><span data-stu-id="458d3-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="458d3-115">Kundattribut skapas som attribut i en ny systemgenererad entitet som kallas **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="458d3-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="458d3-116">**Kundmått**: insikt för kundbeteende med uppdelning efter valda dimensioner.</span><span class="sxs-lookup"><span data-stu-id="458d3-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="458d3-117">En ny entitet skapas för varje mått, eventuellt med flera poster per kund.</span><span class="sxs-lookup"><span data-stu-id="458d3-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="458d3-118">**Affärsmått**: spårar företagets affärsprestanda och hälsa.</span><span class="sxs-lookup"><span data-stu-id="458d3-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="458d3-119">Affärsmått kan ha två olika utgångar: ett numeriskt resultat som visas på **startsidan** eller en ny entitet som du hittar på sidan **entiteter**.</span><span class="sxs-lookup"><span data-stu-id="458d3-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="458d3-120">Ange ett **namn** och ett valfritt **visningsnamn** och välj sedan **nästa**.</span><span class="sxs-lookup"><span data-stu-id="458d3-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="458d3-121">I avsnittet **Entiteter**, markera den första entiteten från listrutan.</span><span class="sxs-lookup"><span data-stu-id="458d3-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="458d3-122">I det här skedet bör du bestämma om ytterligare entiteter behövs som en del av måttdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="458d3-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="458d3-123">![Måttdefinition](media/measure-definition.png "Måttdefinition")</span><span class="sxs-lookup"><span data-stu-id="458d3-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="458d3-124">Om du vill lägga till fler entiteter väljer du **Lägg till entitet** och markerar de entiteter du vill använda för måttet.</span><span class="sxs-lookup"><span data-stu-id="458d3-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="458d3-125">Du kan bara välja entiteter som har förhållanden till din utgångsenhet.</span><span class="sxs-lookup"><span data-stu-id="458d3-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="458d3-126">För mer information om hur du definierar relationer, se [relationer](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="458d3-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="458d3-127">Du kan även konfigurera variabler.</span><span class="sxs-lookup"><span data-stu-id="458d3-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="458d3-128">I avsnittet **Variabler**, välj **Ny variabel**.</span><span class="sxs-lookup"><span data-stu-id="458d3-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="458d3-129">Variabler är beräkningar som görs för varje markerad post.</span><span class="sxs-lookup"><span data-stu-id="458d3-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="458d3-130">Exempel: summering av kassa (POS) och försäljning online för varje kunds post.</span><span class="sxs-lookup"><span data-stu-id="458d3-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="458d3-131">Ange ett **Namn** för variabeln.</span><span class="sxs-lookup"><span data-stu-id="458d3-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="458d3-132">I området **Uttryck** area, välj ett fält att börja din beräkning med.</span><span class="sxs-lookup"><span data-stu-id="458d3-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="458d3-133">Skriv ett uttryck i området **uttryck** och välj fler fält som ska ingå i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="458d3-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="458d3-134">För närvarande stöds endast aritmetiska uttryck.</span><span class="sxs-lookup"><span data-stu-id="458d3-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="458d3-135">Variabla beräkningar stöds inte för entiteter från olika [entitetssökvägar](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="458d3-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="458d3-136">Markera **Klart**.</span><span class="sxs-lookup"><span data-stu-id="458d3-136">Select **Done**.</span></span>

11. <span data-ttu-id="458d3-137">I avsnittet **måttdefinition** anger du hur valda entiteter och beräknade variabler ska slås samman i en ny måttentitet eller ett nytt attribut.</span><span class="sxs-lookup"><span data-stu-id="458d3-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="458d3-138">Välj **Ny dimension**.</span><span class="sxs-lookup"><span data-stu-id="458d3-138">Select **New dimension**.</span></span> <span data-ttu-id="458d3-139">Du kan betrakta som en dimension som en funktion *gruppera efter*.</span><span class="sxs-lookup"><span data-stu-id="458d3-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="458d3-140">Utdata för måttenheten eller attributet grupperas efter alla definierade dimensioner.</span><span class="sxs-lookup"><span data-stu-id="458d3-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="458d3-141">![Välj aggregeringscykel](media/measures-businessreport-measure-definition2.png "Välj aggregeringscykel")</span><span class="sxs-lookup"><span data-stu-id="458d3-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="458d3-142">Välj eller ange följande information som en del av dimensionens definition:</span><span class="sxs-lookup"><span data-stu-id="458d3-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="458d3-143">**Entitet**: om du definierar en måttentitet ska den innehålla minst ett attribut.</span><span class="sxs-lookup"><span data-stu-id="458d3-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="458d3-144">Om du definierar ett måttattribut tas endast ett attribut med som standard.</span><span class="sxs-lookup"><span data-stu-id="458d3-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="458d3-145">Det här alternativet är att välja entiteten som innehåller attributet.</span><span class="sxs-lookup"><span data-stu-id="458d3-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="458d3-146">**Fält**: Välj det specifika attribut som ska ingå antingen i måttentiteten eller attributet.</span><span class="sxs-lookup"><span data-stu-id="458d3-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="458d3-147">**Bucket**: Välj om du vill samla in data per dag, månad eller år.</span><span class="sxs-lookup"><span data-stu-id="458d3-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="458d3-148">Det är endast ett obligatoriskt val om du har valt attribut av datumtyp.</span><span class="sxs-lookup"><span data-stu-id="458d3-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="458d3-149">**Som**: anger namnet på det nya fältet.</span><span class="sxs-lookup"><span data-stu-id="458d3-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="458d3-150">**Visningsnamn**: definierar fältets visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="458d3-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="458d3-151">Ditt affärsmått sparas som en entitet med en siffra och visas på **Startsidan** såvida du inte lägger till fler dimensioner i ditt mått.</span><span class="sxs-lookup"><span data-stu-id="458d3-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="458d3-152">När du har lagt till fler dimensioner visas *inte* måttet på **Startsidan**.</span><span class="sxs-lookup"><span data-stu-id="458d3-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="458d3-153">Alternativt kan du lägga till aggregeringsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="458d3-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="458d3-154">En aggregering som du skapar resulterar i ett nytt värde inom måttentiteten eller attributet.</span><span class="sxs-lookup"><span data-stu-id="458d3-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="458d3-155">Aggregeringsfunktioner som stöds är: **Min**, **Max**, **Genomsnitt**, **Median**, **Summa**, **Antal unika**, **Först** (tar den första posten i ett dimensionsvärde) och **Sista** (tar den sista posten till ett dimensionsvärde).</span><span class="sxs-lookup"><span data-stu-id="458d3-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="458d3-156">Välj **Spara** för att spara ändringarna till måttet.</span><span class="sxs-lookup"><span data-stu-id="458d3-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="458d3-157">Hantera dina mått</span><span class="sxs-lookup"><span data-stu-id="458d3-157">Manage your measures</span></span>

<span data-ttu-id="458d3-158">När du har skapat minst en åtgärd visas en lista med åtgärder på sidan **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="458d3-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="458d3-159">Du hittar information om måttypen, skaparen, datumet och tiden för att skapa datum och tid, senast redigerad, status (om måttet är aktivt, inaktivt eller misslyckat) och datum och tid för senaste uppdatering.</span><span class="sxs-lookup"><span data-stu-id="458d3-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="458d3-160">När du väljer ett mått i listan kan du visa en förhandsgranskning av resultatet.</span><span class="sxs-lookup"><span data-stu-id="458d3-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="458d3-161">Om du vill uppdatera alla dina åtgärder samtidigt markerar du **Uppdatera allt** utan att välja ett specifikt mått.</span><span class="sxs-lookup"><span data-stu-id="458d3-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="458d3-162">![Åtgärder för att hantera enskilda mått](media/measure-actions.png "Åtgärder för att hantera enskilda mått")</span><span class="sxs-lookup"><span data-stu-id="458d3-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="458d3-163">Du kan också välja ett mått i listan och utföra någon av följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="458d3-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="458d3-164">Markera måttets namn om du vill se detaljerna.</span><span class="sxs-lookup"><span data-stu-id="458d3-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="458d3-165">**Redigera** måttets konfiguration.</span><span class="sxs-lookup"><span data-stu-id="458d3-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="458d3-166">**Byt namn** på mått.</span><span class="sxs-lookup"><span data-stu-id="458d3-166">**Rename** the measure.</span></span>
- <span data-ttu-id="458d3-167">**Ta bort** måttet.</span><span class="sxs-lookup"><span data-stu-id="458d3-167">**Delete** the measure.</span></span>
- <span data-ttu-id="458d3-168">Välj tre punkter (...) och sedan **uppdatera** för att starta uppdateringsprocessen för måttet.</span><span class="sxs-lookup"><span data-stu-id="458d3-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="458d3-169">Välj tre punkter (...) och **Hämta** för att hämta en .CSV-fil av måttet.</span><span class="sxs-lookup"><span data-stu-id="458d3-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="458d3-170">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="458d3-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="458d3-171">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="458d3-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="458d3-172">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="458d3-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="458d3-173">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="458d3-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="458d3-174">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="458d3-174">Next step</span></span>

<span data-ttu-id="458d3-175">Du använder befintliga mått för att skapa ditt första kundsegment på sidan **segment**.</span><span class="sxs-lookup"><span data-stu-id="458d3-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="458d3-176">Mer information finns [Segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="458d3-176">For more information, see [Segments](segments.md).</span></span>
