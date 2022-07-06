---
title: Anpassade maskininlärningsmodeller | Microsoft Docs
description: Arbeta med anpassade modeller från Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: a44d1f2c00c90de3ed5a9425e3a197e109cb28e0
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800442"
---
# <a name="custom-machine-learning-models"></a>Anpassade maskininlärningsmodeller

> [!NOTE]
> Support för Machine Learning Studio (klassisk) upphör 31 augusti 2024. Vi rekommenderar att du övergår till [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) det datumet.
>
> Från och med den 1 december 2021 kommer du inte att kunna skapa nya resurser för Machine Learning Studio (klassisk). Till och med 31 augusti 2024 kan du fortsätta använda de befintliga Machine Learning Studio (klassiska) resurserna. Mer information finns i [Migrera till Azure Machine Learning](/azure/machine-learning/migrate-overview).


Med **Intelligens** > **Anpassade modeller** kan du hantera arbetsflöden baserat på Azure Machine Learning-modeller. Arbetsflöden hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kunddata. Mer information om hur du bygger anpassade ML-modeller finns i [Använda Azure Machine Learning-baserade modeller](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Ansvarsfull AI

Förutsägelser erbjuder funktioner för att skapa bättre kundupplevelser, förbättra affärsfunktioner och intäktsströmmar. Vi rekommenderar starkt att du balanserar värdet på din förutsägelse mot den inverkan den har och fördomar som kan införas på ett etiskt sätt. Läs mer om hur Microsoft hanterar [ansvarsfull AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan också lära dig om [tekniker och processer för ansvarsfull maskininlärning](/azure/machine-learning/concept-responsible-ml) som är specifik för Azure Machine Learning.

## <a name="prerequisites"></a>Förutsättningar

- Den här funktionen stöder webbtjänster som publicerats via [Azure Machine Learning batch-pipeline](/azure/machine-learning/concept-ml-pipelines).

- Du behöver ett Azure Data Lake Gen2-lagringskonto som är associerat med din Azure Studio-instans för att kunna använda den här funktionen. Mer information finns i [Skapa ett Azure Data Lake Storage Gen2 Storage-konto](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- För Azure Machine Learning-arbetsytor med pipelines behöver du administratörsbehörighet som ägare eller användare till Azure Machine Learning-arbetsytan.

   > [!NOTE]
   > Data överförs mellan dina Customer Insights-instanser och valda Azure-webbtjänster eller -pipelines i arbetsflödet. När du överför data till en Azure-tjänst måste du se till att tjänsten är konfigurerad för att bearbeta data på det sätt och den plats som krävs för att uppfylla alla juridiska eller nödvändiga krav för att hantera dessa data för din organisation.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Lägg till ett nytt arbetsflöde

1. Gå till **Intelligens** > **Anpassade modeller** och välj **Nytt arbetsflöde**.

1. Ge din anpassade modell ett lätt igenkännligt namn i fältet **Namn**.

   > [!div class="mx-imgBorder"]
   > ![Skärmbild av fönstret Nytt arbetsflöde.](media/new-workflowv2.png "Skärmbild av det nya fönstret för arbetsflöde")

1. Välj den organisation som innehåller webbtjänsten i **Klientorganisation som innehåller din webbtjänst**.

1. Om din Azure Machine Learning-prenumeration finns i en annan klientorganisation än Customer Insights väljer du **Logga in** med dina autentiseringsuppgifter för den valda organisationen.

1. Välj de **arbetsytor** som är kopplade till din webbtjänst. 

1. Välj Azure Machine Learning pipeline i listrutan **Webbtjänst som innehåller din modell**. Välj sedan **Nästa**.    
   Läs mer om att [publicera en pipeline i Azure Machine Learning med designern](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Din pipeline måste publiceras under en [pipelineslutpunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. För varje **Indata till webbtjänst**, välj matchande **Entitet** från Customer Insights och välj **Nästa**.
   > [!NOTE]
   > Arbetsflödet med en anpassad modell används för att mappa webbtjänstens indatafält till entitetsattributen utifrån fältets namn och datatyp. Ett felmeddelande visas om ett webbtjänstfält inte kan mappas till en entitet.

   > [!div class="mx-imgBorder"]
   > ![Konfigurera ett arbetsflöde.](media/intelligence-screen2-updated.png "Konfigurera ett arbetsflöde")

1. I steget **Parametrar för modellens utdata** anger du följande egenskaper:
      1. Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.
      1. Välj **Namn på parametern för utdata för datalager** på din batch-pipeline från listrutan.
      1. Välj **Namn på parametern för utdata för sökväg** på din batch-pipeline från listrutan.

      > [!div class="mx-imgBorder"]
      > ![Parameterfönster för modellens utdata.](media/intelligence-screen3-outputparameters.png "Fönster för parameter för modellens utdata")

1. Välj det matchande attributet i listrutan **Resultat för Kund-ID** som identifierar kunder och välj **Spara**.

   > [!div class="mx-imgBorder"]
   > ![Relatera resultat till fönstret Kunddata.](media/intelligence-screen4-relatetocustomer.png "Relatera resultat till fönstret Kunddata")

1. Skärmen **Arbetsflödet sparades** visas med information om arbetsflödet.    
   Om du har konfigurerat ett arbetsflöde för en Azure Machine Learning pipeline, kommer Customer Insights kopplas till arbetsytan som innehåller pipeline. Customer Insights får rollen **deltagare** på Azure-arbetsytan.

1. Välj **Utfört**.

1. Nu kan du köra arbetsflödet från sidan **Anpassade modeller**.

## <a name="edit-a-workflow"></a>Redigera arbetsflöde

1. På sidan **Anpassade modeller** markerar du den stående ellipsen (&vellip;) i kolumnen **Åtgärder** bredvid ett arbetsflöde som du tidigare skapat och väljer **Redigera**.

1. Du kan uppdatera arbetsflödets igenkännbara namn i fältet **Visningsnamn**, men du kan inte ändra den konfigurerade webbtjänsten eller pipelinen. Välj **Nästa**.

1. För varje **Indata till webbtjänst** kan du uppdatera matchande **Entitet** från Customer Insights. Välj sedan **Nästa**.

1. I steget **Parametrar för modellens utdata** anger du följande egenskaper:
      1. Ange utdata **Entitetens namn** som du vill att utdataresultat för pipelinen ska flöda in i.
      1. Välj **namnet på parametern för utdata till datalager** för din testpipeline.
      1. Välj **namnet på parametern för utdata till sökväg** för din testpipeline.

1. Välj det matchande attributet i listrutan **Resultat för Kund-ID** som identifierar kunder och välj **Spara**.
   Välj ett attribut från inferensutdata med värden som liknar kolumnen Kund-ID i kundentiteten. Om du inte har en sådan kolumn i din datauppsättning väljer du ett attribut som identifierar raden unikt.

## <a name="run-a-workflow"></a>Köra ett arbetsflöde

1. På sidan **Anpassade modeller** markerar du den stående ellipsen (&vellip;) i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.

1. Markera **Kör**.

Arbetsflödet körs också automatiskt tillsammans med alla schemalagda uppdateringar. Läs mer om [att konfigurera schemalagda uppdateringar](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Ta bort arbetsflödet

1. På sidan **Anpassade modeller** markerar du den stående ellipsen (&vellip;) i kolumnen **Åtgärder** bredvid ett arbetsflöde som du har skapat.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]