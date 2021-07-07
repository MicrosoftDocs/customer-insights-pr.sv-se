---
title: Kundaktiviteter
description: Definiera kundaktiviteter och visa dem på tidslinjen för kunden.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304948"
---
# <a name="customer-activities"></a><span data-ttu-id="77a6a-103">Kundaktiviteter</span><span class="sxs-lookup"><span data-stu-id="77a6a-103">Customer activities</span></span>

<span data-ttu-id="77a6a-104">Kombinera kundaktiviteter från [olika datakällor](data-sources.md) i Dynamics 365 Customer Insights för att skapa en tidslinje som visar aktiviteterna kronologiskt.</span><span class="sxs-lookup"><span data-stu-id="77a6a-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="77a6a-105">Ta med tidslinjen i Dynamics 365-appar med [tillägget kundkort](customer-card-add-in.md) eller på en Power BI instrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="77a6a-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="77a6a-106">Definiera en aktivitet</span><span class="sxs-lookup"><span data-stu-id="77a6a-106">Define an activity</span></span>

<span data-ttu-id="77a6a-107">Dina datakällor innehåller entiteter med transaktions- och aktivitetsdata från flera datakällor.</span><span class="sxs-lookup"><span data-stu-id="77a6a-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="77a6a-108">Identifiera entiteterna och välj de aktiviteter du vill visa på kundens tidslinje.</span><span class="sxs-lookup"><span data-stu-id="77a6a-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="77a6a-109">Välj den entitet som innehåller målaktiviteten eller aktiviteterna.</span><span class="sxs-lookup"><span data-stu-id="77a6a-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="77a6a-110">En entitet måste ha minst ett attribut av typen **Datum** för att kunna tas med i en kundtidslinje och du kan inte lägga till entiteter utan **datum**-fält.</span><span class="sxs-lookup"><span data-stu-id="77a6a-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="77a6a-111">Kontrollen **Lägg till aktivitet** är inaktiverad om ingen sådan entitet hittas.</span><span class="sxs-lookup"><span data-stu-id="77a6a-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="77a6a-112">I målgruppsinsikter går du till **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="77a6a-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="77a6a-113">Välj **Lägg till aktivitet** för att starta den guidade upplevelsen för aktivitetens installationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="77a6a-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="77a6a-114">I steget **Aktivitetsdata**, ställ in värdena för följande fält:</span><span class="sxs-lookup"><span data-stu-id="77a6a-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="77a6a-115">**Aktivitetsnamn**: Välj ett namn för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="77a6a-116">**Entitet**: Välj en entitet som innehåller transaktions- eller aktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="77a6a-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="77a6a-117">**Primärnyckeln**: Välj fältet som används för unik identifiering av en post.</span><span class="sxs-lookup"><span data-stu-id="77a6a-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="77a6a-118">Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.</span><span class="sxs-lookup"><span data-stu-id="77a6a-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurera aktivitetsdata med namn, entitet och primärnyckel.":::

1. <span data-ttu-id="77a6a-120">Gå vidare till nästa steg genom att välja **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="77a6a-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="77a6a-121">I steget **Relation** konfigurerar du informationen så att dina aktivitetsdata kan kopplas till motsvarande kund.</span><span class="sxs-lookup"><span data-stu-id="77a6a-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="77a6a-122">Det här steget visualiserar anslutningen mellan entiteter.</span><span class="sxs-lookup"><span data-stu-id="77a6a-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="77a6a-123">**Först**: Fält för externa fält i aktivitetsentiteten som används för att upprätta en relation med en annan entitet.</span><span class="sxs-lookup"><span data-stu-id="77a6a-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="77a6a-124">**Andra**: Motsvarande källkundentitet som din aktivitetsentitet ska vara i relation till.</span><span class="sxs-lookup"><span data-stu-id="77a6a-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="77a6a-125">Du kan endast relatera till källkundentiteter som används i datakällprocessen.</span><span class="sxs-lookup"><span data-stu-id="77a6a-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="77a6a-126">**Tredje**: Om en relation mellan den här aktivitetsentiteten och den valda källkundentiteten redan finns kommer relationsnamnet att vara skrivskyddat läge.</span><span class="sxs-lookup"><span data-stu-id="77a6a-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="77a6a-127">Om det inte finns någon sådan relation skapas en ny relation med det namn du anger i rutan.</span><span class="sxs-lookup"><span data-stu-id="77a6a-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiera entitetsrelation.":::

1. <span data-ttu-id="77a6a-129">Gå vidare till nästa steg genom att välja **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="77a6a-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="77a6a-130">I steget **Samordning av aktiviteter** välj aktivitetshändelsen och starttiden för din aktivitet.</span><span class="sxs-lookup"><span data-stu-id="77a6a-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="77a6a-131">**Obligatoriska fält**</span><span class="sxs-lookup"><span data-stu-id="77a6a-131">**Required fields**</span></span>
      - <span data-ttu-id="77a6a-132">**Händelseaktivitet**: Fält som är händelsen för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="77a6a-133">**Tidsstämpel**: Fält som representerar aktivitetens starttid.</span><span class="sxs-lookup"><span data-stu-id="77a6a-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="77a6a-134">**Valfria fält**</span><span class="sxs-lookup"><span data-stu-id="77a6a-134">**Optional fields**</span></span>
      - <span data-ttu-id="77a6a-135">**Ytterligare information**: Fält med relevant information för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="77a6a-136">**Ikon**: Ikon som bäst representerar den här aktivitetstypen.</span><span class="sxs-lookup"><span data-stu-id="77a6a-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="77a6a-137">**Webbadress**: Fält som innehåller en URL med information om aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="77a6a-138">Det kan till exempel vara det transaktionssystem som visar aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="77a6a-139">URL:en kan vara vilket fält som helst från datakällan, eller också kan den skapas som ett nytt fält med hjälp av en Power Query-omvandling.</span><span class="sxs-lookup"><span data-stu-id="77a6a-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="77a6a-140">URL-data lagras i entiteten *Enhetlig aktivitet*, som kan användas nedströms med [API:er](apis.md). </span><span class="sxs-lookup"><span data-stu-id="77a6a-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Ange kundaktivitetsdata i en entitet för enhetlig aktivitet.":::

1. <span data-ttu-id="77a6a-142">Klicka på **Nästa** för att gå till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="77a6a-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="77a6a-143">Du kan välja **Slutför och granska** om du vill spara aktiviteten nu med aktivitetstypen **Annat**.</span><span class="sxs-lookup"><span data-stu-id="77a6a-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="77a6a-144">Välj aktivitetstyp i steget **Aktivitetstyp** och välj om du vill mappa några av aktivitetstyperna så att de kan användas i andra områden av Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="77a6a-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="77a6a-145">För närvarande går det att mappa aktivitetstyperna *Prenumeration* och *SalesOrderLine* semantiskt efter att ha godkänt att fälten mappas.</span><span class="sxs-lookup"><span data-stu-id="77a6a-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="77a6a-146">Om en aktivitetstyp inte är relevant för den nya aktiviteten kan du välja *Annat* eller *Skapa ny* för en anpassad aktivitetstyp.</span><span class="sxs-lookup"><span data-stu-id="77a6a-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="77a6a-147">Klicka på **Nästa** för att gå till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="77a6a-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="77a6a-148">I steget **Granska**, kontrollera dina val.</span><span class="sxs-lookup"><span data-stu-id="77a6a-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="77a6a-149">Gå tillbaka till valfritt föregående steg och uppdatera informationen vid behov.</span><span class="sxs-lookup"><span data-stu-id="77a6a-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Granska de angivna fälten för en aktivitet.":::
   
1. <span data-ttu-id="77a6a-151">Välj **Spara aktivitet** om du vill tillämpa ändringarna och välj **Klar** för att gå tillbaka till **Data**  > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="77a6a-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="77a6a-152">Här ser du vilka aktiviteter som ska visas på tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="77a6a-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="77a6a-153">På sidan **Aktiviteter**, välj **Kör** för att bearbeta aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="77a6a-154">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="77a6a-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="77a6a-155">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="77a6a-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="77a6a-156">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="77a6a-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="77a6a-157">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="77a6a-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="77a6a-158">Hantera befintliga aktiviteter</span><span class="sxs-lookup"><span data-stu-id="77a6a-158">Manage existing activities</span></span>

<span data-ttu-id="77a6a-159">På **Data** > **Aktiviteter**, kan du visa alla sparade aktiviteter och hantera dem.</span><span class="sxs-lookup"><span data-stu-id="77a6a-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="77a6a-160">Varje aktivitet representeras av en rad som även innehåller information om källan, entiteten och aktivitetstypen.</span><span class="sxs-lookup"><span data-stu-id="77a6a-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="77a6a-161">Följande åtgärder är tillgängliga när du väljer en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="77a6a-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="77a6a-162">**Redigera**: Öppnar aktivitetskonfigurationen i granskningssteget.</span><span class="sxs-lookup"><span data-stu-id="77a6a-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="77a6a-163">Du kan ändra vilken som helst av eller hela den aktuella konfigurationen från det här steget.</span><span class="sxs-lookup"><span data-stu-id="77a6a-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="77a6a-164">När du har ändrat konfigurationen väljer du **Spara aktivitet** och väljer **Kör** för att bearbeta ändringarna.</span><span class="sxs-lookup"><span data-stu-id="77a6a-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="77a6a-165">**Byt namn**: Öppnar en dialog där du kan ange ett annat namn för den valda aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="77a6a-166">Välj **Spara** för att införa ändringarna.</span><span class="sxs-lookup"><span data-stu-id="77a6a-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="77a6a-167">**Ta bort**: Öppnar en dialog för att bekräfta borttagningen av den markerade aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="77a6a-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="77a6a-168">Du kan också ta bort mer än en aktivitet samtidigt genom att markera aktiviteterna och sedan markera ikonen för borttagning.</span><span class="sxs-lookup"><span data-stu-id="77a6a-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="77a6a-169">Välj **Ta bort** för att borttagningen.</span><span class="sxs-lookup"><span data-stu-id="77a6a-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
