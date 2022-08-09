---
title: Power Apps anslutningsprogram (förhandsversion)
description: Anslut med Power Apps och Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196922"
---
# <a name="power-apps-connector-preview"></a>Power Apps anslutningsprogram (förhandsversion)

Få enhetliga kundprofiler i dina anpassade appar med Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Ansluta till Power Apps och Dynamics 365 Customer Insights

Customer Insights är en av de många [tillgängliga källorna för data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Se Power Apps-dokumentationen om hur du [lägger till en dataanslutning i en app](/powerapps/maker/canvas-apps/add-data-connection). Vi rekommenderar att du även granskar [hur Power Apps använder delegering för att hantera stora data mängder i arbetsyteappar](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Tillgängliga entiteter

När du har lagt till Customer Insights som en dataanslutning kan du välja följande entiteter i Power Apps:

- **Kund**: om du vill använda data från den [enhetliga kundprofilen](customer-profiles.md).
- **UnifiedActivity**: för att visa [aktivitetstidslinjen](activities.md) i appen.
- **ContactProfile**: för att visa en kunds kontakter. Den här entiteten är endast tillgänglig i Customer Insights-miljöerna för företagskonton.

## <a name="limitations"></a>Begränsningar

### <a name="retrievable-entities"></a>Hämtningsbara entiteter

Du kan bara hämta entiteterna **Kund**, **UnifiedActivity**, **Segment** och **ContactProfile** via Power Apps anslutningsprogram. ContactProfile är endast tillgänglig i Customer Insights-miljöer för företagskonton. Andra entiteter visas eftersom den underliggande anslutningen stöder dem via utlösare i Power Automate.

Du kan göra maximalt 100 samtal per 60 sekunder. Du kan anropa API-slutpunkt flera gånger med hjälp $skip parametern. [Läs mer om parametern $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegering

Delegering fungerar för entiteten **kund** och **UnifiedActivity**.

- Delegering för entiteten **Kund**: För att använda delegering för den här entiteten måste fältet indexeras i [Sök & filtrera](search-filter-index.md).  
- Delegering för **UnifiedActivity**: delegering för den här entiteten fungerar endast för fälten **ActivityId** och **CustomerId**.  
- Delegering för **ContactProfile**: Delegering för den här entiteten fungerar endast för fälten **ContactId** och **CustomerId**. ContactProfile är endast tillgänglig i Customer Insights-miljöer för företagskonton.

Mer information om delegering finns i [Power Apps delegerbara funktioner och åtgärder](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Kontroll i exempelgalleri

Alternativt kan du lägga till kundprofiler i en [gallerikontroll](/powerapps/maker/canvas-apps/add-gallery).

1. Lägg till en **Galleri**-kontroll i en app som du bygger.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Lägga till ett gallerielement.":::

1. Välj **kund** som datakälla för artiklar.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Välj en datakälla.":::

1. Ändra datapanelen till höger och välja vilket fält för den kundentitet som ska visas i galleriet.

1. Om du vill visa ett fält från den valda kunden i galleriet fyller du i egenskapen **Text** för en etikett **{Name_of_the_gallery}.Valt.{property_name}**  
    - Till exempel: _Gallery1.Selected.address1_city_

1. Om du vill visa den enhetliga tidslinjen för en kund lägger du till ett gallerielement och lägger till egenskapen **objekt** med **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Till exempel: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
