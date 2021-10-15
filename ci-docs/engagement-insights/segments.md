---
title: Visa och skapa segment
description: Skapa, redigera och ta bort segment och var du ska använda dem.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036170"
---
# <a name="view-and-create-segments"></a>Visa och skapa segment

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med hjälp av segment kan du identifiera underuppsättningar av besökare baserat på egenskaper eller interaktioner på webbplatsen. Med segment kan du använda filter och analysera dessa underuppsättningar. Med hjälp av analysen kan du undersöka och reagera på trender i verksamheten. 

:::image type="content" source="media/segments-page.png" alt-text="Skärmbild av engagemangsinsiktsprogrammet som visar listan över befintliga segment på en arbetsyta.":::

## <a name="view-segments"></a>Visa segment

1. Gå till **Data** i vänstra navigeringsfönstret. 

1. Välj fliken **Segment** för att se en lista över alla segment i arbetsytan. 

## <a name="create-a-segment"></a>Skapa ett segment

Segment består av regler och villkor som är kopplade till logiska operatorer. Villkor tillämpar filter på en vald dimension. Varje segment kan använda upp till fem dimensioner.

I följande exempel visas ett segment med två villkor i en och samma regel. Alla webbplatshändelser där webbläsaren är Chrome och operativsystemet är iOS eller Android filtreras.

:::image type="content" source="media/segment-sample.png" alt-text="Exempelsegment med två villkor i en regel för att filtrera efter webbplatshändelser.":::

I det här avsnittet beskrivs hur du skapar ett *tomt segment* från grunden.

1. Gå till **Data** > **Segment**.

1. Välj **Nytt segment**.

1. I **Resursbilbliotek** väljer du det attribut som du vill filtrera efter. För tillfället kan du endast skapa segment utifrån dimensioner.

1. Välj en operator och ett värde för det valda attributet. Följande åtgärder stöds.
   - **är**: kräver en exakt matchning för att ta med värden. Använder **lika med** för ett enskilt värde eller **något av** för att inkludera flera värden.
   - **är inte**: kräver en exakt matchning för att inte ta med värden. Använder **lika med** för ett enskilt värde eller **något av** för att inkludera flera värden.
   - **startar med**: en sträng som de matchande värdena börjar med.
   - **slutar med**: en sträng som de matchande värdena slutar med.
   - **innehåller**: en sträng i matchande värden.

1. Om du vill lägga till villkor i en grupp kan du använda två logiska operatorer. Projekterade attribut räknas in när du använder uppsättningsoperatorer.
   - **OCH** operatör: båda villkoren måste uppfyllas som en del av segmenteringsprocessen. Det här alternativet är mest användbart när du definierar villkor för olika entiteter.
   - **ELLER** operatör: ett av villkoren behöver uppfyllas som en del av segmenteringsprocessen. Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.

1. Välj **Spara** och namnge segmentet. 

Segmenten visas på sidan Segment och du kan använda det för alla rapporter och tratter på arbetsytan.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Använda ett segment i en rapport eller tratt

Du kan använda segment för en rapport eller en tratt för att filtrera dem baserat på villkoren i segmenten. Du kan dock inte använda segment i användningsrapporten i realtid.

:::image type="content" source="media/segment-reports-filter.png" alt-text="En rapport över sidvisningar ned en utfälld listruta där du kan välja vilka segment som ska användas.":::

Om du vill använda ett segment öppnar du rapporten eller tratten. Välj **Lägg till villkor** och välj **Filtrera efter segment**. Välj det segment från listan som du vill använda. Segmenten tillämpas på rapporten. Om ett diagram inte stöder ett segment visas ett fel.
 
Du kan använda *upp till tre segment* för en rapport eller tratt.

## <a name="edit-a-segment"></a>Redigera segment

1. Gå till **Data** > **Segment**.
1. Välj segmentet i listan för att öppna det. 
1. Ändra eller lägg till värden efter behov.
1. Välj **Spara** för att införa ändringarna.

## <a name="change-the-name-of-a-segment"></a>Ändra namnet på ett segment

1. Gå till **Data** > **Segment**.
1. I segmentlistan väljer du **Mer [...]**. 
1. I listrutan väljer du **Redigera namn**.
1. Ange det nya namnet och välj **Byt namn**.

## <a name="delete-a-segment"></a>Ta bort ett segment

1. Gå till **Data** > **Segment**.
1. I segmentlistan väljer du **Mer [...]**. 
1. I listrutan väljer du **Ta bort**.
1. Välj **Ta bort** för att bekräfta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]