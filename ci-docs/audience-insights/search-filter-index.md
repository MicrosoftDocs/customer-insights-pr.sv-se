---
title: Sök och filtrera kundprofiler
description: Hitta snabbt information om enhetliga kundprofiler och filter för angivna attribut.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407108"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="d7111-103">Kundprofiler: Sök- och filterindex</span><span class="sxs-lookup"><span data-stu-id="d7111-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="d7111-104">Resultatet av att förena kunddata är en kundprofils entitet som tillhandahåller en enhetlig vy till den totala kundbasen.</span><span class="sxs-lookup"><span data-stu-id="d7111-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="d7111-105">Om du snabbt vill [hitta information om en viss kund eller grupp](customer-profiles.md) kan du konfigurera funktionerna **Sök** och **Filter** på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="d7111-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="d7111-106">Läs vidare om du vill veta hur administratörer kan redigera attributen på sidan **Sök och filtrera index** som är tillgängliga för användare för sökning och filtrering.</span><span class="sxs-lookup"><span data-stu-id="d7111-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7111-107">![Sökfilter](media/search-filter.png "Sökfilter")</span><span class="sxs-lookup"><span data-stu-id="d7111-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="d7111-108">Lägg till fält och ange attribut</span><span class="sxs-lookup"><span data-stu-id="d7111-108">Add fields and specify attributes</span></span>

<span data-ttu-id="d7111-109">Om det är första gången du definierar sökbara attribut som en administratör måste du definiera indexerade fält först.</span><span class="sxs-lookup"><span data-stu-id="d7111-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="d7111-110">Vi föreslår att du väljer alla attribut som användarna kan söka i och filtrera kunder på i sidan **kunder**.</span><span class="sxs-lookup"><span data-stu-id="d7111-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="d7111-111">Du kan endast ange attribut som finns i entiteten kundprofil som du skapade under dataföreningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="d7111-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="d7111-112">Öppna sidan **Kunder** och välj **Sök & filtrera index**.</span><span class="sxs-lookup"><span data-stu-id="d7111-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="d7111-113">Vi skapar en standardkonfiguration för sökindex på tillgängliga attribut i entiteten för kundentitet från följande semantiska typer som definierats på sidan Mappning.</span><span class="sxs-lookup"><span data-stu-id="d7111-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="d7111-114">Förnamn, Efternamn, Mellannamn, Fullständigt namn</span><span class="sxs-lookup"><span data-stu-id="d7111-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="d7111-115">Organisationsnamn</span><span class="sxs-lookup"><span data-stu-id="d7111-115">Organization Name</span></span>
> - <span data-ttu-id="d7111-116">E-postadress</span><span class="sxs-lookup"><span data-stu-id="d7111-116">Email address</span></span>
> - <span data-ttu-id="d7111-117">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="d7111-117">Phone number</span></span>
> - <span data-ttu-id="d7111-118">Platsinformation</span><span class="sxs-lookup"><span data-stu-id="d7111-118">Location information</span></span>

2. <span data-ttu-id="d7111-119">Välj **+ Lägg till** för att ange indexerade fält.</span><span class="sxs-lookup"><span data-stu-id="d7111-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="d7111-120">Välj attribut i listan som du vill lägga till som indexerade fält.</span><span class="sxs-lookup"><span data-stu-id="d7111-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="d7111-121">Du kan alltid lägga till fler attribut genom att välja **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d7111-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="d7111-122">Du kan även ta bort valda attribut genom att välja symbolen **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="d7111-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="d7111-123">Utforska tabellen indexerade kundfält</span><span class="sxs-lookup"><span data-stu-id="d7111-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="d7111-124">Följande information presenteras i tabellen.</span><span class="sxs-lookup"><span data-stu-id="d7111-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="d7111-125">**Namn**: representerar attributets namn som det visas i entiteten kundprofil.</span><span class="sxs-lookup"><span data-stu-id="d7111-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="d7111-126">**Datatyp**: anger om datatypen är en sträng, ett tal eller ett datum.</span><span class="sxs-lookup"><span data-stu-id="d7111-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="d7111-127">**Ingår i sökningen**: anger om det här attributet kan användas för att söka efter kunder på sidan **Kunder** med hjälp av fältet **Sök**.</span><span class="sxs-lookup"><span data-stu-id="d7111-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="d7111-128">**Lägg till filter**: kontroll för att definiera hur det här attributet kan användas för filtrering på sidan **kunder**.</span><span class="sxs-lookup"><span data-stu-id="d7111-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="d7111-129">Redigera filtreringsalternativ för ett givet attribut</span><span class="sxs-lookup"><span data-stu-id="d7111-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="d7111-130">Menyn **filtrera** på sidan **kunder** kan innehålla ett varierande antal attributvärden (t.ex. olika åldersgrupper för att filtrera kunder).</span><span class="sxs-lookup"><span data-stu-id="d7111-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="d7111-131">Välj **Lägg till filter** för ett givet attribut på sidan **Sök och filtrera index**.</span><span class="sxs-lookup"><span data-stu-id="d7111-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="d7111-132">Du kan ange antalet resultat och i vilken ordning de ska ordnas.</span><span class="sxs-lookup"><span data-stu-id="d7111-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="d7111-133">Beroende på attributets datatyp visas någon av följande rutor.</span><span class="sxs-lookup"><span data-stu-id="d7111-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="d7111-134">Attribut av strängtyp: ange antalet önskade resultat i fönstret **Alternativ för strängfilter** och den ordning som de ska ordnas efter.</span><span class="sxs-lookup"><span data-stu-id="d7111-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="d7111-135">Attribut av numerisk typ: ange intervaller som ingår i fönstret **Alternativ för nummerfilter** och den ordning som de ska ordnas efter.</span><span class="sxs-lookup"><span data-stu-id="d7111-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="d7111-136">Attribut av datumtyp: ange intervaller som ingår i fönstret **Alternativ för datumfilter** och den ordning som de ska ordnas efter.</span><span class="sxs-lookup"><span data-stu-id="d7111-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="d7111-137">Välj **Spara** för att införa ändringarna.</span><span class="sxs-lookup"><span data-stu-id="d7111-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="d7111-138">Välj **kör** när du är redo att tillämpa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="d7111-138">Select **Run** once you're ready to apply your settings.</span></span>
