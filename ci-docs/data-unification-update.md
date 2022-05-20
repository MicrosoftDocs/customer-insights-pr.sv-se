---
title: Uppdatera föreningsinställningarna
description: Uppdatera dubblettregler, matchningsregler eller förenade fält i inställningarna för dubbletter.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755612"
---
# <a name="update-the-unification-settings"></a>Uppdatera föreningsinställningarna

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Granska eller ändra eventuella inställningar när en förenad profil har skapats genom att utföra följande steg.

1. Gå till **Data** > **Förena**.

   :::image type="content" source="media/m3_unified.png" alt-text="Skärmbild på sidan Data förena när data har enhetlig information.":::

   > [!TIP]
   > Panelen **Matchande villkor** visas endast om flera entiteter har markerats.

1. Välj vad du vill uppdatera:
   - [Källfält](#edit-source-fields) för att lägga till entiteter eller attribut eller ändra attributtyper.
   - [Dubblettposter](#manage-deduplication-rules) för att hantera dubblettregler eller kopplingsinställningar.
   - [Matchande villkor](#manage-match-rules) för att uppdatera matchande regler för två eller flera entiteter.
   - [Förenade kundfält](#manage-unified-fields) för att kombinera eller utesluta fält. Du kan också gruppera relaterade profiler i kluster.

1. När du har gjort ändringarna väljer du nästa alternativ:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Skärmbild på sidan Data förena med alternativen för förena.":::

   - Information om hur du uppdaterar Unified customer profile (med eller utan beroenden ) finns i [Köra uppdateringar av kundprofilen](#run-updates-to-the-unified-customer-profile).
   - Information om hur du utvärderar kvaliteten på dina matchningsvillkor utan att uppdatera den förenade profilen finns i [Kör matchande villkor](#run-matching-conditions). Alternativet **Kör endast matchande villkor** visas inte för en entitet.

## <a name="edit-source-fields"></a>Redigera källfält

Du kan inte ta bort ett attribut eller en entitet om de redan är förenade.

1. Välj **Redigera** på panelen **Källfält**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Skärmbild på sidan Källfält som visar antalet primära nycklar, mappade och omappade fält":::

   Antalet mappade och omappade fält som visas.

1. Markera **Välj entiteter och fält** om du vill lägga till andra attribut eller entiteter. Använd sökningen eller bläddra för att hitta och välja dina attribut och enheter av intresse. Välj **Verkställ**.

1. Alternativt kan du ändra primärnyckeln för en entitet, attributtyperna och växla **intelligent mappning** av och på. Mer information finns i [Välj primärnyckel och semantik typ för attribut](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Välj **Nästa** om du vill ändra dubblettreglerna eller välj **Spara och stäng** och återgå till [Uppdatera sammanslagningsinställningarna](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Hantera regler för deduplicering

1. Välj **Redigera** på panelen **Dubblettposter**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Skärmbild på sidan med dubblettposter som visar antalet dubblettposter" lightbox="media/m3_duplicates_edit.png":::

   Antalet dubblettposter som hittades visas under **Dubbletter**. I kolumnen **Poster som är deduplicerade** visas vilka entiteter som hade dubblettposter samt procentandelen duplicerade poster.

1. Om du har lagt till en förädlad entitet väljer du **Använd utökade entiteter**. Mer information: [Berikande för datakällor](data-sources-enrichment.md).

1. Om du vill hantera dubblettregler väljer du något av följande alternativ:
   - **Skapa en ny regel**: Välj **Lägg till regel** under rätt entitet. Mer information finns i [Definiera deduplicering regler](remove-duplicates.md#define-deduplication-rules).
   - **Ändra regelvillkor**: Välj regeln och sedan **Redigera**. Ändra fält, lägga till eller ta bort villkor, eller lägg till eller ta bort undantag.
   - **Förhandsgranskning**: Välj regeln och **förhandsgranska** för att visa senaste körningsresultatet för regeln.
   - **Inaktivera en regel**: Markera regeln och **inaktivera** om du vill behålla en dedupliceringsregel och utesluta den från matchningsprocessen.
   - **Duplicera en regel**: Markera regeln och sedan **Duplicera** om du vill skapa en liknande regel med ändringar.
   - **Ta bort en regel**: Markera regeln och **Ta bort**.

1. Om du vill ändra inställningarna för kopplade dokument markerar du entiteten. Du kan endast ändra inställningarna om en regel skapas.
   1. Välj **Redigera kopplingsinställningar** och ändra alternativet **Post som ska behållas**.
   1. Om du vill ändra kopplingsinställningar för enskilda attribut för en entitet väljer du **Avancerat** och gör nödvändiga ändringar.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Skärmbild på avancerade kopplingsinställningar som visar senaste e-post och mest fullständiga adress":::

   1. Välj **Utfört**.

1. Välj **Nästa** om du vill ändra matchande villkor eller välj **Spara och stäng** och återgå till [Uppdatera sammanslagningsinställningarna](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Hantera matchningsregler

Du kan konfigurera om och finjustera de flesta matchningsparametrarna. Du kan inte lägga till eller ta bort enheter. Matchningsregler gäller inte för en enskild entitet.

1. Välj **Redigera** på panelen **Matchningsvillkor**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Skärmbild av sidan matchningsregel and villkor med statistik." lightbox="media/m3_match_edit.png":::

   På sidan visas matchningsordningen och definierade regler samt följande statistik:
   - **Unika källposter** visar antalet enskilda källposter som behandlades i förra matchningskörningen.
   - **Matchade och icke-matchade poster** visar hur många unika poster som finns kvar efter bearbetningen av matchningsreglerna.
   - **Endast matchade poster** visar antalet matchningar för alla dina matchningspar.

1. Välj **Visa senaste körning** om du vill visa resultatet för alla regler och deras poäng. Resultaten visas, inklusive de alternativa kontakt-ID:erna. Du kan hämta resultaten.

1. Om du vill visa resultatet och poängen för en viss regel markerar du regeln och **förhandsgranskar** den. Resultaten visas. Du kan hämta resultaten.

1. För att se resultatet av ett visst villkor på en regel, välj regeln och sedan **Redigera** den. Välj i redigeringsfönstret **Förhandsgranskning** under villkoret. Du kan hämta resultaten.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafisk representation av poster som inte matchar varandra och som innehåller en lista över dessa data.":::

1. Om du har lagt till en förädlad entitet väljer du **Använd utökade entiteter**. Mer information: [Berikande för datakällor](data-sources-enrichment.md).

1. Om du vill hantera regler väljer du något av följande alternativ:
   - **Skapa en ny regel**: Välj **Lägg till regel** under rätt entitet. Mer information finns i [Definiera regler för matchningspar](match-entities.md#define-rules-for-match-pairs).
   - **Ändra ordningen på reglerna** om du har definierat flera regler: Dra och släpp reglerna i den ordning du vill ha. Mer information finns i [Ange matchordningen](match-entities.md#specify-the-match-order).
   - **Ändra regelvillkor**: Välj regeln och sedan **Redigera**. Ändra fält, lägga till eller ta bort villkor, eller lägg till eller ta bort undantag.
   - **Inaktivera en regel**: Markera regeln och **inaktivera** om du vill behålla en matchningsregel och utesluta den från matchningsprocessen.
   - **Duplicera en regel**: Markera regeln och sedan **Duplicera** om du vill skapa en liknande regel med ändringar.
   - **Ta bort en regel**: Markera regeln och **Ta bort**.

1. Välj **Nästa** om du vill ändra till förenade fält eller välj **Spara och stäng** och återgå till [Uppdatera sammanslagningsinställningarna](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Hantera förenade fält

1. Välj **Redigera** på panelen **förenade kundfält**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Skärmbild av förenade kundfält":::

1. Granska de kombinerade och uteslutna fälten och gör eventuella ändringar. Lägga till eller redigera CustomerID-nyckel eller grupprofiler i kluster. Mer information finns i [förenade kundfält](merge-entities.md).

1. Välj **Nästa** om du vill granska inställningarna och [uppdatera den förenade profilen och beroendena](#run-updates-to-the-unified-customer-profile), eller välj **Spara och stäng** och återgå till [Uppdatera inställningarna](#update-the-unification-settings) för att göra fler ändringar.

## <a name="run-matching-conditions"></a>Kör matchningsvillkor

1. Från sidan **Data** > **Förena** välj **Kör endast matchningsvillkor**.

   Panelerna **Dubblettposter** och **Matchande villkor** visar **Köad** eller **Uppdatering**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. När matchningsprocessen är klar väljer du **Redigera** på panelen **Matchande villkor**.

   :::image type="content" source="media/match-KPIs.png" alt-text="En liten skärmbild av de viktigaste måtten på sidan Matchning med siffror och detaljer.":::

1. Mer information finns i [Hantera dubblettregler](#manage-deduplication-rules) eller [Hantera matchningsregler](#manage-match-rules).

1. Kör matchningsprocessen igen eller [kör uppdateringar för kundprofilen](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Köra uppdateringar till Unified customer profile

1. Från sidan **Data** > **Förena**, välj:

   - **Unified customer profile**: Uppdaterar entiteten för Unified customer profile utan att påverka beroenden (till exempel utöka, segment eller mått). Beroende processer körs inte, men uppdateras enligt vad som [anges i uppdateringsschemat](system.md#schedule-tab).

   - **Unified customer profile och beroenden**: Uppdaterar den förenade profilen och alla beroenden. Alla processer körs automatiskt om. När alla processer nedströms har slutförts återspeglar kundprofilen uppdaterade data.

   Panelerna **Dubblettposter**, **Matchande villkor** och **Förenade kundfält** visar **Köad** eller **Uppdatering**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
