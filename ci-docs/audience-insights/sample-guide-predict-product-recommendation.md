---
title: Exempelguide för förutsägelse av produktrekommendationer
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om produktrekommendation.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270538"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="0140d-103">Exempelguide för förutsägelse av produktrekommendationer (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0140d-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="0140d-104">Vi ger dig ett komplett exempel på förutsägelse av produktrekommendation med hjälp av de exempeldata som anges nedan.</span><span class="sxs-lookup"><span data-stu-id="0140d-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="0140d-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="0140d-105">Scenario</span></span>

<span data-ttu-id="0140d-106">Contoso är ett företag som producerar kaffe och kaffemaskiner av hög kvalitet, som de säljer via Contoso Coffee-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0140d-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="0140d-107">Målet är att förstå vilka produkter de ska rekommendera till sina återkommande kunder.</span><span class="sxs-lookup"><span data-stu-id="0140d-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="0140d-108">Om du vet vilka kunder som **sannolikt kommer att köpa**, kan du göra besparingar på marknadsföring genom att fokusera på specifika objekt.</span><span class="sxs-lookup"><span data-stu-id="0140d-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0140d-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="0140d-109">Prerequisites</span></span>

- <span data-ttu-id="0140d-110">Minst [Deltagarbehörighet](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0140d-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="0140d-111">Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="0140d-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="0140d-112">Uppgift 1 – Mata in data</span><span class="sxs-lookup"><span data-stu-id="0140d-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="0140d-113">Granska artiklarna [om datainmatning](data-sources.md) och [import av datakällor med hjälp av Power Query-anslutningsprogram](connect-power-query.md) specifikt.</span><span class="sxs-lookup"><span data-stu-id="0140d-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="0140d-114">Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="0140d-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="0140d-115">Mata in kunddata från e-handelsplattformen</span><span class="sxs-lookup"><span data-stu-id="0140d-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="0140d-116">Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0140d-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="0140d-117">Ange URL för e-handelskontakter https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="0140d-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="0140d-118">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="0140d-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0140d-119">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="0140d-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="0140d-120">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="0140d-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="0140d-121">**CreatedOn**: Datum/Tid/Zon</span><span class="sxs-lookup"><span data-stu-id="0140d-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformera födelsedatum till datum.":::

5. <span data-ttu-id="0140d-123">I fältet "Namn" i fönstret till höger byter du namn på din datakälla från **Query** till **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="0140d-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="0140d-124">**Spara** datakällan.</span><span class="sxs-lookup"><span data-stu-id="0140d-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="0140d-125">Mata in inköpsdata online</span><span class="sxs-lookup"><span data-stu-id="0140d-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="0140d-126">Lägg till ytterligare en datauppsättning till samma **e-handelskälla**.</span><span class="sxs-lookup"><span data-stu-id="0140d-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="0140d-127">Välj anslutningsprogrammet **Text/CSV** igen.</span><span class="sxs-lookup"><span data-stu-id="0140d-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="0140d-128">Ange URL för **Onlineköpsdata** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="0140d-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="0140d-129">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="0140d-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0140d-130">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="0140d-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="0140d-131">**PurchasedOn**: Datum/tid</span><span class="sxs-lookup"><span data-stu-id="0140d-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="0140d-132">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="0140d-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="0140d-133">I fältet **Namn** i sidofönstret byter du namn på din datakälla från **Fråga** till **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="0140d-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="0140d-134">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="0140d-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="0140d-135">Mata in kunddata från lojalitetsschema</span><span class="sxs-lookup"><span data-stu-id="0140d-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="0140d-136">Skapa en datakälla med namnet **LoyaltyScheme**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0140d-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="0140d-137">Ange URL för e-handelskontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="0140d-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="0140d-138">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="0140d-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0140d-139">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="0140d-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="0140d-140">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="0140d-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="0140d-141">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="0140d-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="0140d-142">**CreatedOn**: Datum/Tid</span><span class="sxs-lookup"><span data-stu-id="0140d-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="0140d-143">I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0140d-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="0140d-144">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="0140d-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="0140d-145">Uppgift 2 – Dataförening</span><span class="sxs-lookup"><span data-stu-id="0140d-145">Task 2 - Data unification</span></span>

<span data-ttu-id="0140d-146">Efter inmatning av datan börjar vi nu processen **mappa, matcha, slå samman** för att skapa en enhetlig kundprofil.</span><span class="sxs-lookup"><span data-stu-id="0140d-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="0140d-147">Mer information finns i [Dataförening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="0140d-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="0140d-148">Mappa</span><span class="sxs-lookup"><span data-stu-id="0140d-148">Map</span></span>

1. <span data-ttu-id="0140d-149">Efter inmatande av data mappar du kontakter från e-handels- och lojalitetsdata till vanliga datatyper.</span><span class="sxs-lookup"><span data-stu-id="0140d-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="0140d-150">Gå till **Data** > **Förena** > **Mappa**.</span><span class="sxs-lookup"><span data-stu-id="0140d-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="0140d-151">Välj de entiteter som representerar kundprofilen – **eCommerceContacts** och **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0140d-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![förena e-handels- och lojalitetsdatakällor.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="0140d-153">Välj **ContactId** som primärnyckel för **eCommerceContacts** och **LoyaltyID** som primärnyckel för **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0140d-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Förena LoyaltyId som primärnyckel.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="0140d-155">Matchning</span><span class="sxs-lookup"><span data-stu-id="0140d-155">Match</span></span>

1. <span data-ttu-id="0140d-156">Gå till fliken **Matcha** och välj **Ange ordning**.</span><span class="sxs-lookup"><span data-stu-id="0140d-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="0140d-157">I listrutan **Primär** väljer du **eCommerceContacts: e-handel** som primär källa och inkluderar alla poster.</span><span class="sxs-lookup"><span data-stu-id="0140d-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="0140d-158">I listrutan **Entitet 2** väljer du **loyCustomers: LoyaltyScheme** och inkluderar alla poster.</span><span class="sxs-lookup"><span data-stu-id="0140d-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Förena matchande e-handel och lojalitet.](media/unify-match-order.png)

4. <span data-ttu-id="0140d-160">Välj **Skapa en ny regel**</span><span class="sxs-lookup"><span data-stu-id="0140d-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="0140d-161">Lägg till ditt första villkor med hjälp av FullName.</span><span class="sxs-lookup"><span data-stu-id="0140d-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="0140d-162">För eCommerceContacts välj **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="0140d-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="0140d-163">För loyCustomers välj **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="0140d-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="0140d-164">Välj listrutan **Normalisera** och välj **Typ (telefon, namn, adress ...)**.</span><span class="sxs-lookup"><span data-stu-id="0140d-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="0140d-165">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="0140d-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="0140d-166">Ange namnet **FullName, E-post** för den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="0140d-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="0140d-167">Lägg till ett andra villkor för e-postadress genom att välja **Lägg till villkor**</span><span class="sxs-lookup"><span data-stu-id="0140d-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="0140d-168">För entitet eCommerceContacts väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="0140d-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="0140d-169">För entitet loyCustomers väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="0140d-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="0140d-170">Lämna Normalisera tomt.</span><span class="sxs-lookup"><span data-stu-id="0140d-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="0140d-171">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="0140d-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Förena matchningsregel för namn och e-post.](media/unify-match-rule.png)

7. <span data-ttu-id="0140d-173">Välj **Spara** och **Kör**.</span><span class="sxs-lookup"><span data-stu-id="0140d-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="0140d-174">Slå ihop</span><span class="sxs-lookup"><span data-stu-id="0140d-174">Merge</span></span>

1. <span data-ttu-id="0140d-175">Gå till fliken **Sammanslå**.</span><span class="sxs-lookup"><span data-stu-id="0140d-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="0140d-176">På **ContactId** för entiteten **loyCustomers** ändrar du visningsnamnet till **ContactIdLOYALTY** för att särskilja den från andra inmatade ID.</span><span class="sxs-lookup"><span data-stu-id="0140d-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![byta namn på contactid från lojalitets-id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="0140d-178">Välj **Spara** och **Kör** för att starta sammanslagningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="0140d-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="0140d-179">Uppgift 3 – Konfigurera förutsägelse av produktrekommendation</span><span class="sxs-lookup"><span data-stu-id="0140d-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="0140d-180">Med de enhetliga kundprofilerna på plats kan vi nu köra förutsägelsen om prenumerationsomsättning.</span><span class="sxs-lookup"><span data-stu-id="0140d-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="0140d-181">Gå till **Intelligens** > **Förutsägelse** välj **Produktrekommendation**.</span><span class="sxs-lookup"><span data-stu-id="0140d-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="0140d-182">Välj **Komma igång**.</span><span class="sxs-lookup"><span data-stu-id="0140d-182">Select **Get started**.</span></span>

1. <span data-ttu-id="0140d-183">Namnge modellen **OOB modellförutsägelse av produktrekommendation** och utdataentiteten **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="0140d-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="0140d-184">Definiera tre villkor för modellen:</span><span class="sxs-lookup"><span data-stu-id="0140d-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="0140d-185">**Antal produkter**: Sätt detta värde på **5**.</span><span class="sxs-lookup"><span data-stu-id="0140d-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="0140d-186">Den här inställningen anger hur många produkter du vill rekommendera till kunderna.</span><span class="sxs-lookup"><span data-stu-id="0140d-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="0140d-187">**Föreslå produkter som kunder nyligen har köpt?**: Välj **Ja** för att ange att du vill inkludera produkter i rekommendationen som dina kunder har köpt tidigare.</span><span class="sxs-lookup"><span data-stu-id="0140d-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="0140d-188">**Fönstret Titta bakåt:** Välj minst **365 dagar**.</span><span class="sxs-lookup"><span data-stu-id="0140d-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="0140d-189">Den här inställningen definierar hur långt bak i tiden som modellen tittar på kundens aktivitet för att använda den som indata i rekommendationerna.</span><span class="sxs-lookup"><span data-stu-id="0140d-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinställningar för produktrekommendationsmodellen.":::

1. <span data-ttu-id="0140d-191">Välj **Data som krävs** och välj **Lägg till data** för köphistorik.</span><span class="sxs-lookup"><span data-stu-id="0140d-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="0140d-192">Lägg till entiteten **eCommercePurchases: e-handel** och mappa fälten från e-handel till motsvarande fält som krävs av modellen.</span><span class="sxs-lookup"><span data-stu-id="0140d-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="0140d-193">Anslut till entiteten **eCommercePurchases: e-handel** med **eCommerceContacts: e-handel**.</span><span class="sxs-lookup"><span data-stu-id="0140d-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Anslut e-handelsentiteter.](media/model-purchase-join.png)

1. <span data-ttu-id="0140d-195">Välj **Nästa** för att ange modellschemat.</span><span class="sxs-lookup"><span data-stu-id="0140d-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="0140d-196">Modellen måste träna regelbundet för att lära sig nya mönster när det finns nya data inmatade.</span><span class="sxs-lookup"><span data-stu-id="0140d-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="0140d-197">För det här exemplet väljer du **Månadsvis**.</span><span class="sxs-lookup"><span data-stu-id="0140d-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="0140d-198">När du har granskat alla detaljer väljer du **Spara och kör**.</span><span class="sxs-lookup"><span data-stu-id="0140d-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="0140d-199">Uppgift 4 – Granska modellresultat och förklaringar</span><span class="sxs-lookup"><span data-stu-id="0140d-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="0140d-200">Låt modellen slutföra träningen och bedömningen av data.</span><span class="sxs-lookup"><span data-stu-id="0140d-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="0140d-201">Du kan nu granska förklaringar av modellen för produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="0140d-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="0140d-202">Mer information finns i [Granska en förutsägelsestatus och resultat](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="0140d-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="0140d-203">Uppgift 5 – Skapa ett segment med ofta köpta produkter</span><span class="sxs-lookup"><span data-stu-id="0140d-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="0140d-204">Om du kör produktionsmodellen skapas en ny entitet som du kan se i **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="0140d-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="0140d-205">Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.</span><span class="sxs-lookup"><span data-stu-id="0140d-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="0140d-206">Gå till **Segment**.</span><span class="sxs-lookup"><span data-stu-id="0140d-206">Go to **Segments**.</span></span> <span data-ttu-id="0140d-207">Välj **Nytt** och välj **Skapa från** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="0140d-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Skapa ett segment med modellutdata.](media/segment-intelligence.png)

1. <span data-ttu-id="0140d-209">Välj slutpunkten **OOBProductRecommendationModelPrediction** och definiera segmentet:</span><span class="sxs-lookup"><span data-stu-id="0140d-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="0140d-210">Fält: Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="0140d-210">Field: ProductID</span></span>
   - <span data-ttu-id="0140d-211">Operator: Värde</span><span class="sxs-lookup"><span data-stu-id="0140d-211">Operator: Value</span></span>
   - <span data-ttu-id="0140d-212">Värde: Välj de tre översta produkt-ID</span><span class="sxs-lookup"><span data-stu-id="0140d-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Skapa ett segment utifrån modellresultatet.":::

<span data-ttu-id="0140d-214">Nu har du ett segment som uppdateras dynamiskt och identifierar de kunder som är mer villiga att köpa de tre mest rekommenderade produkterna</span><span class="sxs-lookup"><span data-stu-id="0140d-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="0140d-215">Mer information finns i [Skapa och hantera segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0140d-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]