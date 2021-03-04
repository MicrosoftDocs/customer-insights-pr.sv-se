---
title: Sök och filtrera kundprofiler
description: Hitta snabbt information om enhetliga kundprofiler och filter för angivna attribut.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270088"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="fb4f8-103">Kundprofiler: Sök- och filterindex</span><span class="sxs-lookup"><span data-stu-id="fb4f8-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="fb4f8-104">Resultatet av att förena kunddata är en kundprofils entitet som tillhandahåller en enhetlig vy till den totala kundbasen.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="fb4f8-105">Om du snabbt vill [hitta information om en viss kund eller grupp](customer-profiles.md) kan du konfigurera funktionerna **Sök** och **Filter** på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="fb4f8-106">Läs vidare om du vill veta hur administratörer kan redigera attributen på sidan **Sök och filtrera index** som är tillgängliga för användare för sökning och filtrering.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb4f8-107">![Sökfilter](media/search-filter.png "Sökfilter")</span><span class="sxs-lookup"><span data-stu-id="fb4f8-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="fb4f8-108">Lägg till fält och ange attribut</span><span class="sxs-lookup"><span data-stu-id="fb4f8-108">Add fields and specify attributes</span></span>

<span data-ttu-id="fb4f8-109">Om det är första gången du definierar sökbara attribut som en administratör måste du definiera indexerade fält först.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="fb4f8-110">Vi föreslår att du väljer alla attribut som användarna kan söka i och filtrera kunder på i sidan **kunder**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="fb4f8-111">Du kan endast ange attribut som finns i entiteten kundprofil som du skapade under dataföreningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="fb4f8-112">Öppna sidan **Kunder** och välj **Sök & filtrera index**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="fb4f8-113">Välj **+ Lägg till** för att ange indexerade fält.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="fb4f8-114">Välj attribut i listan som du vill lägga till som indexerade fält.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="fb4f8-115">Du kan alltid lägga till fler attribut genom att välja **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="fb4f8-116">Du kan även ta bort valda attribut genom att välja symbolen **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="fb4f8-117">Utforska tabellen indexerade kundfält</span><span class="sxs-lookup"><span data-stu-id="fb4f8-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="fb4f8-118">Följande information presenteras i tabellen.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="fb4f8-119">**Namn**: representerar attributets namn som det visas i entiteten kundprofil.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="fb4f8-120">**Datatyp**: anger om datatypen är en sträng, ett tal eller ett datum.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="fb4f8-121">**Ingår i sökningen**: anger om det här attributet kan användas för att söka efter kunder på sidan **Kunder** med hjälp av fältet **Sök**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="fb4f8-122">**Lägg till filter**: kontroll för att definiera hur det här attributet kan användas för filtrering på sidan **kunder**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="fb4f8-123">Redigera filtreringsalternativ för ett givet attribut</span><span class="sxs-lookup"><span data-stu-id="fb4f8-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="fb4f8-124">Menyn **filtrera** på sidan **kunder** kan innehålla ett varierande antal attributvärden (t.ex. olika åldersgrupper för att filtrera kunder).</span><span class="sxs-lookup"><span data-stu-id="fb4f8-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="fb4f8-125">Välj **Lägg till filter** för ett givet attribut på sidan **Sök och filtrera index**.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="fb4f8-126">Du kan ange antalet resultat och i vilken ordning de ska ordnas.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="fb4f8-127">Beroende på attributets datatyp visas någon av följande rutor.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="fb4f8-128">Attribut av strängtyp: ange antalet önskade resultat i fönstret **Alternativ för strängfilter** och den ordning som de ska ordnas efter.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="fb4f8-129">Attribut av numerisk typ: ange intervaller som ingår i fönstret **Alternativ för nummerfilter** och den ordning som de ska ordnas efter.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="fb4f8-130">Attribut av datumtyp: ange intervaller som ingår i fönstret **Alternativ för datumfilter** och den ordning som de ska ordnas efter.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="fb4f8-131">Välj **Spara** för att införa ändringarna.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="fb4f8-132">Välj **kör** när du är redo att tillämpa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb4f8-133">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fb4f8-133">Next steps</span></span>

<span data-ttu-id="fb4f8-134">Gå till sidan **Kunder** om du vill söka efter kundprofiler eller använda de indexerade fälten och visa en deluppsättning av alla kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="fb4f8-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]