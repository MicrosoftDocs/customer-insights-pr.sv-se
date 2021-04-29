---
title: Segmentbaserade på prediktion utdata
description: Skapa segment utifrån utdataenheten i en prediktionsmodell.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741451"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="aee36-103">Skapa ett segment utifrån en prediktionsmodell (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="aee36-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="aee36-104">Resultaten av prognoserna gäller ibland bara en delmängd av kunderna.</span><span class="sxs-lookup"><span data-stu-id="aee36-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="aee36-105">Öka anpassningen av rekommendationerna genom att skapa segment utifrån resultatet av prediktionsmodeller.</span><span class="sxs-lookup"><span data-stu-id="aee36-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="aee36-106">Du kanske t.ex. vill ge specifika rekommendationer till kunder som föredrar en viss typ av tjänst.</span><span class="sxs-lookup"><span data-stu-id="aee36-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="aee36-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="aee36-107">Prerequisites</span></span>

- <span data-ttu-id="aee36-108">Minst [Deltagarbehörighet](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aee36-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="aee36-109">En produktrekommendation, transaktionell omsättning, prenumeration eller kundens livstidsvärdesmodell som konfigurerats i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aee36-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="aee36-110">Läs om kraven för att konfigurera de olika modellerna:</span><span class="sxs-lookup"><span data-stu-id="aee36-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="aee36-111">Produktrekommendationsmodell</span><span class="sxs-lookup"><span data-stu-id="aee36-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="aee36-112">Modell för prenumerationsomsättning</span><span class="sxs-lookup"><span data-stu-id="aee36-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="aee36-113">Transaktionsomsättningsmodell</span><span class="sxs-lookup"><span data-stu-id="aee36-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="aee36-114">Kundens livstidsvärde modell</span><span class="sxs-lookup"><span data-stu-id="aee36-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="aee36-115">Skapa ett kundsegment utifrån förutprognoser</span><span class="sxs-lookup"><span data-stu-id="aee36-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="aee36-116">Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="aee36-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="aee36-117">Markera de stående ellipserna bredvid den modell du vill granska och välj **Visa**.</span><span class="sxs-lookup"><span data-stu-id="aee36-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="aee36-118">Välj på resultatsidan **Skapa segment**.</span><span class="sxs-lookup"><span data-stu-id="aee36-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="aee36-119">Mer information om resultatsidan finns i artikeln om modellen.</span><span class="sxs-lookup"><span data-stu-id="aee36-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Skärmbild på resultatsidan prediktion med markering på åtgärden Skapa segment.":::

1. <span data-ttu-id="aee36-121">Skapa ett nytt segment baserat på utdataentitet för den valda modellen.</span><span class="sxs-lookup"><span data-stu-id="aee36-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="aee36-122">Mer information finns i [Skapa och hantera segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="aee36-122">For more information, see [Create and manage segments](segments.md).</span></span>