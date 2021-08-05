---
title: Segmentinsikter för befintliga segment
description: Få insikter om befintliga segment för att se skillnader och likheter.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0803be651662480ddf1fd22952f6a69ee1603001
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555007"
---
# <a name="segment-insights-preview"></a>Segmentinsikter (förhandsversion)

Upptäck ytterligare information och insikter kring de befintliga segmenten. Ta reda på vad som skiljer mellan två segment och vad de har gemensamt.

## <a name="segment-overlap"></a>Segmentöverlappning

Analysen av segmentöverlappnings visar hur många och vilka kunder som är gemensamma för två eller flera segment. Till exempel överlappar ett segment med kunder som ofta använder ett segment som innehåller kunder som är nöjd med din tjänst eller produkt.
Du kan också analysera hur överlappningen ändras för vissa attribut.

### <a name="run-an-overlap-analysis"></a>Köra en överlappande analys

1. Gå till **segment** och välj fliken **insikter (förhandsversion)**.

1. Välj **Nytt** och välj alternativet **Överlappa** i fönstret **Välj insiktstyp**.

1. Välj segmentet du vill och välj **Nästa**.

1. Alternativt kan du välja ett eller flera intresseområden för att analysera överlappningar för alla möjliga fält värden och välja **Nästa**.

1. Ange ett namn för den överlappande analysen, ett valfritt visningsnamn och en beskrivning.

1. Välj **Spara** för att starta analysen. Den överlappande analysen är klar när status ändras från uppdatering till lyckad.

### <a name="view-and-optimize-an-overlap-analysis"></a>Visa och optimera en överlappningsanalys

När du har genomfört analysen hittar du detaljerad information om den här insikten på **Segment** > **Insikter (förhandsversion)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Överlappande segmentinformation om insikter.":::

Välj en insikt för att se resultatet av analysen:

- Antalet medlemmar som överlappar de segment som valts för analys.
- Antalet medlemmar som ingår i ett av segmenten men inte i resten av segmentet.
- Om du valde fält när du konfigurerade överlappningsanalysen hittar du dem på motsvarande flikar. Du kan använda filterlistrutan för att välja en attributnivå, så visas motsvarande data i tabellen längst ned.

## <a name="segment-differentiators"></a>Differentiatorer för segment

Segmentdifferentieringar hjälper dig att ta reda på vad som skiljer ett segment från övriga kunder eller från ett annat segment. Du behöver bara välja ett segment så identifierar systemet med de profilmappar och mått som kännetecknar det valda segmentet.

### <a name="run-a-differentiator-analysis"></a>Köra en differentieringsanalys

1. Gå till **segment** och välj fliken **insikter (förhandsversion)**.

1. Välj **Nytt** och välj alternativet **Överlappa** i fönstret **Välj insiktstyp**.

1. Välj det segment du vill analysera som ett **primärt segment** och välj **Nästa**.

1. Välj **Alla kunder** eller ett **sekundärt segment** för att jämföra det primära segmentet med och välj **Nästa**.

1. Alternativt kan du välja ett eller flera intresseområden för att fokusera analysen på specifika attribut och välja **Nästa**.

1. Ange ett namn för den överlappande analysen, ett valfritt visningsnamn och en beskrivning.

1. Välj **Spara** för att starta analysen. Den överlappande analysen är klar när status ändras från uppdatering till lyckad.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Visa och optimera en differentieringsanalys

När du har genomfört analysen hittar du detaljerad information om den här insikten på **Segment** > **Insikter (förhandsversion)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segmentdifferentiering för insiktsinformation.":::

Välj en insikt för att se resultatet av analysen. En differentieringsanalys innehåller två flikar. På fliken **attribut** anges de profilmappar som betraktas som differentieringar. På fliken **mått** en lista över differentieringarna. Varje flik innehåller följande detaljer:

- Rangordnad lista med differentieringar sorterade efter poäng.
- **Differenspoängen** för varje differentiering. Differensenspoäng representerar graden av skillnad på ett attribut mellan två segment. Ju högre differenspoängen är, desto fler attribut skiljer sig mellan de två segmenten. Välj en poäng om du vill öppna fönster **differensenspoäng** med fördelningarna för de attributen.

## <a name="manage-segment-insights"></a>Hantera segmentinsikter

Du kan använda följande alternativ för dina insikter från kommandofältet:

- **Tillbaka** för att returnera listan med insikter
- **Uppdatera** om du vill köra analysen igen
- **Ta bort** och ta bort insikt


[!INCLUDE[footer-include](../includes/footer-banner.md)]