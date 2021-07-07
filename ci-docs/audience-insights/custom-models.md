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
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305681"
---
# <a name="custom-machine-learning-models"></a>Anpassade maskininlärningsmodeller

Med **Intelligens** > **Anpassade modeller** kan du hantera arbetsflöden baserat på Azure Machine Learning-modeller. Arbetsflöden hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kunddata. Mer information om hur du bygger anpassade ML-modeller finns i [Använda Azure Machine Learning-baserade modeller](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Ansvarsfull AI

Förutsägelser erbjuder funktioner för att skapa bättre kundupplevelser, förbättra affärsfunktioner och intäktsströmmar. Vi rekommenderar starkt att du balanserar värdet på din förutsägelse mot den inverkan den har och fördomar som kan införas på ett etiskt sätt. Läs mer om hur Microsoft hanterar [ansvarsfull AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan också lära dig om [tekniker och processer för ansvarsfull maskininlärning](/azure/machine-learning/concept-responsible-ml) som är specifik för Azure Machine Learning.

## <a name="prerequisites"></a>Förutsättningar

- För närvarande stöder den här funktionen webbtjänster som publicerats via [Machine Learning Studio (klassisk)](https://studio.azureml.net) och [Azure Machine Learning-batchpipelines](/azure/machine-learning/concept-ml-pipelines).

- Du behöver ett Azure Data Lake Gen2-lagringskonto som är associerat med din Azure Studio-instans för att kunna använda den här funktionen. Mer information finns i [Skapa ett Azure Data Lake Storage Gen2 Storage-konto](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- För Azure Machine Learning-arbetsytor med pipelines behöver du administratörsbehörighet som ägare eller användare till Azure Machine Learning-arbetsytan.

   > [!NOTE]
   > Data överförs mellan dina Customer Insights-instanser och valda Azure-webbtjänster eller -pipelines i arbetsflödet. När du överför data till en Azure-tjänst måste du se till att tjänsten är konfigurerad för att bearbeta data på det sätt och den plats som krävs för att uppfylla alla juridiska eller nödvändiga krav för att hantera dessa data för din organisation.

## <a name="add-a-new-workflow"></a>Lägg till ett nytt arbetsflöde

1. Gå till **Intelligens** > **Anpassade modeller** och välj **Nytt arbetsflöde**.

1. Ge din anpassade modell ett lätt igenkännligt namn i fältet **Namn**.

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av det nya fönstret för arbetsflöde](media/new-workflowv2.png "Skärmbild av det nya fönstret för arbetsflöde")

1. Välj den organisation som innehåller webbtjänsten i **Klientorganisation som innehåller din webbtjänst**.

1. Om din Azure Machine Learning-prenumeration finns i en annan klientorganisation än Customer Insights väljer du **Logga in** med dina autentiseringsuppgifter för den valda organisationen.

1. Välj de **arbetsytor** som är kopplade till din webbtjänst. Det finns två avsnitt som anges, ett för Azure Machine Learning v1 (Machine Learning Studio (klassisk)) och Azure Machine Learning v2 (Azure Machine Learning). Om du är osäker på vilken arbetsyta som är den rätta för din Machine Learning Studio-webbtjänst (klassisk) väljer du **Valfri**.

1. Välj den Machine Learning Studio-webbtjänst (klassisk) eller Azure Machine Learning-pipeline i listrutan **Webbtjänst som innehåller din modell**. Välj sedan **Nästa**.
   - Läs mer om att [publicera en webbtjänst i Machine Learning Studio (klassisk)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Läs mer om att [publicera en pipeline i Azure Machine Learning med designern](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Din pipeline måste publiceras under en [pipelineslutpunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. För varje **indata till webbtjänst** väljer du matchande **entitet** från målgruppsinsikter och väljer **Nästa**.
   > [!NOTE]
   > Arbetsflödet med en anpassad modell används för att mappa webbtjänstens indatafält till entitetsattributen utifrån fältets namn och datatyp. Ett felmeddelande visas om ett webbtjänstfält inte kan mappas till en entitet.

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

1. Välj det matchande attributet i listrutan **Resultat för Kund-ID** som identifierar kunder och välj **Spara**.

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

1. Välj det matchande attributet i listrutan **Resultat för Kund-ID** som identifierar kunder och välj **Spara**.
   Välj ett attribut från inferensutdata med värden som liknar kolumnen Kund-ID i kundentiteten. Om du inte har en sådan kolumn i din datauppsättning väljer du ett attribut som identifierar raden unikt.

## <a name="run-a-workflow"></a>Köra ett arbetsflöde

1. På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.

1. Markera **Kör**.

Arbetsflödet körs också automatiskt tillsammans med alla schemalagda uppdateringar. Läs mer om [att konfigurera schemalagda uppdateringar](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Ta bort arbetsflödet

1. På sidan **anpassade modeller** markerar du den vertikala ellipsen i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.

1. Välj **Ta bort** och bekräfta borttagningen.

Arbetsflödet tas bort. [Entiteten](entities.md) som skapades när du skapade arbetsflödet kvarstår och kan visas från sidan **Entiteter**.

## <a name="results"></a>Resultat

Resultat från ett arbetsflöde lagras i entiteten som konfigureras under fasen Modellutdataparameter. Du kan få åtkomst till dessa data från [entitetssidan](entities.md) eller med [API-åtkomst](apis.md).

### <a name="api-access"></a>API-åtkomst

Använd följande format om du vill hämta data från en anpassad modellentitet för den specifika OData-frågan:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Ersätt `<your instance id>` med ID för Customer Insights-miljön, som du hittar i adressfältet i webbläsaren när du öppnar Customer Insights.

1. Ersätt `<custom model output entity>` med entitetsnamnet du angav under steget Parametrar för modellens utdata i konfigurationen av en anpassad modell.

1. Ersätt `<guid value>` med kund-ID för den kund som du vill använda posten för. Vanligtvis hittar du detta ID på [sidan med kundprofiler](customer-profiles.md) i fältet Kund-ID.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

- Varför visas inte min pipeline när jag anger ett arbetsflöde för en anpassad modell?    
  Det här problemet beror ofta på ett konfigurationsproblem i pipelinen. Kontrollera att [indataparametern har konfigurerats](azure-machine-learning-experiments.md#dataset-configuration) och att [parametrarna för utdatalagring och sökväg](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) också har konfigurerats.

- Vad betyder felmeddelandet "Kunde inte spara ett intelligent arbetsflöde"?    
  Användarna ser vanligtvis det här felmeddelandet om de inte har administratörsprivilegier som ägare eller användare av arbetsytan. Användaren behöver en högre behörighetsnivå för att Customer Insights ska kunna bearbeta arbetsflödet som en tjänst i stället för att använda autentiseringsuppgifterna för efterföljande körningar av arbetsflödet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
