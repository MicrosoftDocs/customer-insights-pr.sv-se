---
title: Översikt över prediktionsscenarier som stöds
description: Prediktionsscenarier och alternativ som omfattas av Dynamics 365 Customer Insights-programmet.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095755"
---
# <a name="predictions-overview"></a>Preditionsöversikt

Dynamics 365 Customer Insights levereras med en mängd olika alternativ som utnyttjar AI och maskininlärning för att förutsäga data. 

## <a name="out-of-box-models"></a>Färdiga modeller

Det enklaste sättet att börja med att förutsäga data är fördefinierade modeller, ofta kallade färdiga modeller. De kräver bara vissa data och strukturer för att generera insikter snabbt. För närvarande är följande modeller tillgängliga: 
- [Kundens livstidsvärde](predict-customer-lifetime-value.md): Förutsäger en kunds potentiella intäkter under hela interaktionen med ett företag. 
- [Produktrekommendation](predict-product-recommendation.md): Föreslår uppsättningar av prediktiva produktrekommendationer baserade på köpbeteende och kunder med liknande inköpsmönster.
- [Prenumerationsomsättning](predict-subscription-churn.md): Förutsäger om en kund riskerar att inte längre använda ditt företags prenumerationsprodukter eller tjänster.
- [Transaktionsbortfall](predict-transactional-churn.md): Förutsäger om en kund inte längre kommer att köpa dina produkter eller tjänster inom en viss tidsram.

## <a name="azure-machine-learning-integration"></a>Integration av Azure Machine Learning

Om en organisation redan använder maskininlärningsscenarier baserade på Azure Machine Learning-experiment hjälper funktionen anpassade modeller i Customer Insights till att ansluta punkterna. Skapa arbetsflöden som hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kundprofiler. Mer information finns i [anpassade maskininlärningsmodeller](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder-prediktion

Ibland är datauppsättningarna ofullständiga och vissa värden saknas. Customer Insights kan hjälpa till att förutsäga saknade värden för kundenhet och segment. Mer information finns i [Slutföra dina partiella data med förutsägelser](predictions.md).
