---
title: Startsida i målgruppsinsikter
description: Börja utforska appen på startsidan.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597257"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="536b4-103">Skapa en ny miljö</span><span class="sxs-lookup"><span data-stu-id="536b4-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="536b4-104">Skapa en utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="536b4-104">Create a trial environment</span></span>

<span data-ttu-id="536b4-105">Du kan registrera dig för en utvärderingsversion på [sidan för registrering av utvärderingsversion](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span><span class="sxs-lookup"><span data-stu-id="536b4-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="536b4-106">Utvärderingsversionen upphör att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="536b4-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="536b4-107">Välj alternativet **Registrera dig för en kostnadsfri utvärderingsversion** och välj **Registrera nu**.</span><span class="sxs-lookup"><span data-stu-id="536b4-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="536b4-108">Ange din e-postadress för arbetet eller skolan, berätta mer om dig själv och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="536b4-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogruta för att registrera sig för en utvärderingsinstans":::

1. <span data-ttu-id="536b4-110">Ange ett **namn** för den nya miljön.</span><span class="sxs-lookup"><span data-stu-id="536b4-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="536b4-111">Välj utvärderingstyp.</span><span class="sxs-lookup"><span data-stu-id="536b4-111">Select the trial type.</span></span>

1. <span data-ttu-id="536b4-112">Välj en **Region** för din miljö.</span><span class="sxs-lookup"><span data-stu-id="536b4-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="536b4-113">Om det är en administratör av en Dynamics 365-organisation kan du välja **avancerade inställningar** och ange URL-adressen till din organisation om du vill använda prediktionsfunktioner som kundomsättning.</span><span class="sxs-lookup"><span data-stu-id="536b4-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="536b4-114">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="536b4-114">Select **Create**.</span></span> 

<span data-ttu-id="536b4-115">När miljön skapades ser du **Demo**-miljön som gör att du kan utforska appen med fiktiva data.</span><span class="sxs-lookup"><span data-stu-id="536b4-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="536b4-116">Du kan ändra exempeldata så att de överensstämmer med din bransch.</span><span class="sxs-lookup"><span data-stu-id="536b4-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="536b4-117">Välj ikonen **Inställningar** i rubriken och välj **Demoinställningar**.</span><span class="sxs-lookup"><span data-stu-id="536b4-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="536b4-118">Dessutom kan du ändra det visuella temat.</span><span class="sxs-lookup"><span data-stu-id="536b4-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="536b4-119">Du [växlar till den miljö](#switch-environments) du skapade under registreringsprocessen för att arbeta med dina egna data.</span><span class="sxs-lookup"><span data-stu-id="536b4-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="536b4-120">Skapa en ny produktions- eller sandbox-miljö</span><span class="sxs-lookup"><span data-stu-id="536b4-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="536b4-121">I din miljö väljer du **Miljö**-väljare i apphuvudet och välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="536b4-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="536b4-122">Följ anvisningarna på samma sätt som om du [skapar en utvärderingsmiljö](#create-a-trial-environment).</span><span class="sxs-lookup"><span data-stu-id="536b4-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="536b4-123">Som standard lagras data i Customer Insights-hanterad datasjö.</span><span class="sxs-lookup"><span data-stu-id="536b4-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="536b4-124">Du kan välja ett annat alternativ när du väljer **Avancerade inställningar** för att lagra dina data i din egen Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="536b4-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="536b4-125">Ange kontonamn och kontonyckel för att upprätta en anslutning till din Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="536b4-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="536b4-126">Genom att spara data i Azure Data Lake Storage godkänner du att data överförs till och lagras på rätt geografiska plats för Azure Storage-kontot, som kan skilja sig från varifrån data lagras i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="536b4-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="536b4-127">Läs mer i Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="536b4-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="536b4-128">Utforska startsidan</span><span class="sxs-lookup"><span data-stu-id="536b4-128">Explore the home page</span></span>

<span data-ttu-id="536b4-129">Du kan [få tillgång till målgruppsinsikter från Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) på följande URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="536b4-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="536b4-130">**Start** sidan visar en översikt över segment, mått och berikningsdata (om konfigurerat) efter slutförandet av faserna [mappa](map-entities.md), [matcha](match-entities.md) och [sammanslå](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="536b4-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="536b4-131">![Insikter på startsidan](media/home-page-insights.png "Insikter på startsidan")</span><span class="sxs-lookup"><span data-stu-id="536b4-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="536b4-132">Under **senaste segment** visas grupper med kunder utifrån demografiska, beteende- eller transaktionella attribut som du har definierat.</span><span class="sxs-lookup"><span data-stu-id="536b4-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="536b4-133">[Genom att skapa segment](segments.md) kan du gruppera din kundbas och rikta dina affärsaktiviteter på ett bättre sätt.</span><span class="sxs-lookup"><span data-stu-id="536b4-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="536b4-134">**Senaste åtgärder** visar paneler med [nyckeltal (KPI:er)](measures.md) som du har definierats.</span><span class="sxs-lookup"><span data-stu-id="536b4-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="536b4-135">Till exempel genomsnittlig sannolikhet för kundomsättning eller genomsnittlig omsättning online per kund.</span><span class="sxs-lookup"><span data-stu-id="536b4-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="536b4-136">I avsnittet **Senast använda** visas resultaten av de nya anriknings körningarna som har slutförts nyligen.</span><span class="sxs-lookup"><span data-stu-id="536b4-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="536b4-137">[Berikningar](enrichment-hub.md) lägger till information om kundbasen.</span><span class="sxs-lookup"><span data-stu-id="536b4-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="536b4-138">Du kan till exempel förstå de intressen och märken som de har tillhörighet för.</span><span class="sxs-lookup"><span data-stu-id="536b4-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="536b4-139">Växla miljö</span><span class="sxs-lookup"><span data-stu-id="536b4-139">Switch environments</span></span>

<span data-ttu-id="536b4-140">Välj kontrollen **miljö** i det övre högra hörnet av sidan om du vill ändra miljöer.</span><span class="sxs-lookup"><span data-stu-id="536b4-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="536b4-141">![Växla miljö](media/home-page-environment-switcher.png "Växla miljö")</span><span class="sxs-lookup"><span data-stu-id="536b4-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="536b4-142">Administratörer kan skapa och hantera [flera miljöer](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="536b4-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="536b4-143">Det kan vara bra att upprätthålla mer än en miljö om din organisation exempelvis arbetar internationellt och du behöver åtskilja data och insikter på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="536b4-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="536b4-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="536b4-144">Next step</span></span>

<span data-ttu-id="536b4-145">Om du vill visa dina egna insikter på startsidan måste du först [lägga till datakällor](data-sources.md) och [förena](data-unification.md) dina data för att skapa kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="536b4-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]