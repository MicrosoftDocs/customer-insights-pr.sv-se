---
title: Visa och skapa mått
description: Skapa, redigera och ta bort mått.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229838"
---
# <a name="view-and-create-metrics"></a>Visa och skapa mått

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mått hjälper dig att förstå hur besökare fungerar. De samlar in händelseegenskaper och mäter statistik och prestanda för dina webbegenskaper.  

Anta att du kör en marknadsföringskampanj på webbplatsen. Du kan använda mått för att spåra antalet unika besökare eller användare som kom till din webbplats under kampanjen. Genom att analysera mått kan du få en bättre förståelse av målgruppen. Om du kombinerar mått med [dimensioner](dimensions.md) i en [anpassad rapport](custom-reports.md) kan du mäta beteendet så att du förstår dina användare. Du kan till exempel dela in besökare i nya och återkommande kategorier för att identifiera skillnaderna i intresse och avsikt mellan grupperna.

## <a name="view-metrics"></a>Visa mått

Engagemangsinsikter omfattar vanliga sammanlagda händelseegenskaper som systemmått: 

- Besökare
- Besök
- Sidvisningar
- Klickningar

Dessa systemmått baseras på befintliga händelseegenskaper i grundhändelser.

1. Gå till **Data** i vänstra navigeringsfönstret. 
1. Välj fliken **Mått** för att se en lista över alla mått i arbetsytan. 
   > [!NOTE]
   > Systemgenererade mått är skrivskyddade. Du kan inte redigera eller ta bort dem. Du kan endast skapa och redigera anpassade mått.

## <a name="create-a-metric"></a>Skapa ett mått

Miljö- och arbetsyteadministratörer kan skapa mått. Händelseegenskaper måste skickas till arbetsytan innan du skapar ett mått. Du kan skapa mått utifrån händelseegenskaper som skickas av grundhändelser eller använda webb-SDK för att [skicka anpassade händelseegenskaper](advanced-SDK-implementation.md).

1. Gå till **Data** > **Mått**.
1. Välj **Nytt mått** om du vill öppna dialogrutan **Resursbibliotek** och **Nytt namnlöst mått**.

   :::image type="content" source="media/new-metric.png" alt-text="Lägg till ett mått i en händelse.":::

1. I dialogrutan **Nytt namnlöst mått** välj listrutan **Format** och datatypen **Heltal** eller **Dubbel**. Heltal är ett helt tal. För Dubbel kan du välja en och tre decimaler.

   :::image type="content" source="media/create-new-metric.png" alt-text="Skapa ett nytt mått.":::
   
5. I fönstret **Resursbibliotek** letar du upp den händelseegenskap som måttet ska baseras på.
6. Välj **plustecknet (+)** bredvid egenskapen som ska användas i formeln. Du kan endast skapa en formel som bygger på en egenskap. 
7. Välj en av följande mängdfunktioner. 

   - Summa: totalsumman för alla värden 
   - Medel: genomsnitt för alla värden
   - Antal: totalt antal värden
   - Distinkt antal: totalt antal distinkta värden

   När du har definierat måttet visas en aktivitetsförhandsgranskning av måttet för den senaste timmen.

1. Välj **Spara**. 
1. Ange ett namn för måttet och välj sedan **Spara**.

Det kan ta upp till en minut för måttet innan du kan använda det till att [skapa anpassade rapporter](custom-reports.md).

## <a name="edit-a-metric"></a>Redigera ett mått

Du kan bara redigera anpassade mått.

1. Gå till **Data** > **Mått**.
1. Välj måttet i listan.
1. Ändra definitionen för måttet
1. Välj **Spara**.

## <a name="change-the-name-of-a-metric"></a>Ändra namnet på ett mått

Du kan bara ändra namnet på anpassade mått.

1. Gå till **Data** > **Mått**.
1. Välj **Mer [...]** för ett mått och välj **Redigera namn**.
1. Ändra namnet. 
1. Välj **Byt namn**.

## <a name="delete-a-metric"></a>Ta bort ett mått

Du kan bara ta bort anpassade mått.

1. Gå till **Data** > **Mått**.
1. Välj **Mer [...]** för ett mått och välj **Ta bort**.

   :::image type="content" source="media/delete-metric.png" alt-text="Ta bort ett mått från en händelse.":::

1. Välj **Ta bort** för att borttagningen.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
