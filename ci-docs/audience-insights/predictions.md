---
title: Slutför partiella data med hjälp av förutsägelser
description: Använd förutsägelser för att fylla i ofullständiga kunddata.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648733"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="9920e-103">Komplettera dina ofullständiga data med förutsägelser</span><span class="sxs-lookup"><span data-stu-id="9920e-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9920e-104">Med hjälp av prediktioner kan du enkelt skapa förutsagda värden som förbättrar förståelsen av en kund.</span><span class="sxs-lookup"><span data-stu-id="9920e-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="9920e-105">På sidan **Intelligens** > **Förutsägelser** kan du välja **Mina förutsägelser** för att se förutsägelser som du har konfigurerat i andra delar av målgruppinsikter och anpassa dem ytterligare.</span><span class="sxs-lookup"><span data-stu-id="9920e-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="9920e-106">Du kan inte använda den här funktionen om din miljö använder Azure Data Lake gen 2-lagring.</span><span class="sxs-lookup"><span data-stu-id="9920e-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="9920e-107">I funktionen prediktioner används automatiska metoder för att utvärdera data och göra prediktioner baserade på dessa data och har därför möjlighet att använda som en metod för profilering, eftersom den termen definieras av allmän dataskyddsförordning ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="9920e-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="9920e-108">Kundens användning av den här funktionen för att bearbeta data kan vara föremål för GDPR eller andra lagar eller förordningar.</span><span class="sxs-lookup"><span data-stu-id="9920e-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="9920e-109">Du ansvarar för att din användning av Dynamics 365 Customer Insights, inklusive förutsägelser, följer alla tillämpliga lagar och förordningar, inklusive lagar som rör sekretess, personuppgifter, biometriska data, dataskydd och sekretess för kommunikation.</span><span class="sxs-lookup"><span data-stu-id="9920e-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9920e-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9920e-110">Prerequisites</span></span>

<span data-ttu-id="9920e-111">Innan du kan använda funktionen prediktioner i organisationen bör du kontrollera att följande förutsättningar är uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="9920e-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="9920e-112">Din organisation har en instans [konfigurerad i Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) och den är i samma organisation som Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9920e-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="9920e-113">Din miljö är kopplad till din Common Data Service-instans.</span><span class="sxs-lookup"><span data-stu-id="9920e-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="9920e-114">Om du [skapar en ny miljö](manage-environments.md) konfigurerar du den i dialogrutan **Skapa en miljö** och väljer **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="9920e-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="9920e-115">Om du redan har skapat en miljö går du till dess inställningar och väljer **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="9920e-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="9920e-116">Oavsett vilket anger du i avsnittet **Använd förutsägelser** Common Data Service-instansens URL som du vill koppla din miljö till.</span><span class="sxs-lookup"><span data-stu-id="9920e-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="9920e-117">Skapa en förutsägelse i entiteten Kund</span><span class="sxs-lookup"><span data-stu-id="9920e-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="9920e-118">I målgruppsinsikter går du till **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="9920e-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="9920e-119">Välj entiteten **Kund**.</span><span class="sxs-lookup"><span data-stu-id="9920e-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="9920e-120">I entiteten **kund: CustomerInsights** väljer du fliken **fält**.</span><span class="sxs-lookup"><span data-stu-id="9920e-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="9920e-121">Sök efter det attributnamn som du vill förutsäga värden för och välj sedan ikonen **översikt** i kolumnen **sammanfattning**.</span><span class="sxs-lookup"><span data-stu-id="9920e-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9920e-122">![Ikonen Översikt](media/intelligence-overviewicon.png "Ikonen Översikt")</span><span class="sxs-lookup"><span data-stu-id="9920e-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="9920e-123">Om attributet saknar en hög hastighet på saknade värden väljer du **Predicera saknade värden** för att fortsätta med din prediktion.</span><span class="sxs-lookup"><span data-stu-id="9920e-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9920e-124">![Översiktsstatus med knappen predicera saknade värden visas](media/intelligence-overviewpredictmissingvalues.png "Översiktsstatus med knappen predicera saknade värden visas")</span><span class="sxs-lookup"><span data-stu-id="9920e-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="9920e-125">Ange ett **visningsnamn** och **utdataenhetens namn** för resultatet av prediktionen.</span><span class="sxs-lookup"><span data-stu-id="9920e-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9920e-126">I en lista över alternativ som är i förväg visas var du kan mappa värdena till en fördefinierad kategori.</span><span class="sxs-lookup"><span data-stu-id="9920e-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="9920e-127">I det här fallet är de enda kategorialternativen 0 eller 1 som mappas till den faktiska/falska eller binära typen av förutsägelse.</span><span class="sxs-lookup"><span data-stu-id="9920e-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="9920e-128">I kolumnen Kategori, mappa de fältvärden som du vill ska vara klassificerade som "0" i den slutliga prediktionen till "0" och de objekt som du vill klassificera som "1" i den slutliga prediktionen till "1".</span><span class="sxs-lookup"><span data-stu-id="9920e-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9920e-129">![Exempel som visar mappade fältvärden för kategorier](media/intelligence-categorymapping.png "Exempel som visar mappade fältvärden för kategorier")</span><span class="sxs-lookup"><span data-stu-id="9920e-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="9920e-130">Välj **klart** och prediktionen kommer att bearbetas.</span><span class="sxs-lookup"><span data-stu-id="9920e-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="9920e-131">Bearbetningen kan ta en stund, beroende på datastorlek och komplexitet.</span><span class="sxs-lookup"><span data-stu-id="9920e-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="9920e-132">Resultatet blir tillgängligt i en ny entitet baserat på **Utdataenhetens namn** för den prediktion du skapade.</span><span class="sxs-lookup"><span data-stu-id="9920e-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="9920e-133">Skapa en prediktion när du skapar ett segment</span><span class="sxs-lookup"><span data-stu-id="9920e-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="9920e-134">Det går också att predicera saknade värden för ett specifikt val av attribut när du skapar ett segment.</span><span class="sxs-lookup"><span data-stu-id="9920e-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="9920e-135">När du snabbt skapar ett segment utifrån antingen den enhetliga entiteten för entiteten kund eller entiteten Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="9920e-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="9920e-136">Som en del av detta flöde kan du välja ett specifikt attribut som du vill basera segmentet på, till exempel kundtillfredsställelse eller inköpsbelopp.</span><span class="sxs-lookup"><span data-stu-id="9920e-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="9920e-137">När ett segment skapas föreslår systemet en metod för att förutsäga alla värden som saknas för attributet.</span><span class="sxs-lookup"><span data-stu-id="9920e-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="9920e-138">I målgruppsinsikter går du till **Segment** och väljer panelen **Profiler**.</span><span class="sxs-lookup"><span data-stu-id="9920e-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="9920e-139">Välj ett **fält** för att skapa ett segment på och välj en **operatör** och välj sedan **granska**.</span><span class="sxs-lookup"><span data-stu-id="9920e-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="9920e-140">Ange ett **namn** och ett **visningsnamn** för segmentet.</span><span class="sxs-lookup"><span data-stu-id="9920e-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="9920e-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9920e-141">Select **Save**.</span></span>

5. <span data-ttu-id="9920e-142">Om det segment du skapade innehåller ofullständiga data i källfältet kan du välja att förutsäga de saknade värdena.</span><span class="sxs-lookup"><span data-stu-id="9920e-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9920e-143">![Knappen prediktion](media/segments-predictoption.png "Knappen prediktion")</span><span class="sxs-lookup"><span data-stu-id="9920e-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="9920e-144">Ange ett **visningsnamn** och **utdataenhetens namn** för resultatet av prediktionen.</span><span class="sxs-lookup"><span data-stu-id="9920e-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9920e-145">Markera **Klart**.</span><span class="sxs-lookup"><span data-stu-id="9920e-145">Select **Done**.</span></span> <span data-ttu-id="9920e-146">Din prediktion skapas inom kort i en ny entitet med det namn du angav för **Utdataenhetens namn**.</span><span class="sxs-lookup"><span data-stu-id="9920e-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="9920e-147">Visa en prediktion</span><span class="sxs-lookup"><span data-stu-id="9920e-147">View a prediction</span></span>

1. <span data-ttu-id="9920e-148">I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="9920e-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9920e-149">Välj den prediktion du vill granska.</span><span class="sxs-lookup"><span data-stu-id="9920e-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="9920e-150">Välj en ellips i kolumnen **Åtgärder** och välj **Visa**.</span><span class="sxs-lookup"><span data-stu-id="9920e-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9920e-151">Du ser flera datapunkter i vyn av din prediktion.</span><span class="sxs-lookup"><span data-stu-id="9920e-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9920e-152">![Sidan Prediktioner](media/intelligence-predictionsviewpage.png "Sidan Prediktioner")</span><span class="sxs-lookup"><span data-stu-id="9920e-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="9920e-153">**Predicerade värden** visar den mappning du skapade vid fältvärdet för kategorimappning.</span><span class="sxs-lookup"><span data-stu-id="9920e-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="9920e-154">Dessa är värden i dina datauppsättning som har mappats till en specifik kategori.</span><span class="sxs-lookup"><span data-stu-id="9920e-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="9920e-155">-**Främsta influerare** är de faktorer inom datauppsättning som sannolikt skulle påverka prediktionens relevans för fältvärdet som mappas till en specifik kategori.</span><span class="sxs-lookup"><span data-stu-id="9920e-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="9920e-156">**Prestanda** indikerar hur prediktionerna fungerar.</span><span class="sxs-lookup"><span data-stu-id="9920e-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="9920e-157">Välj länken om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="9920e-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="9920e-158">**Förhandsgranskning** visar prover av utgående datauppsättning från din prediktion och sannolikheten eller vårt förtroende för det predicerade värdet där 0 är osäker och 1 är säker.</span><span class="sxs-lookup"><span data-stu-id="9920e-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="9920e-159">Uppdatera en prediktion</span><span class="sxs-lookup"><span data-stu-id="9920e-159">Update a prediction</span></span>

1. <span data-ttu-id="9920e-160">I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="9920e-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9920e-161">Markera den prediktion du vill uppdatera och välj ikonen **uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="9920e-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="9920e-162">Prediktionen kommer att schemaläggas för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="9920e-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="9920e-163">Du kan se hur lång tid som uppdaterades senast i kolumnen **Uppdaterad** på sidan **prediktioner**.</span><span class="sxs-lookup"><span data-stu-id="9920e-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="9920e-164">Redigera en prediktion</span><span class="sxs-lookup"><span data-stu-id="9920e-164">Edit a prediction</span></span>

<span data-ttu-id="9920e-165">När du har skapat en prediktion kan du anpassa modellen i AI Builder för att öka modellens effektivitet.</span><span class="sxs-lookup"><span data-stu-id="9920e-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="9920e-166">I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="9920e-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9920e-167">Markera den prediktion du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="9920e-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="9920e-168">Välj en ellips i kolumnen **Åtgärder** och välj **Visa**.</span><span class="sxs-lookup"><span data-stu-id="9920e-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9920e-169">Välj **Anpassa i AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="9920e-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="9920e-170">Uppdatera modellen i AI Builder.</span><span class="sxs-lookup"><span data-stu-id="9920e-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="9920e-171">[Mer information om hur du hanterar modeller i AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="9920e-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="9920e-172">Nästa gång du kör din prediktion används den uppdaterade modell som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="9920e-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="9920e-173">Nya modeller som skapats i AI Builder kommer inte att visas i målgruppsinsikter om inte modellen skapades från de upplevelser som anges ovan.</span><span class="sxs-lookup"><span data-stu-id="9920e-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="9920e-174">Ta bort en prediktion</span><span class="sxs-lookup"><span data-stu-id="9920e-174">Remove a prediction</span></span>

1. <span data-ttu-id="9920e-175">I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="9920e-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9920e-176">Markera den prediktion du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="9920e-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="9920e-177">Välj en ellips i kolumnen **Åtgärder** och välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="9920e-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="9920e-178">Bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="9920e-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9920e-179">Felsökning</span><span class="sxs-lookup"><span data-stu-id="9920e-179">Troubleshooting</span></span>

<span data-ttu-id="9920e-180">Om du inte kan slutföra anslutna Common Data Service-processen på grund av ett fel kan du försöka slutföra processen manuellt.</span><span class="sxs-lookup"><span data-stu-id="9920e-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="9920e-181">Det finns två kända problem som kan uppstå under anslutningsprocessen:</span><span class="sxs-lookup"><span data-stu-id="9920e-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="9920e-182">Tilläggslösningen Customer Card har inte installerats.</span><span class="sxs-lookup"><span data-stu-id="9920e-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="9920e-183">Slutför anvisningarna för att [Installera och konfigurera lösningen](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="9920e-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="9920e-184">Appbehörighet beviljas inte.</span><span class="sxs-lookup"><span data-stu-id="9920e-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="9920e-185">Gå till [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9920e-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="9920e-186">Välj **Miljöer**.</span><span class="sxs-lookup"><span data-stu-id="9920e-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="9920e-187">Markera ellipsknappen bredvid den miljö där du vill lägga till behörighet och markera **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="9920e-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="9920e-188">Expandera **användare + behörigheter** och välj **användare**.</span><span class="sxs-lookup"><span data-stu-id="9920e-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="9920e-189">Välj **+ ny** och välj **användare**.</span><span class="sxs-lookup"><span data-stu-id="9920e-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="9920e-190">Välj **programanvändare** om den inte redan är vald och ange följande information:</span><span class="sxs-lookup"><span data-stu-id="9920e-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="9920e-191">**Användarnamn:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9920e-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="9920e-192">**App-ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="9920e-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="9920e-193">**Förnamn:** Kund</span><span class="sxs-lookup"><span data-stu-id="9920e-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="9920e-194">**Efternamn** Insikter</span><span class="sxs-lookup"><span data-stu-id="9920e-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="9920e-195">**Primär e-post:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9920e-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="9920e-196">Välj **Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="9920e-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="9920e-197">Välj den användare du just skapade.</span><span class="sxs-lookup"><span data-stu-id="9920e-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="9920e-198">Välj **hantera roller** på den övre menyraden.</span><span class="sxs-lookup"><span data-stu-id="9920e-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="9920e-199">Välj **Systemadministratör** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9920e-199">Select **System Administrator**, then select **OK**.</span></span>
