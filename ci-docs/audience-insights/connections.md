---
title: Anslutningar till andra tjänster från Customer Insights.
description: Dela data till andra tjänster.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304994"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="d9552-103">Översikt över anslutningar (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="d9552-103">Connections (preview) overview</span></span>

<span data-ttu-id="d9552-104">Anslutningar är nyckeln till datadelning till och från Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d9552-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="d9552-105">Varje anslutning upprättar datadelning med en viss tjänst.</span><span class="sxs-lookup"><span data-stu-id="d9552-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="d9552-106">Anslutningar utgör grunden för [konfigurera berikningar från tredje part](enrichment-hub.md) och [konfigurera exporter](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d9552-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="d9552-107">Samma anslutning kan användas flera gånger.</span><span class="sxs-lookup"><span data-stu-id="d9552-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="d9552-108">En anslutning till Dynamics 365 Marketing fungerar till exempel för flera exporter och en Leadspace-anslutning kan användas för flera utskick.</span><span class="sxs-lookup"><span data-stu-id="d9552-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="d9552-109">Gå till **Admin** > **Anslutningar** för att skapa och visa anslutningar.</span><span class="sxs-lookup"><span data-stu-id="d9552-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="d9552-110">På fliken **Anslutningar** visas alla aktiva anslutningar.</span><span class="sxs-lookup"><span data-stu-id="d9552-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="d9552-111">I listan visas en rad för varje anslutning.</span><span class="sxs-lookup"><span data-stu-id="d9552-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="d9552-112">Få en snabb översikt, beskrivning och ta reda på vad du kan göra med varje utbyggbarhetsalternativ på fliken **Upptäck**.</span><span class="sxs-lookup"><span data-stu-id="d9552-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="d9552-113">Exporter</span><span class="sxs-lookup"><span data-stu-id="d9552-113">Exports</span></span>

<span data-ttu-id="d9552-114">Endast administratörer kan konfigurera nya anslutningar, men de kan ge deltagare åtkomst till befintliga anslutningar.</span><span class="sxs-lookup"><span data-stu-id="d9552-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="d9552-115">Administratörer styr vart data kan ta vägen. Deltagare anger vilken nyttolast och frekvens som passar deras behov.</span><span class="sxs-lookup"><span data-stu-id="d9552-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="d9552-116">Mer information finns i [Tillåt att deltagare använder en anslutning för export](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d9552-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="d9552-117">Berikningar</span><span class="sxs-lookup"><span data-stu-id="d9552-117">Enrichments</span></span>

<span data-ttu-id="d9552-118">Endast administratörer kan konfigurera nya anslutningar, men de skapade anslutningarna är alltid tillgängliga för både administratörer och deltagare.</span><span class="sxs-lookup"><span data-stu-id="d9552-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="d9552-119">Administratörer hanterar autentiseringsuppgifter och ger sitt godkännande till att använda data.</span><span class="sxs-lookup"><span data-stu-id="d9552-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="d9552-120">Anslutningarna kan sedan användas för ut mer information av både administratörer och deltagare.</span><span class="sxs-lookup"><span data-stu-id="d9552-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="d9552-121">Lägg till ny anslutning</span><span class="sxs-lookup"><span data-stu-id="d9552-121">Add a new connection</span></span>

<span data-ttu-id="d9552-122">Om du vill lägga till anslutningar måste du ha [administratörsbehörighet](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d9552-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="d9552-123">Om du ansluter till andra Microsoft-tjänster förutsätter vi att båda tjänsterna finns i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="d9552-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="d9552-124">Gå till **Admin** > **Anslutningar (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="d9552-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="d9552-125">Gå till fliken **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="d9552-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="d9552-126">Välj **Lägg till kontakt** om du vill skapa en ny anslutning.</span><span class="sxs-lookup"><span data-stu-id="d9552-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="d9552-127">Välj i listrutan vilken typ av anslutning du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="d9552-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="d9552-128">I fönstret **Konfigurera anslutning** ange de uppgifter som krävs.</span><span class="sxs-lookup"><span data-stu-id="d9552-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="d9552-129">En **Visningsnamn** och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="d9552-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="d9552-130">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9552-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="d9552-131">Exakt vilka fält som är beroende av vilken tjänst du ansluter till.</span><span class="sxs-lookup"><span data-stu-id="d9552-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="d9552-132">Mer information om en specifik anslutningstyp finns i artikeln om måltjänsten.</span><span class="sxs-lookup"><span data-stu-id="d9552-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="d9552-133">Välj för att skapa anslutningen **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d9552-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="d9552-134">Du kan också välja **Konfigurera** på panelen **Identifiering**.</span><span class="sxs-lookup"><span data-stu-id="d9552-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="d9552-135">Tillåt deltagare använda en anslutning för export</span><span class="sxs-lookup"><span data-stu-id="d9552-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="d9552-136">När du ställer in eller redigerar en exportanslutning väljer du vilka användare som ska kunna använda den här specifika anslutningen för att definiera [exportera](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d9552-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="d9552-137">Som standard är en anslutning tillgänglig för användare med administratörsroll.</span><span class="sxs-lookup"><span data-stu-id="d9552-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="d9552-138">Du kan ändra den här inställningen under **Välj vem som kan använda den här anslutningen** och tillåta användare deltagare ska använda den här anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9552-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="d9552-139">Deltagare kan inte visa eller redigera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9552-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="d9552-140">Här visas endast visningsnamn typ när en export skapas.</span><span class="sxs-lookup"><span data-stu-id="d9552-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="d9552-141">Genom att dela en anslutning tillåter du deltagare att använda en anslutning.</span><span class="sxs-lookup"><span data-stu-id="d9552-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="d9552-142">Deltagare ser delade anslutningar när de upprättar exporter.</span><span class="sxs-lookup"><span data-stu-id="d9552-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="d9552-143">De kan hantera alla exporter som använder den här specifika anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9552-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="d9552-144">Du kan ändra den här inställningen samtidigt som du behåller de exporter som redan har definierats av deltagare.</span><span class="sxs-lookup"><span data-stu-id="d9552-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="d9552-145">Redigera en anslutning</span><span class="sxs-lookup"><span data-stu-id="d9552-145">Edit a connection</span></span>

1. <span data-ttu-id="d9552-146">Gå till **Admin** > **Anslutningar (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="d9552-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="d9552-147">Gå till fliken **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="d9552-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="d9552-148">Markera den vertikala ellipsen för anslutningen du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="d9552-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="d9552-149">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="d9552-149">Select **Edit**.</span></span>

1. <span data-ttu-id="d9552-150">Ändra de värden du vill uppdatera och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d9552-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="d9552-151">Vill du ta bort anslutningen</span><span class="sxs-lookup"><span data-stu-id="d9552-151">Remove a connection</span></span>

<span data-ttu-id="d9552-152">Om anslutningen som du tar bort används för att utöka eller exportera måste du först ta bort eller ta bort den.</span><span class="sxs-lookup"><span data-stu-id="d9552-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="d9552-153">I dialogrutan för borttagning guidas du till relevanta förbättringar eller exporter.</span><span class="sxs-lookup"><span data-stu-id="d9552-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="d9552-154">Fristående berikningar och export blir inaktiva.</span><span class="sxs-lookup"><span data-stu-id="d9552-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="d9552-155">Du aktiverar dem på nytt genom att lägga till en ny anslutning till dem på sidan [Berikningar](enrichment-hub.md) eller [Exporter](export-destinations.md)..</span><span class="sxs-lookup"><span data-stu-id="d9552-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="d9552-156">Gå till **Admin** > **Anslutningar (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="d9552-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="d9552-157">Gå till fliken **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="d9552-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="d9552-158">Markera den vertikala ellipsen för anslutningen du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="d9552-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="d9552-159">Välj **Ta bort** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="d9552-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="d9552-160">En dialogruta för bekräftelse visas.</span><span class="sxs-lookup"><span data-stu-id="d9552-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="d9552-161">Om det finns anläggningar eller exporter med hjälp av den här anslutningen markerar du knappen för att se vad som använder anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9552-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="d9552-162">**Export:** Du kan välja att antingen ta bort eller koppla bort exporten för att kunna ta bort anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9552-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="d9552-163">Administratörer kan använda åtgärden **Koppla från** för att koppla från export.</span><span class="sxs-lookup"><span data-stu-id="d9552-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="d9552-164">Åtgärden är tillgänglig för enskilda och flera markerade exporter.</span><span class="sxs-lookup"><span data-stu-id="d9552-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="d9552-165">Genom att koppla från behålls exportkonfigurationen, men den körs inte förrän en annan anslutning har lagts till i den.</span><span class="sxs-lookup"><span data-stu-id="d9552-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="d9552-166">**Berikningar:** Du kan välja att antingen ta bort eller inaktivera berikningarna för att kunna ta bort anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9552-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="d9552-167">När anslutningen inte längre har några beroenden går du tillbaka till **Admin** > **Anslutningar** och försök att ta bort anslutningen igen.</span><span class="sxs-lookup"><span data-stu-id="d9552-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="d9552-168">Bekräfta borttagningen genom att markera **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="d9552-168">To confirm the deletion, select **Remove**.</span></span>

