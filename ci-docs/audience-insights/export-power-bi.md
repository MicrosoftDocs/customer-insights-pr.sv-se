---
title: Anslutningsapp för Power BI
description: Läs mer om hur du använder Dynamics 365 Customer Insights anslutningsprogram i Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596061"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="569e5-103">Koppling för Power BI (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="569e5-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="569e5-104">Skapa visualiseringar för dina data med Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="569e5-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="569e5-105">Skapa ytterligare insikter och skapa rapporter med dina enhetliga kunddata.</span><span class="sxs-lookup"><span data-stu-id="569e5-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="569e5-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="569e5-106">Prerequisites</span></span>

- <span data-ttu-id="569e5-107">Du har enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="569e5-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="569e5-108">Den senaste versionen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) är installerad på datorn.</span><span class="sxs-lookup"><span data-stu-id="569e5-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="569e5-109">[Läs mer om Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="569e5-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="569e5-110">Konfigurera koppling för Power BI</span><span class="sxs-lookup"><span data-stu-id="569e5-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="569e5-111">I Power BI Desktop, välj **Fil** > **Hämta data**.</span><span class="sxs-lookup"><span data-stu-id="569e5-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="569e5-112">Välj **Se fler** och sök efter **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="569e5-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="569e5-113">Välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="569e5-113">Select **Connect**.</span></span>

1. <span data-ttu-id="569e5-114">**Logga in** med samma organisationskonto som du använder för Customer Insights och välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="569e5-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="569e5-115">Det konto du anger i det här steget används för att hämta data från Customer Insights som inte behöver vara samma som du är inloggad på Power BI.</span><span class="sxs-lookup"><span data-stu-id="569e5-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="569e5-116">Om du vill återställa kontot som används för datahämtning öppnar du Power BI och går **Fil** > **Alternativ** > **Inställningar** > **Inställningar för datakälla**.</span><span class="sxs-lookup"><span data-stu-id="569e5-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="569e5-117">Välj inloggning i listan över datakällor välj **Dynamics 365 Customer Insights inloggning** och välj **Rensa behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="569e5-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="569e5-118">Klicka på dialogrutan **Navigering**.</span><span class="sxs-lookup"><span data-stu-id="569e5-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="569e5-119">du ser listan över alla miljöer som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="569e5-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="569e5-120">Expandera en miljö och öppna någon av mapparna (entiteter, mått, segment, berikningar).</span><span class="sxs-lookup"><span data-stu-id="569e5-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="569e5-121">Öppna till exempel mappen **entiteter** om du vill visa alla entiteter som du kan importera.</span><span class="sxs-lookup"><span data-stu-id="569e5-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="569e5-122">![Power BI kopplingsnavigering](media/power-bi-navigator.png "Power BI kopplingsnavigering")</span><span class="sxs-lookup"><span data-stu-id="569e5-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="569e5-123">Markera kryssrutorna bredvid de entiteter som ska tas med och **läsas in**.</span><span class="sxs-lookup"><span data-stu-id="569e5-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="569e5-124">Du kan välja flera entiteter från flera miljöer.</span><span class="sxs-lookup"><span data-stu-id="569e5-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="569e5-125">En dialogruta för inläsning visas medan entiteterna har lästs in.</span><span class="sxs-lookup"><span data-stu-id="569e5-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="569e5-126">När alla dina valda entiteter har lästs in kan du använda funktionerna i Power BI för att visualisera data.</span><span class="sxs-lookup"><span data-stu-id="569e5-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="569e5-127">Stora datauppsättningar</span><span class="sxs-lookup"><span data-stu-id="569e5-127">Large data sets</span></span>

<span data-ttu-id="569e5-128">Customer Insights-anslutningen för Power BI har utformats för att fungera för data uppsättningar som innehåller upp till 1 miljon kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="569e5-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="569e5-129">Det kan ta en stund att importera större datauppsättningar, men det tar lång tid.</span><span class="sxs-lookup"><span data-stu-id="569e5-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="569e5-130">Dessutom kan processen köra på en tidsgräns på grund av Power BI begränsningar.</span><span class="sxs-lookup"><span data-stu-id="569e5-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="569e5-131">Mer information finns i [Power BI rekommendationerna för stora datauppsättningar](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="569e5-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="569e5-132">Arbeta med en delmängd av data.</span><span class="sxs-lookup"><span data-stu-id="569e5-132">Work with a subset of data</span></span>

<span data-ttu-id="569e5-133">Överväg att arbeta med en delmängd av dina data.</span><span class="sxs-lookup"><span data-stu-id="569e5-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="569e5-134">Du kan till exempel skapa [segment](segments.md) i stället för att exportera alla kundposter till Power BI.</span><span class="sxs-lookup"><span data-stu-id="569e5-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="569e5-135">Felsökning</span><span class="sxs-lookup"><span data-stu-id="569e5-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="569e5-136">Customer Insights-miljön visas inte i Power BI</span><span class="sxs-lookup"><span data-stu-id="569e5-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="569e5-137">Miljöer som har fler än en [relation](relationships.md) som har definierats mellan två identiska entiteter målgruppsinsikter kommer inte att vara tillgängliga i Power BI-anslutningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="569e5-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="569e5-138">Du kan identifiera och ta bort de duplicerade relationerna.</span><span class="sxs-lookup"><span data-stu-id="569e5-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="569e5-139">I målgruppsinsikter går du till **Data** > **Relationer** i den miljö du saknar i Power BI.</span><span class="sxs-lookup"><span data-stu-id="569e5-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="569e5-140">Identifiera dubblettrelationer:</span><span class="sxs-lookup"><span data-stu-id="569e5-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="569e5-141">Kontrollera om det finns fler än en relation som har definierats mellan samma två entiteter.</span><span class="sxs-lookup"><span data-stu-id="569e5-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="569e5-142">Kontrollera om det finns en relation som har skapats mellan två entiteter som båda ingår i föreningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="569e5-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="569e5-143">Det finns en implicit relation mellan alla entiteter som ingår i föreningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="569e5-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="569e5-144">Ta bort eventuella dubblettrelationer som har identifierats.</span><span class="sxs-lookup"><span data-stu-id="569e5-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="569e5-145">När du har tagit bort dubblettrelationer försöker du konfigurera Power BI-anslutningsprogrammet igen.</span><span class="sxs-lookup"><span data-stu-id="569e5-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="569e5-146">Miljön ska vara tillgänglig nu.</span><span class="sxs-lookup"><span data-stu-id="569e5-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]