---
title: Skapa och hantera mått
description: Definiera mått som ska analyseras och reflektera företagets resultat.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f6be11bd97be71bc0c3a58eaee4d8ed45f535877
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732748"
---
# <a name="define-and-manage-measures"></a>Definiera och hantera mått

Åtgärder hjälper dig att få en bättre förståelse av kundbeteenden och affärsresultat. De tittar på relevanta värden från [enhetliga profiler](data-unification.md). Ett företag vill till exempel se den *totala kostnaden per kund* för att förstå en enskild kunds köphistorik eller mäta företagets *totala försäljning* för att förstå den sammanlagda omsättningen för hela verksamheten.  

Mått skapas med måttverktyget, en datafrågeställningsplattform med olika operatörer och enkla mappningsalternativ. Du kan filtrera data, gruppera resultat, identifiera [entitetsrelationssökvägar](relationships.md) och förhandsgranska utdata.

Använd måttverktyget om du vill planera affärsaktiviteter genom att fråga efter kunddata och extrahera insikter. Om du till exempel skapar ett mått på *totalsumma per kund* och *total intäkt per kund* kan du identifiera en grupp av kunder som spenderar mycket men ger höga intäkter. Du kan [skapa ett segment](segments.md) för att driva på nästa bästa åtgärd. 

## <a name="build-your-own-measure-from-scratch"></a>Bygg upp ditt eget mått från början

Det här avsnittet innehåller information om hur du skapar ett nytt mått från grunden. Du kan skapa ett mått med dataattribut från dataentiteter som har en relation konfigurerad för att ansluta till entiteten för en enhetlig kundprofil.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

1. I målgruppsinsikter går du till **Åtgärder**.

1. Välj **Ny** och välj **Skapa din egen**.

1. Välj **Redigera namn** och tillhandahåll ett **namn** för måttet. 

1. Välj en sammansättningsfunktion i listrutan **Välj funktion** i konfigurationsområdet. Sammansättningsfunktioner omfattar: 
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
  
   1. I avsnittet **Lägg till attribut** i fönstret **Filter** väljer du det attribut som du vill använda för att skapa filter.
   1. Ange filteroperatörerna så att filtret definieras för varje markerat attribut.
   1. Välj **Tillämpa** för att lägga till filtren till måttet.

1. Om du vill lägga till dimensioner väljer du **Dimension** i konfigurationsområdet. Dimensioner visas som kolumner i måttutdataentiteten.
 
   1. Välj **Redigera dimensioner** för att lägga till dataattribut som du vill gruppera måttvärdena efter. Till exempel ort eller kön. Som standard väljs dimensionen *Kund-ID* för att skapa *mått på kundnivå*. Du kan ta bort standarddimensionen om du vill skapa *mått på företagsnivå*.
   1. Välj **Klart** för att lägga till dimensionerna till måttet.

1. Om det finns värden i dina data som du behöver byta ut mot ett heltal väljer du **Regler**. Konfigurera regeln och se till att du endast väljer heltal som ersättare. Ersätt till exempel *null* med *0*.

1. Om det finns flera sökvägar mellan den dataentitet du mappade och entiteten *Kund* måste du välja någon av de identifierade [entitetsrelationssökvägarna](relationships.md). Resultaten av måtten kan variera beroende på den valda sökvägen. 
   
   1. Välj **Relationssökväg** och välj den entitetsväg som ska användas för att identifiera ditt mått. Om det bara finns en enskild sökväg till entiteten *Kund* visas inte den här kontrollen.
   1. Välj **Klart** för att tillämpa dina val. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Välj entitetssökvägen för måttet.":::

1. Om du vill lägga till fler beräkningar för måttet väljer du **Ny beräkning**. Du kan endast använda entiteter på samma entitetssökväg för nya beräkningar. Fler beräkningar visas som nya kolumner i måttutdataentiteten.

1. Välj **...** i beräkningen för att **duplicera**, **byta namn på** eller **ta bort** en beräkning från ett mått.

1. I området **Förhandsgranskning** ser du dataschemat för måttutdataentiteten, inklusive filter och dimensioner. Förhandsgranskningen reagerar dynamiskt på ändringar i konfigurationen.

1. Välj **Kör** för att beräkna resultaten för det konfigurerade måttet. Välj **Spara och stäng** om du vill behålla den aktuella konfigurationen och köra måttet senare.

1. Gå till **Mått** för att se det nyskapade måttet i listan.

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

1. I målgruppsinsikter går du till **Åtgärder**.

1. Välj **Ny** och välj **Skapa din egen**.

1. Välj **Redigera namn** och tillhandahåll ett **namn** för måttet. 

1. Välj en sammansättningsfunktion i listrutan **Välj funktion** i konfigurationsområdet. Sammansättningsfunktioner omfattar: 
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
  
   1. I avsnittet **Lägg till attribut** i fönstret **Filter** väljer du det attribut som du vill använda för att skapa filter.
   1. Ange filteroperatörerna så att filtret definieras för varje markerat attribut.
   1. Välj **Tillämpa** för att lägga till filtren till måttet.

1. Om du vill lägga till dimensioner väljer du **Dimension** i konfigurationsområdet. Dimensioner visas som kolumner i måttutdataentiteten.
 
   1. Välj **Redigera dimensioner** för att lägga till dataattribut som du vill gruppera måttvärdena efter. Till exempel ort eller kön. Som standard väljs dimensionen *Kund-ID* för att skapa *mått på kundnivå*. Du kan ta bort standarddimensionen om du vill skapa *mått på företagsnivå*.
   1. Välj **Klart** för att lägga till dimensionerna till måttet.

1. Om det finns värden i dina data som du behöver byta ut mot ett heltal väljer du **Regler**. Konfigurera regeln och se till att du endast väljer heltal som ersättare. Ersätt till exempel *null* med *0*.

1. Du kan använda växlingen **Sammanslagning av delkonton** om du [använder konton med hierarkier](relationships.md#set-up-account-hierarchies).
   - Om det är inställt på **Av** beräknas måttet för varje konto. Varje konto får sitt eget resultat.
   - Om den har angetts till **På** väljer du **Redigera** för att välja kontohierarkin enligt de hämtade hierarkierna. Måttet ger bara ett resultat eftersom det är aggregerat med underkonton.

1. Om det finns flera sökvägar mellan den dataentitet du mappade och entiteten *Kund* måste du välja någon av de identifierade [entitetsrelationssökvägarna](relationships.md). Resultaten av måtten kan variera beroende på den valda sökvägen. 
   
   1. Välj **Relationssökväg** och välj den entitetsväg som ska användas för att identifiera ditt mått. Om det bara finns en enskild sökväg till entiteten *Kund* visas inte den här kontrollen.
   1. Välj **Klart** för att tillämpa dina val. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Välj entitetssökvägen för måttet.":::

1. Välj **...** i beräkningen för att **duplicera**, **byta namn på** eller **ta bort** en beräkning från ett mått.

1. I området **Förhandsgranskning** ser du dataschemat för måttutdataentiteten, inklusive filter och dimensioner. Förhandsgranskningen reagerar dynamiskt på ändringar i konfigurationen.

1. Välj **Kör** för att beräkna resultaten för det konfigurerade måttet. Välj **Spara och stäng** om du vill behålla den aktuella konfigurationen och köra måttet senare.

1. Gå till **Mått** för att se det nyskapade måttet i listan.

---

## <a name="use-a-template-to-build-a-measure"></a>Skapa ett mått med hjälp av en mall

Du kan använda fördefinierade mallar med vanliga åtgärder för att skapa dem. Detaljerade beskrivningar av mallarna och en guidad upplevelse hjälper dig att skapa effektiva mått. Mallar bygger på mappade data från entiteten *Enhetlig aktivitet*. Kontrollera därför att du har konfigurerat [kundaktiviteter](activities.md) innan du skapar ett mått från en mall.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

Du kan använda fördefinierade mallar med vanliga åtgärder för att skapa dem. Detaljerade beskrivningar av mallarna och en guidad upplevelse hjälper dig att skapa effektiva mått. Mallar bygger på mappade data från entiteten *Enhetlig aktivitet*. Kontrollera därför att du har konfigurerat [kundaktiviteter](activities.md) innan du skapar ett mått från en mall.

Tillgängliga mätmallar: 
- Genomsnittligt transaktionsvärde
- Totalt transaktionsvärde
- Genomsnittlig daglig intäkt
- Genomsnittlig årlig intäkt
- Transaktionsantal
- Intjänade lojalitetspoäng
- Inlösta lojalitetspoäng
- Saldo för lojalitetspoäng
- Livslängd för aktiv kund
- Lojalitetsmedlemskapets varaktighet
- Tid sedan senaste inköpet

I följande procedur beskrivs stegen för att skapa ett nytt mått med hjälp av en mall.

1. I målgruppsinsikter går du till **Åtgärder**.

1. Välj **Ny** och markera **Välj en mall**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Skärmbild på listrutan när du skapar ett nytt mått med markering i mallen.":::

1. Hitta den mall som passar dina behov och välj **Välj mall**.

1. Granska de data som krävs och välj **Kom igång** om alla data är på plats.

1. I rutan **Redigera namn** ange namn för måttet och utdataentiteten. 

1. Välj **Utfört**.

1. I avsnittet **Ange tidsperiod** definierar du tidsram för de data som ska användas. Välj om du vill att det nya måttet ska täcka hela datauppsättningen genom att välja **Hela tiden** eller att måttet ska fokusera på en **Speficik tidsperiod**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skärmbild som visar avsnittet tidsperiod när du konfigurerar ett mått från en mall.":::

1. Välj **Lägg till data** i nästa avsnitt om du vill välja aktiviteter och mappa motsvarande data från entiteten *Enhetlig aktivitet*.

    1. Steg 1 av 2: Under **Aktivitetstyp** väljer du vilken typ av entitet du vill använda. Välj de **Aktiviteter** väljer du de entiteter du vill mappa.
    1. Steg 2 av 2: Välj attributet från entiteten *Enhetlig aktivitet* för den komponent som krävs av formeln. För genomsnittstransaktionsvärdet är det till exempel attributet som representerar transaktionsvärdet. För **tidsstämpeln för aktivitet** väljer du attributet från entiteten Enhetlig aktivitet som representerar datum och tid för aktiviteten.
   
1. När datamappningen är klar kan du se statusen **Slutförd** och namnet på de mappade aktiviteterna och attributen.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Skärmbild av en slutförd måttmallskonfiguration.":::

1. Nu kan du välja **Kör** för att beräkna resultatet av åtgärden. Om du vill förfina den senare markerar du **Spara utkast**.

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

Den här funktionen är endast tillgänglig för åtgärder som har skapats i miljöer med enskilda kunder som primär målgrupp.

---

## <a name="manage-your-measures"></a>Hantera dina mått

Listan med åtgärder finns på sidan **Mått**.

Här finns information om måttypen, den som skapade den, datumet då den skapades, statusen och tillståndet. När du väljer ett mått i listan kan du förhandsgranska utdatan och hämta en CSV-fil.

Om du vill uppdatera alla dina åtgärder samtidigt markerar du **Uppdatera allt** utan att välja ett specifikt mått.

> [!div class="mx-imgBorder"]
> ![Åtgärder för att hantera enskilda mått.](media/measure-actions.png "Åtgärder för att hantera enskilda mått.")

Välj ett mått i listan för följande alternativ:

- Markera måttets namn om du vill se detaljerna.
- **Redigera** måttets konfiguration.
- **Uppdatera** måttet baserat på senaste data.
- **Byt namn** på mått.
- **Ta bort** måttet.
- **Aktivera** eller **Inaktivera**. Inaktiva mått uppdateras inte vid en [schemalagd uppdatering](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Nästa steg

Du kan använda befintliga åtgärder för att skapa [ett kundsegment](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
