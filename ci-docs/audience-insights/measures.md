---
title: Skapa och hantera mått
description: Definiera mått som ska analyseras och reflektera företagets resultat.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269950"
---
# <a name="define-and-manage-measures"></a>Definiera och hantera mått

Med hjälp av mått kan du få en bättre förståelse för kundbeteenden och affärsresultat genom att hämta relevanta värden från [enhetliga profiler](data-unification.md). Ett företag vill till exempel se den *totala kostnaden per kund* för att förstå enskilda kunders köphistorik. Eller mäta *total försäljning för företaget* för att förstå den aggregerade nivån av intäkt i hela verksamheten.  

Mått skapas med måttverktyget, en datafrågeställningsplattform med olika operatörer och enkla mappningsalternativ. Du kan filtrera data, gruppera resultat, identifiera [entitetsrelationssökvägar](relationships.md) och förhandsgranska utdata.

Använd måttverktyget om du vill planera affärsaktiviteter genom att fråga efter kunddata och extrahera insikter. Om du till exempel skapar ett mått på *totalsumma per kund* och *total intäkt per kund* kan du identifiera en grupp av kunder som spenderar mycket men ger höga intäkter. Du kan [skapa ett segment](segments.md) för att driva på nästa bästa åtgärd. 

## <a name="create-a-measure"></a>Skapa ett mått

Det här avsnittet innehåller information om hur du skapar ett nytt mått från grunden. Du kan skapa ett mått med dataattribut från dataentiteter som har en relation som är konfigurerad för att ansluta till entiteten Kund. 

1. I målgruppsinsikter går du till **Åtgärder**.

1. Välj **Nytt**.

1. Välj **Redigera namn** och tillhandahåll ett **namn** för måttet. 
   > [!NOTE]
   > Om den nya måttkonfigurationen endast har två fält, till exempel Kund-ID och en beräkning, läggs utdatan till som en ny kolumn i den systemgenererade entiteten Kundmått. Dessutom kan du se måttens värde i den enhetliga kundprofilen. Andra mått genererar egna entiteter.

1. I konfigurationsområdet väljer du sammansättningsfunktionen från listrutan **Välj funktion**. Sammansättningsfunktioner omfattar: 
   - **Sum**
   - **Medel**
   - **Antal**
   - **Antal unika**
   - **Max**
   - **Min**
   - **Först**: tar det första värdet i dataposten
   - **Sist:** tar det sista värdet som lades till i dataposten

   :::image type="content" source="media/measure-operators.png" alt-text="Operatörer för måttberäkningar.":::

1. Välj **Lägg till attribut** för att välja de data du behöver för att skapa måttet.
   
   1. Välj fliken **Attribut**. 
   1. Dataentitet: Välj den entitet som innehåller attributet du vill mäta. 
   1. Dataattribut: Välj det attribut som du vill använda i sammansättningsfunktionen för att beräkna måttet. Du kan bara välja ett attribut åt gången.
   1. Du kan också välja ett dataattribut från ett befintligt mått genom att välja fliken **Mått**. Du kan också söka efter ett entitets- eller måttnamn. 
   1. Välj **Lägg till** för att lägga till det valda attributet till måttet.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Välj ett attribut som ska användas i beräkningarna.":::

1. Om du vill skapa mer komplexa mått kan du lägga till fler attribut eller använda olika operatörer i måttfunktionen.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Skapa ett komplext mått med matematikoperatörer.":::

1. Om du vill lägga till filter väljer du **Filter** i konfigurationsområdet. 
  
   1. I avsnittet **Lägg till attribut** i rutan **Filter** väljer du det attribut som du vill använda för att skapa filter.
   1. Ange filteroperatörerna så att filtret definieras för varje markerat attribut.
   1. Välj **Tillämpa** för att lägga till filtren till måttet.

1. Om du vill lägga till dimensioner väljer du **Dimension** i konfigurationsområdet. Dimensioner visas som kolumner i måttutdataentiteten.
   1. Välj **Redigera dimensioner** för att lägga till dataattribut som du vill gruppera måttvärdena efter. Till exempel ort eller kön. Som standard väljs dimensionen *Kund-ID* för att skapa *mått på kundnivå*. Du kan ta bort standarddimensionen om du vill skapa *mått på företagsnivå*.
   1. Välj **Klart** för att lägga till dimensionerna till måttet.

1. Om det finns flera sökvägar mellan den dataentitet du mappade och entiteten Kund måste du välja någon av de identifierade [entitetsrelationssökvägarna](relationships.md). Resultaten av måtten kan variera beroende på den valda sökvägen.
   1. Välj **Datainställningar** och välj den entitetssökväg som ska användas för att identifiera måttet.
   1. Välj **Klart** för att tillämpa dina val. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Välj entitetssökvägen för måttet.":::

1. Om du vill lägga till fler beräkningar för måttet väljer du **Ny beräkning**. Du kan endast använda entiteter på samma entitetssökväg för nya beräkningar. Fler beräkningar visas som nya kolumner i måttutdataentiteten.

1. Välj **...** i beräkningen för att **duplicera**, **byta namn på** eller **ta bort** en beräkning från ett mått.

1. I området **Förhandsgranskning** ser du dataschemat för måttutdataentiteten, inklusive filter och dimensioner. Förhandsgranskningen reagerar dynamiskt på ändringar i konfigurationen.

1. Välj **Kör** för att beräkna resultaten för det konfigurerade måttet. Välj **Spara och stäng** om du vill behålla den aktuella konfigurationen och köra måttet senare.

1. Gå till **Mått** för att se det nyskapade måttet i listan.

## <a name="manage-your-measures"></a>Hantera dina mått

När du har [skapat ett mått](#create-a-measure) visas en lista med mått på sidan **Mått**.

Här finns information om måttypen, den som skapade den, datumet då den skapades, statusen och tillståndet. När du väljer ett mått i listan kan du förhandsgranska utdata och hämta en .CSV-fil.

Om du vill uppdatera alla dina åtgärder samtidigt markerar du **Uppdatera allt** utan att välja ett specifikt mått.

> [!div class="mx-imgBorder"]
> ![Åtgärder för att hantera enskilda mått](media/measure-actions.png "Åtgärder för att hantera enskilda mått")

Välj ett mått i listan för följande alternativ:

- Markera måttets namn om du vill se detaljerna.
- **Redigera** måttets konfiguration.
- **Uppdatera** måttet baserat på senaste data.
- **Byt namn** på mått.
- **Ta bort** måttet.
- **Aktivera** eller **Inaktivera**. Inaktiva mått uppdateras inte vid en [schemalagd uppdatering](system.md#schedule-tab).

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="next-step"></a>Nästa steg

Du kan använda befintliga mått för att skapa [ett kundsegment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]