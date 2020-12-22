---
title: Visa kundprofiler
description: Få en kombinerad vy över dina enhetliga kunddata.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653912"
---
# <a name="customer-profiles"></a><span data-ttu-id="90970-103">Kundprofiler</span><span class="sxs-lookup"><span data-stu-id="90970-103">Customer profiles</span></span>

<span data-ttu-id="90970-104">Sidan **Kunder** visar en kombinerad vy över dina kunder, baserat på profildata som samlats in från [alla datakällor](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="90970-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="90970-105">Kundprofiler är tillgängliga när du [har skapat en enhetlig kundentitet](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="90970-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="90970-106">Kontrollera att du har slutfört föreningsprocessen för data för att få bättre vyer över dina kunder.</span><span class="sxs-lookup"><span data-stu-id="90970-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="90970-107">På sidan kan du också söka efter kunder.</span><span class="sxs-lookup"><span data-stu-id="90970-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="90970-108">Kunder kan vara enskilda personer eller organisationer (förhandsgranskning).</span><span class="sxs-lookup"><span data-stu-id="90970-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="90970-109">Varje kund- eller organisations profil representeras av en panel.</span><span class="sxs-lookup"><span data-stu-id="90970-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="90970-110">Välj en panel om du vill visa ytterligare information om just den kunden eller organisationen.</span><span class="sxs-lookup"><span data-stu-id="90970-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="90970-111">Använd sidbrytningskontrollerna längst ned på sidan om du vill visa fler poster.</span><span class="sxs-lookup"><span data-stu-id="90970-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="90970-112">![B2C-kundprofil](media/profiles-customers.png "B2C-kundprofil")</span><span class="sxs-lookup"><span data-stu-id="90970-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="90970-113">Organisationer (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="90970-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="90970-114">![B2B-kundprofil](media/profile-customers-b2b.png "B2B-kundprofil")</span><span class="sxs-lookup"><span data-stu-id="90970-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="90970-115">Om du inte ser panelerna när du väljer **kunder** i navigeringen måste administratören [definiera minst ett sökbart attribut](search-filter-index.md) i **Sök och filtrera index**.</span><span class="sxs-lookup"><span data-stu-id="90970-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="90970-116">Sök efter kunder</span><span class="sxs-lookup"><span data-stu-id="90970-116">Search for customers</span></span>

<span data-ttu-id="90970-117">Sök efter kunder genom att ange ett namn eller ett annat attribut i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="90970-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="90970-118">Sökningen fungerar endast inom entiteten kundprofil som skapades under föreningsprocessen för data.</span><span class="sxs-lookup"><span data-stu-id="90970-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="90970-119">Som administratör kan du konfigurera de sökbara attributen med hjälp av sidan **Sök- och filterindex**.</span><span class="sxs-lookup"><span data-stu-id="90970-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="90970-120">Mer information finns i [Hantera sök- och filterindex](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="90970-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="90970-121">Filtrera kunder</span><span class="sxs-lookup"><span data-stu-id="90970-121">Filter customers</span></span>

<span data-ttu-id="90970-122">Du kan filtrera kunder efter entitetsfältet kundprofil.</span><span class="sxs-lookup"><span data-stu-id="90970-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="90970-123">Precis som du söker måste din administratör först definiera fälten som filtrerbar med hjälp av sida **Sök- och filtrera index**.</span><span class="sxs-lookup"><span data-stu-id="90970-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="90970-124">Välj **Filter** på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="90970-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="90970-125">Markera rutorna bredvid attribut som du vill filtrera kunder efter.</span><span class="sxs-lookup"><span data-stu-id="90970-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="90970-126">![Kundprofiler](media/profiles-customers3.png "Kundprofiler")</span><span class="sxs-lookup"><span data-stu-id="90970-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="90970-127">Ta bort dina filter genom att välja **Rensa filter** på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="90970-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="90970-128">Kundinformationsfönstret</span><span class="sxs-lookup"><span data-stu-id="90970-128">Customer details page</span></span>

<span data-ttu-id="90970-129">Välj någon av kundpanelerna för att öppna **kundinformationsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="90970-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="90970-130">Den här vyn innehåller enhetlig information för den valda kunden.</span><span class="sxs-lookup"><span data-stu-id="90970-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="90970-131">Kundinformation innefattar:</span><span class="sxs-lookup"><span data-stu-id="90970-131">Customer details include:</span></span>

-   <span data-ttu-id="90970-132">**Kundprofilspanel:** Den här panelen visar de olika värdena från den enhetliga kundprofilsentiteten.</span><span class="sxs-lookup"><span data-stu-id="90970-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="90970-133">Informationen kan vara e-postadress, namn, stad och så vidare.</span><span class="sxs-lookup"><span data-stu-id="90970-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="90970-134">**Potentiella intressen, potentiella varumärken:** Visar om du har konfigurerat en förstapartsberikning.</span><span class="sxs-lookup"><span data-stu-id="90970-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="90970-135">Den representerar potentiella intressen och samhörigheter för en kund som har en profil som liknar den som kunden har.</span><span class="sxs-lookup"><span data-stu-id="90970-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="90970-136">Mer information finns i [berika kundprofiler med samhörigheter med varumärke och intresse](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="90970-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="90970-137">**Mått:** Visar om du har konfigurerat ett eller flera mått av en specifik typ: mått av kundattribut.</span><span class="sxs-lookup"><span data-stu-id="90970-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="90970-138">De inkluderar beräknade KPI:er runt dina kunder på den enskilda kundnivån.</span><span class="sxs-lookup"><span data-stu-id="90970-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="90970-139">Mer information finns i [Definiera och hantera mått](measures.md).</span><span class="sxs-lookup"><span data-stu-id="90970-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="90970-140">**Aktivitetstidslinje:** Visar om du har konfigurerat aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="90970-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="90970-141">Vyn tidslinje innehåller kronologiskt sorterade aktiviteter för kunden, med start från den senaste aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="90970-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="90970-142">Mer information finns i [Kundaktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="90970-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="90970-143">Välj **Tillbaka till kunder** för att återgå till kundsöksidan.</span><span class="sxs-lookup"><span data-stu-id="90970-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="90970-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="90970-144">Next steps</span></span>

<span data-ttu-id="90970-145">[Lägg till fler datakällor](data-sources.md) eller [Skapa kundsegment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="90970-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
