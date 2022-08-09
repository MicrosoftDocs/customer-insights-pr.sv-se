---
title: Hantera sök- och filterindex för kundprofiler
description: Hitta snabbt information om enhetliga kundprofiler och filter för angivna attribut.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187931"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Hantera sök- och filterindex för kundprofiler

Resultatet av att förena kunddata är entitet *kund* som tillhandahåller en enhetlig vy till den totala kundbasen. För användare som snabbt vill [hitta information om en viss kund eller grupp](customer-profiles.md) måste administratören konfigurera funktionerna **Sök** och **Filter** på sidan **Kunder**.

   :::image type="content" source="media/search-filter.png" alt-text="Sökfilter":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definiera sökbara attribut och indexerade fält

Om det är första gången du definierar sökbara attribut som en administratör måste du definiera indexerade fält först. Vi föreslår att du väljer alla attribut som användarna kan söka i och filtrera kunder på i sidan **kunder**. Du kan endast ange attribut som finns i entiteten *kund* som du skapade under dataföreningsprocessen.

1. Gå till **Kunder** och välj **Sök & filtrera index**.

1. Markera **+ Lägg till**.

1. Välj attribut i listan som du vill lägga till som indexerade fält och klicka på **Tillämpa**.

1. Om du vill lägga till fler attribut väljer du **Lägg till**. Om du vill ta bort en ett valt attribut markerar du attribut och väljer **Ta bort**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Sök och filtrera indexsida":::

1. Välj **kör** när du är redo att tillämpa sök- och filtreringsinställningarna. När ändringarna har bearbetats hittar du dem i [kundkorten på sidan Kund](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definiera filtreringsalternativ för ett givet attribut

Ställ in fälten som kan användas för att filtrera kunder på sidan **Kunder**.

1. Gå till **Kunder** och välj **Sök & filtrera index**.

1. Välj ett attribut och **Lägg till filter**. Definiera antalet resultat och i vilken ordning de ska ordnas. Beroende på attributets datatyp visas någon av följande rutor.

   - Attribut av strängtyp: ange antalet önskade resultat i fönstret **strängfilter** och den ordning som de ska ordnas efter.

   - Attribut av numerisk typ: ange intervaller som ingår i fönstret **nummerfilter** och den ordning som de ska ordnas efter.

   - Attribut av datumtyp: ange intervaller som ingår i fönstret **datumfilter** och den ordning som de ska ordnas efter.

1. Välj **OK**. Upprepa för alla attribut som du vill filtrera efter.

1. Välj **kör** när du är redo att tillämpa sök- och filtreringsinställningarna. När ändringarna har bearbetats hittar du dem i [kundkorten på sidan Kund](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Visa indexerade kundfält

På sidan **Sök och filtrera index** visas följande information:

- **Namn**: representerar attributets namn som det visas i entiteten *kund*.
- **Datatyp**: anger om datatypen är en sträng, ett tal eller ett datum.
- **Ingår i sökningen**: anger om det här attributet kan användas för att söka efter kunder på sidan **Kunder** med hjälp av fältet **Sök**.
- **Lägg till filter**: kontroll för att definiera hur det här attributet kan användas för filtrering på sidan **kunder**.

## <a name="next-steps"></a>Nästa steg

Gå igenom [sidan med enhetliga profiler](customer-profiles.md) om du vill söka efter profiler eller använd de indexerade fälten för att se en deluppsättning av alla enhetliga profiler.

[!INCLUDE [footer-include](includes/footer-banner.md)]
