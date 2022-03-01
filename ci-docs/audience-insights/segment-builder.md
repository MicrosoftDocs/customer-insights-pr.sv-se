---
title: Skapa och hantera segment.
description: Skapa segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064959"
---
# <a name="create-and-manage-segments"></a>Skapa och hantera segment.

Definiera komplexa filter runt den enhetliga kundentiteten och det är relaterade entiteter. Varje segment skapar en uppsättning kundposter efter bearbetning som du kan exportera och utföra åtgärder på. Segment hanteras på sidan **Segment**. 

Följande exempel illustrerar segmenteringsfunktionen. Vi har definierat ett segment för kunder som beställde minst 500 $ av varor under de senaste 90 dagarna *och* som var inblandade i ett kundtjänstsamtal som har eskalerats.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Skärmbild av användargränssnittet för segmentverktyget med två grupper som anger ett kundsegment.":::

## <a name="create-a-new-segment"></a>Skapa ett nytt segment

Du kan skapa ett nytt segment på flera sätt. I det här avsnittet beskrivs hur du skapar ett *tomt segment* från grunden. Du kan också skapa ett *snabbsegment* som bygger på befintliga entiteter eller använda maskininlärning för att få *förslag på segment*. Mer information: [Segmentöversikt](segments.md).

När du skapar ett segment kan du spara ett utkast. Den sparas som ett inaktivt segment och kan inte aktiveras och avslutas med en giltig konfiguration.

1. Gå till sidan **Segment**.

1. Välj **nytt** > **tomt segment**.

1. I rutan **Nytt segment**, välj en segment typ:

   - **Dynamiska segment** [uppdateras](segments.md#refresh-segments) enligt ett återkommande schema.
   - **Statiska segment** körs en gång när du skapar det.

1. Ange **Utdataentitetens namn** för segment. Om du vill kan du ange en visningsnamn och en beskrivning som hjälper till att identifiera segmentet.

1. Välj **nästa** om du vill komma till sidan **segmentverktyget** där du definierar en grupp. En grupp är en uppsättning kunder.

1. Välj den enhet som innehåller attributet du vill segmentera efter.

1. Välj det attribut du vill segmentera efter. Attributet kan ha en av fyra värdetyper: numerisk, sträng, datum eller boolesk.

1. Välj en operator och ett värde för det valda attributet.

   > [!div class="mx-imgBorder"]
   > ![Anpassat gruppfilter](media/customer-group-numbers.png "Kundgruppfilter")

   |Antal |Definition  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attribut          |
   |3    |Operator         |
   |4    |Värde         |

   1. Om du vill lägga till villkor i en grupp kan du använda två logiska operatorer:

      - **OCH** operatör: båda villkoren måste uppfyllas som en del av segmenteringsprocessen. Det här alternativet är mest användbart när du definierar villkor för olika entiteter.

      - **ELLER** operatör: ett av villkoren behöver uppfyllas som en del av segmenteringsprocessen. Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.

      > [!div class="mx-imgBorder"]
      > ![ELLER operatör där något av villkoren behöver uppfyllas](media/segmentation-either-condition.png "ELLER operatör där något av villkoren behöver uppfyllas")

      Det går för närvarande att kapsla en **ELLER**-operatör under **OCH**-operatör, men inte tvärtom.

   1. Varje grupp matchar en uppsättning kunder. Du kan kombinera grupper så att de kunder som krävs för ditt affärsfall inkluderas.    
   Markera **Lägg till grupp**.

      > [!div class="mx-imgBorder"]
      > ![Lägg till grupp för kundgrupp](media/customer-group-add-group.png "Lägg till grupp för kundgrupp")

   1. Välj en av uppsättningsoperatorerna: **Union**, **Skärning** eller **Förutom**.

   > [!div class="mx-imgBorder"]
   > ![Lägg till sammanförande för kundgrupp](media/customer-group-union.png "Lägg till sammanförande för kundgrupp")

   - **Sammanförande** sammanför de två grupperna.

   - **Överlappande** överlappar de två grupperna. Endast data som *är gemensamma* för båda grupperna behålls i den enhetliga gruppen.

   - **Förutom** kombinerar de två grupperna. Endast data i grupp A som *inte är samma* som data i grupp B behålls.

1. Om entiteten är kopplad till den enhetliga kundentiteten via [Relationer](relationships.md) måste du definiera relationssökvägen för att skapa ett giltigt segment. Lägg till entiteterna från relationssökvägen tills du kan välja entiteten **kund: CustomerInsights** i listrutan. Välj sedan **Alla poster** för varje steg.

   > [!div class="mx-imgBorder"]
   > ![Relationssökväg under skapande av segment](media/segments-multiple-relationships.png "Relationssökväg under skapande av segment")

1. Som standard genererar segment en utdataentitet som innehåller alla attribut i kundprofiler som matchar de definierade filtren. Om ett segment bygger på andra entiteter än entiteten *Kund* kan du lägga till fler attribut från dessa entiteter i utdataentiteten. Välj **Projektattribut** om du vill välja vilka attribut som ska läggas till i utdataentiteten.  
  
   Exempel: Ett segment bygger på en entitet som innehåller kundaktivitetsdata som relaterar till entiteten *Kund*. I segmenten söker du efter alla kunder som har ringt supporten de senaste 60 dagarna. Du kan välja att lägga till samtalslängden och antalet anrop till alla matchande kundposter i utdataentiteten. Den här informationen kan vara användbar om du vill skicka ett e-postmeddelande med länkar till hjälpartiklar online och vanliga frågor och svar till kunder som ofta ringt.

   > [!NOTE]
   > - Projekterade attribut fungerar endast för entiteter som har en till flera-relation med kundentiteten. En kund kan till exempel ha flera prenumerationer.
   > - Du kan endast ha projektattribut från en entitet som används i varje grupp med segmentfrågor som du skapar.
   > - Projekterade attribut räknas in när du använder uppsättningsoperatorer.

1. Välj **Spara** för att spara dina segment. Segmentet sparas och bearbetas om alla krav är validerade. Annars sparas den som ett utkast.

1. Klicka på **Tillbaka till segment** för att gå tillbaka till sidan **Segment**.



## <a name="quick-segments"></a>Snabbsegment

Med snabbsegment kan du bygga enkla segment med en enda operator snabbt för snabbare insikter.

1. På sidan **Segment**, välj **Ny** > **Skapa från**.

   - Välj alternativet **profiler** för att skapa ett segment som baseras på entiteten för den *enhetliga kunden*.
   - Välj alternativet **Mått** om du vill skapa ett segment kring mått som du har skapat tidigare.
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

## <a name="next-steps"></a>Nästa steg

[Exportera ett segment](export-destinations.md) och utforska [kundkortet](customer-card-add-in.md) och [kontakterna](export-power-bi.md) för att komma igång med kundnivån.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
