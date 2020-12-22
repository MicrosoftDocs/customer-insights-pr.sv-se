---
title: Anslut till entiteter i den Common Data Service-hanterade sjön
description: Importera data från en Common Data Service hanterad datasjö.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643420"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="f9475-103">Anslut till data i en Common Data Service hanterad datasjö</span><span class="sxs-lookup"><span data-stu-id="f9475-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f9475-104">Den här artikeln innehåller information om hur befintliga Dynamics 365-kunder snabbt kan ansluta till deras analysenheter i en Common Data Service hanterad sjö.</span><span class="sxs-lookup"><span data-stu-id="f9475-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="f9475-105">Du måste vara administratör i Common Data Service organisationen för att kunna fortsätta och visa en lista över tillgängliga entiteter i den hanterade sjän.</span><span class="sxs-lookup"><span data-stu-id="f9475-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="f9475-106">Viktigt!</span><span class="sxs-lookup"><span data-stu-id="f9475-106">Important considerations</span></span>

<span data-ttu-id="f9475-107">Data som lagras i en onlinetjänster, t.ex. Azure Data Lake Storage kan lagras på en annan plats än där data bearbetas eller lagras i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f9475-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="f9475-108">Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="f9475-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="f9475-109">Ansluta till en Common Data Service hanterad sjö</span><span class="sxs-lookup"><span data-stu-id="f9475-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="f9475-110">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="f9475-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f9475-111">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="f9475-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="f9475-112">Välj **Anslut till Common Data Service** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f9475-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="f9475-113">Ange ett **namn** för datakällan och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f9475-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="f9475-114">Ange **Serveradressen** för din Common Data Service organisation och välj **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="f9475-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f9475-115">![Dialogruta där du anger Common Data Service serveradressen](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="f9475-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="f9475-116">Markera de entiteter som du vill mata in från den tillgängliga listan.</span><span class="sxs-lookup"><span data-stu-id="f9475-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="f9475-117">Om några entiteter redan valts kan de användas av andra Dynamics 365-program (t.ex. Dynamics 365 Sales Insights eller Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="f9475-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="f9475-118">Det går inte att ändra det här valet.</span><span class="sxs-lookup"><span data-stu-id="f9475-118">You can't change the selection.</span></span> <span data-ttu-id="f9475-119">Entiteterna blir tillgängliga när datakälla skapas.</span><span class="sxs-lookup"><span data-stu-id="f9475-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f9475-120">![Dialogruta med en lista över entiteter i Common Data Service organisationen](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="f9475-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="f9475-121">Spara ditt val om du vill synkronisera de valda enheterna med den Common Data Service hanterade sjö.</span><span class="sxs-lookup"><span data-stu-id="f9475-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="f9475-122">Den nyligen tillagda anslutningen finns på sidan **datakällor**.</span><span class="sxs-lookup"><span data-stu-id="f9475-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="f9475-123">Den placeras i kö för uppdatering och visar antalet entiteter som 0 tills alla entiteter har synkroniserats.</span><span class="sxs-lookup"><span data-stu-id="f9475-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="f9475-124">Endast en datakälla av en miljö kan samtidigt använda samma Common Data Service-hanterade sjö.</span><span class="sxs-lookup"><span data-stu-id="f9475-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="f9475-125">Redigera en Common Data Service hanterad sjö datakälla</span><span class="sxs-lookup"><span data-stu-id="f9475-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="f9475-126">Du redigerar endast enhetsurvalet när du har skapat datakälla.</span><span class="sxs-lookup"><span data-stu-id="f9475-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="f9475-127">Exempel: om fler entiteter har lagts till Common Data Service och du vill importera dem också.</span><span class="sxs-lookup"><span data-stu-id="f9475-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="f9475-128">För att ansluta till en annan Common Data Service, [skapa en ny datakälla](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="f9475-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="f9475-129">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="f9475-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f9475-130">Markera tre punkter bredvid datakälla som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="f9475-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="f9475-131">Välj alternativet **Redigera** från listan.</span><span class="sxs-lookup"><span data-stu-id="f9475-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="f9475-132">Välj ytterligare entiteter från listan med tillgängliga entiteter och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f9475-132">Select additional entities from the available list of entities and select **Save**.</span></span>
