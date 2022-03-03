---
title: Föreslagna segment baserade på aktivitet.
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
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354485"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Föreslagna segment baserade på aktivitetsdata (förhandsversion)

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
Om du är i hälso- och sjukvårdsbranschen och erbjuder offentlig hälso- och sjukvård och ditt mål är att minimera utgifter för enskilda utgifter. Ett sätt att göra detta kan vara att minska antalet återkommande besök genom att erbjuda bästa möjliga vård i så få besök som möjligt. I det här fallet är målet att hålla besöksfrekvensen låg och minimera återkommande kostnader för besöket. Du kan också identifiera grupper med personer som ofta har avtalade tider och stora återkommande kostnader, och analysera dessa ärenden för att förbättra den enskildes behov. 

## <a name="required-data"></a>Obligatoriska data

Förslag skapas utifrån valda indata. 

- Kundprofiler: Alla kunder eller medlemmar i ett visst segment. 

- Tidsperiod: Senaste månaden, förra året eller eventuella anpassade tidsram.

- Aktivitetstyp: inköp, återförsäljningstransaktioner, onlinetransaktioner, kundsupportärenden, prenumerationer och så vidare.  

- Entitet i Customer Insights som innehåller aktivitetsdata: Entiteten UnifiedActivity eller entiteten för en viss aktivitet. 

- Mått som ska inkludera: Recency, frekvens eller monetärt, beroende på dina affärsbehov.

## <a name="generate-suggested-segments"></a>Generera föreslagna segment

1. Gå till **Segment**.

1. Välj fliken **Förslag (förhandsversion)**.

1. Välj **Sök efter nya förslag** och välj **Visa eller förutse kundbeteende**. Välj **Start** om du vill köra den guidade upplevelsen.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Första steget i konfigurationsguiden för ett föreslaget segment baserat på aktivitet.":::

1. Ange de indata som krävs och välj **Nästa**.

   - Välj kunder: Ta med alla kunder eller ett specifikt segment.
   - Välj aktivitet: Välj aktivitetstyp och de entiteter som beskriver aktiviteten.
   - Inställningar: Ange den tidsperiod som ska beaktas, faktorerna för förslag och mappa attributen.

1. Granska indata och välj **Kör** för att köra modellen och generera förslag.

1. Beroende på antalet kundprofiler och valda aktiviteter kan det ta några minuter att slutföra. 

När du har genererat förslagen kan du filtrera dem efter det värde du är mest intresserad av. 

## <a name="view-details-of-a-suggested-segment"></a>Visa information om föreslaget segment

När förslagen har genererats hittar du dem listade i **Segment** > **Förslag (förhandsversion)** i avsnittet **Aktivitetsbaserade förslag**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Den expanderade rutan på sidan visar detaljerade data för ett föreslaget segment.":::

Välj **Visa förslag** på ett föreslaget segment för att visa information om det avsnittet. I den vänstra rutan visas information om i vilken omfattning varje ruta visas i jämförelse med målgruppen. Det visar också antalet potentiella medlemmar i segmenten och den motsvarande procentandelen av de totala kunderna. Om du vill behålla förslaget som ett segment väljer du **Skapa segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Spara ett förslag som ett segment

1. Gå till **Segment** > **Förslag (förhandsgranskning)**.

1. Välj det segment som du vill spara. 

1. I den vänstra rutan, välj **Skapa segment**. 

1. När du har sparat segmenten visas det i listan med segment på fliken **Alla segment**. Det kan nu [uppdateras eller tas bort på samma sätt som i andra segment](segments.md). Du kan inte redigera segmentinformationen. Du kan emellertid ändra indatavillkoren för förslagen och generera olika förslag.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Uppdatera eller redigera en uppsättning förslag

1. Gå till **Segment** > **Förslag (förhandsversion)** och leta upp avsnittet **Aktivitetsbaserade förslag**.

1. Välj **Uppdatera förslag** för att uppdatera förslagen samtidigt som du behåller konfigurerade attribut. Eller välj **Redigera förslag** om du vill ändra de konfigurerade attributen. Systemet kör processen på nytt, genererar segmentförslag utifrån senaste data och ersätter de aktuella förslagen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
