---
title: Exportera data från Customer Insights
description: 'Hantera dataexport för att dela data. '
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896165"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="a3f00-103">Exporter (förhandsversion) översikt</span><span class="sxs-lookup"><span data-stu-id="a3f00-103">Exports (preview) overview</span></span>

<span data-ttu-id="a3f00-104">På sidan **Exporter** visas alla konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="a3f00-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="a3f00-105">Med exporter delar du specifika data med olika program.</span><span class="sxs-lookup"><span data-stu-id="a3f00-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="a3f00-106">De kan inkludera kundprofiler eller entiteter, scheman och mappningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="a3f00-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="a3f00-107">För varje export krävs en [anslutning, konfigurerad av en administratör, för att hantera autentisering och åtkomst](connections.md).</span><span class="sxs-lookup"><span data-stu-id="a3f00-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3f00-108">Fram till mars 2021 skapades automatiskt en anslutning till motsvarande tjänst.</span><span class="sxs-lookup"><span data-stu-id="a3f00-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="a3f00-109">För export krävs nu en [anslutning som har skapats och delats av en administratör](connections.md) innan du kan skapa dem.</span><span class="sxs-lookup"><span data-stu-id="a3f00-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="a3f00-110">Gå till **Data** > **Exporter** om du vill visa exportsidan.</span><span class="sxs-lookup"><span data-stu-id="a3f00-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="a3f00-111">Alla användarroller har åtkomst till att visa konfigurerade exporter.</span><span class="sxs-lookup"><span data-stu-id="a3f00-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="a3f00-112">Använda sökfältet i kommandofältet för att söka efter exporter efter namn, anslutningsnamn eller anslutningstyp.</span><span class="sxs-lookup"><span data-stu-id="a3f00-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="a3f00-113">Ställ in en ny export</span><span class="sxs-lookup"><span data-stu-id="a3f00-113">Set up a new export</span></span>

<span data-ttu-id="a3f00-114">Om du vill konfigurera eller redigera en export måste anslutningarna vara tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="a3f00-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="a3f00-115">Anslutningarna beror på din [användarroll](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="a3f00-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="a3f00-116">Administratörer har åtkomst till alla anslutningar.</span><span class="sxs-lookup"><span data-stu-id="a3f00-116">Administrators have access to all connections.</span></span> <span data-ttu-id="a3f00-117">De kan också skapa nya anslutningar när de upprättar en export.</span><span class="sxs-lookup"><span data-stu-id="a3f00-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="a3f00-118">Deltagare kan ha åtkomst till specifika anslutningar.</span><span class="sxs-lookup"><span data-stu-id="a3f00-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="a3f00-119">De är beroende av administratörer för att konfigurera och dela anslutningar.</span><span class="sxs-lookup"><span data-stu-id="a3f00-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="a3f00-120">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a3f00-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="a3f00-121">Det går bara att visa befintlig export men inte skapa den.</span><span class="sxs-lookup"><span data-stu-id="a3f00-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="a3f00-122">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a3f00-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3f00-123">Välj **Lägg till export** om du vill skapa en ny exportmål.</span><span class="sxs-lookup"><span data-stu-id="a3f00-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="a3f00-124">I rutan **Ställ in export** väljer du vilken anslutning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="a3f00-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="a3f00-125">[Anslutningarna ](connections.md) hanteras av administratörer.</span><span class="sxs-lookup"><span data-stu-id="a3f00-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="a3f00-126">Ange den information som krävs och välj **Spara** för att skapa exporten.</span><span class="sxs-lookup"><span data-stu-id="a3f00-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="a3f00-127">Redigera export</span><span class="sxs-lookup"><span data-stu-id="a3f00-127">Edit an export</span></span>

1. <span data-ttu-id="a3f00-128">Markera den vertikala ellipsen för det exportmål du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a3f00-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="a3f00-129">Välj **Redigera** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="a3f00-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="a3f00-130">Ändra de värden du vill uppdatera och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a3f00-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="a3f00-131">Visa export- och exportinformation</span><span class="sxs-lookup"><span data-stu-id="a3f00-131">View Exports and export details</span></span>

<span data-ttu-id="a3f00-132">Efter att ha skapat exportdestinationer listas de på **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a3f00-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="a3f00-133">Alla användare kan se vilka data som delas och dess senaste status.</span><span class="sxs-lookup"><span data-stu-id="a3f00-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="a3f00-134">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a3f00-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3f00-135">Användare utan redigeringsbehörighet väljer **Visa** i stället för **Redigera** visas exportinformationen.</span><span class="sxs-lookup"><span data-stu-id="a3f00-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="a3f00-136">I den här sidan visas hur exporten har ställts in.</span><span class="sxs-lookup"><span data-stu-id="a3f00-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="a3f00-137">Du kan inte ändra värden utan att redigera behörigheter.</span><span class="sxs-lookup"><span data-stu-id="a3f00-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="a3f00-138">Välj **Stäng** om du vill återgå till exportsidan.</span><span class="sxs-lookup"><span data-stu-id="a3f00-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="a3f00-139">Kör exporter på begäran</span><span class="sxs-lookup"><span data-stu-id="a3f00-139">Run exports on demand</span></span>

<span data-ttu-id="a3f00-140">När du har konfigurerat en export körs den med alla [schemalagda uppdateringar](system.md#schedule-tab) så länge den har en fungerande anslutning.</span><span class="sxs-lookup"><span data-stu-id="a3f00-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="a3f00-141">För att exportera data utan att vänta på en schemalagd uppdatering, gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a3f00-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="a3f00-142">Du har två alternativ:</span><span class="sxs-lookup"><span data-stu-id="a3f00-142">You have two options:</span></span>

- <span data-ttu-id="a3f00-143">Om du vill köra alla exporter väljer du **Kör alla** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="a3f00-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="a3f00-144">Om du vill köra en enskild export markerar du denlipsen (...) på ett listobjekt och väljer sedan **Kör**.</span><span class="sxs-lookup"><span data-stu-id="a3f00-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="a3f00-145">Ta bort en export</span><span class="sxs-lookup"><span data-stu-id="a3f00-145">Remove an Export</span></span>

1. <span data-ttu-id="a3f00-146">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a3f00-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3f00-147">Markera den vertikala ellipsen för det export du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="a3f00-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="a3f00-148">Välj **Ta bort** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="a3f00-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="a3f00-149">Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.</span><span class="sxs-lookup"><span data-stu-id="a3f00-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
