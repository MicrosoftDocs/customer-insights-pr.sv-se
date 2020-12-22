---
title: Anpassade maskininlärningsmodeller | Microsoft Docs
description: Arbeta med anpassade modeller från Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668925"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="8c967-103">Anpassade maskininlärningsmodeller</span><span class="sxs-lookup"><span data-stu-id="8c967-103">Custom machine learning models</span></span>

<span data-ttu-id="8c967-104">Med **Intelligens** > **Anpassade modeller** kan du hantera arbetsflöden baserat på Azure Machine Learning-modeller.</span><span class="sxs-lookup"><span data-stu-id="8c967-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="8c967-105">Arbetsflöden hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kunddata.</span><span class="sxs-lookup"><span data-stu-id="8c967-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="8c967-106">Mer information om hur du bygger anpassade ML-modeller finns i [Använda Azure Machine Learning-baserade modeller](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="8c967-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="8c967-107">Ansvarsfull AI</span><span class="sxs-lookup"><span data-stu-id="8c967-107">Responsible AI</span></span>

<span data-ttu-id="8c967-108">Förutsägelser erbjuder funktioner för att skapa bättre kundupplevelser, förbättra affärsfunktioner och intäktsströmmar.</span><span class="sxs-lookup"><span data-stu-id="8c967-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="8c967-109">Vi rekommenderar starkt att du balanserar värdet på din förutsägelse mot den inverkan den har och fördomar som kan införas på ett etiskt sätt.</span><span class="sxs-lookup"><span data-stu-id="8c967-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="8c967-110">Läs mer om hur Microsoft hanterar [ansvarsfull AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="8c967-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="8c967-111">Du kan också lära dig om [tekniker och processer för ansvarsfull maskininlärning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) som är specifik för Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="8c967-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c967-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="8c967-112">Prerequisites</span></span>

- <span data-ttu-id="8c967-113">För närvarande stöder den här funktionen webbtjänster som publicerats via [Machine Learning Studio (klassisk)](https://studio.azureml.net) och [Azure Machine Learning-batchpipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="8c967-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="8c967-114">Du behöver ett Azure Data Lake Gen2-lagringskonto som är associerat med din Azure Studio-instans för att kunna använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="8c967-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="8c967-115">Mer information finns i [skapa ett Azure Data Lake Storage Gen2 Storage-konto](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="8c967-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="8c967-116">Lägg till ett nytt arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="8c967-116">Add a new workflow</span></span>

1. <span data-ttu-id="8c967-117">Gå till **Intelligens** > **Anpassade modeller** och välj **Nytt arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="8c967-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="8c967-118">Ge din anpassade modell ett lätt igenkännligt namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="8c967-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c967-119">![Skärmbild av det nya fönstret för arbetsflöde](media/new-workflowv2.png "Skärmbild av det nya fönstret för arbetsflöde")</span><span class="sxs-lookup"><span data-stu-id="8c967-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="8c967-120">Välj den organisation som innehåller webbtjänsten i **Klientorganisation som innehåller din webbtjänst**.</span><span class="sxs-lookup"><span data-stu-id="8c967-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="8c967-121">Om din Azure Machine Learning-prenumeration finns i en annan klientorganisation än Customer Insights väljer du **Logga in** med dina autentiseringsuppgifter för den valda organisationen.</span><span class="sxs-lookup"><span data-stu-id="8c967-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="8c967-122">Välj de **arbetsytor** som är kopplade till din webbtjänst.</span><span class="sxs-lookup"><span data-stu-id="8c967-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="8c967-123">Det finns två avsnitt som anges, ett för Azure Machine Learning v1 (Machine Learning Studio (klassisk)) och Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="8c967-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="8c967-124">Om du är osäker på vilken arbetsyta som är den rätta för din Machine Learning Studio-webbtjänst (klassisk) väljer du **Valfri**.</span><span class="sxs-lookup"><span data-stu-id="8c967-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="8c967-125">Välj den Machine Learning Studio-webbtjänst (klassisk) eller Azure Machine Learning-pipeline i listrutan **Webbtjänst som innehåller din modell**.</span><span class="sxs-lookup"><span data-stu-id="8c967-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="8c967-126">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8c967-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="8c967-127">Läs mer om att [publicera en webbtjänst i Machine Learning Studio (klassisk)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="8c967-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="8c967-128">Läs mer om att [publicera en pipeline i Azure Machine Learning med designern](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="8c967-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="8c967-129">Din pipeline måste publiceras under en [pipelineslutpunkt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="8c967-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="8c967-130">För varje **indata till webbtjänst** väljer du matchande **entitet** från målgruppsinsikter och väljer **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8c967-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c967-131">![Konfigurera ett arbetsflöde](media/intelligence-screen2-updated.png "Konfigurera ett arbetsflöde")</span><span class="sxs-lookup"><span data-stu-id="8c967-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="8c967-132">I steget **Parametrar för modellens utdata** anger du följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="8c967-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="8c967-133">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="8c967-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="8c967-134">Ange utdata **Entitetens namn** som du vill att utdataresultat för webbtjänsten ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="8c967-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="8c967-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8c967-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="8c967-136">Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="8c967-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="8c967-137">Välj **Namn på parametern för utdata för datalager** på din batch-pipeline från listrutan.</span><span class="sxs-lookup"><span data-stu-id="8c967-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="8c967-138">Välj **Namn på parametern för utdata för sökväg** på din batch-pipeline från listrutan.</span><span class="sxs-lookup"><span data-stu-id="8c967-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="8c967-139">![Fönster för parameter för modellens utdata](media/intelligence-screen3-outputparameters.png "Fönster för parameter för modellens utdata")</span><span class="sxs-lookup"><span data-stu-id="8c967-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="8c967-140">Välj det matchande attributet från listrutan **Kund-ID i resultat** som identifierar kunder och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c967-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c967-141">![Relatera resultat till fönstret Kunddata](media/intelligence-screen4-relatetocustomer.png "Relatera resultat till fönstret Kunddata")</span><span class="sxs-lookup"><span data-stu-id="8c967-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="8c967-142">Skärmen **Arbetsflödet sparades** visas med information om arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8c967-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="8c967-143">Om du har konfigurerat ett arbetsflöde för en Azure Machine Learning-pipeline, kopplats målgruppsinsikter till arbetsytan som innehåller pipelinen.</span><span class="sxs-lookup"><span data-stu-id="8c967-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="8c967-144">Målgruppsinsikter kommer att få rollen **Deltagare** arbetsytan i Azure.</span><span class="sxs-lookup"><span data-stu-id="8c967-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="8c967-145">Välj **Utfört**.</span><span class="sxs-lookup"><span data-stu-id="8c967-145">Select **Done**.</span></span>

1. <span data-ttu-id="8c967-146">Nu kan du köra arbetsflödet från sidan **Anpassade modeller**.</span><span class="sxs-lookup"><span data-stu-id="8c967-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="8c967-147">Redigera arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="8c967-147">Edit a workflow</span></span>

1. <span data-ttu-id="8c967-148">På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat och väljer **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8c967-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="8c967-149">Du kan uppdatera arbetsflödets igenkännbara namn i fältet **Visningsnamn**, men du kan inte ändra den konfigurerade webbtjänsten eller pipelinen.</span><span class="sxs-lookup"><span data-stu-id="8c967-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="8c967-150">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8c967-150">Select **Next**.</span></span>

1. <span data-ttu-id="8c967-151">För varje **indata till webbtjänst** kan du uppdatera matchande **entitet** från målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="8c967-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="8c967-152">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8c967-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="8c967-153">I steget **Parametrar för modellens utdata** anger du följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="8c967-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="8c967-154">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="8c967-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="8c967-155">Ange utdata **Entitetens namn** som du vill att utdataresultat för webbtjänsten ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="8c967-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="8c967-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="8c967-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="8c967-157">Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="8c967-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="8c967-158">Välj **namnet på parametern för utdata till datalager** för din testpipeline.</span><span class="sxs-lookup"><span data-stu-id="8c967-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="8c967-159">Välj **namnet på parametern för utdata till sökväg** för din testpipeline.</span><span class="sxs-lookup"><span data-stu-id="8c967-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="8c967-160">Välj det matchande attributet från listrutan **Kund-ID i resultat** som identifierar kunder och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c967-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="8c967-161">Du behöver välja ett attribut från inferensutdata med värden som liknar kolumnen Kund-ID i kundentiteten.</span><span class="sxs-lookup"><span data-stu-id="8c967-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="8c967-162">Om du inte har en sådan kolumn i din datauppsättning väljer du ett attribut som identifierar raden unikt.</span><span class="sxs-lookup"><span data-stu-id="8c967-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="8c967-163">Köra ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="8c967-163">Run a workflow</span></span>

1. <span data-ttu-id="8c967-164">På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="8c967-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="8c967-165">Markera **Kör**.</span><span class="sxs-lookup"><span data-stu-id="8c967-165">Select **Run**.</span></span>

<span data-ttu-id="8c967-166">Arbetsflödet körs också automatiskt tillsammans med alla schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8c967-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="8c967-167">Läs mer om [att konfigurera schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8c967-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="8c967-168">Ta bort arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="8c967-168">Delete a workflow</span></span>

1. <span data-ttu-id="8c967-169">På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="8c967-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="8c967-170">Välj **Ta bort** och bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="8c967-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="8c967-171">Arbetsflödet tas bort.</span><span class="sxs-lookup"><span data-stu-id="8c967-171">Your workflow will be deleted.</span></span> <span data-ttu-id="8c967-172">[Entiteten](entities.md) som skapades när du skapade arbetsflödet kvarstår och kan visas från sidan **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="8c967-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
