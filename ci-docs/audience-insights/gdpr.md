---
title: Registrerades begäran (DSR) under GDPR | Microsoft Docs
description: Besvara registrerades begäran om funktionen målgruppsinsikter i Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268708"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="d1460-103">Registrerades begäran (DSR) under GDPR</span><span class="sxs-lookup"><span data-stu-id="d1460-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="d1460-104">Besvara GDPR registrerades begäran om borttagning av funktionen målgruppsinsikter i Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d1460-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="d1460-105">Rätten att ta bort personuppgifter från en organisations kunddata är ett viktigt skydd i allmänna dataskyddsförordningen (GDPR).</span><span class="sxs-lookup"><span data-stu-id="d1460-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="d1460-106">Om du tar bort personuppgifter tas även alla personuppgifter och systemgenererade loggar bort, förutom granskningslogginformationen.</span><span class="sxs-lookup"><span data-stu-id="d1460-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="d1460-107">Hantera registrerades begäran för att ta bort data</span><span class="sxs-lookup"><span data-stu-id="d1460-107">Manage data subject delete requests</span></span>

<span data-ttu-id="d1460-108">Målgruppsinsikter erbjuder följande produktupplevelser för borttagning av personuppgifter för en specifik kund eller användare:</span><span class="sxs-lookup"><span data-stu-id="d1460-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="d1460-109">**Hantera rader för borttagning av kunddata**: kunddata i Customer Insights inkommer från ursprungliga datakällor som är externa till Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1460-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="d1460-110">Alla GDPR begäran för att ta bort data måste utföras i original datakälla.</span><span class="sxs-lookup"><span data-stu-id="d1460-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="d1460-111">**Hantera begäranden om borttagning av data för Customer Insights-kund**: Data för användare skapas av Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1460-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="d1460-112">Alla GDPR begäran för att ta bort data måste utföras i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1460-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="d1460-113">Hantera begäran för att ta bort kunddata</span><span class="sxs-lookup"><span data-stu-id="d1460-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="d1460-114">En administratör för Customer Insights kan följa stegen nedan för att ta bort kunddata som tagits bort i datakällan:</span><span class="sxs-lookup"><span data-stu-id="d1460-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="d1460-115">Logga in på Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1460-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="d1460-116">I målgruppsinsikter går du till **Data** > **Datakällor**</span><span class="sxs-lookup"><span data-stu-id="d1460-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="d1460-117">För respektive datakälla i listan som innehåller borttagna kunduppgifter:</span><span class="sxs-lookup"><span data-stu-id="d1460-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="d1460-118">Välj (...) och sedan **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="d1460-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="d1460-119">Kontrollera status för datakälla under **Status**.</span><span class="sxs-lookup"><span data-stu-id="d1460-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="d1460-120">En bockmarkering betyder att uppdateringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="d1460-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="d1460-121">En varningstriangel betyder att något har gått fel.</span><span class="sxs-lookup"><span data-stu-id="d1460-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="d1460-122">Om en varningstriangel visas kontaktar du D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d1460-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d1460-123">![Hantera GDPR begäran för att ta bort kunddata](media/gdpr-data-sources.png "Hantera GDPR begäran för att ta bort kunddata")</span><span class="sxs-lookup"><span data-stu-id="d1460-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="d1460-124">Hantera begäranden om att ta bort användardata</span><span class="sxs-lookup"><span data-stu-id="d1460-124">Manage delete requests for user data</span></span>

<span data-ttu-id="d1460-125">En Customer Insights-administratör kan följa stegen nedan för att ta bort Customer Insights-användardata:</span><span class="sxs-lookup"><span data-stu-id="d1460-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="d1460-126">Logga in på Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1460-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="d1460-127">I målgruppsinsikter går du till **Admin** > **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="d1460-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="d1460-128">Markera kryssrutan för den användare du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="d1460-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="d1460-129">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="d1460-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d1460-130">![Hantera GDPR och begäranden om att ta bort användardata](media/gdpr-permissions.png "Hantera GDPR och begäranden om att ta bort användardata")</span><span class="sxs-lookup"><span data-stu-id="d1460-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="d1460-131">Svara på GDPR registrerades begäran för att exportera data</span><span class="sxs-lookup"><span data-stu-id="d1460-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="d1460-132">Som en del av vårt engagemang i vår strävan efter att resa till allmän dataskyddsförordning (GDPR) har vi utvecklat dokumentation som hjälper dig att förbereda dig.</span><span class="sxs-lookup"><span data-stu-id="d1460-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="d1460-133">I den här dokumentationen beskrivs vad du kan göra i dag för att stödja GDPR-efterlevnad när du använder målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="d1460-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="d1460-134">Hantera export och visa förfrågningar</span><span class="sxs-lookup"><span data-stu-id="d1460-134">Manage export and view requests</span></span>

<span data-ttu-id="d1460-135">Rätten till dataportabilitet kan användas av registrerade för att begära en kopia av deras personuppgifter i elektroniskt format (ett strukturerat, vanligt förekommande, maskinläsbart och driftskompatibelt format) som kan överföras till en annan personuppgiftsansvarig.</span><span class="sxs-lookup"><span data-stu-id="d1460-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="d1460-136">Exportera kunddata (klientorganisationens administratör).</span><span class="sxs-lookup"><span data-stu-id="d1460-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="d1460-137">Klientorganisationens administratör följer de här stegen för att exportera data:</span><span class="sxs-lookup"><span data-stu-id="d1460-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="d1460-138">Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange kundens e-postadress i förfrågan.</span><span class="sxs-lookup"><span data-stu-id="d1460-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="d1460-139">Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.</span><span class="sxs-lookup"><span data-stu-id="d1460-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="d1460-140">Bekräfta bekräftelsen av att exportera data för den begärda kunden.</span><span class="sxs-lookup"><span data-stu-id="d1460-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="d1460-141">Ta emot exporterade data via e-postadressen för innehavaradministration.</span><span class="sxs-lookup"><span data-stu-id="d1460-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="d1460-142">Exportera användardata (klientorganisationens administratör)</span><span class="sxs-lookup"><span data-stu-id="d1460-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="d1460-143">Skicka ett e-postmeddelande till D365CI@microsoft.com för att ange användarens e-postadress i förfrågan.</span><span class="sxs-lookup"><span data-stu-id="d1460-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="d1460-144">Customer Insights-teamet skickar ett e-postmeddelande till den registrerade administratörens e-postadress och ber om bekräftelse för att exportera data.</span><span class="sxs-lookup"><span data-stu-id="d1460-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="d1460-145">Bekräfta bekräftelsen av att exportera data för den begärda användaren.</span><span class="sxs-lookup"><span data-stu-id="d1460-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="d1460-146">Ta emot exporterade data via e-postadressen för innehavaradministration.</span><span class="sxs-lookup"><span data-stu-id="d1460-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]