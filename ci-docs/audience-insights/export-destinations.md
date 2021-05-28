---
title: Exportera data från Customer Insights
description: 'Hantera dataexport för att dela data. '
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016658"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="f8f8e-103">Exporter (förhandsversion) översikt</span><span class="sxs-lookup"><span data-stu-id="f8f8e-103">Exports (preview) overview</span></span>

<span data-ttu-id="f8f8e-104">På sidan **Exporter** visas alla konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="f8f8e-105">Med exporter delar du specifika data med olika program.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="f8f8e-106">De kan inkludera kundprofiler eller entiteter, scheman och mappningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="f8f8e-107">För varje export krävs en [anslutning, konfigurerad av en administratör, för att hantera autentisering och åtkomst](connections.md).</span><span class="sxs-lookup"><span data-stu-id="f8f8e-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="f8f8e-108">Gå till **Data** > **Exporter** om du vill visa exportsidan.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="f8f8e-109">Alla användarroller har åtkomst till att visa konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="f8f8e-110">Använda sökfältet i kommandofältet för att söka efter exporter efter namn, anslutningsnamn eller anslutningstyp.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="f8f8e-111">Ställ in en ny export</span><span class="sxs-lookup"><span data-stu-id="f8f8e-111">Set up a new export</span></span>

<span data-ttu-id="f8f8e-112">Om du vill konfigurera eller redigera en export måste anslutningarna vara tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="f8f8e-113">Anslutningarna beror på din [användarroll](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="f8f8e-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="f8f8e-114">Administratörer har åtkomst till alla anslutningar.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-114">Administrators have access to all connections.</span></span> <span data-ttu-id="f8f8e-115">De kan också skapa nya anslutningar när de upprättar en export.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="f8f8e-116">Deltagare kan ha åtkomst till specifika anslutningar.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="f8f8e-117">De är beroende av administratörer för att konfigurera och dela anslutningar.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="f8f8e-118">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f8f8e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="f8f8e-119">Det går bara att visa befintlig export men inte skapa den.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="f8f8e-120">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f8f8e-121">Välj **Lägg till export** om du vill skapa en ny exportmål.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="f8f8e-122">I rutan **Ställ in export** väljer du vilken anslutning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="f8f8e-123">[Anslutningarna ](connections.md) hanteras av administratörer.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="f8f8e-124">Ange den information som krävs och välj **Spara** för att skapa exporten.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="f8f8e-125">Redigera export</span><span class="sxs-lookup"><span data-stu-id="f8f8e-125">Edit an export</span></span>

1. <span data-ttu-id="f8f8e-126">Markera den vertikala ellipsen för det exportmål du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="f8f8e-127">Välj **Redigera** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="f8f8e-128">Ändra de värden du vill uppdatera och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="f8f8e-129">Visa export- och exportinformation</span><span class="sxs-lookup"><span data-stu-id="f8f8e-129">View Exports and export details</span></span>

<span data-ttu-id="f8f8e-130">Efter att ha skapat exportdestinationer listas de på **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="f8f8e-131">Alla användare kan se vilka data som delas och dess senaste status.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="f8f8e-132">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f8f8e-133">Användare utan redigeringsbehörighet väljer **Visa** i stället för **Redigera** visas exportinformationen.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="f8f8e-134">I den här sidan visas hur exporten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="f8f8e-135">Du kan inte ändra värden utan att redigera behörigheter.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="f8f8e-136">Välj **Stäng** om du vill återgå till exportsidan.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="f8f8e-137">Kör exporter på begäran</span><span class="sxs-lookup"><span data-stu-id="f8f8e-137">Run exports on demand</span></span>

<span data-ttu-id="f8f8e-138">När du har konfigurerat en export körs den med alla [schemalagda uppdateringar](system.md#schedule-tab) så länge den har en fungerande anslutning.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="f8f8e-139">För att exportera data utan att vänta på en schemalagd uppdatering, gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="f8f8e-140">Du har två alternativ:</span><span class="sxs-lookup"><span data-stu-id="f8f8e-140">You have two options:</span></span>

- <span data-ttu-id="f8f8e-141">Om du vill köra alla exporter väljer du **Kör alla** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="f8f8e-142">Om du vill köra en enskild export markerar du denlipsen (...) på ett listobjekt och väljer sedan **Kör**.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="f8f8e-143">Ta bort en export</span><span class="sxs-lookup"><span data-stu-id="f8f8e-143">Remove an Export</span></span>

1. <span data-ttu-id="f8f8e-144">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f8f8e-145">Markera den vertikala ellipsen för det export du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="f8f8e-146">Välj **Ta bort** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="f8f8e-147">Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.</span><span class="sxs-lookup"><span data-stu-id="f8f8e-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
