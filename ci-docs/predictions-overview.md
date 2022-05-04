---
title: Översikt över prediktionsscenarier som stöds
description: Prediktionsscenarier och alternativ som omfattas av Dynamics 365 Customer Insights-programmet.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648000"
---
# <a name="predictions-overview"></a>Preditionsöversikt

Dynamics 365 Customer Insights levereras med en mängd olika alternativ som utnyttjar AI och maskininlärning för att förutsäga data. 

## <a name="out-of-box-models"></a>Färdiga modeller

Det enklaste sättet att börja med att förutsäga data är fördefinierade modeller, ofta kallade färdiga modeller. De kräver bara vissa data och strukturer för att generera insikter snabbt. För närvarande är följande modeller tillgängliga: 

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

- [Kundens livstidsvärde](predict-customer-lifetime-value.md): Förutsäger en kunds potentiella intäkter under hela interaktionen med ett företag.
- [Produktrekommendation](predict-product-recommendation.md): Föreslår uppsättningar av prediktiva produktrekommendationer baserade på köpbeteende och kunder med liknande inköpsmönster.
- [Prenumerationsomsättning](predict-subscription-churn.md): Förutsäger om en kund riskerar att inte längre använda ditt företags prenumerationsprodukter eller tjänster.
- [Transaktionsbortfall](predict-transactional-churn.md): Förutsäger om en kund inte längre kommer att köpa dina produkter eller tjänster inom en viss tidsram.
- [Sentimentanalys](sentiment-analysis.md): Analysera sentiment av kundfeedback och identifiera affärsaspekter som nämns ofta.

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

- [Transaktionsbortfall](predict-transactional-churn.md): Förutsäger om en kund inte längre kommer att köpa dina produkter eller tjänster inom en viss tidsram.

---

> [!TIP]
> Vi rekommenderar att du regelbundet uppdaterar färdiga modeller med uppdaterade data i syfte att se till att de informerar ditt affärsanvändningsfall på ett korrekt sätt. Data uppdateras ad hoc när systemet matar in nya eller uppdaterade datakällor. I det här fallet kommer modeller emellertid endast att omutvärdera och fortsätta använda befintliga utbildningsdata.
> 
> Du kan konfigurera ett **uppdateringsschema** genom att ange modellschema för omprogrammering i konfigurationsupplevelsen. Modellen omprogrammeras och omutvärderas i detta schema, som du kan ändra när som helst.


## <a name="azure-machine-learning-integration"></a>Integration av Azure Machine Learning

Om en organisation redan använder maskininlärningsscenarier baserade på Azure Machine Learning-experiment hjälper funktionen anpassade modeller i Customer Insights till att ansluta punkterna. Skapa arbetsflöden som hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kundprofiler. Mer information finns i [anpassade maskininlärningsmodeller](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder-förutsägelse

Ibland är datauppsättningarna ofullständiga och vissa värden saknas. Customer Insights kan hjälpa till att förutsäga saknade värden för kundenhet och segment. Mer information finns i [Slutföra dina partiella data med förutsägelser](predictions.md).
