---
title: Skapa en enhetlig kontaktprofil (förhandsversion)
description: Gå igenom samordningen av data och skapa en enda huvudprofil datauppsättning kontakter.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305045"
---
# <a name="create-a-unified-contact-profile-preview"></a>Skapa en enhetlig kontaktprofil (förhandsversion)

När du har [enat affärskonton](map-entities.md) kan du eventuellt ena kontakterna för dessa konton och länka de enhetliga kontakterna till de enhetliga kontona. Föreningsprocessen för kontakt mappar kontaktdata från flera datakällor, tar bort dubbletter, matchar data mellan enheter, ställer in semantisk mappning, skapar relationer mellan kontakter och konton och skapar sedan en enhetlig kontaktprofil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

De första stegen är identiska med stegen för att ena konton.

## <a name="prerequisites"></a>Förutsättningar

Konto- och kontaktposter måste ha en unik nyckel (kallas för en utländsk nyckel) som kopplar ihop dem. Exempelvis ett konto-ID som finns i kontoposten och kontaktpersonsposten som kopplar ihop kontot och kontaktpersonen.

## <a name="preview-limitations"></a>Begränsningar i förhandsversionen

- Kontakter utan en länk till ett konto ignoreras.
- Om ett konto är deduplicerat identifieras en post utifrån inställningarna för kopplingen. Förlorarposter väljs inte och tas därför bort. Kontakter som är associerade med de förlorande posterna ignoreras.
- Ett konto kan ha flera kontakter, men en kontakt är länkad till ett enda konto.
- De kontaktattribut som mappats i det semantiska mappningssteget för bildning är de enda attribut som kan visas på kundkorten. Det finns emellertid 17 attribut.

## <a name="select-source-fields"></a>Välj källfält

1. Under **Förena kontakter (förhandsversion)** väljer du **Kom igång**.

1. [Välj entiteter och fält](map-entities.md) för dina kontaktdatakällor, inklusive primärnycklar och attributtyper.

1. Välj **Nästa**.

## <a name="remove-duplicate-records"></a>Ta bort dubblettposter

1. Alternativt [kan du definiera dubblettregler](remove-duplicates.md) för valda entiteter.

1. Välj **Nästa**.

## <a name="match-conditions"></a>Matchningsvillkor

1. [Definiera matchningsorder och reglerna](match-entities.md) entitetsöverskridande matchning

1. Välj **Nästa**.

## <a name="unify-contact-fields"></a>Förena kontaktfält

1. [Kombinera och utesluta kontaktfält](merge-entities.md).

1. Välj **Nästa**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definiera semantiska fält för förenade kontakter

I det här steget i processen mappas de enhetliga kontaktfälten till olika typer av system. I B till B visar kundkort konton. När du väljer kortet visas alla kontakter som är associerade med kontot. Fälten du mappar i det här steget är de fält som visas på korten.

1. Välj den semantiska typen som mappas till varje enhetligt fält. Välj **Inget** om det inte finns någon semantisk typ.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Skärmbild på en sida med fält för att definiera olika typer av semantiska typer." lightbox="media/semantic_mapping.png":::

1. Välj **Nästa** när du har mappat alla enhetliga fält.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Ange relationen mellan kontakter och konton

Detta steg i sammanslagningsprocessen kopplar din kontaktdata till motsvarande kontodata.

1. Ange följande information för varje enhet:

   - **Sekundärnyckel från kontaktentitet**: Välj det attribut som kopplar din kontaktenhet till kontot.
   - **Till kontoentitet**: Välj den kontoentitet som är associerad med kontakten.

   :::image type="content" source="media/contact_relationship.png" alt-text="Skärmbild på sidan Relation om du vill ansluta entiteterna för kontakt och konto.":::

1. Välj **Nästa**.

## <a name="review-contact-unification"></a>Granska kontaktförening

Granska sammanfattningen av ändringarna, skapa en enhetlig profil och granska resultatet.

### <a name="review-and-create-contact-profiles"></a>Granska och skapa kontaktprofiler

Det sista steget i processen visar en sammanfattning av stegen i processen och ger en chans att göra ändringar innan du skapar en enhetlig kontaktprofil.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Skärmbild av gransknings- och skapa kontaktprofiler.":::

1. Välj **Redigera** på något av kontaktföreningsstegen för att granska och göra eventuella ändringar.

1. Om du är nöjd med dina val väljer du **Skapa kontaktprofiler**. Sidan **Förena** visas medan enhetlig kontaktprofil skapas.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Skärmbild på sidan förena kontakter med paneler som visar Köad eller Uppdatera.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritmen tar en stund att slutföra och du kan inte ändra konfigurationen förrän den är klar.

### <a name="view-the-results-of-contact-unification"></a>Visa resultat av kontaktförening

När föreningen är klar visa sidan **Data** > **Förena** antal förenade kontaktprofiler. Resultatet av varje steg i processen visas på varje panel. Till exempel **Källfält** visar antalet mappade attribut (fält) och **Dubblettposter** visar antalet dubblettposter som hittats.

:::image type="content" source="media/unified_contacts.png" alt-text="Skärmbild på sidan Data förena när kontakter är förenade.":::

> [!TIP]
> Panelen **Matchande villkor** visas endast om flera entiteter har markerats.

Vi rekommenderar att du granskar resultaten, särskilt kvaliteten på dina [matchningsregler](data-unification-update.md#manage-match-rules) och förfinar dem vid behov.

När det behövs [kan du ändra inställningarna för kontaktföreningen](data-unification-update.md) och köra den enhetliga profilen igen.

### <a name="verify-output-entities-from-data-unification"></a>Verifiera utdataenheter från dataförening

Gå till **Data** > **Entiteter** för att verifiera utdataenheterna.

Entiteten för en enhetlig kontaktprofil, *ContactProfile*, visas i avsnittet **Semantiska entiteter** Vid den första lyckade körningen skapas enhetlig entitet *ContactProfile*. Alla efterföljande körningar visar den entiteten.

Entiteten *ContactsCustomer* (förhandsgranskning) skapas och visas i avsnittet **Profiler**. Entiteten innehåller kontaktdata utan länkar till konton. Entiteten används som indata i mappnings- och relationsstegen för kontakter.

Duplicerings- och konditorientiteter skapas och visas i avsnittet **System**. En deduplicerad enhet för var och en av källentiteterna skapas med namnet **Deduplication_DataSource_Entity**. Entiteten **ContactsConflationMatchPairs** innehåller information om matchningar för flera entiteter.

En utdataenhet för deduplicering innehåller följande information:
- ID/Nycklar
  - Primärnyckel och Alternativt ID-fält. Fältet Alternativt ID består av alla alternativa ID:n som identifieras för en post.
  - Deduplication_GroupId visar gruppen eller klustret som identifieras i en entitet som grupperar alla liknande poster utifrån de angivna dedupliceringsfälten. Det används för systembearbetning. Om det inte finns några manuella dedupliceringsregler som anges och systemdefinierade dedupliceringsregler gäller kanske inte det här fältet finns i entiteten för dedupliceringsutdata.
  - Deduplication_WinnerId: Det här fältet innehåller vinnande ID från de identifierade grupperna eller klustren. Om Deduplication_WinnerId är samma värde som primärnyckeln för en post innebär det att posten är vinnarposten.
- Fält som används för att definiera dedupliceringsreglerna.
- Regel- och poängfält som anger vilka av dedupliceringsregler som tillämpats och poängen som returneras av den matchande algoritmen.

## <a name="next-step"></a>Nästa steg

Konfigurera [aktiviteter](activities.md), [berikning](enrichment-hub.md)eller [relationer](relationships.md) till mer information om kontakterna.
