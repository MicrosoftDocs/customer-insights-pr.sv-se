---
title: Anpassade maskininlärningsmodeller | Microsoft Docs
description: Arbeta med anpassade modeller från Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700690"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="3def1-103">Anpassade maskininlärningsmodeller</span><span class="sxs-lookup"><span data-stu-id="3def1-103">Custom machine learning models</span></span>

<span data-ttu-id="3def1-104">Med **Intelligens** > **Anpassade modeller** kan du hantera arbetsflöden baserat på Azure Machine Learning-modeller.</span><span class="sxs-lookup"><span data-stu-id="3def1-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="3def1-105">Arbetsflöden hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kunddata.</span><span class="sxs-lookup"><span data-stu-id="3def1-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="3def1-106">Mer information om hur du bygger anpassade ML-modeller finns i [Använda Azure Machine Learning-baserade modeller](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="3def1-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="3def1-107">Ansvarsfull AI</span><span class="sxs-lookup"><span data-stu-id="3def1-107">Responsible AI</span></span>

<span data-ttu-id="3def1-108">Förutsägelser erbjuder funktioner för att skapa bättre kundupplevelser, förbättra affärsfunktioner och intäktsströmmar.</span><span class="sxs-lookup"><span data-stu-id="3def1-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="3def1-109">Vi rekommenderar starkt att du balanserar värdet på din förutsägelse mot den inverkan den har och fördomar som kan införas på ett etiskt sätt.</span><span class="sxs-lookup"><span data-stu-id="3def1-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="3def1-110">Läs mer om hur Microsoft hanterar [ansvarsfull AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="3def1-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="3def1-111">Du kan också lära dig om [tekniker och processer för ansvarsfull maskininlärning](/azure/machine-learning/concept-responsible-ml) som är specifik för Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="3def1-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3def1-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="3def1-112">Prerequisites</span></span>

- <span data-ttu-id="3def1-113">För närvarande stöder den här funktionen webbtjänster som publicerats via [Machine Learning Studio (klassisk)](https://studio.azureml.net) och [Azure Machine Learning-batchpipelines](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="3def1-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="3def1-114">Du behöver ett Azure Data Lake Gen2-lagringskonto som är associerat med din Azure Studio-instans för att kunna använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="3def1-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="3def1-115">Mer information finns i [Skapa ett Azure Data Lake Storage Gen2 Storage-konto](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="3def1-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="3def1-116">För Azure Machine Learning-arbetsytor med pipelines behöver du administratörsbehörighet som ägare eller användare till Azure Machine Learning-arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3def1-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3def1-117">Data överförs mellan dina Customer Insights-instanser och valda Azure-webbtjänster eller -pipelines i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="3def1-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="3def1-118">När du överför data till en Azure-tjänst måste du se till att tjänsten är konfigurerad för att bearbeta data på det sätt och den plats som krävs för att uppfylla alla juridiska eller nödvändiga krav för att hantera dessa data för din organisation.</span><span class="sxs-lookup"><span data-stu-id="3def1-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="3def1-119">Lägg till ett nytt arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="3def1-119">Add a new workflow</span></span>

1. <span data-ttu-id="3def1-120">Gå till **Intelligens** > **Anpassade modeller** och välj **Nytt arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="3def1-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="3def1-121">Ge din anpassade modell ett lätt igenkännligt namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="3def1-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3def1-122">![Skärmbild av det nya fönstret för arbetsflöde](media/new-workflowv2.png "Skärmbild av det nya fönstret för arbetsflöde")</span><span class="sxs-lookup"><span data-stu-id="3def1-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="3def1-123">Välj den organisation som innehåller webbtjänsten i **Klientorganisation som innehåller din webbtjänst**.</span><span class="sxs-lookup"><span data-stu-id="3def1-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="3def1-124">Om din Azure Machine Learning-prenumeration finns i en annan klientorganisation än Customer Insights väljer du **Logga in** med dina autentiseringsuppgifter för den valda organisationen.</span><span class="sxs-lookup"><span data-stu-id="3def1-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="3def1-125">Välj de **arbetsytor** som är kopplade till din webbtjänst.</span><span class="sxs-lookup"><span data-stu-id="3def1-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="3def1-126">Det finns två avsnitt som anges, ett för Azure Machine Learning v1 (Machine Learning Studio (klassisk)) och Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="3def1-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="3def1-127">Om du är osäker på vilken arbetsyta som är den rätta för din Machine Learning Studio-webbtjänst (klassisk) väljer du **Valfri**.</span><span class="sxs-lookup"><span data-stu-id="3def1-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="3def1-128">Välj den Machine Learning Studio-webbtjänst (klassisk) eller Azure Machine Learning-pipeline i listrutan **Webbtjänst som innehåller din modell**.</span><span class="sxs-lookup"><span data-stu-id="3def1-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="3def1-129">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3def1-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="3def1-130">Läs mer om att [publicera en webbtjänst i Machine Learning Studio (klassisk)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="3def1-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="3def1-131">Läs mer om att [publicera en pipeline i Azure Machine Learning med designern](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="3def1-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="3def1-132">Din pipeline måste publiceras under en [pipelineslutpunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="3def1-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="3def1-133">För varje **indata till webbtjänst** väljer du matchande **entitet** från målgruppsinsikter och väljer **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3def1-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3def1-134">Arbetsflödet med en anpassad modell används för att mappa webbtjänstens indatafält till entitetsattributen utifrån fältets namn och datatyp.</span><span class="sxs-lookup"><span data-stu-id="3def1-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="3def1-135">Ett felmeddelande visas om ett webbtjänstfält inte kan mappas till en entitet.</span><span class="sxs-lookup"><span data-stu-id="3def1-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3def1-136">![Konfigurera ett arbetsflöde](media/intelligence-screen2-updated.png "Konfigurera ett arbetsflöde")</span><span class="sxs-lookup"><span data-stu-id="3def1-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="3def1-137">I steget **Parametrar för modellens utdata** anger du följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="3def1-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="3def1-138">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="3def1-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="3def1-139">Ange utdata **Entitetens namn** som du vill att utdataresultat för webbtjänsten ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="3def1-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="3def1-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3def1-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="3def1-141">Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="3def1-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="3def1-142">Välj **Namn på parametern för utdata för datalager** på din batch-pipeline från listrutan.</span><span class="sxs-lookup"><span data-stu-id="3def1-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="3def1-143">Välj **Namn på parametern för utdata för sökväg** på din batch-pipeline från listrutan.</span><span class="sxs-lookup"><span data-stu-id="3def1-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="3def1-144">![Fönster för parameter för modellens utdata](media/intelligence-screen3-outputparameters.png "Fönster för parameter för modellens utdata")</span><span class="sxs-lookup"><span data-stu-id="3def1-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="3def1-145">Välj det matchande attributet från listrutan **Kund-ID i resultat** som identifierar kunder och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3def1-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3def1-146">![Relatera resultat till fönstret Kunddata](media/intelligence-screen4-relatetocustomer.png "Relatera resultat till fönstret Kunddata")</span><span class="sxs-lookup"><span data-stu-id="3def1-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="3def1-147">Skärmen **Arbetsflödet sparades** visas med information om arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="3def1-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="3def1-148">Om du har konfigurerat ett arbetsflöde för en Azure Machine Learning-pipeline, kopplats målgruppsinsikter till arbetsytan som innehåller pipelinen.</span><span class="sxs-lookup"><span data-stu-id="3def1-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="3def1-149">Målgruppsinsikter kommer att få rollen **Deltagare** arbetsytan i Azure.</span><span class="sxs-lookup"><span data-stu-id="3def1-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="3def1-150">Välj **Utfört**.</span><span class="sxs-lookup"><span data-stu-id="3def1-150">Select **Done**.</span></span>

1. <span data-ttu-id="3def1-151">Nu kan du köra arbetsflödet från sidan **Anpassade modeller**.</span><span class="sxs-lookup"><span data-stu-id="3def1-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="3def1-152">Redigera arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="3def1-152">Edit a workflow</span></span>

1. <span data-ttu-id="3def1-153">På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat och väljer **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3def1-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="3def1-154">Du kan uppdatera arbetsflödets igenkännbara namn i fältet **Visningsnamn**, men du kan inte ändra den konfigurerade webbtjänsten eller pipelinen.</span><span class="sxs-lookup"><span data-stu-id="3def1-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="3def1-155">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3def1-155">Select **Next**.</span></span>

1. <span data-ttu-id="3def1-156">För varje **indata till webbtjänst** kan du uppdatera matchande **entitet** från målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="3def1-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="3def1-157">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3def1-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="3def1-158">I steget **Parametrar för modellens utdata** anger du följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="3def1-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="3def1-159">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="3def1-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="3def1-160">Ange utdata **Entitetens namn** som du vill att utdataresultat för webbtjänsten ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="3def1-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="3def1-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3def1-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="3def1-162">Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.</span><span class="sxs-lookup"><span data-stu-id="3def1-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="3def1-163">Välj **namnet på parametern för utdata till datalager** för din testpipeline.</span><span class="sxs-lookup"><span data-stu-id="3def1-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="3def1-164">Välj **namnet på parametern för utdata till sökväg** för din testpipeline.</span><span class="sxs-lookup"><span data-stu-id="3def1-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="3def1-165">Välj det matchande attributet från listrutan **Kund-ID i resultat** som identifierar kunder och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3def1-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="3def1-166">Välj ett attribut från inferensutdata med värden som liknar kolumnen Kund-ID i kundentiteten.</span><span class="sxs-lookup"><span data-stu-id="3def1-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="3def1-167">Om du inte har en sådan kolumn i din datauppsättning väljer du ett attribut som identifierar raden unikt.</span><span class="sxs-lookup"><span data-stu-id="3def1-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="3def1-168">Köra ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="3def1-168">Run a workflow</span></span>

1. <span data-ttu-id="3def1-169">På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="3def1-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="3def1-170">Markera **Kör**.</span><span class="sxs-lookup"><span data-stu-id="3def1-170">Select **Run**.</span></span>

<span data-ttu-id="3def1-171">Arbetsflödet körs också automatiskt tillsammans med alla schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="3def1-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="3def1-172">Läs mer om [att konfigurera schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3def1-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="3def1-173">Ta bort arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="3def1-173">Delete a workflow</span></span>

1. <span data-ttu-id="3def1-174">På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="3def1-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="3def1-175">Välj **Ta bort** och bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="3def1-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="3def1-176">Arbetsflödet tas bort.</span><span class="sxs-lookup"><span data-stu-id="3def1-176">Your workflow will be deleted.</span></span> <span data-ttu-id="3def1-177">[Entiteten](entities.md) som skapades när du skapade arbetsflödet kvarstår och kan visas från sidan **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="3def1-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="3def1-178">Resultat</span><span class="sxs-lookup"><span data-stu-id="3def1-178">Results</span></span>

<span data-ttu-id="3def1-179">Resultat från ett arbetsflöde lagras i entiteten som konfigureras under fasen Modellutdataparameter.</span><span class="sxs-lookup"><span data-stu-id="3def1-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="3def1-180">Du kan få åtkomst till dessa data från [entitetssidan](entities.md) eller med [API-åtkomst](apis.md).</span><span class="sxs-lookup"><span data-stu-id="3def1-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="3def1-181">API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="3def1-181">API Access</span></span>

<span data-ttu-id="3def1-182">Använd följande format om du vill hämta data från en anpassad modellentitet för den specifika OData-frågan:</span><span class="sxs-lookup"><span data-stu-id="3def1-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="3def1-183">Ersätt `<your instance id>` med ID för Customer Insights-miljön, som du hittar i adressfältet i webbläsaren när du öppnar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3def1-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="3def1-184">Ersätt `<custom model output entity>` med entitetsnamnet du angav under steget Parametrar för modellens utdata i konfigurationen av en anpassad modell.</span><span class="sxs-lookup"><span data-stu-id="3def1-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="3def1-185">Ersätt `<guid value>` med kund-ID för den kund som du vill använda posten för.</span><span class="sxs-lookup"><span data-stu-id="3def1-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="3def1-186">Vanligtvis hittar du detta ID på [sidan med kundprofiler](customer-profiles.md) i fältet Kund-ID.</span><span class="sxs-lookup"><span data-stu-id="3def1-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3def1-187">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="3def1-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="3def1-188">Varför visas inte min pipeline när jag anger ett arbetsflöde för en anpassad modell?</span><span class="sxs-lookup"><span data-stu-id="3def1-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="3def1-189">Det här problemet beror ofta på ett konfigurationsproblem i pipelinen.</span><span class="sxs-lookup"><span data-stu-id="3def1-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="3def1-190">Kontrollera att [indataparametern har konfigurerats](azure-machine-learning-experiments.md#dataset-configuration) och att [parametrarna för utdatalagring och sökväg](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) också har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="3def1-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="3def1-191">Vad betyder felmeddelandet "Kunde inte spara ett intelligent arbetsflöde"?</span><span class="sxs-lookup"><span data-stu-id="3def1-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="3def1-192">Användarna ser vanligtvis det här felmeddelandet om de inte har administratörsprivilegier som ägare eller användare av arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3def1-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="3def1-193">Användaren behöver en högre behörighetsnivå för att Customer Insights ska kunna bearbeta arbetsflödet som en tjänst i stället för att använda autentiseringsuppgifterna för efterföljande körningar av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="3def1-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
