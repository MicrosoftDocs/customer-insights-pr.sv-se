---
title: Berikande av datakällor
description: Berika datakällor innan du går igenom dataföreningsprocess.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800303"
---
# <a name="enrichment-for-data-sources-preview"></a>Berika för datakällor (förhandsversion)

Använd data från källor som Microsoft och andra partner för att utöka dina kunddata innan data förenas. Berikning av datakälla ger bättre dataresultat och högre kvalitet som kan hjälpa till att uppnå bättre resultat när dina data har förenats. Om du till exempel använder ett normaliserat och standardiserat format för adresser ökar kvaliteten på matchningsresultatet. En lista över de utökande program som stöds finns i [alternativ för berikning av datakälla](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Berika en datakälla

Du måste ha deltagar- eller administratörsbehörighet att skapa eller redigera utökar. Mer information finns under [Behörigheter](permissions.md).  

1. Gå till **Data** > **Förena**. Välj den entitet du vill utöka och välj ett attribut som primärnyckel för entiteten. För mer information, se [Välj primärnyckel](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Gå till **Data** > **Datakällor**.

1. Välj den vertikala ellipsen (&vellip;) bredvid datakälla du vill berika och markera **Berika**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Sida för berikande av datakällor.":::

   Fliken **Upptäck** visar [alternativ för berikning av datakälla som stöds](#supported-data-source-enrichments).

1. Välj **Berika mina data** om du vill konfigurera berikande av datakällor. Namn på utdataentitet fylls i automatiskt.

## <a name="supported-data-source-enrichments"></a>Berikande av datakällor som stöds

Följande berikningar är för närvarande tillgängliga för datakällor. Detaljerad information om hur du konfigurerar berikning finns i detalj.

- [Utökade adresser](enrichment-enhanced-addresses.md)
- [Berikade företagsdata](enrichment-enhanced-company-data.md)
- [Identifiera data från LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Hantera befintliga berikningar för datakällor

Gå till fliken **Mina berikningar** om du vill visa alla konfigurerade berikningar.

Markera förbättringen om du vill visa tillgängliga alternativ. Du kan också välja den stående ellipsen (&vellip;) för ett listobjekt om du vill visa alternativen för. Om du har konfigurerat flera förbättringar kan du använda sökrutan för att hitta den snabbt.

Du kan visa, redigera, köra eller ta bort berika datakälla. Mer information finns i [Hantera befintliga berikningar](enrichment-hub.md).
