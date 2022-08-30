---
title: Granska dataförening
description: Granska datasynderna, skapa Unified customer profile och granska resultatet
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303989"
---
# <a name="review-data-unification"></a>Granska dataförening

Granska sammanfattningen av ändringarna, skapa en enhetlig profil och granska resultatet.

## <a name="review-and-create-customer-profiles"></a>Granska och skapa kundprofiler

Det sista steget i processen visar en sammanfattning av stegen i processen och ger en chans att göra ändringar innan du skapar en enhetlig profil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Skärmbild av gransknings- och skapa kundprofiler.":::

1. Välj **Redigera** för de data som ska granskas och göra ändringarna.

1. Om du är nöjd med dina val väljer du **Skapa kundprofiler** (eller **Skapa kundprofiler** för B2B). Sidan **Förena** visas medan Unified customer profile skapas.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Skärmbild på sidan förena med paneler som visar Köad eller Uppdatera.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritmen tar en stund att slutföra och du kan inte ändra konfigurationen förrän den är klar.

## <a name="view-the-results-of-data-unification"></a>Visa resultat för datasamordning

Efter samordning visar sidan **Data** > **Förena** visar antal Unified customer profile (eller kontoprofiler för B2B). Resultatet av varje steg i processen visas på varje panel. Till exempel **Källfält** visar antalet mappade attribut (fält) och **Dubblettposter** visar antalet dubblettposter som hittats.

:::image type="content" source="media/m3_unified.png" alt-text="Skärmbild på sidan Data förena när data har enhetlig information.":::

> [!TIP]
> Panelen **Matchande villkor** visas endast om flera entiteter har markerats.

Vi rekommenderar att du granskar resultaten, särskilt kvaliteten på dina [matchningsregler](data-unification-update.md#manage-match-rules) och förfinar dem vid behov.

När det behövs [kan du ändra sammanslagningsinställningarna](data-unification-update.md) och köra den enhetliga profilen igen.

### <a name="verify-output-entities-from-data-unification"></a>Verifiera utdataenheter från dataförening

Gå till **Data** > **Entiteter** för att verifiera utdataenheterna.

Din enhetliga kundprofil kallas *Kunder*, visas i **Profiler**. Vid den första lyckade körningen skapas enhetlig entitet *Kund*. Alla efterföljande körningar visar den entiteten.

Duplicerings- och konditorientiteter skapas och visas i avsnittet **System**. En deduplicerad enhet för var och en av källentiteterna skapas med namnet **Deduplication_DataSource_Entity**. Entiteten **ConflationMatchPairs** innehåller information om matchningar för flera entiteter.

En utdataenhet för deduplicering innehåller följande information:
- ID/Nycklar
  - Primärnyckel och Alternativt ID-fält. Fältet Alternativt ID består av alla alternativa ID:n som identifieras för en post.
  - Deduplication_GroupId visar gruppen eller klustret som identifieras i en entitet som grupperar alla liknande poster utifrån de angivna dedupliceringsfälten. Det används för systembearbetning. Om det inte finns några manuella dedupliceringsregler som anges och systemdefinierade dedupliceringsregler gäller kanske inte det här fältet finns i entiteten för dedupliceringsutdata.
  - Deduplication_WinnerId: Det här fältet innehåller vinnande ID från de identifierade grupperna eller klustren. Om Deduplication_WinnerId är samma värde som primärnyckeln för en post innebär det att posten är vinnarposten.
- Fält som används för att definiera dedupliceringsreglerna.
- Regel- och poängfält som anger vilka av dedupliceringsregler som tillämpats och poängen som returneras av den matchande algoritmen.

## <a name="next-step"></a>Nästa steg

- För B2B, utför valfritt [kontaktföreningen](data-unification-contacts.md).

- För B2C, konfigurera [aktiviteter](activities.md), [berikning](enrichment-hub.md), [relationer](relationships.md) eller [mått](measures.md) för att få mer insikt om dina kunder.

[!INCLUDE[footer-include](includes/footer-banner.md)]
