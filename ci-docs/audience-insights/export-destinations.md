---
title: Exportera data från Customer Insights
description: 'Hantera dataexport för att dela data. '
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253062"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="3e44b-103">Exporter (förhandsversion) översikt</span><span class="sxs-lookup"><span data-stu-id="3e44b-103">Exports (preview) overview</span></span>

<span data-ttu-id="3e44b-104">På sidan **Exporter** visas alla konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="3e44b-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="3e44b-105">Med exporter delar du specifika data med olika program.</span><span class="sxs-lookup"><span data-stu-id="3e44b-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="3e44b-106">De kan inkludera kundprofiler eller entiteter, scheman och mappningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="3e44b-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="3e44b-107">För varje export krävs en [anslutning, konfigurerad av en administratör, för att hantera autentisering och åtkomst](connections.md).</span><span class="sxs-lookup"><span data-stu-id="3e44b-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="3e44b-108">Gå till **Data** > **Exporter** om du vill visa exportsidan.</span><span class="sxs-lookup"><span data-stu-id="3e44b-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="3e44b-109">Alla användarroller har åtkomst till att visa konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="3e44b-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="3e44b-110">Använda sökfältet i kommandofältet för att söka efter exporter efter namn, anslutningsnamn eller anslutningstyp.</span><span class="sxs-lookup"><span data-stu-id="3e44b-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="3e44b-111">Ställ in en ny export</span><span class="sxs-lookup"><span data-stu-id="3e44b-111">Set up a new export</span></span>

<span data-ttu-id="3e44b-112">Om du vill konfigurera eller redigera en export måste anslutningarna vara tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="3e44b-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="3e44b-113">Anslutningarna beror på din [användarroll](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="3e44b-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="3e44b-114">Administratörer har åtkomst till alla anslutningar.</span><span class="sxs-lookup"><span data-stu-id="3e44b-114">Administrators have access to all connections.</span></span> <span data-ttu-id="3e44b-115">De kan också skapa nya anslutningar när de upprättar en export.</span><span class="sxs-lookup"><span data-stu-id="3e44b-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="3e44b-116">Deltagare kan ha åtkomst till specifika anslutningar.</span><span class="sxs-lookup"><span data-stu-id="3e44b-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="3e44b-117">De är beroende av administratörer för att konfigurera och dela anslutningar.</span><span class="sxs-lookup"><span data-stu-id="3e44b-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="3e44b-118">I exportlistan visas deltagare om de kan redigera eller bara visa en export i kolumnen **Dina behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="3e44b-119">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3e44b-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="3e44b-120">Det går bara att visa befintlig export men inte skapa den.</span><span class="sxs-lookup"><span data-stu-id="3e44b-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="3e44b-121">Definiera en ny export</span><span class="sxs-lookup"><span data-stu-id="3e44b-121">Define a new export</span></span>

1. <span data-ttu-id="3e44b-122">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e44b-123">Välj **Lägg till export** för att skapa en ny export.</span><span class="sxs-lookup"><span data-stu-id="3e44b-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="3e44b-124">I rutan **Ställ in export** väljer du vilken anslutning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="3e44b-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="3e44b-125">[Anslutningarna ](connections.md) hanteras av administratörer.</span><span class="sxs-lookup"><span data-stu-id="3e44b-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="3e44b-126">Ange den information som krävs och välj **Spara** för att skapa exporten.</span><span class="sxs-lookup"><span data-stu-id="3e44b-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="3e44b-127">Definiera en ny export utifrån en befintlig export</span><span class="sxs-lookup"><span data-stu-id="3e44b-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="3e44b-128">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e44b-129">I listan över exporter väljer du den export som du vill duplicera.</span><span class="sxs-lookup"><span data-stu-id="3e44b-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="3e44b-130">Välj **Skapa dubblett** i kommandofältet om du vill öppna fönstret **Konfigurera export** med informationen för den valda exporten.</span><span class="sxs-lookup"><span data-stu-id="3e44b-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="3e44b-131">Granska och anpassa exporten och välj **Spara** för att skapa en ny export.</span><span class="sxs-lookup"><span data-stu-id="3e44b-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="3e44b-132">Redigera export</span><span class="sxs-lookup"><span data-stu-id="3e44b-132">Edit an export</span></span>

1. <span data-ttu-id="3e44b-133">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e44b-134">I listan över exporter väljer du den export som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="3e44b-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="3e44b-135">Välj **Redigera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3e44b-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="3e44b-136">Ändra de värden du vill uppdatera och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="3e44b-137">Visa exporter och exportinformation</span><span class="sxs-lookup"><span data-stu-id="3e44b-137">View exports and export details</span></span>

<span data-ttu-id="3e44b-138">Efter att ha skapat exportdestinationer listas de på **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="3e44b-139">Alla användare kan se vilka data som delas och dess senaste status.</span><span class="sxs-lookup"><span data-stu-id="3e44b-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="3e44b-140">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e44b-141">Användare utan redigeringsbehörighet väljer **Visa** i stället för **Redigera** visas exportinformationen.</span><span class="sxs-lookup"><span data-stu-id="3e44b-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="3e44b-142">I sidrutan visas konfigurationen av en export.</span><span class="sxs-lookup"><span data-stu-id="3e44b-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="3e44b-143">Du kan inte ändra värden utan att redigera behörigheter.</span><span class="sxs-lookup"><span data-stu-id="3e44b-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="3e44b-144">Välj **Stäng** om du vill återgå till exportsidan.</span><span class="sxs-lookup"><span data-stu-id="3e44b-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="3e44b-145">Schemalägg och kör exporter</span><span class="sxs-lookup"><span data-stu-id="3e44b-145">Schedule and run exports</span></span>

<span data-ttu-id="3e44b-146">Varje export som du konfigurerar har ett uppdateringsschema.</span><span class="sxs-lookup"><span data-stu-id="3e44b-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="3e44b-147">Vid en uppdatering söker systemet efter nya eller uppdaterade data som ska ingå i en export.</span><span class="sxs-lookup"><span data-stu-id="3e44b-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="3e44b-148">Som standard körs exporter som en del av alla [schemalagda systemuppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3e44b-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3e44b-149">Du kan anpassa uppdateringsschemat eller inaktivera det om du vill köra exporten manuellt.</span><span class="sxs-lookup"><span data-stu-id="3e44b-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="3e44b-150">Exportscheman beror på tillståndet för miljön.</span><span class="sxs-lookup"><span data-stu-id="3e44b-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="3e44b-151">Om det finns uppdateringar av [beroenden](system.md#refresh-policies) som pågår när en schemalagd export ska starta, slutför först systemet beroendena och kör sedan rapporten.</span><span class="sxs-lookup"><span data-stu-id="3e44b-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="3e44b-152">Du kan se när en export senast uppdaterades i kolumnen **Uppdaterad**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="3e44b-153">Schemalägg exporter</span><span class="sxs-lookup"><span data-stu-id="3e44b-153">Schedule exports</span></span>

<span data-ttu-id="3e44b-154">Du kan definiera anpassade uppdateringsscheman för enskilda exporter eller flera exporter samtidigt.</span><span class="sxs-lookup"><span data-stu-id="3e44b-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="3e44b-155">Det för närvarande definierade schemat visas i kolumnen **Schema** i exportlistan.</span><span class="sxs-lookup"><span data-stu-id="3e44b-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="3e44b-156">Du kan ändra schemat på samma sätt som när du [redigerar och definierar exporter](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3e44b-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="3e44b-157">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e44b-158">Välj den export som du vill schemalägga.</span><span class="sxs-lookup"><span data-stu-id="3e44b-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="3e44b-159">Välj **Schemalägg** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3e44b-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="3e44b-160">I fönstret **Schemalägg export** ställer du in **Schemalägg körning** på **På** för att köra exporten automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3e44b-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="3e44b-161">Ställ in på **Av** för att uppdatera manuellt.</span><span class="sxs-lookup"><span data-stu-id="3e44b-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="3e44b-162">För automatiskt uppdaterade exporter väljer du ett värde för **Upprepning** och anger detaljer för det.</span><span class="sxs-lookup"><span data-stu-id="3e44b-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="3e44b-163">Den angivna tiden gäller för alla förekomster av en upprepning.</span><span class="sxs-lookup"><span data-stu-id="3e44b-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="3e44b-164">Det är den tid då en export ska börja uppdateras.</span><span class="sxs-lookup"><span data-stu-id="3e44b-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="3e44b-165">Tillämpa och aktivera ändringarna genom att välja **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="3e44b-166">När du redigerar schemat för flera exporter måste du välja under **Behåll eller åsidosätt scheman**:</span><span class="sxs-lookup"><span data-stu-id="3e44b-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="3e44b-167">**Behåll enskilda scheman**: Bevara det tidigare definierade schemat för den valda exporten och inaktivera eller aktivera dem endast.</span><span class="sxs-lookup"><span data-stu-id="3e44b-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="3e44b-168">**Ange ett nytt schema för alla valda exporter**: Åsidosätta befintliga scheman för de valda exporterna.</span><span class="sxs-lookup"><span data-stu-id="3e44b-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="3e44b-169">Kör exporter på begäran</span><span class="sxs-lookup"><span data-stu-id="3e44b-169">Run exports on demand</span></span>

<span data-ttu-id="3e44b-170">För att exportera data utan att vänta på en schemalagd uppdatering, gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="3e44b-171">Om du vill köra alla exporter väljer du **Kör alla** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3e44b-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="3e44b-172">Den här åtgärden kör endast exporter med ett aktivt schema.</span><span class="sxs-lookup"><span data-stu-id="3e44b-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="3e44b-173">Om du vill köra en enskild export markerar du den i listan och väljer **Kör** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3e44b-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="3e44b-174">På det här viset kör du exporter utan något aktivt schema.</span><span class="sxs-lookup"><span data-stu-id="3e44b-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="3e44b-175">Ta bort en export</span><span class="sxs-lookup"><span data-stu-id="3e44b-175">Remove an Export</span></span>

1. <span data-ttu-id="3e44b-176">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="3e44b-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e44b-177">Markera den export du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="3e44b-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="3e44b-178">Välj **Ta bort** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3e44b-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="3e44b-179">Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.</span><span class="sxs-lookup"><span data-stu-id="3e44b-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
