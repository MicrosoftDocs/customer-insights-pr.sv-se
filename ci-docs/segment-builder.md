---
title: Skapa komplexa segment med segmentverktyget
description: Använd segmentbyggaren för att skapa komplexa segment av kunder genom att gruppera dem baserat på olika attribut.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304771"
---
# <a name="create-complex-segments-with-segment-builder"></a>Skapa komplexa segment med segmentverktyget

Definiera komplexa filter runt den enhetliga kund eller enhetliga kontakt och det är relaterade entiteter. Varje segment skapar en uppsättning kundentitetsposter eller kontaktpost som du kan exportera och utföra åtgärder på efter bearbetning.

> [!TIP]
> Segment som är baserade på **enskilda kunder** innehåller automatiskt tillgänglig kontaktinformation för segmentmedlemmar. I **affärskonton**, om du [förena](data-unification.md) både konton och kontakter, välj om segmentet är baserat på konton eller affärskontakter. Om du vill exportera kontaktinformation till en destination använder du ett kontaktsegment. Om du vill exportera kontaktinformation till en destination använder du ett kontosegment.

## <a name="segment-builder"></a>Segmentverktyg

Följande bild illustrerar de olika delarna av segmentverktyget. Den visar ett segment som resulterar i en grupp kunder. Kunderna ordnade varor i en specifik tidsram samlade ihop förmånspoäng eller använde en viss summa pengar.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Element i segmentverktyget." lightbox="media/segment-builder-overview.png":::

1. Ordna ditt segment med regler och underregler. Varje regel eller underregel består av villkor. Kombinera villkoren med logiska operatorer.

1. Välj [relationssökvägen](relationships.md) mellan entiteter som gäller för en regel. Relationssökvägen avgör vilka attribut som kan användas i ett villkor.

1. Hantera regler och underregler. Ändra positionen för en regel eller ta bort den.

1. Lägg till villkor och bygg upp rätt kapslingsnivå med hjälp av underregler.

1. Tillämpa uppsättningsåtgärder på anslutna regler.

1. Använd attributrutan om du vill lägga till tillgängliga entitetsattribut eller skapa villkor för attribut. I rutan visas listan över entiteter och attribut som är tillgängliga för den valda regeln utifrån den valda relationssökvägen.

1. Lägg till villkor baserat på attribut i befintliga regler och underregler eller lägg till det i en ny regel.

1. Ångra och gör om ändringar medan du skapar segmenten.

Exemplet ovan illustrerar segmenteringsfunktionerna. Vi har definierat ett segment för kunder som köpt varor för minst $ 500 online *och* som har ett intresse för programvaruutveckling.

## <a name="create-a-new-segment-with-segment-builder"></a>Skapa ett nytt segment med segmentverktyget

1. Gå till **Segment**.

1. Välj **Ny** > **Skapa din egen**. På sidan för segmentverktyget definierar eller skapar du regler. En regel består av ett eller flera villkor som definierar en uppsättning kunder.

   > [!NOTE]
   > För miljöer som bygger på affärskonton väljer **Nytt** > **Segment med konton** eller **Segment av kontakter (förhandsgranskning)** baserat på vilken typ av segment du vill skapa. Om en [kontohierarki](relationships.md#set-up-account-hierarchies) har definierats och du vill skapa regler för att filtrera bort data baserat på underordnad- och överordnad relation, välj **Använd hierarki? (förhandsvisning)**, välj hierarkin och sedan **Tillämpa**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Välj segment rutan för kontohierarki.":::

1. Välj **Redigera information** bredvid Namnlöst segment. Ange ett namn för ditt segment och uppdatera det föreslagna **Namnet på utdataentiteten** för segmentet. Alternativt kan du lägga till en beskrivning och [taggar](work-with-tags-columns.md#manage-tags) i segmentet.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogrutan Redigera information.":::

1. I avsnittet **Regel 1** väljer du ett attribut för en entitet som du vill filtrera kunderna efter. Det finns två sätt att välja attribut:
   - Granska listan med tillgängliga entiteter och attribut i rutan **Lägg till regel** och välj ikonn **+** bredvid det alltribut du vill lägga till. Välj om du vill lägga till attributet i en befintlig regel eller använda det för att skapa en ny regel.
   - Ange namnet på attributet i regelavsnittet om du vill se förslag som matchar.

1. Välj operatorer om du vill ange matchningsvärdena för villkoret. Attribut kan ha någon av fyra datatyper som värde: numerisk, sträng, datum eller boolesk. Beroende på attributets datatyp kan olika operatorer ange villkoret.

1. Välj **Lägg till villkor** om du vill lägga till fler villkor i en regel. Om du vill skapa en regel under den aktuella regeln väljer du **Lägg till underregel**.

1. Om en regel använder andra entiteter än *Kund* (eller entiteten *ContactProfile* för B2B), välj **Ange relationssökväg** för att mappa den valda enheten till den förenade kundenheten. Om det bara finns en möjlig relationssökväg markeras denna automatiskt av systemet. Olika [relationssökvägar](relationships.md#relationship-paths) kan ge olika resultat. Alla regler kan ha sin egen relationssökväg.

   :::image type="content" source="media/relationship-path.png" alt-text="Möjlig relationssökväg när en regel skapas utifrån en entitet som är mappad till entiteten för enhetlig kundprofil.":::

1. Om det finns flera villkor i en regel kan du välja vilken logisk operator som ska ansluta dem.  
   - Operatorn **OCH**: Alla villkor måste uppfyllas för att en post ska ingå i segmentet. Använd det här alternativet när du definierar villkor för olika entiteter.
   - Operatorn **ELLER**: Något av villkoren måste uppfyllas för att en post ska ingå i segmentet. Använd det här alternativet när du definierar flera villkor för samma entiteter.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med två &quot;OCH&quot;-villkor.":::

   När du använder operatorn ELLER måste alla villkor baseras på entiteter som ingår i relationssökvägen.

1. Du kan skapa flera regler för att skapa olika uppsättningar med kundposter. Du kan kombinera grupper så att de kunder som krävs för ditt affärsfall inkluderas. Om du inte kan ta med en entitet i en regel på grund av den angivna relationssökvägen, måste du skapa en ny regel för att välja attribut som formar den.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lägg till en ny regel i ett segment och välj den inställda operatorn.":::

   1. Välj **Lägg till regel**.
   1. Välj en av uppsättningsoperatorerna: **Union**, **Skärning** eller **Förutom**.

      - **Sammanförande** sammanför de två grupperna.
      - **Överlappande** överlappar de två grupperna. Endast data som *är gemensamma* för båda grupperna finns kvar i den enhetliga gruppen.
      - **Förutom** kombinerar de två grupperna. Endast data i grupp A som *inte är gemensamma* med data i grupp B bevaras.

1. Som standard innehåller utdataentitet automatiskt alla attribut för kundprofiler som matchar de definierade filtren. När du använder entiteten *ContactProfile* inkluderas konto-ID automatiskt i B2B. Om ett segment är baserat på andra entiteter än *Kund* eller för att inkludera fler attribut från *ContactProfile*, välj **Projektattribut** för att lägga till fler attribut från dessa enheter till utdataenheten.
 
   Ett segment baseras till exempel på en entitet som innehåller köpdata, som är relaterad till entiteten *Kund*. I detta segment söker man efter alla kunder från Spanien som har köpt varor det aktuella året. Du kan välja att lägga till attribut som varornas pris eller köpdatumet i alla matchande kundposter i utdataentiteten. Denna information kan vara användbar om du vill analysera säsongsrelaterade korrelationer till de totala utgifterna.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exempel på projicerade attribut som markerats i den sidoruta som ska läggas till i utdataentiteten.":::
 
   Ett exempel på utdata för ett segment som bygger på affärskonton med projekterade attribut för kontakter kan se ut så här:

   |ID  |Kontonamn  |Intäkter  |Kontaktnamn  | Kontaktens roll|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, inköpschef]

   > [!NOTE]
   > - **Projektattribut** fungerar endast för entiteter som har en 1:N-relationer-relation med entiteten *kund* eller *ContactProfile*. En kund kan till exempel ha flera prenumerationer.
   > - Om attributet du vill projektera är mer än en hop från entiteten *Kund* eller *ContactProfile*, enligt relationens definition, ska attributet användas i alla regler i segmentfrågan som du skapar.
   > - Om attributet du vill projektera är bara ett hopp från entiteten *Kund* eller *ContactProfile*, det attributet behöver inte vara närvarande i alla regler i segmentfrågan som du skapar.
   > - **Projekterade attribut** räknas in när du använder uppsättningsoperatorer.

1. Välj **Kör** för att skapa segmentet. Välj **Spara** om du vill behålla den aktuella konfigurationen och köra segment senare. Sidan **Segment** visas.

### <a name="segment-builder-tips"></a>Segmentverktygstips

Tänk på följande tips när du skapar ett segment med segmentverktyget:

- Segmentverktyget föreslår inga giltiga värden från entiteter när operatorerna anges för villkoren. Du kan gå till **Data** > **Entiteter** och ladda ned entitetsdata för att se vilka värden som är tillgängliga.
- Med villkor baserade på datumen kan du växla mellan fasta datum och ett flexibelt datumintervall.
- Om du har flera regler för ditt segment har regeln du redigerar en stående blå linje bredvid den.
- Du kan flytta regler och villkor till andra platser i segmentdefinitionen. Välj den stående ellipsen (&vellip;) bredvid en regel eller ett villkor och välj hur och var den ska flyttas.
- Med kontrollerna **Ångra** och **Gör om** i kommandofältet kan du återställa ändringar.
- När du har skapat ett segment kan du använda vissa segment för att [spåra användningen av segmentet](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Nästa steg

[Exportera ett segment ](export-destinations.md)och utforska [integreringen av kundkort](customer-card-add-in.md) för att använda segment i andra program.

[!INCLUDE [footer-include](includes/footer-banner.md)]
