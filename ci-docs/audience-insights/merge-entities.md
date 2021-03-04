---
title: Slå samman entiteter i datasammanslutningen
description: Slå samman entiteter för att skapa enhetliga kundprofiler.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268524"
---
# <a name="merge-entities"></a>Slå samman entiteter

Sammanslagningsfasen är den sista fasen i föreningsprocessen för data. Dess syfte avstäms av motstridiga data. Exempel på data som är i konflikt kan vara ett kundnamn som finns i två av dina datauppsättningar, men som visar lite annorlunda i varje (“Grant Marshall” jämfört med “Grant Marshal”), eller ett telefonnummer som skiljer sig från formatet (617-803-091X jämfört med 617803091X). Sammanfoga dessa motstridiga datapunkter görs på ett attribut till attributbasis.

Efter att ha avslutat [matchningsfasen](match-entities.md) kan du starta sammanslagningsfasen genom att välja panelen **Sammanslagning** på sidan **Enhet**.

## <a name="review-system-recommendations"></a>Granska systemrekommendationer

På sidan **Sammanslå** kan du välja och exkludera attribut som ska slås samman i entiteten enhetlig kundprofil (resultatet av konfigurationsprocessen). Vissa attribut slås samman automatiskt av systemet.

### <a name="view-merged-attributes"></a>Visa sammankopplade attribut

Om du vill visa de attribut som är inkluderade i ett av de automatiskt sammankopplade attributen markerar du det sammankopplade attributet. De två attributen som utgör det sammankopplade attributet visas i två nya rader under det sammankopplade attributet.

> [!div class="mx-imgBorder"]
> ![Välj sammankopplade attribut](media/configure-data-merge-profile-attributes.png "Välj sammankopplade attribut")

### <a name="separate-merged-attributes"></a>Separata sammankopplade attribut

Om du vill separera eller ta isär de automatiskt sammankopplade attributen kan du söka efter attributet i tabellen i **profilattribut**.

1. Markera ellips-knappen (...) .
  
2. Välj i listrutan **Separata fält**.

### <a name="remove-merged-attributes"></a>Ta bort sammankopplade attribut

Om du vill utesluta ett attribut från den slutgiltiga entiteten för kundprofilen söker du efter **Profilattribut**.

1. Markera ellips-knappen (...) .
  
2. Välj i listrutan **Koppla inte**.

   Attributet flyttas till avsnittet **borttaget från kundpost**.

## <a name="manually-add-a-merged-attribute"></a>Lägg till ett sammankopplat attribut manuellt

Om du vill lägga till ett kopplar attribut går du till sidan **Koppla**.

1. Välj **Lägg till sammankopplade attribut**.

2. Ange ett **namn** för att identifiera det på sidan **Koppla** senare.

3. Alternativt kan du ange ett **visningsnamn** som ska visas i entiteten för den enhetliga kundprofilen.

4. Konfigurera **Markera dubblettattribut** för att välja de attribut som du vill koppla från de matchade entiteterna. Du kan även söka efter attribut.

5. Ange **rangordna efter prioritet** om du vill prioritera ett attribut ovanför de övriga. Till exempel om entiteten *WebAccountCSV* innehåller den mest exakta informationen om attributet *fullständigt namn* kan du prioritera den här entiteten *ContactCSV* genom att välja *WebAccountCSV*. Detta innebär att *WebAccountCSV* flyttar till den första prioriteten medan *ContactCSV* flyttar till den andra prioriteten när de hämtar värden för attributet *fullständigt namn*.

## <a name="run-your-merge"></a>Kör din koppling

Oavsett om du kopplar attribut manuellt eller låter systemet koppla ihop dem kan du alltid köra kopplingen. Välj **Kör** på sidan **Koppla** för att starta processen.

> [!div class="mx-imgBorder"]
> ![Datakoppling Spara och kör](media/configure-data-merge-save-run.png "Datakoppling Spara och kör")

Om du vill göra ytterligare ändringar och köra steget igen kan du avbryta en pågående koppling. Välj **Uppdatera...** och välj **Avbryt jobb** i sidorutan som visas.

Efter att texten **Uppdaterar...** ändras till **Lyckad**, men sammanslagning har slutfört och löst motstridig information i enlighet med de principer du angav. Sammanslagna och inte sammanslagna attribut ingår i entiteten Enhetliga profiler. Utelämnade attribut ingår inte i entiteten Enhetliga profiler.

Om det inte var första gången som du körde en sammanslagning, kommer alla efterföljande processer, inklusive berikning, segmentering och mått att köras igen automatiskt. När alla efterföljande processer har körts igen återspeglas de ändringar du har gjort i kundprofilen.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="next-step"></a>Nästa steg

Konfigurera [aktiviteter](activities.md), [berikning](enrichment-microsoft-graph.md)eller [relationer](relationships.md) till mer information om kunderna.

Om du redan har konfigurerat aktiviteter, berikning eller relationer eller om du har definierat segment, bearbetas de automatiskt så att de senaste kunddata används.




[!INCLUDE[footer-include](../includes/footer-banner.md)]