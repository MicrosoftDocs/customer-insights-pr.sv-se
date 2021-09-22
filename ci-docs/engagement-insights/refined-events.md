---
title: Skapa och ändra förfinade händelser
description: Så här skapar och ändrar du förfinade händelser.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034796"
---
# <a name="create-and-modify-refined-events"></a>Skapa och ändra förfinade händelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


En händelse är data som representerar användarbeteende, som aktivitet på en webbplats.

- En *bas* händelsepost när en användare visar en sida (visa händelse) eller interagerar med innehåll (åtgärdshändelse).
- En *förfinade* händelser är en virtuell vy av en bashändelse. Du definierar förfinade händelser genom att ta bort och lägga till egenskaper eller genom att filtrera händelser utifrån egenskapsvärden.

Använd förfinade händelser för att minska omfattningen av en bashändelse för [exportera](export-events.md) eller för att ta bort egenskaper som inte är nödvändiga för exponering.

## <a name="create-refined-events"></a>Skapa förfinade händelser

Det finns tre sätt att skapa en förfinad händelse som kan skapas genom en bashändelse. 

1. Gå till **Data**> **Händelser** och välj ett av följande alternativ:
    - Välj **Nya händelser** och välj **Skapa förfinade händelser**.
    - Välj en bashändelse för att öppna en detaljerad vy och välj **Skapa förfinade händelser** från den övre menyn.
    - Välj **Mer [...]** om du vill öppna snabbmenyn för en bashändelse. Välj sedan **Skapa förfinade händelser**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Alternativ för att skapa förfinade händelser.":::

1. I dialogrutan **Skapa förfinade händelser** anger du följande information:

- Välj en händelse i listrutan **Bashändelser** om du skapar en ny händelse.
- Ange ett namn i rutan **Visningsnamn för förfinade händelser**.
- Alternativt kan du uppdatera det föreslagna **faktiska namnet** utan att använda blanksteg.

3. Välj **Skapa** om du vill använda inställningarna.

1. I den detaljerade vyn för din förfinade händelse, välj **Lägg till och ta bort egenskaper** för att öppna rutan **Redigera egenskaper**. 

1. Använd kryssrutorna för att markera de egenskaper som du vill visa och de du vill dölja. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Redigera egenskaper för förfinade händelser.":::

1. Välj **Bekräfta** så att ditt val tillämpas.

1. Välj **Spara** för att spara konfigurationen.

## <a name="edit-refined-events"></a>Redigera förfinade händelser

Du kan ändra namn och egenskaper för en förfinad händelse.

### <a name="edit-event-name"></a>Redigera händelsenamn

1. Gå till **Data** > **Händelser**. 
1. Välj **Mer [...]** för en händelse och välj **Redigera namn**.
1. Uppdatera händelsenamnet och välj **Byt namn**.

### <a name="edit-selected-properties"></a>Redigera valda egenskaper

1. Gå till **Data** > **Händelser** och välj de förfinade händelserna för att öppna den detaljerade vyn.
1. Välj **Lägg till och ta bort egenskaper**. 
1. Redigera markering av kryssrutorna.
1. Välj **Bekräfta** och sedan **Spara** om du vill tillämpa ändringarna.

Information om hur du exporterar händelser finns i [Exportera händelser](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
