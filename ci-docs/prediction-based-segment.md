---
title: Skapa ett segment baserat på en prediktionsmodell
description: Skapa segment utifrån utdataenheten i en prediktionsmodell.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610450"
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

1. Välj den modell du vill granska om och välj **Visa**.

1. Välj på resultatsidan **Skapa segment**. Mer information om resultatsidan finns i artikeln om modellen.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Skärmbild på resultatsidan prediktion med markering på åtgärden Skapa segment.":::

1. Skapa ett nytt segment med attribut från utdataentitet för den valda modellen. Mer information finns i [Skapa och hantera segment](segments.md).

> [!TIP]
> Du kan också skapa ett segment för en prediktionsmodell från **Segment** genom att välja **Nytt** och **Skapa från** > **Intelligens**. För mer information, se [Skapa ett nytt segment med snabba segment](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
