---
title: Sök och filtrera kundprofiler
description: Hitta snabbt information om enhetliga kundprofiler och filter för angivna attribut.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270088"
---
# <a name="customer-profiles-search--filter-index"></a>Kundprofiler: Sök- och filterindex

Resultatet av att förena kunddata är en kundprofils entitet som tillhandahåller en enhetlig vy till den totala kundbasen. Om du snabbt vill [hitta information om en viss kund eller grupp](customer-profiles.md) kan du konfigurera funktionerna **Sök** och **Filter** på sidan **Kunder**. Läs vidare om du vill veta hur administratörer kan redigera attributen på sidan **Sök och filtrera index** som är tillgängliga för användare för sökning och filtrering.

> [!div class="mx-imgBorder"]
> ![Sökfilter](media/search-filter.png "Sökfilter")

## <a name="add-fields-and-specify-attributes"></a>Lägg till fält och ange attribut

Om det är första gången du definierar sökbara attribut som en administratör måste du definiera indexerade fält först. Vi föreslår att du väljer alla attribut som användarna kan söka i och filtrera kunder på i sidan **kunder**. Du kan endast ange attribut som finns i entiteten kundprofil som du skapade under dataföreningsprocessen.

1. Öppna sidan **Kunder** och välj **Sök & filtrera index**.

2. Välj **+ Lägg till** för att ange indexerade fält.

3. Välj attribut i listan som du vill lägga till som indexerade fält. Du kan alltid lägga till fler attribut genom att välja **Lägg till**. Du kan även ta bort valda attribut genom att välja symbolen **Ta bort**.

## <a name="explore-the-indexed-customer-fields-table"></a>Utforska tabellen indexerade kundfält

Följande information presenteras i tabellen.

- **Namn**: representerar attributets namn som det visas i entiteten kundprofil.
- **Datatyp**: anger om datatypen är en sträng, ett tal eller ett datum.
- **Ingår i sökningen**: anger om det här attributet kan användas för att söka efter kunder på sidan **Kunder** med hjälp av fältet **Sök**.
- **Lägg till filter**: kontroll för att definiera hur det här attributet kan användas för filtrering på sidan **kunder**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Redigera filtreringsalternativ för ett givet attribut

Menyn **filtrera** på sidan **kunder** kan innehålla ett varierande antal attributvärden (t.ex. olika åldersgrupper för att filtrera kunder).

1. Välj **Lägg till filter** för ett givet attribut på sidan **Sök och filtrera index**. Du kan ange antalet resultat och i vilken ordning de ska ordnas. Beroende på attributets datatyp visas någon av följande rutor.

- Attribut av strängtyp: ange antalet önskade resultat i fönstret **Alternativ för strängfilter** och den ordning som de ska ordnas efter.

- Attribut av numerisk typ: ange intervaller som ingår i fönstret **Alternativ för nummerfilter** och den ordning som de ska ordnas efter.

- Attribut av datumtyp: ange intervaller som ingår i fönstret **Alternativ för datumfilter** och den ordning som de ska ordnas efter.

2. Välj **Spara** för att införa ändringarna.

3. Välj **kör** när du är redo att tillämpa inställningarna.

## <a name="next-steps"></a>Nästa steg

Gå till sidan **Kunder** om du vill söka efter kundprofiler eller använda de indexerade fälten och visa en deluppsättning av alla kundprofiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]