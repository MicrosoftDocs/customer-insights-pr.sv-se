---
title: Förstå och hantera åtgärder
description: Lär dig hur mått hjälper till att analysera och reflektera företagets resultat.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359817"
---
# <a name="measures-overview"></a>Måttöversikt

Åtgärder hjälper dig att få en bättre förståelse av kundbeteenden och affärsresultat. De tittar på relevanta värden från [enhetliga profiler](data-unification.md). Ett företag vill till exempel se den *totala kostnaden per kund* för att förstå en enskild kunds köphistorik eller mäta företagets *totala försäljning* för att förstå den sammanlagda omsättningen för hela verksamheten.  

Mått skapas [med måttverktyget](measure-builder.md), en datafrågeställningsplattform med olika operatörer och enkla mappningsalternativ. Du kan filtrera data, gruppera resultat, identifiera [entitetsrelationssökvägar](relationships.md) och förhandsgranska utdata. Du kan [använda fördefinierade mallar](measure-templates.md) för att konfigurera vanliga åtgärder på ett effektivt sätt.

Använd måttverktyget om du vill planera affärsaktiviteter genom att fråga efter kunddata och extrahera insikter. Om du till exempel skapar ett mått på *totalsumma per kund* och *total intäkt per kund* kan du identifiera en grupp av kunder som spenderar mycket men ger höga intäkter. Du kan [skapa ett segment](segments.md) utifrån dessa åtgärder för att driva fram nästa bästa åtgärder. 

## <a name="manage-your-measures"></a>Hantera dina mått

Listan med åtgärder finns på sidan **Mått**.

Här finns information om måttypen, den som skapade den, datumet då den skapades, statusen och tillståndet. När du väljer ett mått i listan kan du förhandsgranska utdatan och hämta en CSV-fil.

Om du vill uppdatera alla dina åtgärder samtidigt markerar du **Uppdatera allt** utan att välja ett specifikt mått.

:::image type="content" source="media/measure-actions.png" alt-text="Åtgärder för att hantera enskilda mått.":::

Välj ett mått i listan för följande alternativ:

- Markera måttets namn om du vill se detaljerna.
- **Redigera** måttets konfiguration.
- **Uppdatera** måttet baserat på senaste data.
- **Byt namn** på mått.
- **Ta bort** måttet.
- **Aktivera** eller **Inaktivera**. Inaktiva mått uppdateras inte vid en [schemalagd uppdatering](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Nästa steg

Du kan använda befintliga åtgärder för att skapa [ett kundsegment](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
