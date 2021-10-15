---
title: Visa och skapa dimensioner
description: Skapa, redigera och ta bort dimensioner.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034019"
---
# <a name="view-and-create-dimensions"></a>Visa och skapa dimensioner

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En dimension är ett attribut för en händelse som kan beskriva, filtrera eller gruppera data. Om du kör en marknadsföringskampanj på webbplatsen kan du använda dimensioner för att sortera besökare efter nya och återkommande användare.  

Engagemangsinsikter innehåller färdiga dimensioner för händelseegenskaper. Exempel:

- Webbläsarens namn
- Sidnamn
- Enhetsmodell
- Operativsystem
- Land/region

## <a name="view-dimensions"></a>Visa dimensioner

Dimensioner baseras på befintliga händelseegenskaper. När du använder spårningskoden för insikter i engagemang skapas systemdimensioner automatiskt.

1. Gå till **Data** i vänstra navigeringsfönstret. 
1. Välj **Dimensioner** för att se en lista över alla dimensioner i arbetsytan. 
   > [!NOTE]
   > Systemgenererade dimensioner är skrivskyddade. Det går inte att redigera dem. Du kan endast skapa och redigera anpassade dimensioner.

## <a name="create-a-dimension"></a>Skapa en dimension

Förutom systemgenererade dimensioner kan administratörer för miljö och arbetsytor skapa egna dimensioner. Anpassade dimensioner baseras på standardegenskaper för grundhändelser eller på [anpassade egenskaper för en händelse](advanced-SDK-implementation.md).

1. Gå till **Data** > **Dimensioner**.
1. Välj **Lägg till en dimension**.

   :::image type="content" source="media/add-dimension.png" alt-text="Lägga till en dimension i en händelse.":::

1. I rutan **Skapa en dimension** väljer du en egenskap som dimensionen ska baseras på. I egenskapslistan visas alla egenskaper i arbetsytan som inte har tilldelats någon dimension.
1. Ange ett namn i rutan **Visningsnamn**. Alternativt kan du lägga till en beskrivning.
1. Välj **Skapa** för att spara dimensionen. Det kan ta upp till en minut innan du kan använda dimensionen i en [anpassad rapport](custom-reports.md) eller ett anpassat [segment](segments.md). 

## <a name="edit-a-dimension"></a>Redigera en dimension

Du kan ändra namn och beskrivning av en dimension.

1. Gå till **Data** > **Dimensioner**.
1. Markera den dimension du vill ta bort.
1. I rutan **Redigera dimension** uppdaterar du dimensionen.
1. Välj **Tillämpa** för att spara ändringarna.

## <a name="delete-a-dimension"></a>Ta bort en dimension

Du kan endast ta bort användarskapade dimensioner, men du kan inte ta bort systemdimensioner.

Borttagning av en dimension är permanent. Rapporter och segment som använder en borttagen dimension fungerar inte längre. 

1. Gå till **Data** > **Dimensioner**.
1. Markera den dimension du vill ta bort.
1. I rutan **Redigera dimension** väljer du **Ta bort dimension**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Ta bort en dimension från en händelse.":::

1. Ange **BEKRÄFTA BORTTAGNING** (med stora bokstäver) för att bekräfta borttagningen. 
1. Välj **Ta bort**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]