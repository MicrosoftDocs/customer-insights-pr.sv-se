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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170871"
---
# <a name="measures-overview"></a>Måttöversikt

Åtgärder hjälper dig att få en bättre förståelse av kundbeteenden och affärsresultat. De tittar på relevanta värden från [enhetliga profiler](data-unification.md). Ett företag vill till exempel se den *totala kostnaden per kund* för att förstå en enskild kunds köphistorik eller mäta företagets *totala försäljning* för att förstå den sammanlagda omsättningen för hela verksamheten.

Skapa mått om du vill planera affärsaktiviteter genom att fråga efter kunddata och extrahera insikter. Om du till exempel skapar ett mått på *totalsumma per kund* och *total intäkt per kund* kan du identifiera en grupp av kunder som spenderar mycket men ger höga intäkter. Du kan [skapa ett segment](segments.md) utifrån dessa åtgärder för att driva fram nästa bästa åtgärder.

## <a name="create-a-measure"></a>Skapa ett mått

Välj hur du vill skapa ett mått utifrån din målgrupp.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

- Från grunden med måttverktyget: [Skapa en egen](measure-builder.md).
- Från vanligt använt mått: [Använd fördefinierade mallar](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

Från grunden med måttverktyget: [Skapa en egen](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Hantera befintliga mått

Gå till sidan **Mått** om du vill visa de mått som du skapade, deras status, måttyp och senaste gången data uppdaterades. Du kan sortera listan med mått efter valfri kolumn eller använda sökrutan för att hitta det mått du vill hantera.

Välj bredvid ett mått om du vill visa tillgängliga åtgärder. Välj måttnamnet för att förhandsgranska resultatet och ladda ner en CSV-fil.

:::image type="content" source="media/measures-actions.png" alt-text="Åtgärder för att hantera enskilda mått."lightbox="media/measures-actions.png":::

- **Redigera** mått om du vill ändra dess egenskaper.
- **Uppdatera** mått så att det omfattar senaste data.
- **Byt namn** på mått.
- **Aktivera** eller **Inaktivera** måttet. Inaktiva mått kommer inte att uppdateras under en [schemalagd uppdatering](system.md#schedule-tab) och ha **Status** som anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats.
- **Tagg** för att [hantera taggar](work-with-tags-columns.md#manage-tags) för mått.
- **Ta bort** måttet.
- **Kolumner** för att [anpassa vilka kolumner](work-with-tags-columns.md#customize-columns) som visas.
- **Filtrera** om du vill [filtrera på taggar](work-with-tags-columns.md#filter-on-tags).
- **Söknamn** för att söka efter måttnamn.

## <a name="refresh-measures"></a>Måttet har uppdaterats

Mått kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran. Om du vill uppdatera en eller flera mått manuellt markerar du dem och väljer **Uppdatera**. Om du vill [schemalägga en automatisk uppdatering](system.md#schedule-tab) går du till **Admin** > **System** > **Schemalägg**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
