---
title: Entiteter och datauppsättningar
description: Visa data på sidan Entiteter.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 137de726b243b501491fcbe7866820aaee26097fcf379270c423c277374ae9a4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033837"
---
# <a name="entities-in-audience-insights"></a>Entiteter i målgruppsinsikter

När [du har konfigurerat datakällorna](data-sources.md) går du till sidan **entiteter** för att utvärdera kvaliteten hos hämtade data. Entiteter betraktas som datauppsättningar. Flera funktioner i Dynamics 365 Customer Insights är byggda runt dessa entiteter. Om du granskar dem noga kan du kontrollera hur de funktionerna ser ut.

Sidan **entiteter** visar entiteter och flera kolumner:

- **Namn**: namnet på entiteten för data. Om en varningssymbol visas bredvid ett entitetsnamn betyder det att det inte gick att läsa in data för den entiteten.
- **Källa**: typen av datakälla som hämtade entiteten
- **Skapades den**: Namnet på den person som skapade entiteten
- **Skapad**: datum och tid då entiteten skapades
- **Uppdaterad den**: Namnet på den person som uppdaterade entiteten
- **Senast uppdaterad**: datum och tid för den senaste uppdateringen av entiteten
- **Senast uppdaterad**: datum och tid för när data uppdaterades senast

## <a name="explore-a-specific-entitys-data"></a>Utforska data för en specifik entitet

Välj en entitet för att utforska de olika fält och poster som ingår i entiteten.

> [!div class="mx-imgBorder"]
> ![Välj entitet.](media/data-manager-entities-data.png "Välj en entitet")

- Fliken **Data** visar en tabell med information om enskilda poster i entiteten.

> [!div class="mx-imgBorder"]
> ![Fälttabell.](media/data-manager-entities-fields.PNG "Fälttabell")

- Fliken **Attribut** är markerad som standard och visar en tabell för att granska information om den valda entiteten, till exempel fältnamn, datatyper och typer. Kolumnen **Typ** visar Common Data Model associerade typer som antingen identifieras automatiskt av systemet eller som [mappas manuellt](map-entities.md) av användarna. Dessa typer är semantiska och kan skilja sig åt från attributens datatyper. Fältet *E-post* nedan har exempelvis datatypen *Text*, men dess (semantiska) Common Data Model-typ kan vara *E-post* eller *E-postadress*.

> [!NOTE]
> I båda tabellerna visas endast ett exempel på entitetens data. Om du vill visa hela datauppsättningen går du till sidan **Datakällor**, väljer en entitet och sedan **redigera** och visar sedan entitetens data med Power Query redigeraren som förklaras i [Datakällor](data-sources.md).

Om du vill lära dig mer om data som tas med i entiteten kan du få en del viktiga egenskaper för informationen, t.ex. nullvärden, saknade värden, unika värden, antal och fördelningar, som kan användas för dina data i kolumnen **Sammanfattning**.

Välj diagramikonen om du vill visa en sammanfattning av data.

> [!div class="mx-imgBorder"]
> ![Sammanfattningssymbol.](media/data-manager-entities-summary.png "Datasammanfattningstabell")

## <a name="entity-specific-information"></a>Entitetsspecifik information

I följande avsnitt finns information om vissa systemskapade entiteter.

### <a name="corrupted-data-sources"></a>Skadade datakällor

Fält från en inmatad datakälla kan innehålla skadade data. Poster med skadade fält visas i entiteter som skapats av systemet. Om du känner till skadade poster kan du identifiera vilka data som ska granskas och uppdateras i källsystemet. Efter nästa uppdatering av datakällan skickas de korrigerade posterna till Customer Insights och sedan vidare till processer nedströms. 

Exempelvis har datatypen &quot;datum&quot; angetts för kolumnen &quot;födelsedag&quot;. En kundpost har födelsedagen angiven som &quot;1977-01-01&quot;. Systemet flaggar då denna post som skadad. Någon kan nu ändra födelsedagen i källsystemet till &quot;1977&quot;. Efter en automatisk uppdatering av datakällor har fältet nu ett giltigt format och posten tas bort från den skadade entiteten. 

Gå till **Data** > **Entiteter** och leta efter skadade entiteter i avsnittet **System**. Namnschema för skadade entiteter: &quot;DataSourceName_EntityName_corrupt&quot;.

Customer Insights behandlar fortfarande skadade poster. Däremot kan de orsaka problem när du arbetar med enhetliga data.

Följande kontroller körs på inmatade data för att visa skadade poster: 

- Värdet för ett fält stämmer inte överens med datatypen för kolumnen.
- Fält innehåller tecken som gör att kolumnerna inte matchar det förväntade schemat. Till exempel: felaktigt formaterade offerter, icke-förfallna offerter eller nyradstecken.
- Om det finns kolumner med datetime/date/datetimeoffset måste formatet anges i modellen om ISO-standardformatet inte används.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
