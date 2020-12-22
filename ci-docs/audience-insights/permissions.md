---
title: Hantera användarbehörigheter
description: Läs om behörigheter och användarroller.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689242"
---
# <a name="user-permissions"></a><span data-ttu-id="97355-103">Användarbehörigheter</span><span class="sxs-lookup"><span data-stu-id="97355-103">User permissions</span></span>

<span data-ttu-id="97355-104">Sidan **Behörigheter** är där du ska konfigurera roller och behörigheter för att använda målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="97355-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="97355-105">Du måste ha administratörsbehörighet för att kunna visa sidan.</span><span class="sxs-lookup"><span data-stu-id="97355-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="97355-106">Om du vill komma åt behörighetssidan i målgruppsinsikter går du till **Admin** > **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="97355-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="97355-107">Det finns tre typer av roller:</span><span class="sxs-lookup"><span data-stu-id="97355-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="97355-108">Tittare</span><span class="sxs-lookup"><span data-stu-id="97355-108">Viewer</span></span>

- <span data-ttu-id="97355-109">Utforska insikter och segment på sidorna **Start** och **Segment**.</span><span class="sxs-lookup"><span data-stu-id="97355-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="97355-110">Sök och filtrera kundprofiler med hjälp av sidan **kunder**.</span><span class="sxs-lookup"><span data-stu-id="97355-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="97355-111">Fälten måste vara sökbara.</span><span class="sxs-lookup"><span data-stu-id="97355-111">Fields must be searchable.</span></span>
- <span data-ttu-id="97355-112">Visa och utforska sidan **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="97355-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="97355-113">Utforska och exportera entiteter med hjälp av sidan **entiteter**.</span><span class="sxs-lookup"><span data-stu-id="97355-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="97355-114">Visa status för systemprocesser med hjälp av sidan **system**.</span><span class="sxs-lookup"><span data-stu-id="97355-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="97355-115">Exportera segment från sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="97355-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="97355-116">Installera och använd instrumentpanelen **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="97355-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="97355-117">Deltagare</span><span class="sxs-lookup"><span data-stu-id="97355-117">Contributor</span></span>

- <span data-ttu-id="97355-118">Alla behörigheter som är tillgängliga för visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="97355-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="97355-119">Läsa in och transformera data från sidan **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="97355-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="97355-120">Slutför avsnitten *Dataförening* (**Mappa**, **Matcha** och **Sammanslå**) som resulterar i den enhetliga entiteten för kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="97355-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="97355-121">Definiera **Relationer** och **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="97355-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="97355-122">Skapa segment med hjälp sidan **Segment**.</span><span class="sxs-lookup"><span data-stu-id="97355-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="97355-123">Skapa mått med hjälp av sidan **Mått**.</span><span class="sxs-lookup"><span data-stu-id="97355-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="97355-124">Hantera konfiguration och berika kundprofiler från sidan **Berikning** (endast för de förstapartsberikningar).</span><span class="sxs-lookup"><span data-stu-id="97355-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="97355-125">Administratör</span><span class="sxs-lookup"><span data-stu-id="97355-125">Administrator</span></span>

- <span data-ttu-id="97355-126">Alla behörigheter som är tillgängliga för deltagare.</span><span class="sxs-lookup"><span data-stu-id="97355-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="97355-127">Ändra inställningarna på sidan **System**, inklusive arbetsspråket och uppdateringsscheman för systemprocesserna.</span><span class="sxs-lookup"><span data-stu-id="97355-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="97355-128">Visa och lägg till behörigheter med hjälp av sidan **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="97355-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="97355-129">Ange sök- och filterdefinitioner för sidan Kunder med hjälp av sidan **Sök- och filterindex** (nås via sidan **Kunder**).</span><span class="sxs-lookup"><span data-stu-id="97355-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="97355-130">Definiera segmentmål för Dynamics 365 Sales med hjälp av sidan **Exportmål**.</span><span class="sxs-lookup"><span data-stu-id="97355-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="97355-131">Hantera konfigurationer och berika kundprofiler från sidan **Berikning** (för samtliga berikningar).</span><span class="sxs-lookup"><span data-stu-id="97355-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="97355-132">Installera och använd **Tillägget för kundkort**.</span><span class="sxs-lookup"><span data-stu-id="97355-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="97355-133">Lägg till och använd **Power Apps anslutningsprogram**.</span><span class="sxs-lookup"><span data-stu-id="97355-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="97355-134">Aktivera användning av [Customer Insights-API:er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="97355-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="97355-135">Tilldela roller och behörigheter</span><span class="sxs-lookup"><span data-stu-id="97355-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="97355-136">I målgruppsinsikter går du till **Admin** > **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="97355-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="97355-137">Välj **Lägg till användare** för att öppna fönstret **Lägg till/redigera behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="97355-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="97355-138">Använd fältet **Sök** fältet för att hitta den Azure Active Directory-användare eller -grupp vars behörigheter du vill justera.</span><span class="sxs-lookup"><span data-stu-id="97355-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="97355-139">Välj en **roll** som ska tilldelas användaren eller gruppen.</span><span class="sxs-lookup"><span data-stu-id="97355-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="97355-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="97355-140">Select **Save**.</span></span> <span data-ttu-id="97355-141">Den aktuella miljön kommer automatiskt att delas med användaren eller medlemmarna i gruppen vars behörigheter du har ändrat.</span><span class="sxs-lookup"><span data-stu-id="97355-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="97355-142">Användarna kan komma åt appen Customer Insights och arbeta enligt den angivna rollen.</span><span class="sxs-lookup"><span data-stu-id="97355-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="97355-143">Visa aktuella behörigheter</span><span class="sxs-lookup"><span data-stu-id="97355-143">View current permissions</span></span>

<span data-ttu-id="97355-144">I målgruppsinsikter går du till **Admin** > **Behörigheter** för att se vilken rolltilldelning som är aktiv för tillfället.</span><span class="sxs-lookup"><span data-stu-id="97355-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="97355-145">Kolumnen **typ** anger en enskild användare, grupp eller ett program.</span><span class="sxs-lookup"><span data-stu-id="97355-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="97355-146">Systemet stöder enskilda användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="97355-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="97355-147">Roller anges i kolumnen **roll**.</span><span class="sxs-lookup"><span data-stu-id="97355-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="97355-148">Markera valfri kolumnrubrik om du vill sortera resultaten efter värdet i kolumnen.</span><span class="sxs-lookup"><span data-stu-id="97355-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="97355-149">Använd fältet **Sök** högst upp på sidan om du vill söka efter specifika användare.</span><span class="sxs-lookup"><span data-stu-id="97355-149">Use the **Search** field at the top of the page to locate specific users.</span></span>
