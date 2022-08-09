---
title: Granska dataförening
description: Granska datasynderna, skapa Unified customer profile och granska resultatet
ms.date: 06/02/2022
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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139606"
---
# <a name="review-data-unification"></a>Granska dataförening

Det sista steget i processen visar en sammanfattning av stegen i processen och ger en chans att göra ändringar innan du skapar en enhetlig profil.

:::image type="content" source="media/m3_review.png" alt-text="Skärmbild av gransknings- och skapa kundprofiler.":::

## <a name="review-the-data-unification-steps"></a>Granska datasamordningsstegen

1. Välj **Redigera** för de data som ska granskas och göra ändringarna.

1. Om du är nöjd med dina val väljer du **Skapa kundprofiler**. Sidan **Förena** visas medan Unified customer profile skapas. Alla paneler utom **källfält** visar **kö** eller **uppdatering** status.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Skärmbild på sidan förena med paneler som visar Köad eller Uppdatera.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritmen tar en stund att slutföra och du kan inte ändra konfigurationen förrän den är klar. När processen är klar visas entiteten för entiteten Unified customer profile, kallad *kund* anges på sidan **Entiteter** i avsnittet **Profiler**. Vid den första lyckade körningen skapas enhetlig entitet *Kund*. Alla efterföljande körningar visar den entiteten.

## <a name="review-the-results-of-data-unification"></a>Granska resultat för datasamordning

Efter samordning visar sidan **Data** > **Förena** visar antal Unified customer profile. Resultatet av varje steg i processen visas på varje panel. Till exempel **Källfält** visar antalet mappade attribut (fält) och **Dubblettposter** visar antalet dubblettposter som hittats.

:::image type="content" source="media/m3_unified.png" alt-text="Skärmbild på sidan Data förena när data har enhetlig information.":::

> [!TIP]
> Panelen **Matchande villkor** visas endast om flera entiteter har markerats.

Vi rekommenderar att du granskar resultaten, särskilt kvaliteten på dina [matchningsregler](data-unification-update.md#manage-match-rules) och förfinar dem vid behov.

När det behövs [kan du ändra sammanslagningsinställningarna](data-unification-update.md) och köra den enhetliga profilen igen.

## <a name="next-step"></a>Nästa steg

Konfigurera [aktiviteter](activities.md), [berikning](enrichment-hub.md), [relationer](relationships.md) eller [mått](measures.md) för att få mer information om dina kunder.

[!INCLUDE[footer-include](includes/footer-banner.md)]
