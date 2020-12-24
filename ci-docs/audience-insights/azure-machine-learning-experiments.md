---
title: Azure Machine Learning-experiment
description: Använd Azure Machine Learning-baserade modeller i Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668799"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="41e65-103">Använd Azure Machine Learning-baserade modeller</span><span class="sxs-lookup"><span data-stu-id="41e65-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="41e65-104">Enhetliga data i Dynamics 365 Customer Insights är en källa för maskininlärningsmodeller som kan generera ytterligare affärsinsikter.</span><span class="sxs-lookup"><span data-stu-id="41e65-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="41e65-105">Customer Insights integreras med Machine Learning Studio (klassisk) och Azure Machine Learning för att använda dina egna anpassade modeller.</span><span class="sxs-lookup"><span data-stu-id="41e65-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="41e65-106">Se [Machine Learning Studio-experiment (klassisk)](machine-learning-studio-experiments.md) för exempel på experiment som byggts på Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="41e65-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="41e65-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="41e65-107">Prerequisites</span></span>

- <span data-ttu-id="41e65-108">Åtkomst till Customer Insights</span><span class="sxs-lookup"><span data-stu-id="41e65-108">Access to Customer Insights</span></span>
- <span data-ttu-id="41e65-109">Aktiv prenumeration på Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="41e65-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="41e65-110">Enhetliga kundprofiler</span><span class="sxs-lookup"><span data-stu-id="41e65-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="41e65-111">[Entitetsexport till Azure Blob Storage](export-azure-blob-storage.md) konfigurerad</span><span class="sxs-lookup"><span data-stu-id="41e65-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="41e65-112">Konfigurera arbetsytan Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="41e65-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="41e65-113">Se [skapa en Azure Machine Learning-arbetsyta](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) för olika alternativ för att skapa arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="41e65-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="41e65-114">För bästa prestanda skapar du arbetsytan i en Azure-region som är geografiskt närmast din Customer Insights-miljö.</span><span class="sxs-lookup"><span data-stu-id="41e65-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="41e65-115">Få åtkomst till din arbetsyta via [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="41e65-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="41e65-116">Du kan [interagera med arbetsytan](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="41e65-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="41e65-117">Arbeta med Azure Machine Learning-designer</span><span class="sxs-lookup"><span data-stu-id="41e65-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="41e65-118">Azure Machine Learning-designern tillhandahåller en visuell arbetsyta där du kan dra och släppa datauppsättningar och moduler, liknande Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="41e65-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="41e65-119">En batch-pipeline som skapats från designern kan integreras i Customer Insights om de konfigureras i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="41e65-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="41e65-120">Arbeta med Azure Machine Learning SDK</span><span class="sxs-lookup"><span data-stu-id="41e65-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="41e65-121">Dataforskare och AI-utvecklare använder [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) för att bygga maskininlärningsarbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="41e65-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="41e65-122">För närvarande kan modeller som utbildats med hjälp av SDK inte integreras direkt med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="41e65-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="41e65-123">En batchinferenspipeline som förbrukar den modellen krävs för integration med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="41e65-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="41e65-124">Krav på batch-pipeline för att integrera med Customer Insights</span><span class="sxs-lookup"><span data-stu-id="41e65-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="41e65-125">Konfiguration av datauppsättning</span><span class="sxs-lookup"><span data-stu-id="41e65-125">Dataset Configuration</span></span>

<span data-ttu-id="41e65-126">Du behöver skapa datauppsättningar för att använda entitetsdata från Customer Insights till din batchinferenspipeline.</span><span class="sxs-lookup"><span data-stu-id="41e65-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="41e65-127">Dessa datauppsättningar behöver registreras på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="41e65-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="41e65-128">För närvarande stöder vi bara [tabelldatauppsättningar](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) i .csv-format.</span><span class="sxs-lookup"><span data-stu-id="41e65-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="41e65-129">Datauppsättningarna som motsvarar entitetsdata behöver parameteriseras som en pipeline-parameter.</span><span class="sxs-lookup"><span data-stu-id="41e65-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="41e65-130">Datauppsättningsparametrar i Designer</span><span class="sxs-lookup"><span data-stu-id="41e65-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="41e65-131">I designern öppnar du **Välj kolumner i datauppsättning** och välj **Ställ in som pipeline-parameter** där du anger ett namn på parametern.</span><span class="sxs-lookup"><span data-stu-id="41e65-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="41e65-132">![Parameterisering av datauppsättning i Designer](media/intelligence-designer-dataset-parameters.png "Parameterisering av datauppsättning i Designer")</span><span class="sxs-lookup"><span data-stu-id="41e65-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="41e65-133">Datauppsättningsparameter i SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="41e65-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="41e65-134">Batchinferenspipeline</span><span class="sxs-lookup"><span data-stu-id="41e65-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="41e65-135">I designern kan en utbildningspipeline användas för att skapa eller uppdatera en inferenspipeline.</span><span class="sxs-lookup"><span data-stu-id="41e65-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="41e65-136">För närvarande stöds endast batchinferenspipelines.</span><span class="sxs-lookup"><span data-stu-id="41e65-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="41e65-137">Med hjälp av SDK kan du publicera pipelinen till en slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="41e65-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="41e65-138">För närvarande integreras Customer Insights med standardpipelinen i en batchpipelines slutpunkt i Machine Learning-arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="41e65-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="41e65-139">Importera pipelinedata till Customer Insights</span><span class="sxs-lookup"><span data-stu-id="41e65-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="41e65-140">Designern tillhandahåller [modulen Exportera data](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) som gör att utdata från en pipeline kan exporteras till Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="41e65-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="41e65-141">För närvarande måste modulen använda datalagringstypen **Azure Blob Storage** and parameterisera **Datalagring** och relativ **Sökväg**.</span><span class="sxs-lookup"><span data-stu-id="41e65-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="41e65-142">Customer Insights åsidosätter båda dessa parametrar under pipelinekörning med en datalagring och sökväg som är åtkomlig för produkten.</span><span class="sxs-lookup"><span data-stu-id="41e65-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41e65-143">![Exportera datamodulskonfiguration](media/intelligence-designer-importdata.png "Exportera datamodulskonfiguration")</span><span class="sxs-lookup"><span data-stu-id="41e65-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="41e65-144">När du skriver inferensutdata med hjälp av kod kan du ladda upp utdata till en sökväg inom en *registrerad datalagring* på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="41e65-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="41e65-145">Om sökvägen och datalagringen är parameteriserade i pipelinen, kommer Customer insights att kunna läsa och importera inferensutdata.</span><span class="sxs-lookup"><span data-stu-id="41e65-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="41e65-146">För närvarande stöds en enda tabellutdata i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="41e65-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="41e65-147">Sökvägen måste innehålla katalogen och filnamnet.</span><span class="sxs-lookup"><span data-stu-id="41e65-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```