---
title: Granska dataförening
description: Granska datasynderna, skapa Unified customer profile och granska resultatet
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741714"
---
# <a name="review-data-unification"></a>Granska dataförening

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Det sista steget i processen visar en sammanfattning av stegen i processen och ger en chans att göra ändringar innan du skapar en enhetlig profil.

:::image type="content" source="media/m3_review.png" alt-text="Skärmbild av gransknings- och skapa kundprofiler.":::

## <a name="review-the-data-unification-steps"></a>Granska datasamordningsstegen

1. Välj **Redigera** för de data som ska granskas och göra ändringarna.

1. Om du är nöjd med dina val väljer du **Skapa kundprofiler**. Sidan **Förena** visas medan Unified customer profile skapas. Algoritmen tar en stund att slutföra och du kan inte ändra konfigurationen förrän den är klar.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

När processen är klar visas entiteten för entiteten Unified customer profile, kallad *kund* anges på sidan **Entiteter** i avsnittet **Profiler**. Vid den första lyckade körningen skapas enhetlig entitet *Kund*. Alla efterföljande körningar visar den entiteten.

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
