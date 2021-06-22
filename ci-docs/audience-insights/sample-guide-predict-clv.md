---
title: Kundens livstidsvärde prediktion exempelguide
description: Använd den här exempelguiden för att testa kundens livstidsvärde prediktionsmodellen.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129967"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="70bb1-103">Kundens livstidsvärde (CLV) prediktion exempelguide</span><span class="sxs-lookup"><span data-stu-id="70bb1-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="70bb1-104">Den här guiden förklarar för dig ett slutexempel på CLV-prediktion i Customer Insights med hjälp av exempeldata.</span><span class="sxs-lookup"><span data-stu-id="70bb1-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="70bb1-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="70bb1-105">Scenario</span></span>

<span data-ttu-id="70bb1-106">Contoso är ett företag som producerar högkvalitativt kaffe och kaffemaskiner.</span><span class="sxs-lookup"><span data-stu-id="70bb1-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="70bb1-107">De säljer produkterna via sin Contoso Coffee-webbplats.</span><span class="sxs-lookup"><span data-stu-id="70bb1-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="70bb1-108">Företaget vill förstå värdet (intäkterna) som deras kunder kan generera under de kommande 12 månaderna.</span><span class="sxs-lookup"><span data-stu-id="70bb1-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="70bb1-109">Att veta det förväntade värdet på sina kunder under de kommande 12 månaderna kommer att hjälpa dem att styra sina marknadsföringsinsatser på kunder med högt värde.</span><span class="sxs-lookup"><span data-stu-id="70bb1-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70bb1-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="70bb1-110">Prerequisites</span></span>

- <span data-ttu-id="70bb1-111">Åtminstone [Deltagarbehörigheter](permissions.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="70bb1-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="70bb1-112">Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="70bb1-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="70bb1-113">Uppgift 1 – Mata in data</span><span class="sxs-lookup"><span data-stu-id="70bb1-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="70bb1-114">Granska artiklarna [om datainmatning](data-sources.md) och [import av datakällor med Power Query-kopplingar](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="70bb1-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="70bb1-115">Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="70bb1-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="70bb1-116">Mata in kunddata från e-handelsplattformen</span><span class="sxs-lookup"><span data-stu-id="70bb1-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="70bb1-117">Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="70bb1-118">Ange URL för e-handelskontakter [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="70bb1-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="70bb1-119">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="70bb1-120">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="70bb1-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="70bb1-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="70bb1-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="70bb1-122">**CreatedOn**: Datum/Tid/Zon</span><span class="sxs-lookup"><span data-stu-id="70bb1-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformera födelsedatum till datum.":::

1. <span data-ttu-id="70bb1-124">I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="70bb1-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="70bb1-125">**Spara** datakällan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="70bb1-126">Mata in inköpsdata online</span><span class="sxs-lookup"><span data-stu-id="70bb1-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="70bb1-127">Lägg till ytterligare en datauppsättning till samma **e-handelskälla**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="70bb1-128">Välj anslutningsprogrammet **Text/CSV** igen.</span><span class="sxs-lookup"><span data-stu-id="70bb1-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="70bb1-129">Ange URL för **Onlineköpsdata** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="70bb1-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="70bb1-130">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="70bb1-131">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="70bb1-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="70bb1-132">**PurchasedOn**: Datum/tid</span><span class="sxs-lookup"><span data-stu-id="70bb1-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="70bb1-133">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="70bb1-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="70bb1-134">I fältet **Namn** i sidofönstret byter du namn på din datakälla från **Fråga** till **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="70bb1-135">**Spara** datakällan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="70bb1-136">Mata in kunddata från lojalitetsschema</span><span class="sxs-lookup"><span data-stu-id="70bb1-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="70bb1-137">Skapa en datakälla med namnet **LoyaltyScheme**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="70bb1-138">Ange URL för e-handelskontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="70bb1-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="70bb1-139">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="70bb1-140">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="70bb1-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="70bb1-141">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="70bb1-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="70bb1-142">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="70bb1-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="70bb1-143">**CreatedOn**: Datum/Tid</span><span class="sxs-lookup"><span data-stu-id="70bb1-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="70bb1-144">I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="70bb1-145">**Spara** datakällan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="70bb1-146">Mata in kunddata från webbplatsens recensioner</span><span class="sxs-lookup"><span data-stu-id="70bb1-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="70bb1-147">Skapa en datakälla med namnet **Website**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="70bb1-148">Ange URL för e-handelskontakter https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="70bb1-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="70bb1-149">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="70bb1-150">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="70bb1-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="70bb1-151">**ReviewRating**: Decimaltal</span><span class="sxs-lookup"><span data-stu-id="70bb1-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="70bb1-152">**ReviewDate**: Datum</span><span class="sxs-lookup"><span data-stu-id="70bb1-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="70bb1-153">I fältet Namn i den högra rutan byter du namn på din datakälla från **Fråga** till **Recensioner**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="70bb1-154">**Spara** datakällan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="70bb1-155">Uppgift 2 – Dataförening</span><span class="sxs-lookup"><span data-stu-id="70bb1-155">Task 2 - Data unification</span></span>

<span data-ttu-id="70bb1-156">När vi har matat in data börjar vi nu datasammanföringsprocessen för att skapa en enhetlig kundprofil.</span><span class="sxs-lookup"><span data-stu-id="70bb1-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="70bb1-157">Mer information finns i [Dataförening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="70bb1-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="70bb1-158">Mappa</span><span class="sxs-lookup"><span data-stu-id="70bb1-158">Map</span></span>

1. <span data-ttu-id="70bb1-159">Efter inmatande av data mappar du kontakter från e-handels- och lojalitetsdata till vanliga datatyper.</span><span class="sxs-lookup"><span data-stu-id="70bb1-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="70bb1-160">Gå till **Data** > **Förena** > **Mappa**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="70bb1-161">Välj de entiteter som representerar kundprofilen – **eCommerceContacts** och **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="70bb1-162">Välj därefter **Tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-162">Then, select **Apply**.</span></span>

   ![förena e-handels- och lojalitetsdatakällor.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="70bb1-164">Välj **ContactId** som primärnyckel för **eCommerceContacts** och **LoyaltyID** som primärnyckel för **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Förena LoyaltyId som primärnyckel.](media/unify-loyaltyid.png)

1. <span data-ttu-id="70bb1-166">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="70bb1-167">Matchning</span><span class="sxs-lookup"><span data-stu-id="70bb1-167">Match</span></span>

1. <span data-ttu-id="70bb1-168">Gå till fliken **Matcha** och välj **Ange ordning**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="70bb1-169">I listrutan **Primär** väljer du **eCommerceContacts: e-handel** som primär källa och inkluderar alla poster.</span><span class="sxs-lookup"><span data-stu-id="70bb1-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="70bb1-170">I listrutan **Entitet 2** väljer du **loyCustomers: LoyaltyScheme** och inkluderar alla poster.</span><span class="sxs-lookup"><span data-stu-id="70bb1-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Förena matchande e-handel och lojalitet.](media/unify-match-order.png)

1. <span data-ttu-id="70bb1-172">Välj **Lägg till regel**</span><span class="sxs-lookup"><span data-stu-id="70bb1-172">Select **Add rule**</span></span>

1. <span data-ttu-id="70bb1-173">Lägg till ditt första villkor med hjälp av FullName.</span><span class="sxs-lookup"><span data-stu-id="70bb1-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="70bb1-174">För eCommerceContacts välj **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="70bb1-175">För loyCustomers välj **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="70bb1-176">Välj listrutan **Normalisera** och välj **Typ (telefon, namn, adress ...)**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="70bb1-177">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="70bb1-178">Ange namnet **FullName, E-post** för den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="70bb1-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="70bb1-179">Lägg till ett andra villkor för e-postadress genom att välja **Lägg till villkor**</span><span class="sxs-lookup"><span data-stu-id="70bb1-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="70bb1-180">För entitet eCommerceContacts väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="70bb1-181">För entitet loyCustomers väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="70bb1-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="70bb1-182">Lämna Normalisera tomt.</span><span class="sxs-lookup"><span data-stu-id="70bb1-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="70bb1-183">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Förena matchningsregel för namn och e-post.](media/unify-match-rule.png)

1. <span data-ttu-id="70bb1-185">Välj **Utfört**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-185">Select **Done**.</span></span>

1. <span data-ttu-id="70bb1-186">Välj **Spara** och **Kör**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="70bb1-187">Sammanslå</span><span class="sxs-lookup"><span data-stu-id="70bb1-187">Merge</span></span>

1. <span data-ttu-id="70bb1-188">Gå till fliken **Sammanslå**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="70bb1-189">På **ContactId** för entiteten **loyCustomers** ändrar du visningsnamnet till **ContactIdLOYALTY** för att särskilja den från andra inmatade ID.</span><span class="sxs-lookup"><span data-stu-id="70bb1-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![byta namn på contactid från lojalitets-id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="70bb1-191">Välj **Spara** och **Kör sammanslagnings- och nedströmsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="70bb1-192">Uppgift 3 – Konfigurera kundens livstidsvärdesprediktion</span><span class="sxs-lookup"><span data-stu-id="70bb1-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="70bb1-193">Med de enhetliga kundprofilerna på plats kan vi nu köra kundens livstidsvärdesprediktion.</span><span class="sxs-lookup"><span data-stu-id="70bb1-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="70bb1-194">Detaljerade steg finns i [Kundens livstidsvärdesprediktion (förhandsversion)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="70bb1-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="70bb1-195">Gå till **Intelligens**  > **Förutsägelser** och välj **Kundens livstidsvärdesmodell**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="70bb1-196">Gå igenom informationen i sidorutan och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="70bb1-197">Namnge modellen **OOB eCommerce CLV prediktion** och utdataentiteten **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="70bb1-198">Definiera modellinställningar för CLV-modellen:</span><span class="sxs-lookup"><span data-stu-id="70bb1-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="70bb1-199">**Prediktionstidsperiod**: **12 månader eller 1 år**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="70bb1-200">Den här inställningen definierar hur långt in i framtiden som kundens livstidsvärde ska förutsägas.</span><span class="sxs-lookup"><span data-stu-id="70bb1-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="70bb1-201">**Aktiva kunder**: Ange vad aktiva kunder betyder för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="70bb1-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="70bb1-202">Ange den historiska tidsram där en kund måste ha haft minst en transaktion som ska betraktas som aktiv.</span><span class="sxs-lookup"><span data-stu-id="70bb1-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="70bb1-203">Modellen förutser endast kundens livstid för aktiva kunder.</span><span class="sxs-lookup"><span data-stu-id="70bb1-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="70bb1-204">Välj mellan att låta modellen beräkna tidsperioden baserat på historiska transaktionsdata eller ange en specifik tidsram.</span><span class="sxs-lookup"><span data-stu-id="70bb1-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="70bb1-205">I den här exempelguiden **låter vi modellen beräkna inköpsintervall**, vilket är standardalternativet.</span><span class="sxs-lookup"><span data-stu-id="70bb1-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="70bb1-206">**Kunder med högt värde**: Definiera kunder med högt värde som en percentil av toppbetalande kunder.</span><span class="sxs-lookup"><span data-stu-id="70bb1-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="70bb1-207">Modellen använder den här indata för att ge resultat som passar din affärsdefinition av kunder med högt värde.</span><span class="sxs-lookup"><span data-stu-id="70bb1-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="70bb1-208">Du kan välja att låta modellen definiera kunder med högt värde.</span><span class="sxs-lookup"><span data-stu-id="70bb1-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="70bb1-209">Den använder en heuristisk regel som härleder percentilen.</span><span class="sxs-lookup"><span data-stu-id="70bb1-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="70bb1-210">Du kan också definiera kunder med högt värde som en percentil av framtida toppbetalande kunder.</span><span class="sxs-lookup"><span data-stu-id="70bb1-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="70bb1-211">I den här exempelguiden definierar vi manuellt kunder med högt värde som **topp 30 % av aktiva betalande kunder** och väljer **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Inställningssteg i den guidade upplevelsen för CLV-modellen.":::

1. <span data-ttu-id="70bb1-213">I steget **Obligatoriska data** väljer du **Lägg till data** för att tillhandahålla transaktionshistorikdata.</span><span class="sxs-lookup"><span data-stu-id="70bb1-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="70bb1-214">Lägg till entiteten **eCommercePurchases: e-handel** och mappa de attribut som krävs av modellen:</span><span class="sxs-lookup"><span data-stu-id="70bb1-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="70bb1-215">Transaktions-ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="70bb1-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="70bb1-216">Transaktionsdatum: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="70bb1-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="70bb1-217">Transaktionsbelopp: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="70bb1-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="70bb1-218">Produkt-ID: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="70bb1-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="70bb1-219">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-219">Select **Next**.</span></span>

1. <span data-ttu-id="70bb1-220">Ställ in förhållandet mellan entiteten **eCommercePurchases: e-handel** och **eCommerceContacts: e-handel**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="70bb1-221">Med steget **Ytterligare data (valfritt)** kan du lägga till mer data om kundaktivitet.</span><span class="sxs-lookup"><span data-stu-id="70bb1-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="70bb1-222">Dessa data kan hjälpa till att få fler insikter för kundinteraktioner med ditt företag, vilket kan bidra till CLV.</span><span class="sxs-lookup"><span data-stu-id="70bb1-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="70bb1-223">Att lägga till viktiga kundinteraktioner som webbloggar, kundtjänstloggar eller belöningsprogramhistorik kan förbättra förutsägelsernas noggrannhet.</span><span class="sxs-lookup"><span data-stu-id="70bb1-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="70bb1-224">Välj **Lägg till data** för att inkludera mer data om kundaktivitet.</span><span class="sxs-lookup"><span data-stu-id="70bb1-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="70bb1-225">Lägg till entiteten för kundaktivitet och mappa fältnamnen till motsvarande fält som krävs enligt modellen:</span><span class="sxs-lookup"><span data-stu-id="70bb1-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="70bb1-226">Kundaktivitetsenhet: Recensioner:Webbplats</span><span class="sxs-lookup"><span data-stu-id="70bb1-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="70bb1-227">Primärnyckel: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="70bb1-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="70bb1-228">Tidsstämpel: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="70bb1-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="70bb1-229">Händelse (aktivitetsnamn): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="70bb1-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="70bb1-230">Information (belopp eller värde): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="70bb1-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="70bb1-231">Välj **Nästa** och konfigurera aktiviteten och relationen mellan transaktionsdata och kunddata:</span><span class="sxs-lookup"><span data-stu-id="70bb1-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="70bb1-232">Aktivitetstyp: Välj befintlig</span><span class="sxs-lookup"><span data-stu-id="70bb1-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="70bb1-233">Aktivitetsetikett: Recension</span><span class="sxs-lookup"><span data-stu-id="70bb1-233">Activity label: Review</span></span>
   - <span data-ttu-id="70bb1-234">Motsvarande etikett: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="70bb1-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="70bb1-235">Kundenhet: eCommerceContacts:e-handel</span><span class="sxs-lookup"><span data-stu-id="70bb1-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="70bb1-236">Relation: Webbplatsrecensioner</span><span class="sxs-lookup"><span data-stu-id="70bb1-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="70bb1-237">Välj **Nästa** för att ange modellschemat.</span><span class="sxs-lookup"><span data-stu-id="70bb1-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="70bb1-238">Modellen måste träna regelbundet för att lära sig nya mönster när nya data matas in.</span><span class="sxs-lookup"><span data-stu-id="70bb1-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="70bb1-239">I det här exemplet väljer du **Månadsvis**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="70bb1-240">När du har granskat alla detaljer väljer du **Spara och kör**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="70bb1-241">Uppgift 4 – Granska modellresultat och förklaringar</span><span class="sxs-lookup"><span data-stu-id="70bb1-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="70bb1-242">Låt modellen slutföra träningen och bedömningen av data.</span><span class="sxs-lookup"><span data-stu-id="70bb1-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="70bb1-243">Därefter kan du granska CLV-modellens resultat och förklaringar.</span><span class="sxs-lookup"><span data-stu-id="70bb1-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="70bb1-244">Mer information finns i [Granska en förutsägelsestatus och resultat](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="70bb1-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="70bb1-245">Uppgift 5 - Skapa ett segment med kunder med högt värde</span><span class="sxs-lookup"><span data-stu-id="70bb1-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="70bb1-246">Om du kör modellen skapas en ny entitet som visas på **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="70bb1-247">Du kan skapa ett nytt kundsegment baserat på den entitet som skapas av modellen.</span><span class="sxs-lookup"><span data-stu-id="70bb1-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="70bb1-248">Gå till **Segment**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="70bb1-249">Välj **Nytt** och välj **Skapa från** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="70bb1-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Skapa ett segment med modellutdata.](media/segment-intelligence.png)

1. <span data-ttu-id="70bb1-251">Välj entiteten **OOBeCommerceCLVPrediction** och definiera segmentet:</span><span class="sxs-lookup"><span data-stu-id="70bb1-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="70bb1-252">Fält: CLVScore</span><span class="sxs-lookup"><span data-stu-id="70bb1-252">Field: CLVScore</span></span>
  - <span data-ttu-id="70bb1-253">Operatör: större än</span><span class="sxs-lookup"><span data-stu-id="70bb1-253">Operator: greater than</span></span>
  - <span data-ttu-id="70bb1-254">Värde: 1500</span><span class="sxs-lookup"><span data-stu-id="70bb1-254">Value: 1500</span></span>

1. <span data-ttu-id="70bb1-255">Välj **Granska** och **Spara** segmentet.</span><span class="sxs-lookup"><span data-stu-id="70bb1-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="70bb1-256">Du har nu ett segment som identifierar kunder som förväntas generera mer än 1 500 dollar i intäkter under de kommande 12 månaderna.</span><span class="sxs-lookup"><span data-stu-id="70bb1-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="70bb1-257">Det här segmentet uppdateras dynamiskt om mer data matas in.</span><span class="sxs-lookup"><span data-stu-id="70bb1-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="70bb1-258">Mer information finns i [Skapa och hantera segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="70bb1-258">For more information, see [Create and manage segments](segments.md).</span></span>
