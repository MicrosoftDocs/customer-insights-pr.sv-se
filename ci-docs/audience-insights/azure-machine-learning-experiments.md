---
title: Azure Machine Learning-experiment
description: Använd Azure Machine Learning-baserade modeller i Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597441"
---
# <a name="use-azure-machine-learning-based-models"></a>Använd Azure Machine Learning-baserade modeller

Enhetliga data i Dynamics 365 Customer Insights är en källa för maskininlärningsmodeller som kan generera ytterligare affärsinsikter. Customer Insights integreras med Machine Learning Studio (klassisk) och Azure Machine Learning för att använda dina egna anpassade modeller. Se [Machine Learning Studio-experiment (klassisk)](machine-learning-studio-experiments.md) för exempel på experiment som byggts på Machine Learning Studio (klassisk). 

## <a name="prerequisites"></a>Förutsättningar

- Åtkomst till Customer Insights
- Aktiv prenumeration på Azure Enterprise
- [Enhetliga kundprofiler](data-unification.md)
- [Entitetsexport till Azure Blob Storage](export-azure-blob-storage.md) konfigurerad

## <a name="set-up-azure-machine-learning-workspace"></a>Konfigurera arbetsytan Azure Machine Learning

1. Se [skapa en Azure Machine Learning-arbetsyta](/azure/machine-learning/concept-workspace#-create-a-workspace) för olika alternativ för att skapa arbetsytan. För bästa prestanda skapar du arbetsytan i en Azure-region som är geografiskt närmast din Customer Insights-miljö.

1. Få åtkomst till din arbetsyta via [Azure Machine Learning Studio](https://ml.azure.com/). Du kan [interagera med arbetsytan](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) på flera olika sätt.

## <a name="work-with-azure-machine-learning-designer"></a>Arbeta med Azure Machine Learning-designer

Azure Machine Learning-designern tillhandahåller en visuell arbetsyta där du kan dra och släppa datauppsättningar och moduler, liknande Machine Learning Studio (klassisk). En batch-pipeline som skapats från designern kan integreras i Customer Insights om de konfigureras i enlighet med detta. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Arbeta med Azure Machine Learning SDK

Dataforskare och AI-utvecklare använder [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) för att bygga maskininlärningsarbetsflöden. För närvarande kan modeller som utbildats med hjälp av SDK inte integreras direkt med Customer Insights. En batchinferenspipeline som förbrukar den modellen krävs för integration med Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Krav på batch-pipeline för att integrera med Customer Insights

### <a name="dataset-configuration"></a>Konfiguration av datauppsättning

Du behöver skapa datauppsättningar för att använda entitetsdata från Customer Insights till din batchinferenspipeline. Dessa datauppsättningar behöver registreras på arbetsytan. För närvarande stöder vi bara [tabelldatauppsättningar](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) i .csv-format. Datauppsättningarna som motsvarar entitetsdata behöver parameteriseras som en pipeline-parameter.
   
* Datauppsättningsparametrar i Designer
   
     I designern öppnar du **Välj kolumner i datauppsättning** och välj **Ställ in som pipeline-parameter** där du anger ett namn på parametern.

     > [!div class="mx-imgBorder"]
     > ![Parameterisering av datauppsättning i Designer](media/intelligence-designer-dataset-parameters.png "Parameterisering av datauppsättning i Designer")
   
* Datauppsättningsparameter i SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Batchinferenspipeline
  
* I designern kan en utbildningspipeline användas för att skapa eller uppdatera en inferenspipeline. För närvarande stöds endast batchinferenspipelines.

* Med hjälp av SDK kan du publicera pipelinen till en slutpunkt. För närvarande integreras Customer Insights med standardpipelinen i en batchpipelines slutpunkt i Machine Learning-arbetsytan.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importera pipelinedata till Customer Insights

* Designern tillhandahåller [modulen Exportera data](/azure/machine-learning/algorithm-module-reference/export-data) som gör att utdata från en pipeline kan exporteras till Azure Storage. För närvarande måste modulen använda datalagringstypen **Azure Blob Storage** and parameterisera **Datalagring** och relativ **Sökväg**. Customer Insights åsidosätter båda dessa parametrar under pipelinekörning med en datalagring och sökväg som är åtkomlig för produkten.
   > [!div class="mx-imgBorder"]
   > ![Exportera datamodulskonfiguration](media/intelligence-designer-importdata.png "Exportera datamodulskonfiguration")
   
* När du skriver inferensutdata med hjälp av kod kan du ladda upp utdata till en sökväg inom en *registrerad datalagring* på arbetsytan. Om sökvägen och datalagringen är parameteriserade i pipelinen, kommer Customer insights att kunna läsa och importera inferensutdata. För närvarande stöds en enda tabellutdata i CSV-format. Sökvägen måste innehålla katalogen och filnamnet.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]