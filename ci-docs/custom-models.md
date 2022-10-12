---
title: Anpassade maskininlärningsmodeller | Microsoft Docs
description: Arbeta med anpassade modeller från Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609768"
---
# <a name="custom-machine-learning-models"></a>Anpassade maskininlärningsmodeller

> [!NOTE]
> Support för Machine Learning Studio (klassisk) upphör 31 augusti 2024. Vi rekommenderar att du övergår till [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) det datumet.
>
> Från och med den 1 december 2021 kommer du inte att kunna skapa nya resurser för Machine Learning Studio (klassisk). Till och med 31 augusti 2024 kan du fortsätta använda de befintliga Machine Learning Studio (klassiska) resurserna. Mer information finns i [Migrera till Azure Machine Learning](/azure/machine-learning/migrate-overview).

Anpassade modeller visar arbetsflöden baserade på Azure Machine Learning modeller. Arbetsflöden hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kunddata. Mer information om hur du bygger anpassade ML-modeller finns i [Använda Azure Machine Learning-baserade modeller](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Förutsättningar

- Webbtjänster som publicerats via [Azure Machine Learning batch-pipeline](/azure/machine-learning/concept-ml-pipelines).
- Pipeline måste publiceras under en [pipelineslutpunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Ett [Azure Data Lake Gen2 lagringskonto](/azure/storage/blobs/data-lake-storage-quickstart-create-account) som är associerat med din Azure Studio-instans.
- För Azure Machine Learning-arbetsytor med pipelines behöver du administratörsbehörighet som ägare eller användare till Azure Machine Learning-arbetsytan.

  > [!NOTE]
  > Data överförs mellan dina Customer Insights-instanser och valda Azure-webbtjänster eller -pipelines i arbetsflödet. När du överför data till en Azure-tjänst måste du se till att tjänsten är konfigurerad för att bearbeta data på det sätt och den plats som krävs för att uppfylla alla juridiska eller nödvändiga krav för att hantera dessa data för din organisation.

## <a name="add-a-new-workflow"></a>Lägg till ett nytt arbetsflöde

1. Gå till **Intelligens** > **Anpassade modeller** och välj **Nytt arbetsflöde**.

1. Ange ett igenkänningsbart **namn**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Skärmbild av fönstret Nytt arbetsflöde.":::

1. Välj den organisation som innehåller webbtjänsten i **Klientorganisation som innehåller din webbtjänst**.

1. Om din Azure Machine Learning-prenumeration finns i en annan klientorganisation än Customer Insights väljer du **Logga in** med dina autentiseringsuppgifter för den valda organisationen.

1. Välj de **arbetsytor** som är kopplade till din webbtjänst.

1. Välj Azure Machine Learning pipeline i listrutan **Webbtjänst som innehåller din modell**. Välj sedan **Nästa**.
   Läs mer om att [publicera en pipeline i Azure Machine Learning med designern](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. För varje **Indata till webbtjänst**, välj matchande **Entitet** från Customer Insights. Välj sedan **Nästa**.
   > [!NOTE]
   > Arbetsflödet med en anpassad modell används för att mappa webbtjänstens indatafält till entitetsattributen utifrån fältets namn och datatyp. Ett felmeddelande visas om ett webbtjänstfält inte kan mappas till en entitet.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurera ett arbetsflöde.":::

1. För **Parametrar för modellens utdata** anger du följande egenskaper:
   - **Entitetsnamn** för pipelineutdataresultaten
   - **Namnet på parametern för utdata till datalager** på batch-pipeline
   - **Namn på parametern för utdata för sökväg** på batch-pipeline.

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Parameterfönster för modellens utdata.":::

1. Välj det matchande attributet i **Resultat för Kund-ID** som identifierar kunder och välj **Spara**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Relatera resultat till fönstret Kunddata.":::

   Skärmen **Arbetsflödet sparades** visas med information om arbetsflödet. Om du har konfigurerat ett arbetsflöde för en Azure Machine Learning pipeline, kommer Customer Insights kopplas till arbetsytan som innehåller pipeline. Customer Insights får rollen **deltagare** på Azure-arbetsytan.

1. Välj **Klar**. Sidan **Anpassade modeller** visas.

1. Markera den stående ellipsen (&vellip;) för arbetsflöde och välj sedan **Kör**. Arbetsflödet körs också automatiskt tillsammans med alla [schemalagda uppdateringar](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Hantera en befintlig arbetsflöde

Gå till **Intelligens** > **Anpassade modeller** för att se de arbetsflöden du skapat.

Välj ett arbetsflöde om du vill visa tillgängliga åtgärder.

- **Redigera** arbetsflöde
- **Köra** ett arbetsflöde
- [**Radera**](#delete-a-workflow) arbetsflöde

### <a name="edit-a-workflow"></a>Redigera arbetsflöde

1. Gå till **Intelligens** > **Anpassade modeller**.

1. Välj den vertikala ellipsen bredvid arbetsflödet du vill uppdatera (&vellip;) och välj **Redigera**.

1. Ändra **visningsnamn** vid behov och välj **Nästa**.

1. För varje **Indata till webbtjänst** kan du uppdatera matchande **Entitet** från Customer Insights. Välj sedan **Nästa**.

1. För **Parametrar för modellens utdata** ändra något av följande:
   - **Entitetsnamn** för pipelineutdataresultaten
   - **Namnet på parametern för utdata till datalager** på batch-pipeline
   - **Namn på parametern för utdata för sökväg** på batch-pipeline.

1. Välj det matchande attributet i listrutan **Kund-ID i resultat** för att identifiera kunder. Välj ett attribut från inferensutdata med värden som liknar kolumnen Kund-ID i kundentiteten. Om du inte har en sådan kolumn i din datauppsättning väljer du ett attribut som identifierar raden unikt.

1. Välj **Spara**

### <a name="delete-a-workflow"></a>Ta bort arbetsflödet

1. Gå till **Intelligens** > **Anpassade modeller**.

1. Välj den vertikala ellipsen bredvid arbetsflödet du vill ta bort (&vellip;) och välj **Ta bort**.

1. Bekräfta borttagningen.

Arbetsflödet tas bort. Den [entitet](entities.md) som skapades när du skapade arbetsflödet kvarstår och kan visas från sidan **Data** > **Entiteter**.

## <a name="view-the-results"></a>Visa resultatet

Resultat från ett arbetsflöde lagras i entitetsnamnet som definieras för **Parametrar för modellens utdata**. Få åtkomst till dessa data från sidan [**Data** > **Entiteter**](entities.md) eller med [API-åtkomst](apis.md).

### <a name="api-access"></a>API-åtkomst

Använd följande format om du vill hämta data från en anpassad modellentitet för den specifika OData-frågan:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Ersätt `<your instance id>` med ID för Customer Insights-miljön, som du hittar i adressfältet i webbläsaren när du öppnar Customer Insights.

1. Ersätt `<custom model output entity>` med entitetsnamnet som du angav för **Parametrar för modellens utdata**.

1. Ersätt `<guid value>` med kund-ID för den kund som du vill använda. Detta ID visar på [sidan med kundprofiler](customer-profiles.md) i fältet Kund-ID.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

- Varför visas inte min pipeline när jag anger ett arbetsflöde för en anpassad modell?
  Det här problemet beror ofta på ett konfigurationsproblem i pipelinen. Kontrollera att [indataparametern har konfigurerats](azure-machine-learning-experiments.md#dataset-configuration) och att [parametrarna för utdatalagring och sökväg](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) också har konfigurerats.

- Vad betyder felmeddelandet "Kunde inte spara ett intelligent arbetsflöde"? 
  Användarna ser vanligtvis det här felmeddelandet om de inte har administratörsprivilegier som ägare eller användare av arbetsytan. Användaren behöver en högre behörighetsnivå för att Customer Insights ska kunna bearbeta arbetsflödet som en tjänst i stället för att använda autentiseringsuppgifterna för efterföljande körningar av arbetsflödet.

- Stöds en privat slutpunkt/privat länk för arbetsflödet för min anpassade modell?
  Customer Insights stöder för närvarande inte privata slutpunkt för anpassade modeller, men en manuell lösning är tillgänglig. Kontakta support för mer information.

## <a name="responsible-ai"></a>Ansvarsfull AI

Förutsägelser erbjuder funktioner för att skapa bättre kundupplevelser, förbättra affärsfunktioner och intäktsströmmar. Vi rekommenderar starkt att du balanserar värdet på din förutsägelse mot den inverkan den har och fördomar som kan införas på ett etiskt sätt. Läs mer om hur Microsoft hanterar [ansvarsfull AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan också lära dig om [tekniker och processer för ansvarsfull maskininlärning](/azure/machine-learning/concept-responsible-ml) som är specifik för Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
