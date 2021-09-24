---
title: Skapa segment med segmentverktyget
description: Skapa segment med kunder för att gruppera dem utifrån olika attribut.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494569"
---
# <a name="create-segments"></a>Skapa segment

Definiera komplexa filter runt den enhetliga kundentiteten och det är relaterade entiteter. Varje segment skapar en uppsättning kundposter efter bearbetning som du kan exportera och utföra åtgärder på. Segment hanteras på sidan **Segment**. Du kan [skapa nya segment](#create-a-new-segment) med hjälp av [segmentverktyget](#segment-builder) eller [skapa snabbsegment](#quick-segments) från andra områden i appen.

## <a name="segment-builder"></a>Segmentverktyg

Följande bild illustrerar de olika delarna av segmentverktyget. Den visar ett segment som resulterar i en grupp kunder. Kunderna har beställt varor inom en specifik tidsram och har samlat ett antal förmånspoäng eller spenderat en viss summa pengar. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Element i segmentverktyget." lightbox="media/segment-builder-overview.png":::

1 – Ordna ditt segment med regler och underregler. Varje regel eller underregel består av villkor. Kombinera villkoren med logiska operatorer

2 – Välj [relationssökvägen](relationships.md) mellan entiteter som gäller för en regel. Relationssökvägen avgör vilka attribut som kan användas i ett villkor.

3 – Hantera regler och underregler. Ändra positionen för en regel eller ta bort den.

4 – Lägg till villkor och bygg upp rätt kapslingsnivå med hjälp av underregler.

5 – Tillämpa uppsättningsåtgärder på anslutna regler.

6 – Använd attributrutan om du vill lägga till tillgängliga entitetsattribut eller skapa villkor för attribut. I rutan visas listan över entiteter och attribut som är tillgängliga för den valda regeln utifrån den valda relationssökvägen.

7 – Lägg till villkor baserat på attribut i befintliga regler och underregler eller lägg till det i en ny regel.

8 – Ångra och gör om ändringar medan du skapar segmenten.

Exemplet ovan illustrerar segmenteringsfunktionerna. Vi har definierat ett segment för kunder som köpt varor för minst $ 500 online *och* som har ett intresse för programvaruutveckling.

## <a name="create-a-new-segment"></a>Skapa ett nytt segment

Du kan skapa ett nytt segment på flera sätt. I detta avsnitt beskrivs hur du bygger ett eget segment från grunden. Du kan också skapa ett *snabbsegment* som bygger på befintliga entiteter eller använda maskininlärning för att få *förslag på segment*. Mer information: [Segmentöversikt](segments.md).

När du skapar ett segment kan du spara ett utkast. Den sparas som ett inaktivt segment och kan inte aktiveras och avslutas med en giltig konfiguration.

1. Gå till sidan **Segment**.

1. Välj **Ny** > **Skapa din egen**.

1. På sidan för segmentverktyget definierar du den första regeln. En regel består av ett eller flera villkor och definierar en uppsättning kunder.

1. I avsnittet **Regel 1** väljer du ett attribut för en entitet som du vill filtrera kunder efter. Det finns två sätt att välja attribut: 
   - Granska listan med tillgängliga entiteter och attribut i rutan **Lägg till regel** och välj ikonn **+** bredvid det alltribut du vill lägga till. Välj om du vill lägga till attributet i en befintlig regel eller använda det för att skapa en ny regel.
   - Ange namnet på attributet i regelavsnittet om du vill se förslag som matchar.

1. Välj operatorer om du vill ange matchningsvärdena för villkoret. Attribut kan ha någon av fyra datatyper som värde: numerisk, sträng, datum eller boolesk. Beroende på attributets datatyp kan olika operatorer ange villkoret. 

1. Välj **Lägg till villkor** om du vill lägga till fler villkor i en regel. Om du vill skapa en regel under den aktuella regeln väljer du **Lägg till underregel**.

1. Om en regel använder andra entiteter än entiteten *Kund* måste du ange relationssökvägen. Relationssökvägen krävs för att informera systemet om de relationer du vill ska få åtkomst till entiteten för enhetlig kundprofil. Välj **Ange relationssökväg** för att mappa vald entitet till entiteten för enhetlig kundprofil. Om det bara finns en möjlig relationssökväg markeras denna automatiskt av systemet. Olika relationssökvägar kan ge olika resultat. Alla regler kan ha sin egen relationssökväg.

   :::image type="content" source="media/relationship-path.png" alt-text="Möjlig relationssökväg när en regel skapas utifrån en entitet som är mappad till entiteten för enhetlig kundprofil.":::

   Entiteten *eCommerce_eCommercePurchases* på skärmdumpen har exempelvis fyra alternativ för mappning av entiteten *Kund*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Kund
   - eCommerce_eCommercePurchases > kund
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > kund
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Kund När vi väljer det sista alternativet kan vi inkludera attribut från alla listade entiteter under regelvillkoren. Vi kommer troligen att få färre resultat eftersom matchande kundposter måste ingå i alla entiteter. I detta exempel har man köpt varor via näthandel (*eCommerce_eCommercePurchases*), i en kassa (*POS_posPurchases*), och delta i vårt lojalitetsprogram (*loyaltyScheme_loyCustomers*). När vi väljer det andra alternativet kan vi bara välja attribut från *eCommerce_eCommercePurchases* och entiteten *Kund*. Detta resulterar troligen i fler resulterande kundprofiler.

1. Om det finns flera villkor i en regel kan du välja vilken logisk operator som ska ansluta dem.

   - Operatorn **OCH**: Alla villkor måste uppfyllas för att en post ska ingå i segmentet. Det här alternativet är mest användbart när du definierar villkor för olika entiteter.

   - Operatorn **ELLER**: Något av villkoren måste uppfyllas för att en post ska ingå i segmentet. Det här alternativet är mest användbart när du definierar flera villkor för samma entiteter.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med två &quot;OCH&quot;-villkor.":::

   När du använder operatorn ELLER måste alla villkor baseras på entiteter som ingår i relationssökvägen.

   1. Du kan skapa flera regler för att skapa olika uppsättningar med kundposter. Du kan kombinera grupper så att de kunder som krävs för ditt affärsfall inkluderas. Välj **Lägg till regel** för att skapa en ny regel. Om du inte kan ta med en entitet i en regel på grund av den angivna relationssökvägen måste du skapa en ny regel för att välja attribut som utgör den.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lägg till en ny regel i ett segment och välj den inställda operatorn.":::

   1. Välj en av uppsättningsoperatorerna: **Union**, **Skärning** eller **Förutom**.

   - **Sammanförande** sammanför de två grupperna.

   - **Överlappande** överlappar de två grupperna. Endast data som *är gemensamma* för båda grupperna behålls i den enhetliga gruppen.

   - **Förutom** kombinerar de två grupperna. Endast data i grupp A som *inte är samma* som data i grupp B behålls.

1. Som standard genererar segment den utdataentitet som innehåller alla attribut för kundprofiler som matchar de definierade filtren. Om ett segment bygger på andra entiteter än entiteten *Kund* kan du lägga till fler attribut från dessa entiteter i utdataentiteten. Välj **Projektattribut** om du vill välja vilka attribut som ska läggas till i utdataentiteten.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exempel på projicerade attribut som markerats i den sidoruta som ska läggas till i utdataentiteten.":::
  
   Exempel: Ett segment bygger på en entitet som innehåller inköpsdata som är relaterade till entiteten *Kund*. I detta segment söker man efter alla kunder från Spanien som har köpt varor det aktuella året. Du kan välja att lägga till attribut som varornas pris eller köpdatumet i alla matchande kundposter i utdataentiteten. Denna information kan vara användbar om du vill analysera säsongsrelaterade korrelationer till de totala utgifterna.

   > [!NOTE]
   > - Projekterade attribut fungerar endast för entiteter som har en till flera-relation med kundentiteten. En kund kan till exempel ha flera prenumerationer.
   > - Du kan endast projicera attribut från en entitet som används i varje regel i segmentfrågan som du skapar.
   > - Projekterade attribut räknas in när du använder uppsättningsoperatorer.

1. Innan du sparar och kör ett segment väljer du **Redigera information** bredvid segmentnamnet. Ange ett namn för ditt segment och uppdatera det föreslagna **Namnet på utdataentiteten** för segmentet. Du kan också lägga till en beskrivning i segmentet.

1. Välj **Kör** om du vill spara och bearbeta ditt segment om alla krav har verifierats. I annat fall sparas den som ett inaktivt segmentutkast.

1. Klicka på **Tillbaka till segment** för att gå tillbaka till sidan **Segment**.

> [!TIP]
> - Segmentverktyget föreslår inga giltiga värden från entiteter när operatorerna anges för villkoren. Du kan gå till **Data** > **Entiteter** och ladda ned entitetsdata för att se vilka värden som är tillgängliga.
> - Med villkor baserade på datumen kan du växla mellan fasta datum och ett flexibelt datumintervall.
> - Om du har flera regler för ditt segment hittar du ett blått fält runt den regel du redigerar.
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

    > [!div class="mx-imgBorder"]
    > ![Namn och uppskattning för ett snabbsegment.](media/quick-segment-name.png "Namn och uppskattning för ett snabbsegment")

5. Ange ett **namn** för ditt segment. Eventuellt ge en **visningsnamn**.

6. Välj **Spara** för att skapa segmentet.

7. När segmentet har bearbetat klart kan du visa det på samma sätt som andra segment som du har skapat.

## <a name="next-steps"></a>Nästa steg

[Exportera ett segment ](export-destinations.md)och utforska [integreringen av kundkort](customer-card-add-in.md) för att använda segment i andra program.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
