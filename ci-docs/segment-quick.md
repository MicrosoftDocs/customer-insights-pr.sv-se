---
title: Skapa enkla segment med snabba segment
description: Skapa enkla segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171144"
---
# <a name="create-simple-segments-with-quick-segments"></a>Skapa enkla segment med snabba segment

Med snabbsegment kan du bygga enkla segment med en enda operator snabbt för snabbare insikter. Snabbsegment stöds endast i miljöer för **enskilda kunder**.

## <a name="create-a-new-segment-with-quick-segments"></a>Skapa ett nytt segment med snabbsegment

1. Gå till **Segment**.

1. Välj **Ny** > **Skapa från**.
   - Välj alternativet **profiler** för att skapa ett segment som baseras på entiteten för den *enhetliga kunden*.
   - Välj alternativet **Mått** om du vill skapa ett segment kring mått som du har skapat tidigare.
   - Markera alternativet **Intelligens** om du vill skapa ett segment runt en av de utdataentiteter som du skapade med funktionerna **prediktioner** eller **anpassade modeller**.

1. I dialogrutan **Nytt snabbsegment**, välj ett attribut i listrutan **Fält**. Systemet har olika värden, baserat på dina val.
   - För kategorifält visas tio populära kundräkningar. Välj ett **Värde** och välj **Granska**.
   - För ett numeriskt attribut visar systemet vilket attributvärde som faller under varje kunds percentil. Välj en **operatör** och ett **värde** och välj sedan **granska**.

1. Systemet tillhandahåller en **uppskattad segmentstorlek**. Du kan välja om du vill skapa ett segment som du har definierat eller gå tillbaka för att välja ett annat fält.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Namn och uppskattning för ett snabbsegment.":::

1. Ange ett **Namn** och **utgående entitetsnamn** för ditt segment. Alternativt kan du lägga till [taggar](work-with-tags-columns.md#manage-tags).

1. Välj **Spara** för att skapa segmentet. Sidan **Segment** visas.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Nästa steg

[Exportera ett segment ](export-destinations.md)och utforska [integreringen av kundkort](customer-card-add-in.md) för att använda segment i andra program.

[!INCLUDE [footer-include](includes/footer-banner.md)]
