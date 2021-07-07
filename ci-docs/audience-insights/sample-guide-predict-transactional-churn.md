---
title: Exempelguide för förutsägelse om transaktionell omsättning
description: Använd exempelguiden för att prova den medföljande modellen för förutsägelse om transaktionell omsättning.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306142"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="26bbd-103">Exempelguide för förutsägelse om transaktionell omsättning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="26bbd-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="26bbd-104">Den här guiden ger dig ett komplett exempel på förutsägelse av transaktionell omsättning i Customer Insights med hjälp av de data som anges nedan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="26bbd-105">Alla data som används i den här guiden är inte verkliga kunddata och är en del av den Contoso-datauppsättning som finns i *demomiljön* i din Customer Insights-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="26bbd-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="26bbd-106">Scenario</span><span class="sxs-lookup"><span data-stu-id="26bbd-106">Scenario</span></span>

<span data-ttu-id="26bbd-107">Contoso är ett företag som producerar högkvalitativt kaffe och kaffemaskiner, som de säljer via sin Contoso Coffee-webbplats.</span><span class="sxs-lookup"><span data-stu-id="26bbd-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="26bbd-108">Deras mål är att veta vilka kunder som vanligtvis köper deras produkter regelbundet kommer att sluta vara aktiva kunder under de närmaste 60 dagarna.</span><span class="sxs-lookup"><span data-stu-id="26bbd-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="26bbd-109">Att veta vilka av deras kunder som **sannolikt kommer att omsättas** kan hjälpa dem att spara marknadsföringsinsatser genom att fokusera på att behålla dem.</span><span class="sxs-lookup"><span data-stu-id="26bbd-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26bbd-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="26bbd-110">Prerequisites</span></span>

- <span data-ttu-id="26bbd-111">Minst [Deltagarbehörighet](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="26bbd-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="26bbd-112">Vi rekommenderar att du implementerar följande steg [i en ny miljö](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="26bbd-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="26bbd-113">Uppgift 1 – Mata in data</span><span class="sxs-lookup"><span data-stu-id="26bbd-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="26bbd-114">Granska artiklarna [om datainmatning](data-sources.md) och [import av datakällor med hjälp av Power Query-anslutningsprogram](connect-power-query.md) specifikt.</span><span class="sxs-lookup"><span data-stu-id="26bbd-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="26bbd-115">Följande information förutsätter att du bekantat dig med inmatningsdata i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="26bbd-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="26bbd-116">Mata in kunddata från e-handelsplattformen</span><span class="sxs-lookup"><span data-stu-id="26bbd-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="26bbd-117">Skapa en datakälla med namnet **eCommerce**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="26bbd-118">Ange URL för e-handelskontakter https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="26bbd-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="26bbd-119">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="26bbd-120">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="26bbd-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="26bbd-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="26bbd-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="26bbd-122">**CreatedOn**: Datum/Tid/Zon</span><span class="sxs-lookup"><span data-stu-id="26bbd-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="26bbd-123">![Transformera födelsedatum till datum](media/ecommerce-dob-date.PNG "transformera födelsedatum till datum")</span><span class="sxs-lookup"><span data-stu-id="26bbd-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="26bbd-124">I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="26bbd-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="26bbd-125">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="26bbd-126">Mata in inköpsdata online</span><span class="sxs-lookup"><span data-stu-id="26bbd-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="26bbd-127">Lägg till ytterligare en datauppsättning till samma **e-handelskälla**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="26bbd-128">Välj anslutningsprogrammet **Text/CSV** igen.</span><span class="sxs-lookup"><span data-stu-id="26bbd-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="26bbd-129">Ange URL för **Onlineköpsdata** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="26bbd-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="26bbd-130">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="26bbd-131">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="26bbd-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="26bbd-132">**PurchasedOn**: Datum/tid</span><span class="sxs-lookup"><span data-stu-id="26bbd-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="26bbd-133">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="26bbd-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="26bbd-134">I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="26bbd-135">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="26bbd-136">Mata in kunddata från lojalitetsschema</span><span class="sxs-lookup"><span data-stu-id="26bbd-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="26bbd-137">Skapa en datakälla med namnet **LoyaltyScheme**, välj importalternativet och välj anslutningsprogrammet **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="26bbd-138">Ange URL för e-handelskontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="26bbd-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="26bbd-139">Medan du redigerar data väljer du **Transformera** och sedan **Använd första raden som rubriker**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="26bbd-140">Uppdatera datatypen för kolumnerna som anges nedan:</span><span class="sxs-lookup"><span data-stu-id="26bbd-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="26bbd-141">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="26bbd-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="26bbd-142">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="26bbd-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="26bbd-143">**CreatedOn**: Datum/Tid</span><span class="sxs-lookup"><span data-stu-id="26bbd-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="26bbd-144">I fältet **Namn** i fönstret till höger byter du namn på din datakälla från **Fråga** till **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="26bbd-145">Spara datakällan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="26bbd-146">Uppgift 2 – Dataförening</span><span class="sxs-lookup"><span data-stu-id="26bbd-146">Task 2 - Data unification</span></span>

<span data-ttu-id="26bbd-147">Efter inmatning av datan börjar vi nu processen **mappa, matcha, slå samman** för att skapa en enhetlig kundprofil.</span><span class="sxs-lookup"><span data-stu-id="26bbd-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="26bbd-148">Mer information finns i [Dataförening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="26bbd-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="26bbd-149">Mappa</span><span class="sxs-lookup"><span data-stu-id="26bbd-149">Map</span></span>

1. <span data-ttu-id="26bbd-150">Efter inmatande av data mappar du kontakter från e-handels- och lojalitetsdata till vanliga datatyper.</span><span class="sxs-lookup"><span data-stu-id="26bbd-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="26bbd-151">Gå till **Data** > **Förena** > **Mappa**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="26bbd-152">Välj de entiteter som representerar kundprofilen – **eCommerceContacts** och **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="förena e-handels- och lojalitetsdatakällor.":::

1. <span data-ttu-id="26bbd-154">Välj **ContactId** som primärnyckel för **eCommerceContacts** och **LoyaltyID** som primärnyckel för **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Förena LoyaltyId som primärnyckel.":::

### <a name="match"></a><span data-ttu-id="26bbd-156">Matchning</span><span class="sxs-lookup"><span data-stu-id="26bbd-156">Match</span></span>

1. <span data-ttu-id="26bbd-157">Gå till fliken **Matcha** och välj **Ange ordning**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="26bbd-158">I listrutan **Primär** väljer du **eCommerceContacts : eCommerce** som primär källa och inkluderar samtliga poster.</span><span class="sxs-lookup"><span data-stu-id="26bbd-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="26bbd-159">I listrutan **Entitet 2** väljer du **loyCustomers : LoyaltyScheme** och inkluderar alla poster.</span><span class="sxs-lookup"><span data-stu-id="26bbd-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Förena matchande e-handel och lojalitet.":::

1. <span data-ttu-id="26bbd-161">Välj **Skapa en ny regel**</span><span class="sxs-lookup"><span data-stu-id="26bbd-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="26bbd-162">Lägg till ditt första villkor med hjälp av FullName.</span><span class="sxs-lookup"><span data-stu-id="26bbd-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="26bbd-163">För eCommerceContacts väljer du **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="26bbd-164">För loyCustomers väljer du **FullName** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="26bbd-165">Välj listrutan **Normalisera** och välj **Typ (telefon, namn, adress ...)**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="26bbd-166">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="26bbd-167">Ange namnet **FullName, E-post** för den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="26bbd-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="26bbd-168">Lägg till ett andra villkor för e-postadress genom att välja **Lägg till villkor**</span><span class="sxs-lookup"><span data-stu-id="26bbd-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="26bbd-169">För entiteten eCommerceContacts väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="26bbd-170">För entiteten loyCustomers väljer du **EMail** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="26bbd-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="26bbd-171">Lämna Normalisera tomt.</span><span class="sxs-lookup"><span data-stu-id="26bbd-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="26bbd-172">Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Förena matchningsregel för namn och e-post.":::

7. <span data-ttu-id="26bbd-174">Välj **Spara** och **Kör**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="26bbd-175">Slå ihop</span><span class="sxs-lookup"><span data-stu-id="26bbd-175">Merge</span></span>

1. <span data-ttu-id="26bbd-176">Gå till fliken **Sammanslå**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="26bbd-177">På **ContactId** för entiteten **loyCustomers** ändrar du visningsnamnet till **ContactIdLOYALTY** för att särskilja den från andra inmatade ID.</span><span class="sxs-lookup"><span data-stu-id="26bbd-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="byta namn på contactid från lojalitets-id.":::

1. <span data-ttu-id="26bbd-179">Välj **Spara** och **Kör** för att starta sammanslagningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="26bbd-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="26bbd-180">Uppgift 3 – Konfigurera förutsägelsen om transaktionell omsättning</span><span class="sxs-lookup"><span data-stu-id="26bbd-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="26bbd-181">Med de enhetliga kundprofilerna på plats kan vi nu köra förutsägelsen om prenumerationsomsättning.</span><span class="sxs-lookup"><span data-stu-id="26bbd-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="26bbd-182">Detaljerade steg finns i artikeln [Förutsägelse om prenumerationsomsättning (förhandsversion)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="26bbd-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="26bbd-183">Gå till **Intelligens** > **Utforska** och välj att använda **modellen Kundomsättning**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="26bbd-184">Välj alternativet **Transaktionell** och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="26bbd-185">Namnge modellen **OOB förutsägelse om transaktionell omsättning inom e-handel** och utdataentiteten **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="26bbd-186">Definiera två villkor för omsättningsmodellen:</span><span class="sxs-lookup"><span data-stu-id="26bbd-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="26bbd-187">**Fönsstret Förutsägelse**: **minst 60** dagar.</span><span class="sxs-lookup"><span data-stu-id="26bbd-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="26bbd-188">Den här inställningen definierar hur långt in i framtiden vi vill förutsäga kundomsättning.</span><span class="sxs-lookup"><span data-stu-id="26bbd-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="26bbd-189">**Omsättningsdefinition**: **minst 60** dagar.</span><span class="sxs-lookup"><span data-stu-id="26bbd-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="26bbd-190">Tidsperiod utan köp varefter en kund anses vara omsatt.</span><span class="sxs-lookup"><span data-stu-id="26bbd-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Välj modellens förutsägelsefönster och omsättningsdefinition.":::

1. <span data-ttu-id="26bbd-192">Välj **Inköpshistorik (obligatoriskt)** och välj **Lägg till data** för inköpshistorik.</span><span class="sxs-lookup"><span data-stu-id="26bbd-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="26bbd-193">Lägg till entiteten **eCommercePurchases: e-handel** och mappa fälten från e-handel till motsvarande fält som krävs av modellen.</span><span class="sxs-lookup"><span data-stu-id="26bbd-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="26bbd-194">Anslut till entiteten **eCommercePurchases: e-handel** med **eCommerceContacts: e-handel**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Anslut e-handelsentiteter.":::

1. <span data-ttu-id="26bbd-196">Välj **Nästa** för att ange modellschemat.</span><span class="sxs-lookup"><span data-stu-id="26bbd-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="26bbd-197">Modellen måste träna regelbundet för att lära sig nya mönster när det finns nya data inmatade.</span><span class="sxs-lookup"><span data-stu-id="26bbd-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="26bbd-198">För det här exemplet väljer du **Månadsvis**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="26bbd-199">När du har granskat alla detaljer väljer du **Spara och kör**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="26bbd-200">Uppgift 4 – Granska modellresultat och förklaringar</span><span class="sxs-lookup"><span data-stu-id="26bbd-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="26bbd-201">Låt modellen slutföra träningen och bedömningen av data.</span><span class="sxs-lookup"><span data-stu-id="26bbd-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="26bbd-202">Du kan nu granska förklaringar av modellen för prenumerationsomsättning.</span><span class="sxs-lookup"><span data-stu-id="26bbd-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="26bbd-203">Mer information finns i [Granska en förutsägelsestatus och resultat](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="26bbd-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="26bbd-204">Uppgift 5 – Skapa ett segment med kunder med hög omsättningsrisk</span><span class="sxs-lookup"><span data-stu-id="26bbd-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="26bbd-205">Om du kör produktionsmodellen skapas en ny entitet som du kan se i **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="26bbd-206">Du kan skapa ett nytt segment baserat på entiteten som skapats av modellen.</span><span class="sxs-lookup"><span data-stu-id="26bbd-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="26bbd-207">Gå till **Segment**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-207">Go to **Segments**.</span></span> <span data-ttu-id="26bbd-208">Välj **Nytt** och välj **Skapa från** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="26bbd-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Skapa ett segment med modellutdata.":::

1. <span data-ttu-id="26bbd-210">Välj slutpunkten **OOBSubscriptionChurnPrediction** och definiera segmentet:</span><span class="sxs-lookup"><span data-stu-id="26bbd-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="26bbd-211">Fält: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="26bbd-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="26bbd-212">Operatör: större än</span><span class="sxs-lookup"><span data-stu-id="26bbd-212">Operator: greater than</span></span>
   - <span data-ttu-id="26bbd-213">Värde: 0,6</span><span class="sxs-lookup"><span data-stu-id="26bbd-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Konfigurera segment för prenumerationsomsättning.":::

<span data-ttu-id="26bbd-215">Du har nu ett segment som uppdateras dynamiskt som identifierar kunder med hög omsättningsrisk för den här prenumerationsverksamheten.</span><span class="sxs-lookup"><span data-stu-id="26bbd-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="26bbd-216">Mer information finns i [Skapa och hantera segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="26bbd-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]