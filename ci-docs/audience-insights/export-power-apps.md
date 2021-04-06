---
title: Anslutningsapp för Power Apps
description: Anslut med Power Apps och Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598177"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps anslutningsprogram (förhandsversion)

Få enhetliga kundprofiler i dina anpassade appar med Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Ansluta till Power Apps och Dynamics 365 Customer Insights

Customer Insights är en av de många [tillgängliga källorna för data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Se Power Apps-dokumentationen om hur du [lägger till en dataanslutning i en app](/powerapps/maker/canvas-apps/add-data-connection). Vi rekommenderar att du även granskar [hur Power Apps använder delegering för att hantera stora data mängder i arbetsyteappar](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Tillgängliga entiteter

När du har lagt till Customer Insights som en dataanslutning kan du välja följande entiteter i Power Apps:

- Kund: om du vill använda data från den [enhetliga kundprofilen](customer-profiles.md).
- Enhetlig aktivitet: så här visar du [aktivitetstidslinje](activities.md) i appen.

## <a name="limitations"></a>Begränsningar

### <a name="retrievable-entities"></a>Hämtningsbara entiteter

Du kan bara hämta entiteterna **Kund**, **UnifiedActivity** och **Segment** via Power Apps-anslutaren. Andra entiteter visas eftersom den underliggande anslutningen stöder dem via utlösare i Power Automate.  

### <a name="delegation"></a>Delegering

Delegering fungerar för entiteten kund och UnifiedActivity. 

- Delegering för entiteten **Kund**: För att använda delegering för den här entiteten måste fältet indexeras i [Sök & filtrera](search-filter-index.md).  

- Delegering för **UnifiedActivity**: delegering för den här entiteten fungerar endast för fälten **ActivityId** och **CustomerId**.  

- Mer information om delegering finns i [Power Apps delegerbara funktioner och åtgärder](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Kontroll i exempelgalleri

Du lägger till exempel till kundprofiler i en [gallerikontroll](/powerapps/maker/canvas-apps/add-gallery).

1. Lägg till en **Galleri**-kontroll i en app som du bygger.

> [!div class="mx-imgBorder"]
> ![Lägga till ett gallerielement](media/connector-powerapps9.png "Lägga till ett gallerielement")

1. Välj **kund** som datakälla för artiklar.

    > [!div class="mx-imgBorder"]
    > ![Välj datakälla](media/choose-datasource-powerapps.png "Välj datakälla")

1. Du kan ändra datapanelen till höger och välja vilket fält för den kundentitet som ska visas i galleriet.

1. Om du vill visa ett fält från den valda kunden i galleriet fyller du i egenskapen text för en etikett: **{Name_of_the_gallery}.Valt.{property_name}**

    Exempel: Gallery1.Selected.address1_city

1. Om du vill visa den enhetliga tidslinjen för en kund lägger du till ett gallerielement och lägger till egenskapen för Objekt: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Exempel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]