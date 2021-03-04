---
title: Anslutningsapp för Power Apps
description: Anslut med Power Apps och Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268938"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="b2c40-103">Microsoft Power Apps anslutningsprogram (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="b2c40-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="b2c40-104">Få enhetliga kundprofiler i dina anpassade appar med Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b2c40-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="b2c40-105">Ansluta till Power Apps och Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b2c40-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="b2c40-106">Customer Insights är en av de många [tillgängliga källorna för data i Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="b2c40-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="b2c40-107">Se Power Apps-dokumentationen om hur du [lägger till en dataanslutning i en app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="b2c40-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="b2c40-108">Vi rekommenderar att du även granskar [hur Power Apps använder delegering för att hantera stora data mängder i arbetsyteappar](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="b2c40-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="b2c40-109">Tillgängliga entiteter</span><span class="sxs-lookup"><span data-stu-id="b2c40-109">Available entities</span></span>

<span data-ttu-id="b2c40-110">När du har lagt till Customer Insights som en dataanslutning kan du välja följande entiteter i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="b2c40-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="b2c40-111">Kund: om du vill använda data från den [enhetliga kundprofilen](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b2c40-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="b2c40-112">Enhetlig aktivitet: så här visar du [aktivitetstidslinje](activities.md) i appen.</span><span class="sxs-lookup"><span data-stu-id="b2c40-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="b2c40-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="b2c40-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="b2c40-114">Hämtningsbara entiteter</span><span class="sxs-lookup"><span data-stu-id="b2c40-114">Retrievable entities</span></span>

<span data-ttu-id="b2c40-115">Du kan bara hämta entiteterna **Kund**, **UnifiedActivity** och **Segment** via Power Apps-anslutaren.</span><span class="sxs-lookup"><span data-stu-id="b2c40-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="b2c40-116">Andra entiteter visas eftersom den underliggande anslutningen stöder dem via utlösare i Power Automate.</span><span class="sxs-lookup"><span data-stu-id="b2c40-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="b2c40-117">Delegering</span><span class="sxs-lookup"><span data-stu-id="b2c40-117">Delegation</span></span>

<span data-ttu-id="b2c40-118">Delegering fungerar för entiteten kund och UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="b2c40-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="b2c40-119">Delegering för entiteten **Kund**: För att använda delegering för den här entiteten måste fältet indexeras i [Sök & filtrera](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="b2c40-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="b2c40-120">Delegering för **UnifiedActivity**: delegering för den här entiteten fungerar endast för fälten **ActivityId** och **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="b2c40-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="b2c40-121">Mer information om delegering finns i [Power Apps delegerbara funktioner och åtgärder](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="b2c40-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="b2c40-122">Kontroll i exempelgalleri</span><span class="sxs-lookup"><span data-stu-id="b2c40-122">Example gallery control</span></span>

<span data-ttu-id="b2c40-123">Du lägger till exempel till kundprofiler i en [gallerikontroll](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="b2c40-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="b2c40-124">Lägg till en **Galleri**-kontroll i en app som du bygger.</span><span class="sxs-lookup"><span data-stu-id="b2c40-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b2c40-125">![Lägga till ett gallerielement](media/connector-powerapps9.png "Lägga till ett gallerielement")</span><span class="sxs-lookup"><span data-stu-id="b2c40-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="b2c40-126">Välj **kund** som datakälla för artiklar.</span><span class="sxs-lookup"><span data-stu-id="b2c40-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b2c40-127">![Välj datakälla](media/choose-datasource-powerapps.png "Välj datakälla")</span><span class="sxs-lookup"><span data-stu-id="b2c40-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="b2c40-128">Du kan ändra datapanelen till höger och välja vilket fält för den kundentitet som ska visas i galleriet.</span><span class="sxs-lookup"><span data-stu-id="b2c40-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="b2c40-129">Om du vill visa ett fält från den valda kunden i galleriet fyller du i egenskapen text för en etikett: **{Name_of_the_gallery}.Valt.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="b2c40-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="b2c40-130">Exempel: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="b2c40-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="b2c40-131">Om du vill visa den enhetliga tidslinjen för en kund lägger du till ett gallerielement och lägger till egenskapen för Objekt: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="b2c40-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="b2c40-132">Exempel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="b2c40-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]