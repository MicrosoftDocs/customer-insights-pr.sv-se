---
title: Exempelguide för förutsägelse om prenumerationsomsättning
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om prenumerationsomsättning.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654002"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="23326-103">Exempelguide för förutsägelse om prenumerationsomsättning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="23326-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="23326-104">Vi ger dig ett komplett exempel på förutsägelse av prenumerationsomsättning med hjälp av de exempeldata som anges nedan.</span><span class="sxs-lookup"><span data-stu-id="23326-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="23326-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="23326-105">Scenario</span></span>

<span data-ttu-id="23326-106">Contoso är ett företag som producerar kaffe och kaffemaskiner av hög kvalitet, som de säljer via Contoso Coffee-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="23326-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="23326-107">De startade nyligen ett prenumerationsalternativ för sina kunder för att med jämna mellanrum få kaffe.</span><span class="sxs-lookup"><span data-stu-id="23326-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="23326-108">Deras mål är att förstå vilka prenumererande kunder som kan komma att säga upp prenumerationen inom de kommande månaderna.</span><span class="sxs-lookup"><span data-stu-id="23326-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="23326-109">Att veta vilka av deras kunder som **sannolikt kommer att omsättas** kan hjälpa dem att spara marknadsföringsinsatser genom att fokusera på att behålla dem.</span><span class="sxs-lookup"><span data-stu-id="23326-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23326-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="23326-110">Prerequisites</span></span>

- <span data-ttu-id="23326-111">Minst [Deltagarbehörighet](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23326-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="23326-112">Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="23326-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="23326-113">Uppgift 1 – Mata in data</span><span class="sxs-lookup"><span data-stu-id="23326-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="23326-114">Granska artiklarna [om datainmatning](data-sources.md) och [import av datakällor med hjälp av Power Query-anslutningsprogram](connect-power-query.md) specifikt.</span><span class="sxs-lookup"><span data-stu-id="23326-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="23326-115">Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="23326-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="23326-116">Mata in kunddata från e-handelsplattformen</span><span class="sxs-lookup"><span data-stu-id="23326-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="23326-117">Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="23326-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="23326-118">Ange URL för e-handelskontakter https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="23326-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="23326-119">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="23326-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="23326-120">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="23326-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="23326-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="23326-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="23326-122">**CreatedOn**: Datum/Tid/Zon</span><span class="sxs-lookup"><span data-stu-id="23326-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="23326-123">![Transformera födelsedatum till datum](media/ecommerce-dob-date.PNG "transformera födelsedatum till datum")</span><span class="sxs-lookup"><span data-stu-id="23326-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="23326-124">I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="23326-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="23326-125">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="23326-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="23326-126">Mata in kunddata från lojalitetsschema</span><span class="sxs-lookup"><span data-stu-id="23326-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="23326-127">Skapa en datakälla med namnet **LoyaltyScheme**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="23326-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="23326-128">Ange URL för e-handelskontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="23326-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="23326-129">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="23326-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="23326-130">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="23326-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="23326-131">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="23326-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="23326-132">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="23326-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="23326-133">**CreatedOn**: Datum/Tid</span><span class="sxs-lookup"><span data-stu-id="23326-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="23326-134">I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="23326-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="23326-135">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="23326-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="23326-136">Mata in prenumerationsinformation</span><span class="sxs-lookup"><span data-stu-id="23326-136">Ingest subscription information</span></span>

1. <span data-ttu-id="23326-137">Skapa en datakälla med namnet **SubscriptionHistory**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="23326-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="23326-138">Ange URL för e-handelskontakter https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="23326-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="23326-139">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="23326-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="23326-140">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="23326-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="23326-141">**SubscriptioID**: Hela numret</span><span class="sxs-lookup"><span data-stu-id="23326-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="23326-142">**SubscriptionAmount**: Valuta</span><span class="sxs-lookup"><span data-stu-id="23326-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="23326-143">**SubscriptionEndDate**: Datum/tid</span><span class="sxs-lookup"><span data-stu-id="23326-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="23326-144">**SubscriptionStartDate**: Datum/tid</span><span class="sxs-lookup"><span data-stu-id="23326-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="23326-145">**TransactionDate**: Datum/tid</span><span class="sxs-lookup"><span data-stu-id="23326-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="23326-146">**IsRecurring**: Sant/falskt</span><span class="sxs-lookup"><span data-stu-id="23326-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="23326-147">**Is_auto_renew**: Sant/falskt</span><span class="sxs-lookup"><span data-stu-id="23326-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="23326-148">**RecurringFrequencyInMonths**: Hela numret</span><span class="sxs-lookup"><span data-stu-id="23326-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="23326-149">I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="23326-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="23326-150">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="23326-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="23326-151">Mata in kunddata från webbplatsens recensioner</span><span class="sxs-lookup"><span data-stu-id="23326-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="23326-152">Skapa en datakälla med namnet **Website**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="23326-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="23326-153">Ange URL för e-handelskontakter https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="23326-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="23326-154">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="23326-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="23326-155">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="23326-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="23326-156">**ReviewRating**: Hela numret</span><span class="sxs-lookup"><span data-stu-id="23326-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="23326-157">**ReviewDate**: Datum</span><span class="sxs-lookup"><span data-stu-id="23326-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="23326-158">I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="23326-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="23326-159">Uppgift 2 – Dataförening</span><span class="sxs-lookup"><span data-stu-id="23326-159">Task 2 - Data unification</span></span>

<span data-ttu-id="23326-160">Efter inmatning av datan börjar vi nu processen **mappa, matcha, slå samman** för att skapa en enhetlig kundprofil.</span><span class="sxs-lookup"><span data-stu-id="23326-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="23326-161">Mer information finns i [Dataförening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="23326-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="23326-162">Mappa</span><span class="sxs-lookup"><span data-stu-id="23326-162">Map</span></span>

1. <span data-ttu-id="23326-163">Efter inmatande av data mappar du kontakter från e-handels- och lojalitetsdata till vanliga datatyper.</span><span class="sxs-lookup"><span data-stu-id="23326-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="23326-164">Gå till **Data** > **Förena** > **Mappa**.</span><span class="sxs-lookup"><span data-stu-id="23326-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="23326-165">Välj de entiteter som representerar kundprofilen – **eCommerceContacts** och **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="23326-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="förena e-handels- och lojalitetsdatakällor.":::

1. <span data-ttu-id="23326-167">Välj **ContactId** som primärnyckel för **eCommerceContacts** och **LoyaltyID** som primärnyckel för **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="23326-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Förena LoyaltyId som primärnyckel.":::

### <a name="match"></a><span data-ttu-id="23326-169">Matchning</span><span class="sxs-lookup"><span data-stu-id="23326-169">Match</span></span>

1. <span data-ttu-id="23326-170">Gå till fliken **Matcha** och välj **Ange ordning**.</span><span class="sxs-lookup"><span data-stu-id="23326-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="23326-171">I listrutan **Primär** väljer du **eCommerceContacts: e-handel** som primär källa och inkluderar alla poster.</span><span class="sxs-lookup"><span data-stu-id="23326-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="23326-172">I listrutan **Entitet 2** väljer du **loyCustomers: LoyaltyScheme** och inkluderar alla poster.</span><span class="sxs-lookup"><span data-stu-id="23326-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Förena matchande e-handel och lojalitet.":::

1. <span data-ttu-id="23326-174">Välj **Skapa en ny regel**</span><span class="sxs-lookup"><span data-stu-id="23326-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="23326-175">Lägg till ditt första villkor med hjälp av FullName.</span><span class="sxs-lookup"><span data-stu-id="23326-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="23326-176">För eCommerceContacts välj **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="23326-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="23326-177">För loyCustomers välj **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="23326-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="23326-178">Välj listrutan **Normalisera** och välj **Typ (telefon, namn, adress ...)**.</span><span class="sxs-lookup"><span data-stu-id="23326-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="23326-179">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="23326-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="23326-180">Ange namnet **FullName, E-post** för den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="23326-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="23326-181">Lägg till ett andra villkor för e-postadress genom att välja **Lägg till villkor**</span><span class="sxs-lookup"><span data-stu-id="23326-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="23326-182">För entitet eCommerceContacts väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="23326-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="23326-183">För entitet loyCustomers väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="23326-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="23326-184">Lämna Normalisera tomt.</span><span class="sxs-lookup"><span data-stu-id="23326-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="23326-185">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="23326-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Förena matchningsregel för namn och e-post.":::

7. <span data-ttu-id="23326-187">Välj **Spara** och **Kör**.</span><span class="sxs-lookup"><span data-stu-id="23326-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="23326-188">Slå ihop</span><span class="sxs-lookup"><span data-stu-id="23326-188">Merge</span></span>

1. <span data-ttu-id="23326-189">Gå till fliken **Sammanslå**.</span><span class="sxs-lookup"><span data-stu-id="23326-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="23326-190">På **ContactId** för entiteten **loyCustomers** ändrar du visningsnamnet till **ContactIdLOYALTY** för att särskilja den från andra inmatade ID.</span><span class="sxs-lookup"><span data-stu-id="23326-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="byta namn på contactid från lojalitets-id.":::

1. <span data-ttu-id="23326-192">Välj **Spara** och **Kör** för att starta sammanslagningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="23326-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="23326-193">Uppgift 3 – Konfigurera förutsägelsen om prenumerationsomsättning</span><span class="sxs-lookup"><span data-stu-id="23326-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="23326-194">Med de enhetliga kundprofilerna på plats kan vi nu köra förutsägelsen om prenumerationsomsättning.</span><span class="sxs-lookup"><span data-stu-id="23326-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="23326-195">Detaljerade steg finns i artikeln [Förutsägelse om prenumerationsomsättning (förhandsversion)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="23326-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="23326-196">Gå till **Intelligens** > **Utforska** och välj att använda **modellen Kundomsättning**.</span><span class="sxs-lookup"><span data-stu-id="23326-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="23326-197">Välj alternativet **Prenumeration** och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="23326-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="23326-198">Namnge modellen **OOB förutsägelse om prenumerationsomsättning** och utdataentiteten **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="23326-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="23326-199">Definiera två villkor för omsättningsmodellen:</span><span class="sxs-lookup"><span data-stu-id="23326-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="23326-200">**Dagar sedan prenumerationen avslutades**: **minst 60** dagar.</span><span class="sxs-lookup"><span data-stu-id="23326-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="23326-201">Om en kund inte förnyar prenumerationen under den här tidsperioden efter att prenumerationen avslutades, anses de vara omsatta.</span><span class="sxs-lookup"><span data-stu-id="23326-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="23326-202">**Omsättningsdefinition**: **minst 93** dagar.</span><span class="sxs-lookup"><span data-stu-id="23326-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="23326-203">Den tidsperiod inom vilken modellen förutser att kunden kan komma att omsättas.</span><span class="sxs-lookup"><span data-stu-id="23326-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="23326-204">Ju längre in i framtiden du tittar, desto mindre exakta blir resultaten.</span><span class="sxs-lookup"><span data-stu-id="23326-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Välj modellens förutsägelsefönster och omsättningsdefinition.":::

1. <span data-ttu-id="23326-206">Välj **Lägg till obligatoriska data** och välj **Lägg till data** för prenumerationshistorik.</span><span class="sxs-lookup"><span data-stu-id="23326-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="23326-207">Lägg till entiteten **Prenumeration: SubscriptionHistory** och mappa fälten från e-handel till motsvarande fält som krävs av modellen.</span><span class="sxs-lookup"><span data-stu-id="23326-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="23326-208">Anslut entiteten **Prenumeration: SubscriptionHistory** med **eCommerceContacts: e-handel**, namnge relationen **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="23326-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Anslut e-handelsentiteter.":::

1. <span data-ttu-id="23326-210">Under Kundaktiviteter lägger du till entiteten **webReviews: Webbplats** och mappar fälten från webReviews till motsvarande fält som krävs av modellen.</span><span class="sxs-lookup"><span data-stu-id="23326-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="23326-211">Primär nyckel: ReviewId</span><span class="sxs-lookup"><span data-stu-id="23326-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="23326-212">Tidsstämpel: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="23326-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="23326-213">Händelse: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="23326-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="23326-214">Konfigurera en aktivitet för recensioner av webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="23326-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="23326-215">Välj aktiviteten **Recension** och anslut entiteten **webReviews : Webbplats** till **eCommerceContacts : e-handel**.</span><span class="sxs-lookup"><span data-stu-id="23326-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="23326-216">Välj **Nästa** för att ange modellschemat.</span><span class="sxs-lookup"><span data-stu-id="23326-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="23326-217">Modellen måste träna regelbundet för att lära sig nya mönster när det finns nya data inmatade.</span><span class="sxs-lookup"><span data-stu-id="23326-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="23326-218">För det här exemplet väljer du **Månadsvis**.</span><span class="sxs-lookup"><span data-stu-id="23326-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="23326-219">När du har granskat alla detaljer väljer du **Spara och kör**.</span><span class="sxs-lookup"><span data-stu-id="23326-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="23326-220">Uppgift 4 – Granska modellresultat och förklaringar</span><span class="sxs-lookup"><span data-stu-id="23326-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="23326-221">Låt modellen slutföra träningen och bedömningen av data.</span><span class="sxs-lookup"><span data-stu-id="23326-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="23326-222">Du kan nu granska förklaringar av modellen för prenumerationsomsättning.</span><span class="sxs-lookup"><span data-stu-id="23326-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="23326-223">Mer information finns i [Granska en förutsägelsestatus och resultat](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="23326-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="23326-224">Uppgift 5 – Skapa ett segment med kunder med hög omsättningsrisk</span><span class="sxs-lookup"><span data-stu-id="23326-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="23326-225">Om du kör produktionsmodellen skapas en ny entitet som du kan se i **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="23326-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="23326-226">Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.</span><span class="sxs-lookup"><span data-stu-id="23326-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="23326-227">Gå till **Segment**.</span><span class="sxs-lookup"><span data-stu-id="23326-227">Go to **Segments**.</span></span> <span data-ttu-id="23326-228">Välj **Nytt** och välj **Skapa från** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="23326-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Skapa ett segment med modellutdata.":::

1. <span data-ttu-id="23326-230">Välj slutpunkten **OOBSubscriptionChurnPrediction** och definiera segmentet:</span><span class="sxs-lookup"><span data-stu-id="23326-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="23326-231">Fält: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="23326-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="23326-232">Operatör: större än</span><span class="sxs-lookup"><span data-stu-id="23326-232">Operator: greater than</span></span>
   - <span data-ttu-id="23326-233">Värde: 0,6</span><span class="sxs-lookup"><span data-stu-id="23326-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Konfigurera segment för prenumerationsomsättning.":::

<span data-ttu-id="23326-235">Du har nu ett segment som uppdateras dynamiskt som identifierar kunder med hög omsättningsrisk för den här prenumerationsverksamheten.</span><span class="sxs-lookup"><span data-stu-id="23326-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="23326-236">Mer information finns i [Skapa och hantera segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="23326-236">For more information, see [Create and manage segments](segments.md).</span></span>