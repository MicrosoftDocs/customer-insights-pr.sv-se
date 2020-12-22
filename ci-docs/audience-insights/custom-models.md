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
# <a name="custom-machine-learning-models"></a>Anpassade maskininlärningsmodeller

Med **Intelligens** > **Anpassade modeller** kan du hantera arbetsflöden baserat på Azure Machine Learning-modeller. Arbetsflöden hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kunddata. Mer information om hur du bygger anpassade ML-modeller finns i [Använda Azure Machine Learning-baserade modeller](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Ansvarsfull AI

Förutsägelser erbjuder funktioner för att skapa bättre kundupplevelser, förbättra affärsfunktioner och intäktsströmmar. Vi rekommenderar starkt att du balanserar värdet på din förutsägelse mot den inverkan den har och fördomar som kan införas på ett etiskt sätt. Läs mer om hur Microsoft hanterar [ansvarsfull AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan också lära dig om [tekniker och processer för ansvarsfull maskininlärning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) som är specifik för Azure Machine Learning.

## <a name="prerequisites"></a>Förutsättningar

- För närvarande stöder den här funktionen webbtjänster som publicerats via [Machine Learning Studio (klassisk)](https://studio.azureml.net) och [Azure Machine Learning-batchpipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Du behöver ett Azure Data Lake Gen2-lagringskonto som är associerat med din Azure Studio-instans för att kunna använda den här funktionen. Mer information finns i [skapa ett Azure Data Lake Storage Gen2 Storage-konto](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Lägg till ett nytt arbetsflöde

1. Gå till **Intelligens** > **Anpassade modeller** och välj **Nytt arbetsflöde**.

1. Ge din anpassade modell ett lätt igenkännligt namn i fältet **Namn**.

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av det nya fönstret för arbetsflöde](media/new-workflowv2.png "Skärmbild av det nya fönstret för arbetsflöde")

1. Välj den organisation som innehåller webbtjänsten i **Klientorganisation som innehåller din webbtjänst**.

1. Om din Azure Machine Learning-prenumeration finns i en annan klientorganisation än Customer Insights väljer du **Logga in** med dina autentiseringsuppgifter för den valda organisationen.

1. Välj de **arbetsytor** som är kopplade till din webbtjänst. Det finns två avsnitt som anges, ett för Azure Machine Learning v1 (Machine Learning Studio (klassisk)) och Azure Machine Learning v2 (Azure Machine Learning). Om du är osäker på vilken arbetsyta som är den rätta för din Machine Learning Studio-webbtjänst (klassisk) väljer du **Valfri**.

1. Välj den Machine Learning Studio-webbtjänst (klassisk) eller Azure Machine Learning-pipeline i listrutan **Webbtjänst som innehåller din modell**. Välj sedan **Nästa**.
   - Läs mer om att [publicera en webbtjänst i Machine Learning Studio (klassisk)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Läs mer om att [publicera en pipeline i Azure Machine Learning med designern](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Din pipeline måste publiceras under en [pipelineslutpunkt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. För varje **indata till webbtjänst** väljer du matchande **entitet** från målgruppsinsikter och väljer **Nästa**.

   > [!div class="mx-imgBorder"]
   > ![Konfigurera ett arbetsflöde](media/intelligence-screen2-updated.png "Konfigurera ett arbetsflöde")

1. I steget **Parametrar för modellens utdata** anger du följande egenskaper:
   - Machine Learning Studio (klassisk)
      1. Ange utdata **Entitetens namn** som du vill att utdataresultat för webbtjänsten ska flöda in i.
   - Azure Machine Learning
      1. Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.
      1. Välj **Namn på parametern för utdata för datalager** på din batch-pipeline från listrutan.
      1. Välj **Namn på parametern för utdata för sökväg** på din batch-pipeline från listrutan.
      
      > [!div class="mx-imgBorder"]
      > ![Fönster för parameter för modellens utdata](media/intelligence-screen3-outputparameters.png "Fönster för parameter för modellens utdata")

1. Välj det matchande attributet från listrutan **Kund-ID i resultat** som identifierar kunder och välj **Spara**.
   
   > [!div class="mx-imgBorder"]
   > ![Relatera resultat till fönstret Kunddata](media/intelligence-screen4-relatetocustomer.png "Relatera resultat till fönstret Kunddata")

1. Skärmen **Arbetsflödet sparades** visas med information om arbetsflödet.    
   Om du har konfigurerat ett arbetsflöde för en Azure Machine Learning-pipeline, kopplats målgruppsinsikter till arbetsytan som innehåller pipelinen. Målgruppsinsikter kommer att få rollen **Deltagare** arbetsytan i Azure.

1. Välj **Utfört**.

1. Nu kan du köra arbetsflödet från sidan **Anpassade modeller**.

## <a name="edit-a-workflow"></a>Redigera arbetsflöde

1. På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat och väljer **Redigera**.

1. Du kan uppdatera arbetsflödets igenkännbara namn i fältet **Visningsnamn**, men du kan inte ändra den konfigurerade webbtjänsten eller pipelinen. Välj **Nästa**.

1. För varje **indata till webbtjänst** kan du uppdatera matchande **entitet** från målgruppsinsikter. Välj sedan **Nästa**.

1. I steget **Parametrar för modellens utdata** anger du följande egenskaper:
   - Machine Learning Studio (klassisk)
      1. Ange utdata **Entitetens namn** som du vill att utdataresultat för webbtjänsten ska flöda in i.
   - Azure Machine Learning
      1. Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.
      1. Välj **namnet på parametern för utdata till datalager** för din testpipeline.
      1. Välj **namnet på parametern för utdata till sökväg** för din testpipeline.

1. Välj det matchande attributet från listrutan **Kund-ID i resultat** som identifierar kunder och välj **Spara**.
   Du behöver välja ett attribut från inferensutdata med värden som liknar kolumnen Kund-ID i kundentiteten. Om du inte har en sådan kolumn i din datauppsättning väljer du ett attribut som identifierar raden unikt.

## <a name="run-a-workflow"></a>Köra ett arbetsflöde

1. På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.

1. Markera **Kör**.

Arbetsflödet körs också automatiskt tillsammans med alla schemalagda uppdateringar. Läs mer om [att konfigurera schemalagda uppdateringar](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Ta bort arbetsflödet

1. På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.

1. Välj **Ta bort** och bekräfta borttagningen.

Arbetsflödet tas bort. [Entiteten](entities.md) som skapades när du skapade arbetsflödet kvarstår och kan visas från sidan **Entiteter**.
