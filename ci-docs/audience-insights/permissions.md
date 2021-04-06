---
title: Hantera användarbehörigheter
description: Läs om behörigheter och användarroller.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595724"
---
# <a name="user-permissions"></a><span data-ttu-id="8ab53-103">Användarbehörigheter</span><span class="sxs-lookup"><span data-stu-id="8ab53-103">User permissions</span></span>

<span data-ttu-id="8ab53-104">Sidan **Behörigheter** är där du ska konfigurera roller och behörigheter för att använda målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="8ab53-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="8ab53-105">Du måste ha administratörsbehörighet för att kunna visa sidan.</span><span class="sxs-lookup"><span data-stu-id="8ab53-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="8ab53-106">Om du vill komma åt behörighetssidan i målgruppsinsikter går du till **Admin** > **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="8ab53-107">Det finns tre typer av roller:</span><span class="sxs-lookup"><span data-stu-id="8ab53-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="8ab53-108">Tittare</span><span class="sxs-lookup"><span data-stu-id="8ab53-108">Viewer</span></span>

- <span data-ttu-id="8ab53-109">Utforska insikter och segment på sidorna **Start** och **Segment**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="8ab53-110">Sök och filtrera kundprofiler med hjälp av sidan **kunder**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="8ab53-111">Fälten måste vara sökbara.</span><span class="sxs-lookup"><span data-stu-id="8ab53-111">Fields must be searchable.</span></span>
- <span data-ttu-id="8ab53-112">Visa och utforska sidan **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="8ab53-113">Utforska och exportera entiteter med hjälp av sidan **entiteter**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="8ab53-114">Visa status för systemprocesser med hjälp av sidan **system**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="8ab53-115">Exportera segment från sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="8ab53-116">Installera och använd instrumentpanelen **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="8ab53-117">Deltagare</span><span class="sxs-lookup"><span data-stu-id="8ab53-117">Contributor</span></span>

- <span data-ttu-id="8ab53-118">Alla behörigheter som är tillgängliga för visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="8ab53-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="8ab53-119">Läsa in och transformera data från sidan **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="8ab53-120">Slutför avsnitten *Dataförening* (**Mappa**, **Matcha** och **Sammanslå**) som resulterar i den enhetliga entiteten för kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="8ab53-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="8ab53-121">Definiera **Relationer** och **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="8ab53-122">Skapa segment med hjälp sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="8ab53-123">Skapa mått med hjälp av sidan **Mått**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="8ab53-124">Hantera konfiguration och berika kundprofiler från sidan **Berikning** (endast för de förstapartsberikningar).</span><span class="sxs-lookup"><span data-stu-id="8ab53-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="8ab53-125">Administratör</span><span class="sxs-lookup"><span data-stu-id="8ab53-125">Administrator</span></span>

- <span data-ttu-id="8ab53-126">Alla behörigheter som är tillgängliga för deltagare.</span><span class="sxs-lookup"><span data-stu-id="8ab53-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="8ab53-127">Ändra inställningarna på sidan **System**, inklusive arbetsspråket och uppdateringsscheman för systemprocesserna.</span><span class="sxs-lookup"><span data-stu-id="8ab53-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="8ab53-128">Visa och lägg till behörigheter med hjälp av sidan **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="8ab53-129">Ange sök- och filterdefinitioner för sidan Kunder med hjälp av sidan **Sök- och filterindex** (nås via sidan **Kunder**).</span><span class="sxs-lookup"><span data-stu-id="8ab53-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="8ab53-130">Definiera segmentmål för Dynamics 365 Sales med hjälp av sidan **Exportmål**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="8ab53-131">Hantera konfigurationer och berika kundprofiler från sidan **Berikning** (för samtliga berikningar).</span><span class="sxs-lookup"><span data-stu-id="8ab53-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="8ab53-132">Installera och använd **Tillägget för kundkort**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="8ab53-133">Lägg till och använd **Power Apps anslutningsprogram**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="8ab53-134">Aktivera användning av [Customer Insights-API:er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="8ab53-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="8ab53-135">Tilldela roller och behörigheter</span><span class="sxs-lookup"><span data-stu-id="8ab53-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="8ab53-136">I målgruppsinsikter går du till **Admin** > **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="8ab53-137">Välj **Lägg till användare** för att öppna fönstret **Lägg till/redigera behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="8ab53-138">Använd fältet **Sök** fältet för att hitta den Azure Active Directory-användare eller -grupp vars behörigheter du vill justera.</span><span class="sxs-lookup"><span data-stu-id="8ab53-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="8ab53-139">Välj en **roll** som ska tilldelas användaren eller gruppen.</span><span class="sxs-lookup"><span data-stu-id="8ab53-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="8ab53-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-140">Select **Save**.</span></span> <span data-ttu-id="8ab53-141">Den aktuella miljön kommer automatiskt att delas med användaren eller medlemmarna i gruppen vars behörigheter du har ändrat.</span><span class="sxs-lookup"><span data-stu-id="8ab53-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="8ab53-142">Användarna kan komma åt appen Customer Insights och arbeta enligt den angivna rollen.</span><span class="sxs-lookup"><span data-stu-id="8ab53-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="8ab53-143">Visa aktuella behörigheter</span><span class="sxs-lookup"><span data-stu-id="8ab53-143">View current permissions</span></span>

<span data-ttu-id="8ab53-144">I målgruppsinsikter går du till **Admin** > **Behörigheter** för att se vilken rolltilldelning som är aktiv för tillfället.</span><span class="sxs-lookup"><span data-stu-id="8ab53-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="8ab53-145">Kolumnen **typ** anger en enskild användare, grupp eller ett program.</span><span class="sxs-lookup"><span data-stu-id="8ab53-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="8ab53-146">Systemet stöder enskilda användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="8ab53-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="8ab53-147">Roller anges i kolumnen **roll**.</span><span class="sxs-lookup"><span data-stu-id="8ab53-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="8ab53-148">Markera valfri kolumnrubrik om du vill sortera resultaten efter värdet i kolumnen.</span><span class="sxs-lookup"><span data-stu-id="8ab53-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="8ab53-149">Använd fältet **Sök** högst upp på sidan om du vill söka efter specifika användare.</span><span class="sxs-lookup"><span data-stu-id="8ab53-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]