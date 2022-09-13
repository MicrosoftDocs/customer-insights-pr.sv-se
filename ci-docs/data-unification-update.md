---
title: Uppdatera inställningar för kund-, konto- eller kontaktförening
description: Uppdatera dubblettregler, matchningsregler eller förenade fält i inställningarna för kund- eller kontoförening.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392493"
---
# <a name="update-unification-settings"></a>Uppdatera föreningsinställningarna

Granska eller ändra eventuella inställningar när en förenad profil har skapats genom att utföra följande steg.

1. Gå till **Data** > **Förena**.

   För enskilda kunder (B2C) visar sidan **Förena** antalet förenade kundprofiler och paneler för vart och ett av sammanslagningsstegen.

   :::image type="content" source="media/m3_unified.png" alt-text="Skärmbild på sidan Data förena när data har enhetlig information." lightbox="media/m3_unified.png":::

   För företagskonton kunder (B2B) visar sidan **Förena** antalet förenade kontoprofiler och paneler för vart och ett av sammanslagningsstegen för konto. Om kontakterna var enhetliga visades antalet enhetliga kontaktprofiler och paneler för de olika kontaktföreningsstegen. Välj lämplig panel under **Förena konton** eller **Förena kontakter (förhandsversion)** beroende på vad du vill uppdatera.

   :::image type="content" source="media/b2b_unified.png" alt-text="Skärmdump av sidan Data förena efter att konto- och kontaktdata har förenats." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Panelen **Matchande villkor** visas endast om flera entiteter har markerats.

1. Välj vad du vill uppdatera:
   - [Källfält](#edit-source-fields) för att lägga till attribut eller entiteter eller ändra attributtyper. Information om hur du tar bort ett attribut finns i [Ta bort ett enhetligt fält](#remove-a-unified-field). Information om hur du tar bort en entitet finns i [Ta bort en enhetlig entitet](#remove-a-unified-entity).
   - [Dubblettposter](#manage-deduplication-rules) för att hantera dubblettregler eller kopplingsinställningar.
   - [Matchande villkor](#manage-match-rules) för att uppdatera matchande regler för två eller flera entiteter.
   - [Förenade kundfält](#manage-unified-fields) för att kombinera eller utesluta fält. Du kan också gruppera relaterade profiler i kluster.
   - [Semantiksa fält](#manage-semantic-fields-for-unified-contacts) för att hantera semantiska typer för enhetliga kontaktfält.
   - [Relationer](#manage-contact-and-account-relationships) för att hantera kontakten till kontorelationen.

1. När du har gjort ändringarna väljer du nästa alternativ:

   - [Kör matchande villkor](#run-matching-conditions) för att snabbt utvärdera kvaliteten på dina matchningsvillkor (deduplicering och matchningsregler) utan att uppdatera den enhetliga profilen. Alternativet **Kör endast matchande villkor** visas inte för en entitet.
   - [Förena profiler](#run-updates-to-the-unified-profile) för att köra matchningsvillkor och uppdatera entiteten förenad profil utan att påverka beroenden (till exempel utöka, segment eller mått). Beroende processer körs inte, men uppdateras enligt vad som [anges i uppdateringsschemat](schedule-refresh.md).
   - [Förena profil och beroenden](#run-updates-to-the-unified-profile) för att köra matchningsvillkor, uppdatera entiteten för förenad profil och uppdatera alla beroenden (till exempel utöka, segment eller mått). Alla processer körs automatiskt om. I B2B körs sammanslagning på både konto- och kontaktenheter som uppdaterar de förenade profilerna.

## <a name="edit-source-fields"></a>Redigera källfält

1. Välj **Redigera** på panelen **Källfält**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Skärmbild på sidan Källfält som visar antalet primära nycklar, mappade och omappade fält":::

   Antalet mappade och omappade fält som visas.

1. Markera **Välj entiteter och fält** om du vill lägga till andra attribut eller entiteter.

1. Alternativt kan du ändra primärnyckeln för en entitet, attributtyperna och växla **intelligent mappning** av och på. Mer information finns i [Välj fler källfält](map-entities.md).

1. Välj **Nästa** om du vill ändra dubblettreglerna eller välj **Spara och stäng** och återgå till [Uppdatera sammanslagningsinställningarna](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Ta bort ett enhetligt fält

Om du vill ta bort ett enhetligt fält måste fältet tas bort från alla beroenden, till exempel segment, mått, berikningar eller relationer.

1. När alla beroenden för fältet har tagits bort går du till **Data** > **Förena**.

1. Välj **Redigera** på panelen **förenade kundfält**.

1. Välj alla förekomster av fältet och välj sedan **Utelämna**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Skärmbild på sidan Förenade fält med valda fält och knappen Utelämna":::

1. Välj **Klart** för att bekräfta och välj sedan **Spara och stäng**.

   > [!TIP]
   > Om du ser meddelandet "Kunde inte spara förening. Den angivna resursen kan inte ändras eller tas bort på grund av beroenden nedströms." används fältet fortfarande i ett beroende nedströms.

1. Om fältet används i en regel för dubblettposter eller matchande villkor gör du följande. Annars går du till nästa steg.
   1. Välj **Redigera** på panelen **Dubblettposter**.
   1. Ta bort fältet från alla regler som det används i, om det finns några, och välj sedan **Nästa**.
   1. På sidan **Matchande villkor** tar du bort fältet från alla regler som det används i, om det finns några, och väljer sedan **Spara och stäng**.
   1. Välj **Förena** > **Förena kundprofiler och beroenden**. Vänta tills föreningen är klar innan du går vidare till nästa steg.

1. Välj **Redigera** på panelen **Källfält**.

1. Välj **Välj entiteter och fält** och avmarkera kryssrutan bredvid varje förekomst av fältet.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Skärmbild av dialogrutan Välj entiteter och fält med avmarkerade kryssrutor":::

1. Välj **Verkställ**.

1. Välj **Spara och stäng**.

1. Välj **Förena** > **Förena kundprofiler och beroenden** för att uppdatera den enhetliga profilen.

### <a name="remove-a-unified-entity"></a>Ta bort en enhetlig entitet

Om du vill ta bort en entitet som har förenats måste entiteten tas bort från alla beroenden, till exempel segment, mått, berikningar eller relationer.

1. När alla beroenden för entiteten har tagits bort går du till **Data** > **Förena**.

1. Välj **Redigera** på panelen **förenade kundfält**.

1. Välj alla fält för entiteten och välj sedan **Utelämna**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Skärmbild på Förenade fält med alla fält för en entitet valda och knappen Utelämna":::

1. Välj **Klart** för att bekräfta och välj sedan **Spara och stäng**.

   > [!TIP]
   > Om du ser meddelandet "Kunde inte spara förening. Den angivna resursen kan inte ändras eller tas bort på grund av beroenden nedströms." används entiteten fortfarande i ett beroende nedströms.

1. Välj **Redigera** på panelen **Dubblettposter**.

1. Ta bort alla regler från entiteten, om några, och välj sedan **Nästa**.

1. På sidan **Matchande villkor** väljer du entiteten och sedan **Ta bort**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Skärmbild av Matchande villkor med entitet vald och knappen Ta bort":::

1. Välj **Spara och stäng**.

1. Välj **Redigera** på panelen **Källfält**.

1. Välj **Välj entiteter och fält** och avmarkera kryssrutan bredvid entiteten.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Skärmbild av dialogrutan Välj entiteter och fält med entitetskryssrutan avmarkerad":::

1. Välj **Verkställ**.

1. Välj **Spara och stäng**.

1. Välj **Förena** > **Förena kundprofiler och beroenden** för att uppdatera den enhetliga profilen.

## <a name="manage-deduplication-rules"></a>Hantera regler för deduplicering

1. Välj **Redigera** på panelen **Dubblettposter**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Skärmbild på sidan med dubblettposter som visar antalet dubblettposter" lightbox="media/m3_duplicates_edit.png":::

   Antalet dubblettposter som hittades visas under **Dubbletter**. I kolumnen **Poster som är deduplicerade** visas vilka entiteter som hade dubblettposter samt procentandelen duplicerade poster.

1. För att välja en utökad entitet väljer du **Använd utökade entiteter**. Mer information: [Berikande för datakällor](data-sources-enrichment.md).

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

   1. Välj **Klar**.

1. Välj **Nästa** om du vill ändra matchande villkor eller välj **Spara och stäng** och återgå till [Uppdatera sammanslagningsinställningarna](#update-unification-settings).

## <a name="manage-match-rules"></a>Hantera matchningsregler

Du kan konfigurera om och finjustera de flesta matchningsparametrarna. Du kan inte lägga till eller ta bort enheter. Matchningsregler gäller inte för en enskild entitet.

1. Välj **Redigera** på panelen **Matchningsvillkor**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Skärmbild av sidan matchningsregel and villkor med statistik." lightbox="media/m3_match_edit.png":::

   På sidan visas matchningsordningen och definierade regler samt följande statistik:
   - **Unika källposter** visar antalet enskilda källposter som behandlades i förra matchningskörningen.
   - **Matchade och icke-matchade poster** visar hur många unika poster som finns kvar efter bearbetningen av matchningsreglerna.
   - **Endast matchade poster** visar antalet matchningar för alla dina matchningspar.

1. Välj **Visa senaste körning** om du vill visa resultatet för alla regler och deras poäng. Resultaten visas, inklusive de alternativa kontakt-ID:erna. Du kan hämta resultaten.

1. Om du vill visa resultatet och poängen för en viss regel markerar du regeln och **förhandsgranskar** den. Resultatet visas. Du kan hämta resultaten.

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

1. Välj **Nästa** om du vill ändra till förenade fält eller välj **Spara och stäng** och återgå till [Uppdatera sammanslagningsinställningarna](#update-unification-settings).

## <a name="manage-unified-fields"></a>Hantera förenade fält

1. Välj **Redigera** på panelen **förenade kundfält**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Skärmbild av förenade kundfält":::

1. Granska de kombinerade och uteslutna fälten och gör eventuella ändringar. Lägga till eller redigera CustomerID-nyckel eller grupprofiler i kluster. Mer information finns i [förenade kundfält](merge-entities.md).

1. För kunder eller konton, välj **Nästa** för att granska och [uppdatera den enhetliga profilen och beroenden](#run-updates-to-the-unified-profile). Eller välj **Spara och stäng** och återgå till [Uppdatera föreningsinställningarna](#update-unification-settings) att göra fler ändringar.

   Välj **Nästa** för kontakter om du vill hantera semantiska fält. Eller välj **Spara och stäng** och återgå till [Uppdatera föreningsinställningarna](#update-unification-settings) att göra fler ändringar.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Hantera semantiska fält för förenade kontakter

1. Välj **Redigera** på panelen **Semantiska fält**.

1. För att ändra den semantiska typen för ett enhetligt fält, välj en ny typ. För mer information, se [Definiera semantiska fält för förenade kontakter](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Välj **Nästa** om du vill hantera konto och kontakt relationer eller välj **Spara och stäng** och återgå till [Uppdatera sammanslagningsinställningarna](#update-unification-settings).

## <a name="manage-contact-and-account-relationships"></a>Hantera kontakt- och kontorelationer

1. Välj **Redigera** på panelen **Relationer**.

1. Ändra kontakt- och kontorelationen genom att ändra följande information:

   - **Sekundärnyckel från kontaktentitet**: Välj det attribut som kopplar din kontaktenhet till kontot.
   - **Till kontoentitet**: Välj den kontoentitet som är associerad med kontakten.

1. Välj **Nästa** om du vill granska inställningarna och [uppdatera den förenade profilen och beroendena](#run-updates-to-the-unified-profile), eller välj **Spara och stäng** och återgå till [Uppdatera inställningarna](#update-unification-settings) för att göra fler ändringar.

## <a name="run-matching-conditions"></a>Kör matchningsvillkor

Kör matchningsvillkor kör endast deduplicering och matchningsregler och uppdaterar entiteterna *deduplicering_* och *ConflationMatchPair*.

1. Från sidan **Data** > **Förena** välj **Kör endast matchningsvillkor**.

   Panelerna **Dubblettposter** och **Matchande villkor** visar status **Köad** eller **Uppdatering**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. När matchningsprocessen är klar väljer du **Redigera** på panelen **Matchande villkor**.

   :::image type="content" source="media/match-KPIs.png" alt-text="En liten skärmbild av de viktigaste måtten på sidan Matchning med siffror och detaljer.":::

1. Mer information finns i [Hantera dubblettregler](#manage-deduplication-rules) eller [Hantera matchningsregler](#manage-match-rules).

1. Kör matchningsprocessen igen eller [kör uppdateringar för profilen](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Köra uppdateringar till enhetlig profil

- För att köra matchningsvillkor och uppdatera entiteten för enhetlig profil *utan* att påverka beroenden (som kundkort, berikningar, segment eller åtgärder), välj **Unified customer profile**. För konton, välj **Förena konton** > **Förena profiler**. För kontakter välj **Förena kontakter (förhandsversion)** > **Förena profiler**. Beroende processer körs inte, men uppdateras enligt vad som [anges i uppdateringsschemat](schedule-refresh.md).
- För att köra matchande villkor, uppdatera den enhetliga profilen och alla beroenden och välj **Unified customer profile och beroenden**. Alla processer körs automatiskt om. För konton och kontaktpersoner väljer du **Förena konton** > **Förena profiler och beroenden**. Matchande villkor körs för både konton och kontakter som uppdaterar både enhetliga profiler och alla andra beroenden körs.

Alla paneler utom **källfält** visar **kö** eller **uppdatering**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Resultatet av en lyckad körning visas på sidan **Förena** med antalet förenad profil.
