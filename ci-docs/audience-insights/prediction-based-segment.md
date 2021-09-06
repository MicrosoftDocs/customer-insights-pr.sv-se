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
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036441"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Skapa ett segment utifrån en prediktionsmodell (förhandsgranskning)

Resultaten av prognoserna gäller ibland bara en delmängd av kunderna. Öka anpassningen av rekommendationerna genom att skapa segment utifrån resultatet av prediktionsmodeller. Du kanske t.ex. vill ge specifika rekommendationer till kunder som föredrar en viss typ av tjänst. 

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.

- En produktrekommendation, transaktionell omsättning, prenumeration eller kundens livstidsvärdesmodell som konfigurerats i Customer Insights. Läs om kraven för att konfigurera de olika modellerna:

  - [Produktrekommendationsmodell](predict-product-recommendation.md)
  - [Modell för prenumerationsomsättning](predict-subscription-churn.md)
  - [Transaktionsomsättningsmodell](predict-transactional-churn.md)
  - [Kundens livstidsvärde modell](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Skapa ett kundsegment utifrån förutprognoser

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Markera de stående ellipserna bredvid den modell du vill granska och välj **Visa**.

1. Välj på resultatsidan **Skapa segment**. Mer information om resultatsidan finns i artikeln om modellen.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Skärmbild på resultatsidan prediktion med markering på åtgärden Skapa segment.":::

1. Skapa ett nytt segment baserat på utdataentitet för den valda modellen. Mer information finns i [Skapa och hantera segment](segments.md).