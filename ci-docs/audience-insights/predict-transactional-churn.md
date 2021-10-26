---
title: Prediktion för transaktionsomsättning
description: Förutse om det finns en risk med att kunden inte längre vill köpa dina produkter eller tjänster.
ms.date: 10/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ac484f74e388aa23422a89e25dabb555f2ad4118
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643454"
---
# <a name="transaction-churn-prediction-preview"></a>Prediktion för transaktionsomsättning (förhandsversion)

Förutsägelse av transaktionell omsättning hjälper till att förutsäga om en kund inte längre kommer att köpa dina produkter eller tjänster i ett visst tidsfönster. Du kan skapa nya omsättningsförutsägelser i **Intelligens** > **Förutsägelser**. Välj **Mina förutsägelser** för att se andra förutsägelser som du har skapat. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

För miljöer som bygger på affärskonton kan vi skapa transaktioner för ett konto och även en kombination av konto och en annan informationsnivå, till exempel produktkategori. Om du lägger till en produkt kan du se hur sannolikt det är att kontot "Contoso" slutar köpa produktkategorin "kontorsmaterial". Dessutom, för företagskonton kan vi också använda AI för att skapa en lista över potentiella skäl till varför ett konto sannolikt kommer att gå för en kategori av sekundär information.

> [!TIP]
> Prova självstudien om en prediktion exempeldata: [Exempelguide för prediktion för transaktionsomsättning (förhandsgranskning)](sample-guide-predict-transactional-churn.md). 

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.
- Affärskunskaper för att förstå vad omsättningen innebär för företaget. Vi har stöd för tidsbaserade omsättningsdefinitioner, vilket innebär att en kund anses ha omsatts efter en period där inga inköp gjorts.
- Data om dina transaktioner/inköp och deras historik:
    - Transaktionsidentifierare för att särskilja inköp och transaktioner.
    - Kundidentifierare för att matcha transaktioner mot dina kunder.
    - Datum för transaktionshändelser, som definierar datumen då transaktionen genomfördes.
    - Det semantiska dataschemat för inköp/transaktioner kräver följande information:
        - **Transaktions-ID**: En unik identifierare för ett inköp eller en transaktion.
        - **Transaktionsdatum**: Datumet för köpet eller transaktionen.
        - **Värde för transaktionen**: Valutan/det numeriska värdet för transaktionen/artikeln.
        - (Valfritt) **Unikt produkt-ID**: ID för den produkt eller tjänst som köpts om dina data finns på en radartikelnivå.
        - (Valfritt) **Om transaktionen var en retur**: Ett sant/falskt-fält som identifierar om transaktionen returnerades. Om **värdet för transaktionen** är negativt används även den här informationen för att härleda en retur.
- (Valfri) Data om kundaktiviteter:
    - Aktivitetsidentifierare för att särskilja aktiviteter av samma typ.
    - Kundidentifierare för att mappa aktiviteter mot dina kunder.
    - Aktivitetsinformation som innehåller namnet och datumet för aktiviteten.
    - Det semantiska dataschemat för kundaktiviteter omfattar:
        - **Primärnyckel:** En unik identifierare för en aktivitet. Exempelvis kan ett besök på en webbplats eller en användningspost som visar att kunden testade ett exempel på din produkt.
        - **Tidsstämpel:** Datum och tid för händelsen som identifierats av primärnyckeln.
        - **Händelse:** Namnet på den händelse som du vill använda. Ett fält med namnet "UserAction" i en livsmedelsbutik kan till exempel vara en kuponganvändning av kunden.
        - **Detaljer:** Detaljerad information om händelsen. Ett fält med namnet "CouponValue" i en livsmedelsbutik kan till exempel vara valutavärdet på kupongen.
- (Valfritt) Data om dina kunder:
    - Dessa data bör justeras mot fler statiska attribut för att säkerställa att modellen fungerar bäst.
    - Dataschemat för förknöjning för kunddata omfattar:
        - **CustomerID:** En unik identifierare för en kund.
        - **Skapad den:** Det datum då kunden ursprungligen lades till.
        - **Region:** En kunds region eller region.
        - **Land:** Land för en kund.
        - **Bransch:** En kunds branschtyp. Ett fält med namnet Bransch i en kaffeställen kan till exempel visa om kunden var återförsäljningskund.
        - **Klassificering:** Kategorisering av en kund för företaget. Ett fält med namnet ValueSegment i en kaffesoffa kan exempelvis vara kundnivån utifrån kundens storlek.
- Föreslagna dataegenskaper:
    - Tillräckliga tidigare data: Transaktionsdata för minst dubbla det valda tidsfönstret. Helst två till tre års transaktionshistorik. 
    - Flera inköp per kund: helst minst två transaktioner per kund.
    - Antal kunder: Minst 10 kundprofiler, helst mer än 1 000 unika kunder. Modellen fungerar inte med färre än 10 kunder och det finns för få tidigare data.
    - Datafullständighet: Mindre än 20 % av de värden som saknas i entitetens datafält.

> [!NOTE]
> För ett företag med hög kundinköpsfrekvens (varannan vecka) bör du välja en kortare prediktion definition för fönster och kund. För låg inköpsfrekvens (med några månader eller en gång per år) väljer du en längre prediktion och omsättningsdefinitionen.

## <a name="create-a-transaction-churn-prediction"></a>Skapa prediktion för transaktionsomsättning

1. I Customer Insights, gå till **Intelligens** > **Prediktioner**.

1. Välj panelen **Kundomsättningsmodell (förhandsversion)** och välj **Använd denna modell**.

1. I rutan **Kundomsättningsmodell**, välj **Transaktion** och välj **Komma igång**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Skärmbild med valt transaktionsalternativ i rutan Kundomsättningsmodell.":::

### <a name="name-model"></a>Namnge modell

1. Ange ett namn för modellen om du vill särskilja den från andra modeller.

1. Ange ett namn för entiteten för utdata med endast bokstäver och siffror utan blanksteg. Detta är det namn som modellentiteten kommer att använda. 

1. Välj **Nästa**.

### <a name="define-customer-churn"></a>Definiera kundomsättning

1. Ange ett antal dagar som omsättnings ska förutsägas för i fältet **Identifiera kunder som kan omsättas inom de kommande**. Du kan till exempel förutse risken för omsättning av dina kunder under de kommande 90 dagarna för att anpassa dina marknadsföringsinsatser för att behålla kunder. Om du förutser omsättningrisker under en längre eller kortare tid kan det bli svårare att åtgärda faktorerna i din omsättningsriskprofil, men det beror på dina specifika affärskrav.
   >[!TIP]
   > Du kan välja att **Spara och stänga** när som helst när du vill spara förutsägelsen som ett utkast. Du hittar utkastförutsägelsen i fliken **Mina förutsägelser** om du vill fortsätta med den.

1. Ange antalet dagar som du vill definiera omsättningen för i fältet **En kund har omsatts om han/hon inte har genomfört något köp på:**. Om en kund exempelvis inte har gjort några inköp under de senaste 30 dagarna kan han/hon betraktas som omsatt. 

1. Fortsätt genom att klicka på **Nästa**.

### <a name="add-required-data"></a>Lägg till obligatoriska data

1. Välj **Lägg till data** och välj den aktivitetstyp i sidorutan som innehåller information om den erforderliga transaktionen eller köphistoriken.

1. Under **Välj aktiviteter** väljer du specifika aktiviteter från den valda aktivitet som du vill att beräkningen ska fokusera på.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="En sidoruta som anger specifika aktiviteter under semantiktypen.":::

1. Om du ännu inte har mappat aktiviteten till någon semantisk typ väljer du **Redigera** för att göra så. Den guidade upplevelsen att mappa aktiviteter öppnas. Mappa dina data till motsvarande fält i vald aktivitets typ.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Aktivitetstyp för sidinställning.":::

1. När du har mappat aktiviteten till motsvarande semantiska typ väljer du **Nästa** för att gå vidare

1. Mappa de semantiska attributen till de fält som krävs för att köra modellen. Om fälten nedan inte är ifyllda konfigurerar du relationen från entiteten för inköpshistorik till entiteten *Kund*.

1. Välj **Nästa**.

### <a name="select-prediction-level"></a>Välj prediktionsnivå

De flesta prediktioner skapas på kundnivå. I vissa situationer kanske det inte är tillräckligt detaljerad för att kunna tillgodose företagets behov. Du kan använda den här funktionen för att skapa nya funktioner för en kundgren, till exempel i stället för kunden som helhet.

1. Om du vill skapa prediktion på en mer detaljerad nivå än kunden väljer du **Välj entitet för en sekundär nivå**. Om alternativet inte är tillgängligt ser du till att du har slutfört avsnittet nedan.

1. Expandera de entiteter du vill välja den sekundära nivån från eller filtrera de markerade alternativen med hjälp av sökfilterrutan.

1. Välj attributet du vill använda som sekundär nivå och välj sedan **Lägg till**

1. Välj **Nästa**

> [!NOTE]
> De entiteter som är tillgängliga i det här avsnittet visas eftersom de har en relation till den entitet du valde i föregående avsnitt. Om du inte ser den entitet du vill lägga till ska du kontrollera att den har en giltig relation i **Relationer**. Endast en till en och flera-till-en relationer för den här konfigurationen.

### <a name="add-additional-data-optional"></a>Lägg till ytterligare data (valfritt)

Konfigurera relationen från kundaktivitetsentiteten till entiteten *Kund*.

1. Välj det fält som identifierar kunden i tabellen för kundaktivitet. Den kan vara direkt relaterad till det primära kund-ID för entiteten *Kund*.

1. Välj den entitet som är din primära entiteten *Kund*.

1. Ange ett namn som beskriver relationen.

#### <a name="customer-activities"></a>Kundaktiviteter

1. Alternativt kan du välja **Lägg till data** för **Kundaktiviteter**.

1. Välj den typ av aktivitet som innehåller den information du vill använda och välj sedan en eller flera aktiviteter i avsnittet **Aktiviteter**.

1. Välj en aktivitetstyp som överensstämmer med den typ av kundaktivitet som du konfigurerar. Välj **Skapa ny** och välj en tillgänglig aktivitetstyp eller skapa en ny typ.

1. Välj **Nästa**, sedan **Spara**.

1. Om du har andra kundaktiviteter som du vill ta med upprepar du stegen ovan.

#### <a name="customers-data"></a>Kunddata

1. Alternativt väljer du **Lägg till data** för **Kunddata**.

1. Mappa attributen till fält i dina egna kunddata enligt vad som har identifierats. Data i fälten som används bör inte ändras ofta för att säkerställa modellens bästa prestanda. Om du till exempel väljer ett fält för Klassificering som ändras varje månad används bara det sista värdet i prediktion,även om tidigare samma värde kanske inte gäller kunden när de prediktionsmönster.

1. Välj **Nästa**.

### <a name="provide-an-optional-list-of-benchmark-accounts-business-accounts-only"></a>Ange en valfri lista med jämförelsekonton (endast företagskonton)

Lägg till en lista över dina företagskunder och konton som du vill använda som riktmärken. Du får [information om dessa jämförelsekonton](#review-a-prediction-status-and-results), bland annat deras omsättningspoäng och de flesta funktioner som har påverkat deras prediktion.

1. Välj **+ Lägg till kunder**.

1. Välj vilka kunder som ska fungera som jämförelse.

1. Fortsätt genom att klicka på **Nästa**.

### <a name="set-schedule-and-review-configuration"></a>Ange schema och granska konfigurationen

1. Ange en frekvens för att träna om modellen. Den här inställningen är viktig för att uppdatera noggrannheten i förutsägelser när nya data matas in. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

1. Granska konfigurationen av förutsägelsen. Du kan gå tillbaka till föregående steg genom att välja **Redigera** under visat värde. Du kan också välja ett konfigurationssteg via förloppsindikatorn.

1. Om alla värden är korrekt konfigurerade väljer du **Spara och kör** för att starta förutsägelseprocessen. På fliken **Mina förutsägelser** visas statusen för dina förutsägelser. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

## <a name="review-a-prediction-status-and-results"></a>Granska en förutsägelsestatus och resultat

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Välj den prediktion du vill granska.
   - **Förutsägelsens namn**: Namnet på förutsägelsen som angavs när den skapades.
   - **Förutsägelsetyp**: Den modelltyp som används för förutsägelse
   - **Utdataentitet**: Namnet på den entitet där utdata för förutsägelsen ska lagras. Du kan söka efter en entitet med det här namnet på **Data** > **Entiteter**.
     I utdataentiteten är *ChurnScore* är den förutsagda sannolikheten för omsättning och *IsChurn* är en binär etikett baserad på *ChurnScore* med 0,5 tröskel. Standardtröskeln kanske inte fungerar för ditt scenario. [Skapa ett nytt segment](segments.md#create-a-new-segment) med önskad tröskel.
     Alla kunder behöver inte vara aktiva kunder. En del av dem kanske inte har haft någon aktivitet under en längre tid och betraktas som redan nedtonade, baserat på din definition. Det är inte bra att ta risken för kunder som redan har börjat använda programmet eftersom de inte är målgruppen av intresse.
   - **Förutsagt fält**: Det här fältet fylls endast i för vissa typer av förutsägelser och används inte i omsättningsförutsägelser.
   - **Status**: Status för förutsägelsekörningen.
        - **Köade**: Förutsägelse väntar på att andra processer ska köras.
        - **Uppdatera**: Förutsägelse körs för närvarande för att producera resultat som ska flöda till utdataentiteten.
        - **Misslyckades**: Förutsägelsekörningen misslyckades. [Granska loggar](manage-predictions.md#troubleshoot-a-failed-prediction) för mer information.
        - **Lyckades**: Förutsägelsen har slutförts. Välj **Visa** under de lodräta punkterna för att granska förutsägelsen
   - **Redigerad**: Det datum då konfigurationen för förutsägelsen ändrades.
   - **Senaste uppdatering**: Det datum då förutsägelsen uppdaterade resultat i utdataenheten.

1. Markera de lodräta punkterna bredvid den förutsägelse som du vill granska resultat för och välj **Visa**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Visa kontroll om du vill visa resultatet av en förutsägelse.":::

1. Det finns tre primära dataområden på resultatsidan:
   - **Prestanda för övningsmodell**: A, B eller C är möjliga poäng. Detta resultat anger förutsägelsens prestanda och kan hjälpa dig att fatta beslutet att använda resultaten som lagras i utdataenheten. Poängen bestäms utifrån följande regler: 
        - **A** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är större än baslinjen med minst 10 %.
            
        - **B** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är upp till 10 % större än baslinjen.
            
        - **C** När modellen korrekt förutsäger mindre än 50 % av det totala antalet förutsägelser, eller när procentandelen av korrekta förutsägelser för kunder som har omsatts är mindre än baslinjen.
               
        - **Baslinjen** tar tidsintervallet för förutsägelse för modellen (till exempel 1 år) och modellen skapar olika tidsintervall genom att dela det med 2 tills det når 1 månad eller mindre. De mindre tidsintervallen används för att skapa en affärsregel för kunder som inte har köpt något i denna tidsram. Dessa kunder betraktas som omsatta. Den tidsbaserade affärsregeln med den högsta förmågan att förutse vem som sannolikt omsätts väljs som baslinjemodell.
            
    - **Sannolikhet för omsättning (antal kunder)**: Kundgrupper utifrån deras förutsedda omsättningsrisk. Den här informationen kan hjälpa dig senare om du vill skapa ett kundsegment med hög omsättningsrisk. Sådana segment hjälper dig att förstå var avgränsarna bör finnas för segmentmedlemskap.
       
    - **Faktorer med störst påverkan**: Det finns många faktorer som bör beaktas när du skapar en förutsägelse. Var och en av faktorerna har en betydelse beräknad för de aggregerade förutsägelserna som skapas av en modell. Du kan använda dessa faktorer för att validera prediktion resultat, eller så kan du använda den här informationen senare för att [skapa segment](segments.md) som kan påverka kundrisken.


1. För affärskonton hittar du en sida med information om **Analys av påverkansfaktor**. Den innehåller fyra dataavsnitt:

    - Innehållet på den här sidan avgörs av objektet som är markerat i den högra rutan. Välj ett objekt från **De främsta kunderna** eller **Jämförelsekunder**. Båda listorna beställas genom att minska värdet på omsättningspoängen, oavsett om poängen endast är för kunden eller en kombinationspoäng för kunder och en sekundär nivå som produktkategori.
        
        - **De främsta kunderna**: Lista över tio kunder som har den högsta risken för omsättning och lägsta risken för omsättning utifrån deras omsättningspoäng. 
        - **Jämförelsekunder**: Lista över upp till 10 kunder som valdes när de konfigurerade modellen.
 
    - **Omsättningspoäng:** Visar omsättningspoängen för det valda objektet i den högra rutan.
    
    - **Riskfördelning av omsättning:** Visar riskfördelning av omsättning mellan kunder och den percentil den valda kunden finns i. 
    
    - **De främsta funktionerna som ökar och minskar omsättningsrisken:** För det valda objektet i den högra rutan visas de fem främsta funktionerna som har ökat och minskat omsättningsrisken. För varje funktion som har betydelse för objektet hittar du värdet av funktionen för objektet och dess påverkan på objektets resultat. Det finns även ett genomsnittsvärde för varje funktion i kundsegmenten med låg och hög omsättningsrisk. Det hjälper till att bättre kontextualisera värdena för de funktioner som valts för det valda objektet och jämföra det med kundsegment med låg eller hög omsättning.

       - Låg: konton eller kombinationer av konto och sekundär nivå med en poäng från 0 till 0,33
       - Medel: konton eller kombinationer av konton och sekundära nivåer med en poäng från 0,33 till 0,66
       - Hög: konton eller kombinationer av konton och sekundära nivåer med en poäng större än 0,66
    
       Om du försöker lösa detta på kontonivån tas hänsyn till alla konton genom att beräkna genomsnittsvärdena för funktionen för segment av omsättning. För prognos på sekundär nivå för varje konto beror spridning av segment på den sekundära nivån för objektet som valts i sidoruta. Om ett objekt till exempel har en sekundär nivå av produktkategori = kontorsmaterial, beaktas endast de objekt som har kontorsmaterial som produktkategori när genomsnittsvärdena för funktionen för segment används. Den här logiken används för att säkerställa en korrekt jämförelse av objektets funktionsvärden med genomsnittsvärdena i segmenten låg, tjock och hög.

       I vissa fall är genomsnittsvärdet för segment med låg eller hög omsättning tom eller inte tillgänglig eftersom det inte finns några objekt i motsvarande segment för segmenten ovan.

## <a name="manage-predictions"></a>Hantera förutsägelser

Det är möjligt att optimera, felsöka, uppdatera eller ta bort förutsägelser. Granska en användbarhetsrapport för indata för att ta reda på hur du gör en prediktion snabbare och mer tillförlitlig. Mer information finns i [Hantera prediktioner](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
