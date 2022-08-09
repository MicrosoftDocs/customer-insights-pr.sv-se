---
title: Förslag på segment baserat på aktivitet (förhandsgranskning)
description: Låt maskininlärning hjälpa dig att hitta nya segment som bygger på kundaktiviteter.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170611"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Förslag på segment baserat på aktivitet (förhandsgranskning)

Upptäck kundsegment som är intressanta och baserade på kundaktivitetsdata som är baserade på Customer Insights. Exempel på aktivitetsdata är transaktioner, varaktighet för supportsamtal, köp eller returer. Om du vill föreslå segment analyseras aktivitetsdata efter recency, frekvens och monetärt värde (eller varaktighet). Du kan också skapa [segment som föreslås för att förbättra ett mått eller förstå vad som påverkar ett attribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fliken Förslag på segment visar segmentförslag för aktivitetsbaserade och attributbaserade segment.":::

## <a name="categorize-customers-by-activity"></a>Kategorisera kunder efter aktivitet

Med [aktivitetsdata](activities.md) som är tillgängliga i Customer Insights kan vi generera förslag som representerar kundgrupper:

- mes aktiva kunderna 
- kunder som har gjort flest inköp 
- kunder som genererat mest omsättning 
- kunder som inte har varit aktiva på sistone 
- kunder som ofta interagerar med ditt företag  

Om du har ett återförsäljningsföretag kan du ta reda på vilka kunder som genererar mest intäkter och ge dem en rabatt. Du kan även identifiera enstaka kunder och erbjuda dem att gå med i ett program för att besöka din verksamhet oftare.
Om du tillhandahåller offentlig hälso- och sjukvård och har som mål att minimera kostnaderna för den enskilda personen, kan du försöka minska antalet återkommande besök genom att erbjuda bästa möjliga vård på så få besök som möjligt. I det här fallet är målet att hålla besöksfrekvensen låg och minimera återkommande kostnader för besöket. Du kan också identifiera grupper med personer som ofta har avtalade tider och stora återkommande kostnader, och analysera dessa ärenden för att förbättra den enskildes behov.

## <a name="required-data"></a>Obligatoriska data

Förslag skapas utifrån valda indata.

- Kundprofiler: Alla kunder eller medlemmar i ett visst segment.

- Tidsperiod: Senaste månaden, förra året eller eventuella anpassade tidsram.

- Aktivitetstyp: inköp, återförsäljningstransaktioner, onlinetransaktioner, kundsupportärenden, prenumerationer och så vidare.  

- Entitet i Customer Insights som innehåller aktivitetsdata: Entiteten UnifiedActivity eller entiteten för en viss aktivitet.

- Mått som ska inkludera: Recency, frekvens eller monetärt, beroende på dina affärsbehov.

## <a name="generate-suggested-segments"></a>Generera föreslagna segment

1. Gå till **segment** och välj fliken **Förslag (förhandsversion)**.

1. Välj **Sök efter nya förslag** och välj **Visa eller förutse kundbeteende**. Välj **start**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Första steget i konfigurationsguiden för ett föreslaget segment baserat på aktivitet.":::

1. Ange de indata som krävs och välj **Nästa**.

   - Välj kunder: Ta med alla kunder eller ett specifikt segment.
   - Välj aktivitet: Välj aktivitetstyp och de entiteter som beskriver aktiviteten.
   - Inställningar: Ange den tidsperiod som ska beaktas, faktorerna för förslag och mappa attributen.

1. Granska indata och välj **Kör** för att köra modellen och generera förslag.

Beroende på antalet kundprofiler och valda aktiviteter kan det ta några minuter att slutföra.

När du har genererat förslagen kan du filtrera dem efter det värde du är mest intresserad av.

## <a name="manage-suggested-segments"></a>Hantera föreslagna segment

Gå till **Segment** och välj fliken **Förslag (förhandsgranskning**). I avsnittet **Aktivitetsbaserade förslag** välj ett föreslaget segment för att visa tillgängliga åtgärder.

- **Visa förslag** för att se detaljerna för det segmentet som omfattningen av varje dimension i jämförelse med målgruppen. Det visar också antalet potentiella medlemmar i segmenten och den motsvarande procentandelen av de totala kunderna.
- **Skapa segment** för att spara det föreslagna som ett segment. Den visas på fliken **Alla segment** och kan [uppdateras eller tas bort](segments.md). Du kan inte redigera segmentinformationen. Du kan emellertid ändra indatavillkoren för förslagen och generera olika förslag.
- **Redigera förslag** och ändra de konfigurerade attributen som ersätter de aktuella förslagen.
- **Uppdatera förslag** för att uppdatera förslagen samtidigt som du behåller konfigurerade attribut.

[!INCLUDE [footer-include](includes/footer-banner.md)]
