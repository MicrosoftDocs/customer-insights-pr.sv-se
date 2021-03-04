---
title: Skapa och hantera segment.
description: Skapa segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270378"
---
# <a name="create-and-manage-segments"></a>Skapa och hantera segment.

Med segment kan du gruppera dina kunder baserat på demografiska attribut, transaktionella eller beteendemässiga attribut. Du kan använda segment för att rikta reklamkampanjer, säljaktiviteter och kundsupport för att uppnå dina affärsmål.

Du kan definiera komplexa filter runt entiteten kundprofil och dess relaterade entiteter. Varje segment skapar en uppsättning kundposter efter bearbetning som du kan exportera och utföra åtgärder på. Vissa [servicegränser](service-limits.md) gäller.

Om inget annat anges är alla segment **Dynamiska segment**, som uppdateras enligt ett återkommande schema.

Följande exempel illustrerar segmenteringsfunktionen. Vi har definierat ett segment för kunder som beställde minst 500 $ av varor under de senaste 90 dagarna *och* som var inblandade i ett kundtjänstsamtal som har eskalerats.

> [!div class="mx-imgBorder"]
> ![Flera grupper](media/segmentation-group1-2.png "Flera grupper")

## <a name="create-a-new-segment"></a>Skapa ett nytt segment

Segment hanteras på sidan **Segment**.

1. I målgruppsinsikter går du till sidan **Segment**.

2. Välj **nytt** > **tomt segment**.

3. I rutan **Nytt segment** välj en segmenttyp och ange ett **namn**.

   Om du vill kan du ange en visningsnamn och en beskrivning som hjälper till att identifiera segmentet.

4. Välj **nästa** om du vill komma till sidan **segmentverktyget** där du definierar en grupp. En grupp är en uppsättning kunder.

5. Välj den enhet som innehåller attributet du vill segmentera efter.

6. Välj det attribut du vill segmentera efter. Attributet kan ha en av fyra värdetyper: numerisk, sträng, datum eller boolesk.

7. Välj en operator och ett värde för det valda attributet.

   > [!div class="mx-imgBorder"]
   > ![Anpassat gruppfilter](media/customer-group-numbers.png "Kundgruppfilter")

   |Antal |Definition  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attribut          |
   |3    |Operator         |
   |4    |Värde         |

8. Om entiteten är kopplad till den enhetliga kundentiteten via [Relationer](relationships.md) måste du definiera relationssökvägen för att skapa ett giltigt segment. Lägg till entiteterna från relationssökvägen tills du kan välja entiteten **kund: CustomerInsights** i listrutan. Välj sedan **alla poster** för varje villkor.

   > [!div class="mx-imgBorder"]
   > ![Relationssökväg under skapande av segment](media/segments-multiple-relationships.png "Relationssökväg under skapande av segment")

9. Välj **Spara** för att spara dina segment. Segmentet sparas och bearbetas om alla krav är validerade. Annars sparas den som ett utkast.

10. Klicka på **Tillbaka till segment** för att gå tillbaka till sidan **Segment**.

## <a name="manage-existing-segments"></a>Hantera befintliga segment

På sidan **segment** kan du visa alla dina sparade segment och hantera dem.

Varje segment representeras av en rad som innehåller ytterligare information om segmentet.

Du kan sortera segmenten i en kolumn genom att markera kolumnrubriken.

Använd rutan **Sök** i det övre högra hörnet för att filtrera segmenten.

> [!div class="mx-imgBorder"]
> ![Alternativ för att hantera ett befintligt segment](media/segments-selected-segment.png "Alternativ för att hantera ett befintligt segment")

Följande åtgärd är tillgänglig när du väljer ett segment:

- **Visa** information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.
- **Redigera** segmentet om du vill ändra dess egenskaper.
- **Uppdatera** segmentet så att det omfattar senaste data.
- **Aktivera** eller **Inaktivera** segmentet. Segment har två möjliga tillstånd - aktiva eller inaktiva. Dessa tillstånd har praktiskt taget när de redigerar ett segment. För inaktiva segment finns segmentdefinitionen, men den innehåller inga kunder ännu. När du aktiverar ett segment ändras dess status från "inaktivt" till "aktivt" och sökningen börjar söka efter kunder som matchar segmentdefinitionen. Om en [schemalagd uppdatering](system.md#schedule-tab) har konfigurerats har inaktiva segment **Status** anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats. När ett inaktivt segment aktiveras uppdateras och tas med i schemalagda uppdateringar.
  Du kan också använda funktionen **Schemalägg senare** i listrutan **Aktivera/inaktivera** för att ange ett framtida datum och tid för aktivering och inaktivering av ett visst segment.
- **Byt namn** på segment.
- **Hämta** listan över medlemmar som en .CSV-fil.
- Alternativet **Lägg till** skickar listan med kund-ID i segmentet för bearbetning i ett annat program.
- **Ta bort** segment.

## <a name="refresh-segments"></a>Uppdatera segment

Du kan uppdatera alla segment på en gång genom att markera **Uppdatera alla** på sidan **Segment**, eller också kan du uppdatera ett eller flera segment när du markerar dem och väljer **Uppdatera** bland alternativen. Du kan även konfigurera en återkommande uppdatering på **Administratör** > **System** > **Schemalägg**.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="download-and-export-segments"></a>Ladda ned och exportera segment

Du kan hämta segmenten till en CSV-fil eller exportera dem till Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Ladda ned segment till en CSV-fil

1. I målgruppsinsikter går du till sidan **Segment**.

2. Välj en ellips på en specifik segmentpanel.

3. Välj **Hämta som CSV** i listrutan för åtgärder.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportera segment till Dynamics 365 Sales

Innan du exporterar segment till Dynamics 365 Sales måste en administratör [skapa exportmålet](export-destinations.md) för Dynamics 365 Sales.

1. I målgruppsinsikter går du till sidan **Segment**.

2. Välj en ellips på en specifik segmentpanel.

3. Välj **Lägg till** från listrutan åtgärder och välj det exportmål som du vill skicka data till.

## <a name="draft-mode-for-segments"></a>Utkastläge för segment

Om inte alla krav för att bearbeta ett segment uppfylls kan du spara segmentet som ett utkast och komma åt det från sidan **segment**.

Det sparas som ett inaktivt segment och kan inte aktiveras förrän det är giltigt.

## <a name="add-more-conditions-to-a-group"></a>Lägga till fler villkor i en grupp

Om du vill lägga till villkor i en grupp kan du använda två logiska operatorer:

- **OCH** operatör: båda villkoren måste uppfyllas som en del av segmenteringsprocessen. Det här alternativet är mest användbart när du definierar villkor för olika entiteter.

- **ELLER** operatör: ett av villkoren behöver uppfyllas som en del av segmenteringsprocessen. Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.

   > [!div class="mx-imgBorder"]
   > ![ELLER operatör där något av villkoren behöver uppfyllas](media/segmentation-either-condition.png "ELLER operatör där något av villkoren behöver uppfyllas")

Det går för närvarande att kapsla en **ELLER**-operatör under **OCH**-operatör, men inte tvärtom.

## <a name="combine-multiple-groups"></a>Kombinera flera grupper

Varje grupp skapar en specifik uppsättning kunder. Du kan kombinera grupperna så att de omfattar de kunder som krävs för affärsärendet.

1. I målgruppsinsikter går du till sidan **Segment** och väljer ett segment.

2. Markera **Lägg till grupp**.

   > [!div class="mx-imgBorder"]
   > ![Lägg till grupp för kundgrupp](media/customer-group-add-group.png "Lägg till grupp för kundgrupp")

3. Välj en av följande uppsättningar med operatorer: **förbindelse**, **överlappa** eller **förutom**.

   > [!div class="mx-imgBorder"]
   > ![Lägg till sammanförande för kundgrupp](media/customer-group-union.png "Lägg till sammanförande för kundgrupp")

   Välj en uppsättnings operatör kan du definiera en ny grupp. Spara olika grupper för att fastställa vilka data som ska behållas:

   - **Sammanförande** sammanför de två grupperna.

   - **Överlappande** överlappar de två grupperna. Endast data som *är gemensamma* för båda grupperna behålls i den enhetliga gruppen.

   - **Förutom** kombinerar de två grupperna. Endast data i grupp A som *inte är samma* som data i grupp B behålls.

## <a name="view-processing-history-and-segment-members"></a>Visa historik- och segmentmedlemmar för bearbetning

Du kan visa konsoliderade data om ett segment genom att granska dess detaljer.

På sidan **Segment**, välj det segment du vill granska.

Den övre delen av sidan innehåller ett trenddiagram som visualiserar ändringar i medlemsantal. Hovra över datapunkter om du vill visa antal medlemmar för ett visst datum.

Du kan uppdatera visualiseringens tidsram.

> [!div class="mx-imgBorder"]
> ![Tidsintervall för segment](media/segment-time-range.png "Tidsintervall för segment")

Den nedre delen innehåller en lista över segmentets medlemmar.

> [!NOTE]
> Fält som visas i listan bygger på attributen för segmentets entiteter.
>
>Listan är en förhandsgranskning av de matchande segmentmedlemmarna och visar de första 100 posterna för ditt segment så att du snabbt kan utvärdera den och granska dess definitioner om det behövs. Om du vill visa alla matchande poster måste du [exportera segmentet](export-destinations.md).

## <a name="quick-segments"></a>Snabbsegment

Förutom segmentbyggaren finns det en annan väg för att skapa segment. Med hjälp av snabbsegment kan du snabbt skapa enkla segment (med en enskild operator) och med omedelbara insikter.

1. På sidan **Segment** välj **Ny** > **Snabbskapa från**.

   - Välj alternativet **profiler** för att skapa ett segment som baseras på entiteten för den enhetliga kunden.
   - Välj alternativet **mått** för att skapa ett segment runt varje kundattribut av typen av mått som du redan har skapat på sidan **mått**.
   - Markera alternativet **Intelligens** om du vill skapa ett segment runt en av de utdataentiteter som du skapade med funktionerna **prediktioner** eller **anpassade modeller**.

2. I dialogrutan **Nytt snabbsegment**, välj ett attribut i listrutan **Fält**.

3. Systemet tillhandahåller ytterligare insikter som hjälper dig att skapa bättre segment av dina kunder.
   - För kategorifält visas tio populära kundräkningar. Välj ett **Värde** och välj **Granska**.

   - För ett numeriskt attribut visar systemet vilket attributvärde som faller under varje kunds percentil. Välj en **operatör** och ett **värde** och välj sedan **granska**.

4. Systemet tillhandahåller en **uppskattad segmentstorlek**. Du kan välja om du vill skapa ett segment som du har definierat eller om du först vill ha en annan segmentstorlek.

    > [!div class="mx-imgBorder"]
    > ![Namn och uppskattning för ett snabbsegment](media/quick-segment-name.png "Namn och uppskattning för ett snabbsegment")

5. Ange ett **namn** för ditt segment. Eventuellt ge en **visningsnamn**.

6. Välj **Spara** för att skapa segmentet.

7. När segmentet har bearbetat klart kan du visa det på samma sätt som andra segment som du har skapat.

För följande scenarier rekommenderar vi att du använder segmentbyggare i stället för de rekommenderade segmenten:

- Skapa segment med filter för kategorifält där operatorn är annorlunda än operatorn **Är**
- Skapa segment med filter för numeriska fält där operatorn är annorlunda än operatorerna **Mellan**, **Större än** och **Mindre än**
- Skapa segment med filter för datumtypfält

## <a name="next-steps"></a>Nästa steg

[Exportera ett segment](export-destinations.md) och utforska [kundkortet](customer-card-add-in.md) och [kontakterna](export-power-bi.md) för att komma igång med kundnivån.


[!INCLUDE[footer-include](../includes/footer-banner.md)]