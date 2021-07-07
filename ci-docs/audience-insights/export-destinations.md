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
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305500"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="0da49-103">Exporter (förhandsversion) översikt</span><span class="sxs-lookup"><span data-stu-id="0da49-103">Exports (preview) overview</span></span>

<span data-ttu-id="0da49-104">På sidan **Exporter** visas alla konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="0da49-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="0da49-105">Med exporter delar du specifika data med olika program.</span><span class="sxs-lookup"><span data-stu-id="0da49-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="0da49-106">De kan inkludera kundprofiler eller entiteter, scheman och mappningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="0da49-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="0da49-107">För varje export krävs en [anslutning, konfigurerad av en administratör, för att hantera autentisering och åtkomst](connections.md).</span><span class="sxs-lookup"><span data-stu-id="0da49-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="0da49-108">Gå till **Data** > **Exporter** om du vill visa exportsidan.</span><span class="sxs-lookup"><span data-stu-id="0da49-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="0da49-109">Alla användarroller kan visa konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="0da49-109">All user roles can view configured exports.</span></span> <span data-ttu-id="0da49-110">Använd sökfältet i kommandofältet om du vill söka efter exporter efter namn, anslutningsnamn eller anslutningstyp.</span><span class="sxs-lookup"><span data-stu-id="0da49-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="0da49-111">Ställ in en ny export</span><span class="sxs-lookup"><span data-stu-id="0da49-111">Set up a new export</span></span>

<span data-ttu-id="0da49-112">Om du vill konfigurera eller redigera en export måste anslutningarna vara tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="0da49-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="0da49-113">Anslutningarna beror på din [användarroll](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="0da49-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="0da49-114">Administratörer har åtkomst till alla anslutningar.</span><span class="sxs-lookup"><span data-stu-id="0da49-114">Administrators have access to all connections.</span></span> <span data-ttu-id="0da49-115">De kan också skapa nya anslutningar när de upprättar en export.</span><span class="sxs-lookup"><span data-stu-id="0da49-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="0da49-116">Deltagare kan ha åtkomst till specifika anslutningar.</span><span class="sxs-lookup"><span data-stu-id="0da49-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="0da49-117">De är beroende av administratörer för att konfigurera och dela anslutningar.</span><span class="sxs-lookup"><span data-stu-id="0da49-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="0da49-118">I exportlistan visas deltagare om de kan redigera eller bara visa en export i kolumnen **Dina behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="0da49-119">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0da49-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="0da49-120">Det går bara att visa befintlig export men inte skapa den.</span><span class="sxs-lookup"><span data-stu-id="0da49-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="0da49-121">Definiera en ny export</span><span class="sxs-lookup"><span data-stu-id="0da49-121">Define a new export</span></span>

1. <span data-ttu-id="0da49-122">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0da49-123">Välj **Lägg till export** för att skapa en ny export.</span><span class="sxs-lookup"><span data-stu-id="0da49-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="0da49-124">I rutan **Ställ in export** väljer du vilken anslutning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="0da49-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="0da49-125">[Anslutningarna ](connections.md) hanteras av administratörer.</span><span class="sxs-lookup"><span data-stu-id="0da49-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="0da49-126">Ange den information som krävs och välj **Spara** för att skapa exporten.</span><span class="sxs-lookup"><span data-stu-id="0da49-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="0da49-127">Definiera en ny export utifrån en befintlig export</span><span class="sxs-lookup"><span data-stu-id="0da49-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="0da49-128">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0da49-129">I listan över exporter väljer du den export som du vill duplicera.</span><span class="sxs-lookup"><span data-stu-id="0da49-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="0da49-130">Välj **Skapa dubblett** i kommandofältet om du vill öppna fönstret **Konfigurera export** med informationen för den valda exporten.</span><span class="sxs-lookup"><span data-stu-id="0da49-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="0da49-131">Granska och anpassa exporten och välj **Spara** för att skapa en ny export.</span><span class="sxs-lookup"><span data-stu-id="0da49-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="0da49-132">Redigera export</span><span class="sxs-lookup"><span data-stu-id="0da49-132">Edit an export</span></span>

1. <span data-ttu-id="0da49-133">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0da49-134">I listan över exporter väljer du den export som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0da49-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="0da49-135">Välj **Redigera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="0da49-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="0da49-136">Ändra de värden du vill uppdatera och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0da49-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="0da49-137">Visa exporter och exportinformation</span><span class="sxs-lookup"><span data-stu-id="0da49-137">View exports and export details</span></span>

<span data-ttu-id="0da49-138">Efter att ha skapat exportdestinationer listas de på **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="0da49-139">Alla användare kan se vilka data som delas och dess senaste status.</span><span class="sxs-lookup"><span data-stu-id="0da49-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="0da49-140">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0da49-141">Användare utan redigeringsbehörigheter väljer du **Visa** istället för **Redigera** för att visa exportinformationen.</span><span class="sxs-lookup"><span data-stu-id="0da49-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="0da49-142">I sidrutan visas konfigurationen av en export.</span><span class="sxs-lookup"><span data-stu-id="0da49-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="0da49-143">Du kan inte ändra värden utan att redigera behörigheter.</span><span class="sxs-lookup"><span data-stu-id="0da49-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="0da49-144">Välj **Stäng** om du vill återgå till exportsidan.</span><span class="sxs-lookup"><span data-stu-id="0da49-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="0da49-145">Schemalägg och kör exporter</span><span class="sxs-lookup"><span data-stu-id="0da49-145">Schedule and run exports</span></span>

<span data-ttu-id="0da49-146">Varje export som du konfigurerar har ett uppdateringsschema.</span><span class="sxs-lookup"><span data-stu-id="0da49-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="0da49-147">Vid en uppdatering söker systemet efter nya eller uppdaterade data som ska ingå i en export.</span><span class="sxs-lookup"><span data-stu-id="0da49-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="0da49-148">Som standard körs exporter som en del av alla [schemalagda systemuppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0da49-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0da49-149">Du kan anpassa uppdateringsschemat eller inaktivera det om du vill köra exporten manuellt.</span><span class="sxs-lookup"><span data-stu-id="0da49-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="0da49-150">Exportscheman beror på tillståndet för miljön.</span><span class="sxs-lookup"><span data-stu-id="0da49-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="0da49-151">Om det pågår uppdateringar för [beroenden](system.md#refresh-policies) när en schemalagd export ska starta, slutför systemet först uppdateringarna och kör sedan exporten.</span><span class="sxs-lookup"><span data-stu-id="0da49-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="0da49-152">Du kan se när en export senast uppdaterades i kolumnen **Uppdaterad**.</span><span class="sxs-lookup"><span data-stu-id="0da49-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="0da49-153">Schemalägg exporter</span><span class="sxs-lookup"><span data-stu-id="0da49-153">Schedule exports</span></span>

<span data-ttu-id="0da49-154">Du kan definiera anpassade uppdateringsscheman för enskilda exporter eller flera exporter samtidigt.</span><span class="sxs-lookup"><span data-stu-id="0da49-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="0da49-155">Det för närvarande definierade schemat visas i kolumnen **Schema** i exportlistan.</span><span class="sxs-lookup"><span data-stu-id="0da49-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="0da49-156">Du kan ändra schemat på samma sätt som när du [redigerar och definierar exporter](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0da49-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="0da49-157">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0da49-158">Välj den export som du vill schemalägga.</span><span class="sxs-lookup"><span data-stu-id="0da49-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="0da49-159">Välj **Schemalägg** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="0da49-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="0da49-160">I fönstret **Schemalägg export** ställer du in **Schemalägg körning** på **På** för att köra exporten automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0da49-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="0da49-161">Ställ in på **Av** för att uppdatera manuellt.</span><span class="sxs-lookup"><span data-stu-id="0da49-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="0da49-162">För automatiskt uppdaterade exporter väljer du ett värde för **Upprepning** och anger detaljer för det.</span><span class="sxs-lookup"><span data-stu-id="0da49-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="0da49-163">Den angivna tiden gäller för alla förekomster av en upprepning.</span><span class="sxs-lookup"><span data-stu-id="0da49-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="0da49-164">Det är den tid då en export ska börja uppdateras.</span><span class="sxs-lookup"><span data-stu-id="0da49-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="0da49-165">Tillämpa och aktivera ändringarna genom att välja **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0da49-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="0da49-166">När du redigerar schemat för flera exporter måste du välja under **Behåll eller åsidosätt scheman**:</span><span class="sxs-lookup"><span data-stu-id="0da49-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="0da49-167">**Behåll enskilda scheman**: Bevara det tidigare definierade schemat för den valda exporten och inaktivera eller aktivera dem endast.</span><span class="sxs-lookup"><span data-stu-id="0da49-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="0da49-168">**Ange ett nytt schema för alla valda exporter**: Åsidosätta befintliga scheman för de valda exporterna.</span><span class="sxs-lookup"><span data-stu-id="0da49-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="0da49-169">Kör exporter på begäran</span><span class="sxs-lookup"><span data-stu-id="0da49-169">Run exports on demand</span></span>

<span data-ttu-id="0da49-170">För att exportera data utan att vänta på en schemalagd uppdatering, gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="0da49-171">Om du vill köra alla exporter väljer du **Kör alla** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="0da49-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="0da49-172">Den här åtgärden kör endast exporter med ett aktivt schema.</span><span class="sxs-lookup"><span data-stu-id="0da49-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="0da49-173">Om du vill köra en enskild export markerar du den i listan och väljer **Kör** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="0da49-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="0da49-174">På det här viset kör du exporter utan något aktivt schema.</span><span class="sxs-lookup"><span data-stu-id="0da49-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="0da49-175">Ta bort en export</span><span class="sxs-lookup"><span data-stu-id="0da49-175">Remove an Export</span></span>

1. <span data-ttu-id="0da49-176">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0da49-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0da49-177">Markera den export du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="0da49-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="0da49-178">Välj **Ta bort** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="0da49-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="0da49-179">Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.</span><span class="sxs-lookup"><span data-stu-id="0da49-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
