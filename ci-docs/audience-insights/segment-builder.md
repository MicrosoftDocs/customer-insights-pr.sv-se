---
title: Skapa segment med segmentverktyget
description: Skapa segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 03/25/2022
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
ms.openlocfilehash: 1a28289ecb740ab6cdfa603b2cd66376e7e8b576
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529607"
---
# <a name="create-segments"></a>Skapa segment

Definiera komplexa filter runt den enhetliga kundentiteten och det är relaterade entiteter. Varje segment skapar en uppsättning kundposter efter bearbetning som du kan exportera och utföra åtgärder på. Segment hanteras på sidan **Segment**. Du kan [skapa nya segment](#create-a-new-segment) med hjälp av segmentverktyget eller [skapa snabbsegment](#quick-segments) från andra områden i appen.

> [!TIP]
> - Snabbsegment stöds endast i miljöer för **enskilda kunder**.
> - Segment som är baserade på **enskilda kunder** innehåller automatiskt tillgänglig kontaktinformation för segmentmedlemmar. I miljöer för **affärskonton** baseras segmenten på konton (företag eller dotterbolag). Om du vill ta med kontaktinformation i ett segment använder du funktionerna för **projektattribut** i segmentverktyget. Se till att kontaktdatakällorna är [semantiskt mappade till entiteten ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Segmentverktyg

Följande bild illustrerar de olika delarna av segmentverktyget. Den visar ett segment som resulterar i en grupp kunder. Kunderna ordnade varor i en specifik tidsram samlade ihop förmånspoäng eller använde en viss summa pengar.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Element i segmentverktyget." lightbox="media/segment-builder-overview.png":::

1. Ordna ditt segment med regler och underregler. Varje regel eller underregel består av villkor. Kombinera villkoren med logiska operatorer

1. Välj [relationssökvägen](relationships.md) mellan entiteter som gäller för en regel. Relationssökvägen avgör vilka attribut som kan användas i ett villkor.

1. Hantera regler och underregler. Ändra positionen för en regel eller ta bort den.

1. Lägg till villkor och bygg upp rätt kapslingsnivå med hjälp av underregler.

1. Tillämpa uppsättningsåtgärder på anslutna regler.

1. Använd attributrutan om du vill lägga till tillgängliga entitetsattribut eller skapa villkor för attribut. I rutan visas listan över entiteter och attribut som är tillgängliga för den valda regeln utifrån den valda relationssökvägen.

1. Lägg till villkor baserat på attribut i befintliga regler och underregler eller lägg till det i en ny regel.

1. Ångra och gör om ändringar medan du skapar segmenten.

Exemplet ovan illustrerar segmenteringsfunktionerna. Vi har definierat ett segment för kunder som köpt varor för minst $ 500 online *och* som har ett intresse för programvaruutveckling.

## <a name="create-a-new-segment"></a>Skapa ett nytt segment

Du kan skapa ett nytt segment på flera sätt. I detta avsnitt beskrivs hur du bygger ett eget segment från grunden. Du kan också skapa ett *snabbsegment* som bygger på befintliga entiteter eller använda maskininlärning för att få *förslag på segment*. Mer information finns i [Segment – översikt](segments.md).

När du skapar ett segment kan du spara ett utkast. I utkaststadiet sparas ett segment som ett inaktivt segment. När du har slutfört segmentkonfigurationen kör du den för att aktivera segmenten. Du kan också **Aktivera** ett segment från sidan **Alla segments**.

1. Gå till sidan **Segment**.

1. Välj **Ny** > **Skapa din egen**.

1. På sidan för segmentverktyget definierar eller skapar du regler. En regel består av ett eller flera villkor som definierar en uppsättning kunder.

1. I avsnittet **Regel 1** väljer du ett attribut för en entitet som du vill filtrera kunderna efter. Det finns två sätt att välja attribut:
   - Granska listan med tillgängliga entiteter och attribut i rutan **Lägg till regel** och välj ikonn **+** bredvid det alltribut du vill lägga till. Välj om du vill lägga till attributet i en befintlig regel eller använda det för att skapa en ny regel.
   - Ange namnet på attributet i regelavsnittet om du vill se förslag som matchar.

1. Välj operatorer om du vill ange matchningsvärdena för villkoret. Attribut kan ha någon av fyra datatyper som värde: numerisk, sträng, datum eller boolesk. Beroende på attributets datatyp kan olika operatorer ange villkoret. I segment med företagskonton är två särskilda operatorer tillgängliga för att inkludera potentiella hierarkier mellan de hämtade kontona. Använd *underordnade* och *överordnade* operatorer för att inkludera relaterade konton.

1. Välj **Lägg till villkor** om du vill lägga till fler villkor i en regel. Om du vill skapa en regel under den aktuella regeln väljer du **Lägg till underregel**.

1. Om en regel använder andra entiteter än entiteten *Kund* måste du ange relationssökvägen. Relationssökvägen krävs för att informera systemet om de relationer du vill ska få åtkomst till entiteten för enhetlig kundprofil. Välj **Ange relationssökväg** för att mappa vald entitet till entiteten för enhetlig kundprofil. Om det bara finns en möjlig relationssökväg markeras denna automatiskt av systemet. Olika relationssökvägar kan ge olika resultat. Alla regler kan ha sin egen relationssökväg.

   :::image type="content" source="media/relationship-path.png" alt-text="Möjlig relationssökväg när en regel skapas utifrån en entitet som är mappad till entiteten för enhetlig kundprofil.":::

   Entiteten *eCommerce_eCommercePurchases* på skärmdumpen har exempelvis fyra alternativ för mappning av entiteten *Kund*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Kund
   - eCommerce_eCommercePurchases > kund
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > kund
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Kund När vi väljer det sista alternativet kan vi inkludera attribut från alla listade entiteter under regelvillkoren. Vi kommer troligen att få färre resultat eftersom matchande kundposter måste vara en del av alla entiteter. I detta exempel har man köpt varor via näthandel (*eCommerce_eCommercePurchases*), i en kassa (*POS_posPurchases*), och delta i vårt lojalitetsprogram (*loyaltyScheme_loyCustomers*). När vi väljer det andra alternativet kan vi bara välja attribut från *eCommerce_eCommercePurchases* och entiteten *Kund*. Detta resulterar troligen i fler resulterande kundprofiler.

1. Om det finns flera villkor i en regel kan du välja vilken logisk operator som ska ansluta dem.  
   - Operatorn **OCH**: Alla villkor måste uppfyllas för att en post ska ingå i segmentet. Det här alternativet är mest användbart när du definierar villkor för olika entiteter.
   - Operatorn **ELLER**: Något av villkoren måste uppfyllas för att en post ska ingå i segmentet. Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med två &quot;OCH&quot;-villkor.":::

   När du använder operatorn ELLER måste alla villkor baseras på entiteter som ingår i relationssökvägen.

   - Du kan skapa flera regler för att skapa olika uppsättningar med kundposter. Du kan kombinera grupper så att de kunder som krävs för ditt affärsfall inkluderas. Välj **Lägg till regel** för att skapa en ny regel. Om du inte kan ta med en entitet i en regel på grund av den angivna relationssökvägen, måste du skapa en ny regel för att välja attribut som formar den.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lägg till en ny regel i ett segment och välj den inställda operatorn.":::

   - Välj en av uppsättningsoperatorerna: **Union**, **Skärning** eller **Förutom**.

      - **Sammanförande** sammanför de två grupperna.
      - **Överlappande** överlappar de två grupperna. Endast data som *är gemensamma* för båda grupperna finns kvar i den enhetliga gruppen.
      - **Förutom** kombinerar de två grupperna. Endast data i grupp A som *inte är gemensamma* med data i grupp B bevaras.

1. Som standard genererar segment den utdataentitet som innehåller alla attribut för kundprofiler som matchar de definierade filtren. Om ett segment bygger på andra entiteter än entiteten *Kund* kan du lägga till fler attribut från dessa entiteter i utdataentiteten. Välj **Projektattribut** om du vill välja vilka attribut som ska läggas till i utdataentiteten.

   > [!IMPORTANT]
   > För segment som bygger på affärskonton måste information om en eller flera kontakter för varje konto från entiteten *ContactProfile* inkluderas i avsnittet så att det kan aktiveras eller exporteras till mål där det krävs kontaktinformation. Mer information om entiteten *ContactProfile* finns i [Semantiska mappningar](semantic-mappings.md).
   > Ett exempel på utdata för ett segment som bygger på affärskonton med projekterade attribut för kontakter kan se ut så här:
   >
   > |ID  |Kontonamn  |Intäkter  |Kontaktnamn  | Kontaktens roll|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, inköpschef]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exempel på projicerade attribut som markerats i den sidoruta som ska läggas till i utdataentiteten.":::
  
   Ett segment baseras till exempel på en entitet som innehåller köpdata, som är relaterad till entiteten *Kund*. I detta segment söker man efter alla kunder från Spanien som har köpt varor det aktuella året. Du kan välja att lägga till attribut som varornas pris eller köpdatumet i alla matchande kundposter i utdataentiteten. Denna information kan vara användbar om du vill analysera säsongsrelaterade korrelationer till de totala utgifterna.

   > [!NOTE]
   > - **Projektattribut** fungerar endast för entiteter som har en 1:N-relationer-relation med kundentiteten. En kund kan till exempel ha flera prenumerationer.
   > - Om attributet du vill projektera är mer än en hop från entiteten *Kund*, enligt relationens definition, ska attributet användas i alla regler i segmentfrågan som du skapar.
   > - Om attributet du vill projektera är bara ett hopp från entiteten *Kund*, det attributet behöver inte vara närvarande i alla regler i segmentfrågan som du skapar.
   > - **Projekterade attribut** räknas in när du använder uppsättningsoperatorer.

1. Välj **Redigera information** bredvid Namnlöst segment. Ange ett namn för ditt segment och uppdatera det föreslagna **Namnet på utdataentiteten** för segmentet. Alternativt kan du lägga till en beskrivning och [taggar](work-with-tags-columns.md#manage-tags) i segmentet.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogrutan Redigera information.":::

1. Välj **Kör** om du vill spara avsnittet, aktivera det och börja bearbeta ditt segment utifrån alla regler och villkor. I annat fall sparas det som ett inaktivt segment.

1. Klicka på **Tillbaka till segment** för att gå tillbaka till sidan **Segment**.

1. Som standard skapas segment som ett dynamiskt segment. Det innebär att segmenten uppdateras vid systemuppdateringar. Om du vill [stoppa den automatiska uppdateringen](segments.md#manage-existing-segments) väljer du segmentet och väljer alternativet **Gör statisk**. Statiska segment kan [uppdateras manuellt](segments.md#refresh-segments) när som helst.

> [!TIP]
> - Segmentverktyget föreslår inga giltiga värden från entiteter när operatorerna anges för villkoren. Du kan gå till **Data** > **Entiteter** och ladda ned entitetsdata för att se vilka värden som är tillgängliga.
> - Med villkor baserade på datumen kan du växla mellan fasta datum och ett flexibelt datumintervall.
> - Om du har flera regler för ditt segment har regeln du redigerar en stående blå linje bredvid den.
> - Du kan flytta regler och villkor till andra platser i segmentdefinitionen. Välj […] bredvid en regel eller ett villkor och välj hur och var den/det ska flyttas.
> - Med kontrollerna **Ångra** och **Gör om** i kommandofältet kan du återställa ändringar.

## <a name="quick-segments"></a>Snabbsegment

Med snabbsegment kan du bygga enkla segment med en enda operator snabbt för snabbare insikter.

1. På sidan **Segment**, välj **Ny** > **Skapa från**.
   - Välj alternativet **profiler** för att skapa ett segment som baseras på entiteten för den *enhetliga kunden*.
   - Välj alternativet **Mått** om du vill skapa ett segment kring mått som du har skapat tidigare.
   - Markera alternativet **Intelligens** om du vill skapa ett segment runt en av de utdataentiteter som du skapade med funktionerna **prediktioner** eller **anpassade modeller**.

2. I dialogrutan **Nytt snabbsegment**, välj ett attribut i listrutan **Fält**.

3. Systemet ger fler insikter som hjälper dig att skapa bättre kundsegment.
   - För kategorifält visas tio populära kundräkningar. Välj ett **Värde** och välj **Granska**.
   - För ett numeriskt attribut visar systemet vilket attributvärde som faller under varje kunds percentil. Välj en **operatör** och ett **värde** och välj sedan **granska**.

4. Systemet tillhandahåller en **uppskattad segmentstorlek**. Du kan välja om du vill skapa ett segment som du har definierat eller om du först vill ha en annan segmentstorlek.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Namn och uppskattning för ett snabbsegment.":::

5. Ange ett **Namn** och **utgående entitetsnamn** för ditt segment. Alternativt kan du lägga till [taggar](work-with-tags-columns.md#manage-tags).

6. Välj **Spara** för att skapa segmentet.

7. När segmentet har bearbetat klart kan du visa det på samma sätt som andra segment som du har skapat.

## <a name="next-steps"></a>Nästa steg

[Exportera ett segment ](export-destinations.md)och utforska [integreringen av kundkort](customer-card-add-in.md) för att använda segment i andra program.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
