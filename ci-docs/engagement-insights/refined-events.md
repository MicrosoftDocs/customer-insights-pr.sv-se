---
title: Skapa och ändra händelser
description: Hur man skapar och ändrar händelser.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606277"
---
# <a name="create-and-modify-events"></a>Skapa och ändra händelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En händelse är data som representerar användarbeteende, som aktivitet på en webbplats.

- En *bas* händelsepost när en användare visar en sida (visa händelse) eller interagerar med innehåll (åtgärdshändelse).
- En *förfinade* händelser är en virtuell vy av en bashändelse. Du definierar förfinade händelser genom att ta bort och lägga till egenskaper eller genom att filtrera händelser utifrån egenskapsvärden.

## <a name="prerequisites"></a>Förutsättningar

För att få evenemang måste din webbplatsdata först kopplas till Engagemangsinsikter med ett kodavsnitt. Mer information finns i [Installera webb-SDK på en webbplats](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Anslut dina data först.":::

## <a name="create-refined-events"></a>Skapa förfinade händelser

Använd förfinade händelser för att minska omfattningen av en bashändelse för [exportera](export-events.md) eller för att ta bort egenskaper som inte är nödvändiga för exponering.

> [!NOTE]
> När du har lagt till webb-SDK:n på webbplatsen kan du visa dina grundhändelser och skapa evenemang. 

Så här visar du bashändelser:

1. Gå till **Data** i vänstra navigeringsfönstret.

1. Välj **Händelser** om du vill visa en lista över alla händelser på arbetsytan.

    :::image type="content" source="media/data-events.png" alt-text="Visa händelser.":::

Så här skapar du en förfinad händelse från en bashändelse: 

1. Gå till **Data** > **Händelser** och välj **+ Nya händelser** högst upp på skärmen.

1. I dialogen **Ny händelser**, välj **Skapa förfinade händelser** och välj **Nästa**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Guiden nya händelser.":::
     
1. I dialogen **Nya händelser** ange följande information:

   - Välj en händelse i listrutan **Bashändelser**.
   - Ange ett namn i rutan **Visningsnamn för förfinade händelser**.
   - Alternativt kan du uppdatera det föreslagna **faktiska namnet** utan att använda blanksteg.

1. Välj **Skapa** om du vill använda inställningarna.

Händelsen inträffar nu i listan **Händelser**.

### <a name="edit-event-name"></a>Redigera händelsenamn

Du kan ändra namn och egenskaper för en bashändelse eller händelse som infinnat sig.

1. Gå till **Data** > **Händelser**. 

1. Välj **Mer [...]** för en händelse och välj **Redigera namn**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Alternativ för att skapa förfinade händelser.":::

3. Uppdatera händelsenamnet och välj **Byt namn**.

### <a name="view-the-details-of-a-refined-event"></a>Se detaljer om en förfinad händelse:

1. Välj bas eller händelse i listan **Händelse**. 

1. Välj **Lägg till och ta bort egenskaper** högst upp på skärmen för att öppna **Redigera egenskaper**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Lägg till och ta bort egenskaper.":::

1. Använd kryssrutorna för att markera de egenskaper som du vill visa och de du vill dölja. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Redigera egenskaper för förfinade händelser.":::

1. Välj **Bekräfta** om du vill använda de val du valt och välj sedan **Spara**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Redigera valda egenskaper för en händelse som förfinat

1. Gå till **Data** > **Händelser** och välj de förfinade händelserna för att öppna den detaljerade vyn.
1. Välj **Lägg till och ta bort egenskaper**. 
1. Redigera markering av kryssrutorna.
1. Välj **Bekräfta** och sedan **Spara** om du vill tillämpa ändringarna.

Information om hur du exporterar händelser finns i [Exportera händelser](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
