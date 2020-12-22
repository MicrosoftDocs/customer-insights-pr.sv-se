---
title: Exportmål
description: Exportera data och hantera exportdestinationer.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643885"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="bbda2-103">Exportmål (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="bbda2-103">Export destinations (preview)</span></span>

<span data-ttu-id="bbda2-104">På sidan **exportera destinationer** visas alla platser som du har konfigurerat för att exportera data till.</span><span class="sxs-lookup"><span data-stu-id="bbda2-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="bbda2-105">Du kan också lägga till nya destinationer för export.</span><span class="sxs-lookup"><span data-stu-id="bbda2-105">You can also add new destinations for export.</span></span> <span data-ttu-id="bbda2-106">Dessutom visas exportalternativ som är tillgängliga för tillfället.</span><span class="sxs-lookup"><span data-stu-id="bbda2-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="bbda2-107">Få en snabb översikt, beskrivning och ta reda på vad du kan göra med de olika utökningsalternativen.</span><span class="sxs-lookup"><span data-stu-id="bbda2-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="bbda2-108">Exportera enhetliga profiler, mått och segment till program som stöds och som är relevanta för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="bbda2-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="bbda2-109">Gå till **administration** > **exportdestinationer** för att hitta följande utökningsalternativ:</span><span class="sxs-lookup"><span data-stu-id="bbda2-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="bbda2-110">Tillägget för kundkort i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bbda2-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="bbda2-111">Anslutning för Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="bbda2-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="bbda2-112">Power Automate anslutningsprogram</span><span class="sxs-lookup"><span data-stu-id="bbda2-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="bbda2-113">Power Apps anslutningsprogram</span><span class="sxs-lookup"><span data-stu-id="bbda2-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="bbda2-114">Power BI anslutningsprogram</span><span class="sxs-lookup"><span data-stu-id="bbda2-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="bbda2-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="bbda2-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="bbda2-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="bbda2-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="bbda2-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="bbda2-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="bbda2-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="bbda2-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="bbda2-119">LiveRamp&reg; anslutning</span><span class="sxs-lookup"><span data-stu-id="bbda2-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="bbda2-120">Robot för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbda2-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="bbda2-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="bbda2-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="bbda2-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="bbda2-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="bbda2-123">Lägg till ett nytt exportmål</span><span class="sxs-lookup"><span data-stu-id="bbda2-123">Add a new export destination</span></span>

<span data-ttu-id="bbda2-124">Om du vill lägga till exportdestinationer har du [administratörsbehörigheter](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bbda2-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="bbda2-125">Om du exporterar till Microsoft-tjänster antar vi att båda tjänsterna finns i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="bbda2-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="bbda2-126">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="bbda2-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bbda2-127">Gå till fliken **Mina exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="bbda2-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="bbda2-128">Välj **Lägg till mål** om du vill skapa ett nytt exportmål.</span><span class="sxs-lookup"><span data-stu-id="bbda2-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="bbda2-129">I rutan **Lägg till mål** väljer du **Typ** av exportmål i listrutan.</span><span class="sxs-lookup"><span data-stu-id="bbda2-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="bbda2-130">Ange de uppgifter som krävs och välj **Nästa** för att skapa exportmålet.</span><span class="sxs-lookup"><span data-stu-id="bbda2-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="bbda2-131">Du kan också välja **Konfigurera** på panelen **Identifiering**.</span><span class="sxs-lookup"><span data-stu-id="bbda2-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="bbda2-132">Visa exportmål</span><span class="sxs-lookup"><span data-stu-id="bbda2-132">View Export destinations</span></span>

<span data-ttu-id="bbda2-133">När du har skapat exportmål hittar du dem i en tabell på fliken **Mina exportmål**. Tabellen har tre kolumner:</span><span class="sxs-lookup"><span data-stu-id="bbda2-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="bbda2-134">**Visningsnamn**: det namn du angav när du skapade målet.</span><span class="sxs-lookup"><span data-stu-id="bbda2-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="bbda2-135">**Typ**: den exportmåltyp du angav när du skapade målet.</span><span class="sxs-lookup"><span data-stu-id="bbda2-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="bbda2-136">**Skapades**: Det datum då du skapade målet.</span><span class="sxs-lookup"><span data-stu-id="bbda2-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="bbda2-137">Redigera ett exportmål</span><span class="sxs-lookup"><span data-stu-id="bbda2-137">Edit an export destination</span></span>

1. <span data-ttu-id="bbda2-138">Markera den vertikala ellipsen för det exportmål du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="bbda2-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbda2-139">![Lodrät ellips](media/export-destinations-page-ellipsis.png "Lodrät ellips")</span><span class="sxs-lookup"><span data-stu-id="bbda2-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="bbda2-140">Välj **Redigera** från listruta.</span><span class="sxs-lookup"><span data-stu-id="bbda2-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="bbda2-141">Ändra värdena som kräver uppdatering och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bbda2-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="bbda2-142">Exportera data på begäran</span><span class="sxs-lookup"><span data-stu-id="bbda2-142">Export data on demand</span></span>

<span data-ttu-id="bbda2-143">När du har konfigurerat en anslutning till ett exportmål körs exporten med varje [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bbda2-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="bbda2-144">För att exportera data utan att vänta på en schemalagd uppdatering, gå till fliken **Mina exportmål** på **Administratör** > **Exportmål**.</span><span class="sxs-lookup"><span data-stu-id="bbda2-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bbda2-145">![Lodrät ellips](media/export-destinations-page-ellipsis.png "Lodrät ellips")</span><span class="sxs-lookup"><span data-stu-id="bbda2-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="bbda2-146">Välj **Exportera** ovanför listan om du vill köra exporten till alla exportmål samtidigt.</span><span class="sxs-lookup"><span data-stu-id="bbda2-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="bbda2-147">Markera ellipsknappen (...) efter ett listobjekt och välj alternativet **export** för att köra exporten för ett enskilt exportmål.</span><span class="sxs-lookup"><span data-stu-id="bbda2-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="bbda2-148">Ta bort ett exportmål</span><span class="sxs-lookup"><span data-stu-id="bbda2-148">Remove an Export destination</span></span>

<span data-ttu-id="bbda2-149">Om du vill ta bort ett exportmål går du till sidan **exportmål**.</span><span class="sxs-lookup"><span data-stu-id="bbda2-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="bbda2-150">Markera den vertikala ellipsen för det exportmål du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="bbda2-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbda2-151">![Lodrät ellips](media/export-destinations-page-ellipsis.png "Lodrät ellips")</span><span class="sxs-lookup"><span data-stu-id="bbda2-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="bbda2-152">Välj **Ta bort** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="bbda2-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="bbda2-153">Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.</span><span class="sxs-lookup"><span data-stu-id="bbda2-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
