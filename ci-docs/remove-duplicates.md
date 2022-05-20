---
title: Ta bort dubbletter innan data samordnas
description: Det andra steget i processen är att välja vilken post som ska behållas när dubbletter hittas.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741670"
---
# <a name="remove-duplicates-before-unifying-data"></a>Ta bort dubbletter innan data samordnas

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Det här steget innebär eventuellt att du kan skapa regler för hantering av dubblettposter inom en entitet. Med *dedupliceringen* identifieras dubblettposter och kopplas till en post. Källposter länkas till den sammanslagna posten med alternativa ID. Om reglerna inte konfigureras tillämpas systemdefinierade regler.

## <a name="include-enriched-entities-preview"></a>Inkludera utökade entiteter (förhandsgranskning)

Om du har förädlat entiteter på datakälla nivå för att förbättra resultaten markerar du dem. Mer information: [Berikande för datakällor](data-sources-enrichment.md).

1. På sidan **Dubblettposter**, välj **Använd berikade entiteter** högst upp på sidan.

1. Från rutan **Använd berikade entiteter** välj en eller flera berikade entiteter.

1. Välj **Utfört**.

## <a name="define-deduplication-rules"></a>Definiera regler för deduplicering

1. På sidan **Dubblettposter** markerar du en entitet och väljer **Lägg till regel** för att definiera dubblettreglerna.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Skärmbild på sidor med dubblettposter med Visa fler uppgifter":::

   1. I fönstret **Lägg till regel**, ange följande information:
      - **Välj fält**: Välj i listan över tillgängliga fält från den entitet som du vill söka efter dubbletter i. Välj fält som troligen är unika för varje enskild kund. Till exempel en e-postadress eller kombinationen av namn, ort och telefonnummer.
      - **Normalisera**: Välj bland följande normaliseringsalternativ för de valda attributen.
        - **Siffror**: Konverterar andra numeriska system, t.ex. romerska tecken till arabiska siffror. *VIII* blir *8*.
        - **Symboler**: Tar bort alla symboler och specialtecken. *Head&Shoulder* blir *HeadShoulder*.
        - **Text till gemener: Konverterar alla tecken till gemener**. *ALLA VERSALER och rubriker* blir *alla versaler och rubriker*.
        - **Typ (telefon, namn, adress, organisation)**: Standardiserar namn, titlar, telefonnummer, adresser osv.
        - **Unicode till ASCII**: Konverterar unicode-notation till ASCII-tecken. */u00B2* blir *2*.
        - **Tomt utrymme**: Tar bort alla blanksteg. *Hej   världen* blir *Hejvärlden*.
      - **Precision**: Ange vilken precisionsnivå som ska tillämpas för detta villkor.
        - **Grundläggande**: Välj mellan *Låg (30 %)*, *Medel (60 %)*, *Hög (80 %)* och *Exakt (100 %)*. Välj **Exakt** om du endast vill matcha poster som matchar 100 procent.
        - **Anpassad**: Ange en procentandel som posterna måste matcha. Systemet matchar endast poster som passerar tröskelvärdet.
      - **Namn**: Namn för regeln.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Skärmbild av rutan Lägg till regel för att ta bort dubbletter.":::

   1. Alternativt väljer du **Lägg till** > **Lägg till villkor** om du vill lägga till fler villkor i regeln. Villkoren är kopplade till en logisk OCH-operator och körs därför endast om alla villkor uppfylls.

   1. Alternativt **Lägg till** > **Lägg till undantag** till [lägga till undantag till regeln](match-entities.md#add-exceptions-to-a-rule). Undantag används för att hantera få fall av falskt positiva och falskt negativa.

   1. Välj **Klar** för att skapa regeln.

1. Alternativt kan du [lägga till fler regler](#define-deduplication-rules).

1. Välj en entitet och **redigera inställningarna för kopplade dokument**.

1. I rutan **Kopplingsinställningar**:
   1. Välj ett av tre alternativ för att avgöra vilken post som ska behållas om en dubblett påträffas:
      - **Mest ifylld**: Identifierar posten med flest ifyllda attributfält som vinnarpost. Det här är standardalternativet för sammanfogning.
      - **Senaste**: Identifierar vinnarpost baserat på aktualitet. Kräver ett datum eller ett numeriskt fält för att definiera aktualitet.
      - **Minst aktuell**: Identifierar vinnarpost baserat på lägsta aktualitet. Kräver ett datum eller ett numeriskt fält för att definiera aktualitet.
      
      Vid händelse av en händelse är posten den med MAX(PK) eller det större primärnyckelns värde.
      
   1. Om du vill definiera kopplingsinställningar för enskilda attribut för en entitet väljer du **Avancerat** längst ned i fönstret. Du kan till exempel välja att behålla den senaste e-postadressen OCH den mest fullständiga adressen från olika poster. Expandera entiteten om du vill visa alla attribut och definiera vilket alternativ som ska användas för enskilda attribut. Om du väljer ett recency-baserat alternativ måste du också ange ett datum- och tidsfält som definierar recency.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Fönstret Avancerade sammanslagningsinställningar som visar senaste e-post och fullständig adress":::

   1. Välj **Klart** för att tillämpa kopplingsinställningar.

1. När du har definierat dedupliceringsreglerna och sammanslagningsinställningarna väljer du **Nästa**.
  
> [!div class="nextstepaction"]
> [Nästa steg för en enskild entitet: Förena fält](merge-entities.md)

> [!div class="nextstepaction"]
> [Nästa steg för flera entiteter: Matchande villkor](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Dedupliceringsutdata som en entitet

Med dubbleringsprocessen skapas en ny deduplicerad entitet för alla källentiteter. Dessa entiteter finns tillsammans med **ConflationMatchPairs:CustomerInsights** i avsnittet **System** på sidan **Entiteter**, med namnet **Deduplication_DataSource_Entity**.

En utdataenhet för deduplicering innehåller följande information:

- ID/Nycklar
  - Primärnyckel och Alternativt ID-fält. Fältet Alternativt ID består av alla alternativa ID:n som identifieras för en post.
  - Deduplication_GroupId visar gruppen eller klustret som identifieras i en entitet som grupperar alla liknande poster utifrån de angivna dedupliceringsfälten. Det används för systembearbetning. Om det inte finns några manuella dedupliceringsregler som anges och systemdefinierade dedupliceringsregler gäller kanske inte det här fältet finns i entiteten för dedupliceringsutdata.
  - Deduplication_WinnerId: Det här fältet innehåller vinnande ID från de identifierade grupperna eller klustren. Om Deduplication_WinnerId är samma värde som primärnyckeln för en post innebär det att posten är vinnarposten.
- Fält som används för att definiera dedupliceringsreglerna.
- Regel- och poängfält som anger vilka av dedupliceringsregler som tillämpats och poängen som returneras av den matchande algoritmen.

[!INCLUDE[footer-include](includes/footer-banner.md)]
