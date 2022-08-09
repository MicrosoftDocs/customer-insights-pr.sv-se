---
title: Berika för datakällor (förhandsversion)
description: Berika datakällor innan du går igenom dataföreningsprocess.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207205"
---
# <a name="enrichment-for-data-sources-preview"></a>Berika för datakällor (förhandsversion)

Använd data från källor som Microsoft och andra partner för att utöka dina kunddata innan data förenas. Berikning av datakälla ger bättre dataresultat och högre kvalitet som kan hjälpa till att uppnå bättre resultat när dina data har förenats. Om du till exempel använder ett normaliserat och standardiserat format för adresser ökar kvaliteten på matchningsresultatet. En lista över de utökande program som stöds finns i [alternativ för berikning av datakälla](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Berika en datakälla

Du måste har [behörigheter](permissions.md) för deltagare eller administratör för att skapa eller redigera utökar.  

1. Gå till **Data** > **Förena**. Välj den entitet du vill utöka och välj ett attribut som [primärnyckel](map-entities.md#select-primary-key-and-semantic-type-for-attributes) för entiteten.

1. Gå till **Data** > **Datakällor**.

1. Välj den vertikala ellipsen (&vellip;) bredvid datakälla du vill berika och markera **Berika**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Sidan Datakällor med berika markerad":::

   Fliken **Upptäck** visar [alternativ för berikning av datakälla som stöds](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Sida för berikande av datakällor.":::

1. Välj **Berika mina data** om du vill konfigurera berikande av datakällor. Namn på utdataentitet fylls i automatiskt.

## <a name="supported-data-source-enrichments"></a>Berikande av datakällor som stöds

Följande berikningar är för närvarande tillgängliga för datakällor. Detaljerad information om hur du konfigurerar berikning finns i detalj.

- [Utökade adresser](enrichment-enhanced-addresses.md)
- [Berikade företagsdata](enrichment-enhanced-company-data.md)
- [Identifiera data från LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Hantera befintliga berikningar för datakällor

Gå till **Data** > **Berikning**. På fliken **Mina berikningar** visar du de konfigurerade berikningar, deras status, antal utökade kunder och sista gången data uppdaterades. Du kan sortera listan med utökar efter valfri kolumn eller använda sökrutan för att hitta det utökande du vill hantera.

Markera förbättringen om du vill visa tillgängliga alternativ. Du kan också välja den stående ellipsen (&vellip;) för ett listobjekt om du vill visa alternativen för.

Du kan visa, redigera, köra eller ta bort berika datakälla. Mer information finns i [Hantera befintliga berikningar](enrichment-hub.md#manage-existing-enrichments).
