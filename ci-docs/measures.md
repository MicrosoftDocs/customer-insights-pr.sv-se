---
title: Måttöversikt
description: Lär dig hur mått hjälper till att analysera och reflektera företagets resultat.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081986"
---
# <a name="measures-overview"></a>Måttöversikt

Åtgärder hjälper dig att få en bättre förståelse av kundbeteenden och affärsresultat. De tittar på relevanta värden från [enhetliga profiler](data-unification.md). Ett företag vill till exempel se den *totala kostnaden per kund* för att förstå en enskild kunds köphistorik eller mäta företagets *totala försäljning* för att förstå den sammanlagda omsättningen för hela verksamheten.  

Mått skapas [med måttverktyget](measure-builder.md), en datafrågeställningsplattform med olika operatörer och enkla mappningsalternativ. Du kan filtrera data, gruppera resultat, identifiera [entitetsrelationssökvägar](relationships.md) och förhandsgranska utdata. Du kan [använda fördefinierade mallar](measure-templates.md) för att konfigurera vanliga åtgärder på ett effektivt sätt.

Använd måttverktyget om du vill planera affärsaktiviteter genom att fråga efter kunddata och extrahera insikter. Om du till exempel skapar ett mått på *totalsumma per kund* och *total intäkt per kund* kan du identifiera en grupp av kunder som spenderar mycket men ger höga intäkter. Du kan [skapa ett segment](segments.md) utifrån dessa åtgärder för att driva fram nästa bästa åtgärder.

## <a name="manage-your-measures"></a>Hantera dina mått

Listan med åtgärder finns på sidan **Mått**.

Här finns information om måttypen, den som skapade den, datumet då den skapades, statusen och tillståndet. När du väljer ett mått i listan kan du förhandsgranska utdatan och hämta en CSV-fil.

:::image type="content" source="media/measures-actions.png" alt-text="Åtgärder för att hantera enskilda mått."lightbox="media/measures-actions.png":::

Följande åtgärder är tillgängliga när du väljer ett mått:

- **Redigera** måttets konfiguration.
- **Duplicera** ett mått. Du kan välja att redigera egenskaperna direkt eller bara spara dubbletten.
- **Uppdatera** måttet baserat på senaste data. Om du vill uppdatera alla åtgärder samtidigt markerar du alla åtgärder och **uppdaterar** sedan.
- **Byt namn** på mått.
- **Aktivera** eller **Inaktivera**. Inaktiva mått uppdateras inte vid en [schemalagd uppdatering](system.md#schedule-tab).
- **Tagg** för att [hantera taggar](work-with-tags-columns.md#manage-tags) för segmentet.
- **Ta bort** måttet.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Nästa steg

Du kan använda befintliga åtgärder för att skapa [ett kundsegment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
