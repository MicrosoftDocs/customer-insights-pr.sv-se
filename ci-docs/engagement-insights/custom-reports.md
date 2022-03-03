---
title: Om anpassade rapporter
description: Lär dig hur du skapar och anpassar rapporter.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232170"
---
# <a name="create-and-edit-custom-reports"></a>Skapa och redigera anpassade rapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Förutom att använda färdiga (OOB) rapporter kan du skapa en anpassad rapport med diagram- och tabellvisualiseringar för att bättre förstå användarbeteendet. I den här artikeln förklaras hur du skapar en rapport med de data du behöver med hjälp av tabell- och diagramvisualiseringar. Mer information om OOB-rapporter finns i [Visa rapporter](view-reports.md).

## <a name="create-a-custom-report"></a>Skapa en anpassad rapport

1. Gå till **Analysera** > **Anpassa** för att komma åt den anpassade rapportlistan.

1. Välj **Ny rapport** om du vill börja skapa en anpassad rapport.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nya anpassade rapporter.":::

1. Bestäm vilken typ av rapport du vill bygga:

    - Välj **Lägg till visuellt element** i kommandofältet om du vill skapa en standardvisualisering i tabellen.
    - Du kan också markera en kolumn, stapel, rad, område, cirkel, ring eller tabellvisualisering i **rapportredigeraren**.

1. I avsnittet **Data** i redigeraren för **visualisering** väljer du ett av de tillgängliga alternativen (till exempel sidvyer) i listrutan **Mått**. Du kan också lägga till **Mått** (till exempel land) som ska visas i visualiseringen. Mer information finns i V[isa och skapa mått](metrics.md) och [Visa och skapa mått](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Välj ett mått för din rapport.":::

1. Välj avsnittet **Design** i **redigeraren för visualisering** om du vill lägga till **rubriktext** och växla **rubrik** av och på.  Du kan också ändra visualiseringstyp genom att välja ett annat diagram, till exempel **cirkeldiagram**.

1. Så här ändrar du storlek och placering för en visualisering:
   - Välj visualiseringen och dra sedan en av de olika objekten för att justera storleken.
   - Välj visualiseringen och flytta den till en ny plats. Du kan också ändra positionen med hjälp av piltangenterna.
1. Om du vill lägga till ytterligare en visualisering väljer du **Lägg till visuellt objekt** i kommandofältet.
1. När du har lagt till de visualiseringar du vill använda för rapporten väljer du **Spara** i kommandofältet.

1. Ange ett namn på den anpassade rapporten och välj **Spara** för att skapa den.
 
## <a name="filter-a-custom-report"></a>Filtrera en anpassad rapport

Du kan välja tidsram eller datumintervall i en anpassad rapport om du vill fokusera på ett värde eller en tidsperiod.

Välj en tidsram genom att välja ett värde i den nedrullningsbara listan i rapporten längst upp till höger i rapportvyn. Du kan också välja ett **Fast datumintervall*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrera efter tid eller datumintervall.":::

För de flesta rapporter väljer du **+ Lägg till villkor** om du vill välja ett segment för filtrering av rapporten. Mer information finns i [Visa och skapa segment](segments.md).

## <a name="edit-a-custom-report"></a>Redigera en anpassad rapport

1. Gå till **Analysera** > **Anpassa** för att komma åt den anpassade rapportlistan.

1. I den anpassade rapportlistan, välj **Mer [...]** 

1. Välj **Redigera namn** om du vill ändra namnet på rapporten.

1. Markera namnet på rapporten och använd alternativen **+ Lägg visuellt objekt** och **Redigera** för att lägga till, ta bort, flytta eller ändra storlek på visualiseringarna.

1. Om du vill ändra egenskaperna för en visualisering väljer du det visuella och väljer **...** och sedan **Redigera visuellt objekt**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Redigera diagramegenskaper för anpassade rapporter.":::

1. Välj **Spara** när du har redigerat rapporten för att tillämpa ändringarna. 

## <a name="delete-a-custom-report"></a>Ta bort en anpassad rapport

1. Gå till **Analysera** > **Anpassa** för att komma åt den anpassade rapportlistan.

1. I den anpassade rapportlistan, välj **...**

1. Välj **Ta bort** om du vill ta bort rapporten.

1. Bekräfta borttagningen om du vill ta bort rapporten permanent.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
