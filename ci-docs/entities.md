---
title: Entiteter i Customer Insights
description: Visa data på sidan Entiteter.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183607"
---
# <a name="entities-in-customer-insights"></a>Entiteter i Customer Insights

När [du har konfigurerat datakällorna](data-sources.md) går du till sidan **entiteter** för att utvärdera kvaliteten hos hämtade data. Entiteter betraktas som datauppsättningar. Flera funktioner i Dynamics 365 Customer Insights är byggda runt dessa entiteter. Om du granskar dem noga kan du kontrollera hur de funktionerna ser ut.

När du arbetar i Customer Insights och utökar dina data eller skapar segment, mått och aktiviteter visas entiteterna som skapas från dessa åtgärder på sidan **Entiteter**.

## <a name="view-a-list-of-entities"></a>Visa en lista över entiteter

Gå till **Data** > **Entiteter** om du vill visa en lista med entiteter. Följande information visas för varje entitet.

- **Namn**: Namnet på dataentiteten. Om en varningssymbol visas bredvid ett entitetsnamn betyder det att det inte gick att läsa in data för den entiteten.
- **Källa**: Typ av datakälla som hämtade entiteten.
- **Uppdaterad**: Tidpunkt då enheten senast uppdaterades.
- **Status**: Information om den senaste uppdateringen av entiteten.

## <a name="explore-a-specific-entitys-data"></a>Utforska data för en specifik entitet

1. Gå till **Data** > **Entiteter**.
1. Välj en entitet för att öppna informationssidan.  
1. Utforska de olika fält och poster som ingår i entiteten.

- Fliken **Attribut** är markerad som standard och visar detaljer för den valda enheten, såsom fältnamn, datatyper och typer. Kolumnen **Typ** visar Common Data Model associerade typer som antingen identifieras automatiskt av systemet eller som [mappas manuellt](map-entities.md) av användarna. Dessa typer är semantiska och kan skilja sig åt från attributens datatyper. Fältet *E-post* nedan har exempelvis datatypen *Sträng* men dess (semantiska) Common Data Model-typ kan vara *Email-post*, *EmailAddress* eller *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Fälttabell.":::

   > [!NOTE]
   > På den här sidan visas endast ett exempel på entitetens data. Om du vill visa hela datauppsättningen går du till sidan **Datakällor**, väljer en entitet och sedan **Redigera** och visar sedan entitetens data med Power Query-redigeraren som förklaras i [Datakällor](data-sources.md).

   Om du vill lära dig mer om data som tas med i entiteten kan du få en del viktiga egenskaper för informationen, t.ex. nullvärden, saknade värden, unika värden, antal och fördelningar, som kan användas för dina data i kolumnen **Sammanfattning**. Välj diagramikonen om du vill visa en sammanfattning av data.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Datasammanfattningstabell.":::

- Fliken **Data** visar information om enskilda poster i entiteten. Informationen i listan beror på entitetens datatyp.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Välj entitet.":::

- Med fliken **Rapporter** (tillgänglig för vissa entiteter) kan du visualisera dina data genom att skapa en rapport och inkluderar följande kolumner:

  - **Rapportnamn**: Namn på rapporten.
  - **Skapades den**: Namnet på den person som skapade entiteten.
  - **Skapad**: datum och tid då entiteten skapades.
  - **Redigerades den**: Namnet på den person som ändrade entiteten.
  - **Redigerad**: datum och tid då entiteten ändrades.

## <a name="entity-specific-information"></a>Entitetsspecifik information

I följande avsnitt finns information om vissa systemskapade entiteter.

### <a name="corrupted-data-sources"></a>Skadade datakällor

Fält från en inmatad datakälla kan innehålla skadade data. Poster med skadade fält visas i entiteter som skapats av systemet. Om du känner till skadade poster kan du identifiera vilka data som ska granskas och uppdateras i källsystemet. Efter nästa uppdatering av datakällan skickas de korrigerade posterna till Customer Insights och sedan vidare till processer nedströms. 

Exempelvis har datatypen &quot;datum&quot; angetts för kolumnen &quot;födelsedag&quot;. En kundpost har födelsedagen angiven som &quot;1977-01-01&quot;. Systemet flaggar då denna post som skadad. Någon kan nu ändra födelsedagen i källsystemet till &quot;1977&quot;. Efter en automatisk uppdatering av datakällor har fältet nu ett giltigt format och posten tas bort från den skadade entiteten.

Gå till **Data** > **Entiteter** och leta efter skadade entiteter i avsnittet **System**. Namnschema för skadade entiteter: &quot;DataSourceName_EntityName_corrupt&quot;. Välj en skadad entitet om du vill identifiera skadade fält och orsaken på individuell postnivå.

   :::image type="content" source="media/corruption-reason.png" alt-text="Orsak till fel.":::

Customer Insights behandlar fortfarande skadade poster. Däremot kan de orsaka problem när du arbetar med enhetliga data.

Följande kontroller körs på inmatade data för att visa skadade poster:

- Värdet för ett fält stämmer inte överens med datatypen för kolumnen.
- Fält innehåller tecken som gör att kolumnerna inte matchar det förväntade schemat. Till exempel: felaktigt formaterade offerter, icke-förfallna offerter eller nyradstecken.
- Om det finns kolumner med datetime/date/datetimeoffset måste formatet anges i modellen om det inte följer standard ISO-formatet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
