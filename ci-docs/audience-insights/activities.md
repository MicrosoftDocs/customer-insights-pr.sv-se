---
title: Kundaktiviteter
description: Definiera kundaktiviteter och visa dem på tidslinjen för kunden.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596751"
---
# <a name="customer-activities"></a><span data-ttu-id="664bc-103">Kundaktiviteter</span><span class="sxs-lookup"><span data-stu-id="664bc-103">Customer activities</span></span>

<span data-ttu-id="664bc-104">Kombinera kundaktiviteter från [olika datakällor](data-sources.md) i Dynamics 365 Customer Insights och skapa en kundtidslinje som visar aktiviteterna i kronologisk ordning.</span><span class="sxs-lookup"><span data-stu-id="664bc-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="664bc-105">Du kan lägga till tidslinjen i appar för kundengagemang i Dynamics 365 via [tillägget kundkort](customer-card-add-in.md) eller på en Power BI-instrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="664bc-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="664bc-106">Definiera en aktivitet</span><span class="sxs-lookup"><span data-stu-id="664bc-106">Define an activity</span></span>

<span data-ttu-id="664bc-107">Dina datakällor innehåller entiteter med transaktions- och aktivitetsdata från flera datakällor.</span><span class="sxs-lookup"><span data-stu-id="664bc-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="664bc-108">Identifiera entiteterna och välj de aktiviteter du vill visa på kundens tidslinje.</span><span class="sxs-lookup"><span data-stu-id="664bc-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="664bc-109">Välj den entitet som innehåller målaktiviteten eller aktiviteterna.</span><span class="sxs-lookup"><span data-stu-id="664bc-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="664bc-110">I målgruppsinsikter går du till **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="664bc-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="664bc-111">Välj **Lägg till aktivitet**.</span><span class="sxs-lookup"><span data-stu-id="664bc-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="664bc-112">En entitet måste ha minst ett attribut av typen **Datum** för att kunna tas med i en kundtidslinje och du kan inte lägga till entiteter utan **datum**-fält.</span><span class="sxs-lookup"><span data-stu-id="664bc-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="664bc-113">Kontrollen **Lägg till aktivitet** är inaktiverad om ingen sådan entitet hittas.</span><span class="sxs-lookup"><span data-stu-id="664bc-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="664bc-114">I rutan **Lägg till aktivitet** ställa in värdena för följande fält:</span><span class="sxs-lookup"><span data-stu-id="664bc-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="664bc-115">**Entitet**: Välj en entitet som innehåller transaktions- eller aktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="664bc-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="664bc-116">**Primärnyckeln**: Välj fältet som används för unik identifiering av en post.</span><span class="sxs-lookup"><span data-stu-id="664bc-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="664bc-117">Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.</span><span class="sxs-lookup"><span data-stu-id="664bc-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="664bc-118">**Tidsstämpel**: Välj det fält som representerar starttiden för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="664bc-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="664bc-119">**Händelse**: Välj det fält som utgör händelsen för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="664bc-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="664bc-120">**Webbadress**: Markera fältet som representerar en URL som tillhandahåller ytterligare information om aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="664bc-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="664bc-121">Det kan till exempel vara det transaktionssystem som visar aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="664bc-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="664bc-122">URL:en kan vara vilket fält som helst från datakällan, eller också kan den skapas som ett nytt fält med hjälp av en Power Query-omvandling.</span><span class="sxs-lookup"><span data-stu-id="664bc-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="664bc-123">URL-data kommer att lagras i entiteten för enhetliga aktiviteter och kan konsumeras längre fram med hjälp av API:er.</span><span class="sxs-lookup"><span data-stu-id="664bc-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="664bc-124">**Detaljer**: Alternativt kan du välja det fält som du vill lägga till ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="664bc-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="664bc-125">**Ikon**: om du vill kan du markera den ikon som representerar aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="664bc-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="664bc-126">**Aktivitetstyp**: Definiera den referens till Common Data Model för aktivitetstypen som bäst beskriver den semantiska definitionen av aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="664bc-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="664bc-127">I avsnittet **Konfigurera relation** konfigurerar du detaljerna för att koppla dina aktivitets data till den motsvarande kunden.</span><span class="sxs-lookup"><span data-stu-id="664bc-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="664bc-128">**Fältet aktivitetsentitet**: Välj det fält i aktivitetsentiteten som ska användas för att skapa en relation med en annan entitet.</span><span class="sxs-lookup"><span data-stu-id="664bc-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="664bc-129">**Kundentitet**: Välj den motsvarande källkundentitet som du vill att aktivitetsentiteten ska finnas i relation till.</span><span class="sxs-lookup"><span data-stu-id="664bc-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="664bc-130">Du kan bara relatera till de kundentiteter för kunder som används i föreningsprocessen för data.</span><span class="sxs-lookup"><span data-stu-id="664bc-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="664bc-131">**Fältet kundentitet**: i det här fältet visas primärnyckeln för källkundentiteten enligt vad som valts i mappningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="664bc-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="664bc-132">Det här primära nyckelfältet i entiteten för källkund används för att upprätta en relation med entiteten aktivitet.</span><span class="sxs-lookup"><span data-stu-id="664bc-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="664bc-133">**Namn**: om det redan finns en relation mellan den här aktivitetsentiteten och den valda källkundentiteten är relationsnamnet i skrivskyddat läge.</span><span class="sxs-lookup"><span data-stu-id="664bc-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="664bc-134">Om det inte finns någon sådan relation skapas en ny relation med det namn som visas här.</span><span class="sxs-lookup"><span data-stu-id="664bc-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="664bc-135">![Definiera entitetsrelation](media/activities-entities-define.png "Definiera entitetsrelation")</span><span class="sxs-lookup"><span data-stu-id="664bc-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="664bc-136">Välj **Spara** för att införa ändringarna.</span><span class="sxs-lookup"><span data-stu-id="664bc-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="664bc-137">På sidan **Aktiviteter**, välj **Kör**.</span><span class="sxs-lookup"><span data-stu-id="664bc-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="664bc-138">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="664bc-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="664bc-139">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="664bc-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="664bc-140">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="664bc-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="664bc-141">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="664bc-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="664bc-142">Redigera en aktivitet</span><span class="sxs-lookup"><span data-stu-id="664bc-142">Edit an activity</span></span>

1. <span data-ttu-id="664bc-143">I målgruppsinsikter går du till **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="664bc-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="664bc-144">Välj den aktivitetsenhet du vill redigera och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="664bc-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="664bc-145">Du kan också hovra över entitetens rad och välja ikonen **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="664bc-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="664bc-146">Klicka på ikonen **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="664bc-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="664bc-147">Uppdatera värdena i fönstret **redigera aktivitet** och välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="664bc-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="664bc-148">På sidan **Aktiviteter**, välj **Kör**.</span><span class="sxs-lookup"><span data-stu-id="664bc-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="664bc-149">Ta bort en aktivitet</span><span class="sxs-lookup"><span data-stu-id="664bc-149">Delete an activity</span></span>

1. <span data-ttu-id="664bc-150">I målgruppsinsikter går du till **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="664bc-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="664bc-151">Välj den aktivitetsenhet du vill ta bort och välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="664bc-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="664bc-152">Du kan också hovra över entitetens rad och välja ikonen **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="664bc-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="664bc-153">Dessutom kan du välja att flera aktivitetsentiteter ska tas bort samtidigt.</span><span class="sxs-lookup"><span data-stu-id="664bc-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="664bc-154">![Redigera eller ta bort entitetsrelationerna](media/activities-entities-edit-delete.png "Redigera eller ta bort entitetsrelationerna")</span><span class="sxs-lookup"><span data-stu-id="664bc-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="664bc-155">Välj ikonen **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="664bc-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="664bc-156">Bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="664bc-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]