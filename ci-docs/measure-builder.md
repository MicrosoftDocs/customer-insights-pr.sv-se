---
title: Skapa nya mått med måttverktyget
description: Skapa mått från grunden och analysera viktiga värden för din verksamhet.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647917"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Med måttverktyget kan du skapa mått från grunden

I den här artikeln förklaras hur du skapar ett nytt [mått](measures.md) från grunden. Med måttverktyget kan du definiera beräkningar med hjälp av operatörer, sammansättningsfunktioner och filter. Du kan skapa ett mått med attribut från entiteter som är relaterade till den enhetliga *kund*-entiteten.

Att skapa mått i B2C- och B2B-miljöer fungerar på samma sätt. Men om din B2B-miljö [använder konton med hierarkier](relationships.md#set-up-account-hierarchies) kan du välja att aggregera måttet över relaterade underkonton.

Du kan också snabbt skapa ett mått genom att välja bland en uppsättning vanliga och fördefinierade mått. Mer information finns i [Använda en mall för att skapa ett mått](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

Du kan skapa mått på nivån för enskilda kunder (kundattribut, kundmått) eller på nivån för företaget/organisationen (affärsmått). Kundattribut och kundmått är två typer som du kan använda för att spåra prestanda per kund. Till exempel den totala kostnaden för varje kund. Med affärsåtgärder kan du spåra prestationer per verksamhet. Till exempel den totala omsättningen per företag.

- Kundattribut: Genererar utdata som ett nytt attribut, som sparas som en ny kolumn i den systemgenererade entiteten med namnet *Customer_Measure*. När du uppdaterar ett kundattribut uppdateras alla andra kundattribut i entiteten *Customer_Measure* samtidigt. Dessutom visas kundattribut i kundprofilkort. När kundattributet har körts eller sparats kan du inte ändra det till ett kundmått.

- Kundmått: Genererar utdata som sin egen entitet och du kan inte ändra den till ett kundattribut när du har kört eller sparat det. Kundmått visas inte på kundprofilkort.

- Affärsmått: Genererar utdata som sin egen entitet och visas på startsidan för din Customer Insights-miljö.

1. Gå till **Mått**.

1. Välj **Ny** och välj **Skapa din egen**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tom konfigurationsskärm för ett B2C-mått. " lightbox="media/measure-b2c.png":::

1. Om du vill spåra prestanda på företagsnivå växlar du **Måttyp** till **Företagsnivå**. Som standard är **Kundnivå** valt. **Kundnivå** lägger automatiskt till attributet *CustomerId* i Mått medan **affärsnivå** automatiskt tar bort det.

1. Välj en sammansättningsfunktion i listrutan **Välj funktion** i konfigurationsområdet. Sammansättningsfunktioner omfattar:
   - **Sum**
   - **Medel**
   - **Antal**
   - **Antal unika**
   - **Max**
   - **Min**
   - **Först**: tar det första värdet i dataposten
   - **Sist:** tar det sista värdet som lades till i dataposten
   - **ArgMax**: hittar dataposten som ger det maximala värdet från en målfunktion
   - **ArgMin**: hittar dataposten som ger det minsta värdet från en målfunktion

1. Välj **Lägg till attribut** för att välja de data du behöver för att skapa måttet.

   1. Välj fliken **Attribut**.
   1. Dataentitet: Välj den entitet som innehåller attributet du vill mäta.
   1. Dataattribut: Välj det attribut som du vill använda i sammansättningsfunktionen för att beräkna måttet. Du kan bara välja ett attribut åt gången.
   1. Du kan också välja ett dataattribut från ett befintligt mått genom att välja fliken **Mått**. Du kan också söka efter ett entitets- eller måttnamn.
   1. Välj **Lägg till** för att lägga till det valda attributet till måttet.

1. Om du vill skapa mer komplexa mått kan du lägga till fler attribut eller använda olika operatörer i måttfunktionen.

1. Om du vill lägga till filter väljer du **Filter** i konfigurationsområdet. Vid användning av filter används endast de poster som matchar filtren för att beräkna måttet.
  
   1. I avsnittet **Lägg till attribut** i fönstret **Filter** väljer du det attribut som du vill använda för att skapa filter.
   1. Ange filteroperatörerna så att filtret definieras för varje markerat attribut.
   1. Välj **Tillämpa** för att lägga till filtren till måttet.

1. Välj **Dimension** för att välja fler fält som läggs till som kolumner i entiteten för måttutdata.

   1. Välj **Redigera dimensioner** för att lägga till dataattribut som du vill gruppera måttvärdena efter. Till exempel ort eller kön.
   > [!TIP]
   > Om du valde **Kundnivå** som **Måttyp** har attributet *CustomerId* redan lagts till. Om du tar bort attributet växlar **Måttyp** till **Affärsnivå**.
   1. Välj **Klart** för att lägga till dimensionerna till måttet.

1. Om det finns värden i dina data som du behöver byta ut mot ett heltal väljer du **Regler**. Konfigurera regeln och se till att du endast väljer heltal som ersättare. Ersätt till exempel *null* med *0*.

1. Om det finns flera sökvägar mellan den dataentitet du mappade och entiteten *Kund* måste du välja någon av de identifierade [entitetsrelationssökvägarna](relationships.md). Resultaten av måtten kan variera beroende på den valda sökvägen.

   1. Välj **Relationssökväg** och välj den entitetsväg som ska användas för att identifiera ditt mått. Om det bara finns en enskild sökväg till entiteten *Kund* visas inte den här kontrollen.
   1. Välj **Klart** för att tillämpa dina val.

1. Om du vill lägga till fler beräkningar för måttet väljer du **Ny beräkning**. Du kan endast använda entiteter på samma entitetssökväg för nya beräkningar. Fler beräkningar visas som nya kolumner i måttutdataentiteten.

1. Välj **...** i beräkningen för att **duplicera**, **byta namn på** eller **ta bort** en beräkning från ett mått.

1. I området **Förhandsgranskning** ser du dataschemat för måttutdataentiteten, inklusive filter och dimensioner. Förhandsgranskningen reagerar dynamiskt på ändringar i konfigurationen.

1. Välj **Redigera information** bredvid Namnlöst mått. Ange ett namn för måttet. Alternativt kan du lägga till [taggar](work-with-tags-columns.md#manage-tags) i måttet.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogrutan Redigera information.":::

1. Välj **Kör** för att beräkna resultaten för det konfigurerade måttet. Välj **Spara och stäng** om du vill behålla den aktuella konfigurationen och köra måttet senare.

1. Gå till **Mått** för att se det nyskapade måttet i listan.

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

Du kan skapa mått på nivån för enskilda konton (kundmått) eller på nivån för alla konton (affärsmått).

- Kundmått: Genererar utdata som sin egen entitet. Kundmått visas inte på kundprofilkort.

- Affärsmått: Genererar utdata som sin egen entitet och visas på startsidan för din Customer Insights-miljö.

1. Gå till **Mått**.

1. Välj **Nytt**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tom konfigurationsskärm för ett B2B-mått. ":::

1. Välj en sammansättningsfunktion i listrutan **Välj funktion** i konfigurationsområdet. Sammansättningsfunktioner omfattar:
   - **Sum**
   - **Medel**
   - **Antal**
   - **Antal unika**
   - **Max**
   - **Min**
   - **Först**: tar det första värdet i dataposten
   - **Sist:** tar det sista värdet som lades till i dataposten

1. Välj **Lägg till attribut** för att välja de data du behöver för att skapa måttet.

   1. Välj fliken **Attribut**.
   1. Dataentitet: Välj den entitet som innehåller attributet du vill mäta.
   1. Dataattribut: Välj det attribut som du vill använda i sammansättningsfunktionen för att beräkna måttet. Du kan bara välja ett attribut åt gången.
   1. Du kan också välja ett dataattribut från ett befintligt mått genom att välja fliken **Mått**. Du kan också söka efter ett entitets- eller måttnamn.
   1. Välj **Lägg till** för att lägga till det valda attributet till måttet.

1. Om du vill skapa mer komplexa mått kan du lägga till fler attribut eller använda olika operatörer i måttfunktionen.

1. Om du vill lägga till filter väljer du **Filter** i konfigurationsområdet. Vid användning av filter används endast de poster som matchar filtren för att beräkna måttet.
  
   1. I avsnittet **Lägg till attribut** i fönstret **Filter** väljer du det attribut som du vill använda för att skapa filter.
   1. Ange filteroperatörerna så att filtret definieras för varje markerat attribut.
   1. Välj **Tillämpa** för att lägga till filtren till måttet.

1. Välj **Dimension** för att välja fler fält som läggs till som kolumner i entiteten för måttutdata.

   1. Välj **Redigera dimensioner** för att lägga till dataattribut som du vill gruppera måttvärdena efter. Till exempel ort eller kön.
      > [!TIP]
      > Om du valde **Kundnivå** som **Måttyp** har attributet *CustomerId* redan lagts till. Om du tar bort attributet växlar **Måttyp** till **Affärsnivå**.
   1. Välj **Klart** för att lägga till dimensionerna till måttet.

1. Om det finns värden i dina data som du behöver byta ut mot ett heltal väljer du **Regler**. Konfigurera regeln och se till att du endast väljer heltal som ersättare. Ersätt till exempel *null* med *0*.

1. Du kan använda växlingen **Sammanslagning av delkonton** om du [använder konton med hierarkier](relationships.md#set-up-account-hierarchies).
   - Om det är inställt på **Av** beräknas måttet för varje konto. Varje konto får sitt eget resultat.
   - Om den har angetts till **På** väljer du **Redigera** för att välja kontohierarkin enligt de hämtade hierarkierna. Måttet ger bara ett resultat eftersom det är aggregerat med underkonton.

1. Om det finns flera sökvägar mellan den dataentitet du mappade och entiteten *Kund* måste du välja någon av de identifierade [entitetsrelationssökvägarna](relationships.md). Resultaten av måtten kan variera beroende på den valda sökvägen.

   1. Välj **Relationssökväg** och välj den entitetsväg som ska användas för att identifiera ditt mått. Om det bara finns en enskild sökväg till entiteten *Kund* visas inte den här kontrollen.
   1. Välj **Klart** för att tillämpa dina val.

1. Välj **...** i beräkningen för att **duplicera**, **byta namn på** eller **ta bort** en beräkning från ett mått.

1. I området **Förhandsgranskning** ser du dataschemat för måttutdataentiteten, inklusive filter och dimensioner. Förhandsgranskningen reagerar dynamiskt på ändringar i konfigurationen.

1. Välj **Redigera information** bredvid Namnlöst mått. Ange ett namn för måttet. Alternativt kan du lägga till [taggar](work-with-tags-columns.md#manage-tags) i måttet.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogrutan Redigera information.":::

1. Välj **Kör** för att beräkna resultaten för det konfigurerade måttet. Välj **Spara och stäng** om du vill behålla den aktuella konfigurationen och köra måttet senare.

1. Gå till **Mått** för att se det nyskapade måttet i listan.
