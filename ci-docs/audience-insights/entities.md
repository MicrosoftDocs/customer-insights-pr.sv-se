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
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049416"
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

## <a name="exploring-a-specific-entitys-data"></a>Utforska data för en specifik entitet

Välj en entitet för att utforska de olika fält och poster som ingår i entiteten.

> [!div class="mx-imgBorder"]
> ![Välj en entitet](media/data-manager-entities-data.png "Välj en entitet")

- Fliken **Data** visar en tabell med information om enskilda poster i entiteten.

> [!div class="mx-imgBorder"]
> ![Fälttabell](media/data-manager-entities-fields.PNG "Fälttabell")

- Fliken **Attribut** är markerad som standard och visar en tabell för att granska information om den valda entiteten, till exempel fältnamn, datatyper och typer. Kolumnen **Typ** visar Common Data Model associerade typer som antingen identifieras automatiskt av systemet eller som [mappas manuellt](map-entities.md) av användarna. Dessa är semantiska typer som kan skilja sig från attributens datatyper, t.ex. fältet *E-post* nedan har datatypen *Text* men dess (semantiska) Common Data Model-typ kan vara *E-post* eller *EmailAddress*.

> [!NOTE]
> I båda tabellerna visas endast ett exempel på entitetens data. Om du vill visa hela datauppsättningen går du till sidan **Datakällor**, väljer en entitet och sedan **redigera** och visar sedan entitetens data med Power Query redigeraren som förklaras i [Datakällor](data-sources.md).

Om du vill lära dig mer om data som tas med i entiteten kan du få en del viktiga egenskaper för informationen, t.ex. nullvärden, saknade värden, unika värden, antal och fördelningar, som kan användas för dina data i kolumnen **Sammanfattning**.

Välj diagramikonen om du vill visa en sammanfattning av data.

> [!div class="mx-imgBorder"]
> ![Sammanfattningssymbol](media/data-manager-entities-summary.png "Datasammanfattningstabell")

### <a name="next-step"></a>Nästa steg

Se ämnet [Förena](data-unification.md) för att lära dig *mappa*, *matcha* och *koppling* hämtade data.


[!INCLUDE[footer-include](../includes/footer-banner.md)]