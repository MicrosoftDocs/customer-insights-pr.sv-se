---
title: Anslutningsapp för Power BI
description: Läs mer om hur du använder Dynamics 365 Customer Insights anslutningsprogram i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407066"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="d70c2-103">Koppling för Power BI (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="d70c2-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="d70c2-104">Skapa visualiseringar för dina data med Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="d70c2-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="d70c2-105">Skapa ytterligare insikter och skapa rapporter med dina enhetliga kunddata.</span><span class="sxs-lookup"><span data-stu-id="d70c2-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d70c2-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d70c2-106">Prerequisites</span></span>

- <span data-ttu-id="d70c2-107">Du har enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="d70c2-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="d70c2-108">Den senaste versionen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) är installerad på datorn.</span><span class="sxs-lookup"><span data-stu-id="d70c2-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="d70c2-109">[Läs mer om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="d70c2-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="d70c2-110">Konfigurera koppling för Power BI</span><span class="sxs-lookup"><span data-stu-id="d70c2-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="d70c2-111">I Power BI Desktop, välj **Fil** > **Hämta data**.</span><span class="sxs-lookup"><span data-stu-id="d70c2-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="d70c2-112">Välj **Se fler** och sök efter **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="d70c2-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="d70c2-113">Markera resultatet och välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="d70c2-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="d70c2-114">**Logga in** med samma organisationskonto som du använder för Customer Insights och välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="d70c2-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d70c2-115">Det konto du anger i det här steget används för att hämta data från Customer Insights som inte behöver vara samma som du är inloggad på Power BI.</span><span class="sxs-lookup"><span data-stu-id="d70c2-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="d70c2-116">Om du vill återställa kontot som används för datahämtning öppnar du Power BI och går **Fil** > **Alternativ** > **Inställningar** > **Inställningar för datakälla**.</span><span class="sxs-lookup"><span data-stu-id="d70c2-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="d70c2-117">Välj inloggning i listan över datakällor välj **Dynamics 365 Customer Insights inloggning** och välj **Rensa behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="d70c2-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="d70c2-118">Klicka på dialogrutan **Navigering**.</span><span class="sxs-lookup"><span data-stu-id="d70c2-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="d70c2-119">du ser listan över alla miljöer som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="d70c2-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="d70c2-120">Expandera en miljö och öppna någon av mapparna (entiteter, mått, segment, berikningar).</span><span class="sxs-lookup"><span data-stu-id="d70c2-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="d70c2-121">Öppna till exempel mappen **entiteter** om du vill visa alla entiteter som du kan importera.</span><span class="sxs-lookup"><span data-stu-id="d70c2-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="d70c2-122">![Power BI kopplingsnavigering](media/power-bi-navigator.png "Power BI kopplingsnavigering")</span><span class="sxs-lookup"><span data-stu-id="d70c2-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="d70c2-123">Markera kryssrutorna bredvid de entiteter som ska tas med och **läsas in**.</span><span class="sxs-lookup"><span data-stu-id="d70c2-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="d70c2-124">Du kan välja flera entiteter från flera miljöer.</span><span class="sxs-lookup"><span data-stu-id="d70c2-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="d70c2-125">En dialogruta för inläsning visas medan entiteterna har lästs in.</span><span class="sxs-lookup"><span data-stu-id="d70c2-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="d70c2-126">När alla dina valda entiteter har lästs in kan du använda funktionerna i Power BI för att visualisera data.</span><span class="sxs-lookup"><span data-stu-id="d70c2-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="d70c2-127">Stora datauppsättningar</span><span class="sxs-lookup"><span data-stu-id="d70c2-127">Large data sets</span></span>

<span data-ttu-id="d70c2-128">Customer Insights-anslutningen för Power BI har utformats för att fungera för data uppsättningar som innehåller upp till 1 miljon kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="d70c2-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="d70c2-129">Det kan ta en stund att importera större datauppsättningar, men det tar lång tid.</span><span class="sxs-lookup"><span data-stu-id="d70c2-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="d70c2-130">Dessutom kan processen köra på en tidsgräns på grund av Power BI begränsningar.</span><span class="sxs-lookup"><span data-stu-id="d70c2-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="d70c2-131">Mer information finns i [Power BI rekommendationerna för stora datauppsättningar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="d70c2-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="d70c2-132">Arbeta med en delmängd av data.</span><span class="sxs-lookup"><span data-stu-id="d70c2-132">Work with a subset of data</span></span>

<span data-ttu-id="d70c2-133">Överväg att arbeta med en delmängd av dina data.</span><span class="sxs-lookup"><span data-stu-id="d70c2-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="d70c2-134">Du kan till exempel skapa [segment](segments.md) i stället för att exportera alla kundposter till Power BI.</span><span class="sxs-lookup"><span data-stu-id="d70c2-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
