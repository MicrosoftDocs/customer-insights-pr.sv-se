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
# <a name="predictions-overview"></a><span data-ttu-id="11292-103">Preditionsöversikt</span><span class="sxs-lookup"><span data-stu-id="11292-103">Predictions overview</span></span>

<span data-ttu-id="11292-104">Dynamics 365 Customer Insights levereras med en mängd olika alternativ som utnyttjar AI och maskininlärning för att förutsäga data.</span><span class="sxs-lookup"><span data-stu-id="11292-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="11292-105">Färdiga modeller</span><span class="sxs-lookup"><span data-stu-id="11292-105">Out-of-box models</span></span>

<span data-ttu-id="11292-106">Det enklaste sättet att börja med att förutsäga data är fördefinierade modeller, ofta kallade färdiga modeller.</span><span class="sxs-lookup"><span data-stu-id="11292-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="11292-107">De kräver bara vissa data och strukturer för att generera insikter snabbt.</span><span class="sxs-lookup"><span data-stu-id="11292-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="11292-108">För närvarande är följande modeller tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="11292-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="11292-109">[Kundens livstidsvärde](predict-customer-lifetime-value.md): Förutsäger en kunds potentiella intäkter under hela interaktionen med ett företag.</span><span class="sxs-lookup"><span data-stu-id="11292-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="11292-110">[Produktrekommendation](predict-product-recommendation.md): Föreslår uppsättningar av prediktiva produktrekommendationer baserade på köpbeteende och kunder med liknande inköpsmönster.</span><span class="sxs-lookup"><span data-stu-id="11292-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="11292-111">[Prenumerationsomsättning](predict-subscription-churn.md): Förutsäger om en kund riskerar att inte längre använda ditt företags prenumerationsprodukter eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="11292-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="11292-112">[Transaktionsbortfall](predict-transactional-churn.md): Förutsäger om en kund inte längre kommer att köpa dina produkter eller tjänster inom en viss tidsram.</span><span class="sxs-lookup"><span data-stu-id="11292-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="11292-113">Integration av Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="11292-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="11292-114">Om en organisation redan använder maskininlärningsscenarier baserade på Azure Machine Learning-experiment hjälper funktionen anpassade modeller i Customer Insights till att ansluta punkterna.</span><span class="sxs-lookup"><span data-stu-id="11292-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="11292-115">Skapa arbetsflöden som hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="11292-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="11292-116">Mer information finns i [anpassade maskininlärningsmodeller](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="11292-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="11292-117">AI Builder-prediktion</span><span class="sxs-lookup"><span data-stu-id="11292-117">AI Builder prediction</span></span>

<span data-ttu-id="11292-118">Ibland är datauppsättningarna ofullständiga och vissa värden saknas.</span><span class="sxs-lookup"><span data-stu-id="11292-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="11292-119">Customer Insights kan hjälpa till att förutsäga saknade värden för kundenhet och segment.</span><span class="sxs-lookup"><span data-stu-id="11292-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="11292-120">Mer information finns i [Slutföra dina partiella data med förutsägelser](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="11292-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
