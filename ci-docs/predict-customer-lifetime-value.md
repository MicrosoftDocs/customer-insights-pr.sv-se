---
title: Förutsägelse av kundens livstidsvärde
description: Förutse potentiell intäkt för aktiva kunder i framtiden.
ms.date: 07/21/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: b6f6665d906cc96688efe84035336f64d2a39303
ms.sourcegitcommit: 80d8436d8c940f1267e6f26b221b8d7ce02ed26b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186462"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Förutsägelse av kundens livstidsvärde

Förutse potentiellt värde (intäkt) som enskilda aktiva kunder ger verksamheten under en angiven tidsperiod i framtiden. Med den här funktionen kan du uppnå olika mål:

- Identifiera kunder med högt värde och bearbeta den här insikten
- Skapa strategiska kundsegment utifrån deras potentiella värde för att köra anpassade kampanjer med riktad försäljning, marknadsföring och support
- Vägleder produktutveckling genom att fokusera på funktioner som ökar kundvärdet
- Optimera försäljnings- eller marknadsföringsstrategin och fördela budgeten på ett bättre sätt för att nå kunderna
- Identifiera och uppmärksamma kunder med högt värde genom lojalitets- eller belöningsprogram

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar bör du fundera över vad kundens livstidsvärde betyder för din verksamhet. För närvarande stöder vi transaktionsbaserad förutsägelse av kundens livstidsvärde. Det förutsagda värdet för en kund baseras på transaktionshistoriken. För att skapa förutsägelsen behöver du minst behörighet som [Deltagare](permissions.md).

Eftersom det inte tar lång tid att konfigurera och köra en modell för kundens livstidsvärde bör du överväga att skapa flera modeller med olika indatainställningar och jämföra modellresultat för att se vilket modellscenario som passar dina affärsbehov bäst.

### <a name="data-requirements"></a>Datakrav

Följande data krävs och där de är markerade som valfria rekommenderas de för ökad prestanda för modellen. Ju fler data modellen kan bearbeta, desto exaktare blir förutsägelsen. Därför rekommenderar vi att du matar in fler aktivitetsdata för kunderna, om de finns tillgängliga.

- Kundidentifierare: Unik identifierare som matchar transaktioner till en enskild kund

- Transaktionshistorik: Logg över tidigare transaktioner med nedanstående dataschema
    - **Transaktions-ID**: Unik identifierare för varje transaktion
    - **Transaktionsdatum**: Datum, helst en tidstämpel för varje transaktion
    - **Transaktionsbelopp**: Penningvärde (till exempel omsättning eller vinstmarginal) för varje transaktion
    - **Etikett tilldelad för returer** (valfritt): Booleskt värde som anger om transaktionen är en retur 
    - **Produkt-ID** (valfritt): Produkt-ID för produkten som är inblandad i transaktionen

- Ytterligare data (valfritt), till exempel
    - Webbaktiviteter: webbplatsbesökshistorik, e-posthistorik
    - Lojalitetsaktiviteter: insamlade lojalitetspoäng och inlösningshistorik
    - Kundtjänstlogg, servicesamtal, klagomål eller returhistorik
    - Information om kundprofil
- Data om kundaktiviteter (valfritt):
    - Aktivitetsidentifierare för att särskilja aktiviteter av samma typ
    - Kundidentifierare för att mappa aktiviteter till dina kunder
    - Aktivitetsinformation som innehåller namnet och datumet för aktiviteten
    - Ett dataschema för aktiviteter inkluderar:
        - **Primärnyckel**: En unik identifierare för en aktivitet
        - **Tidsstämpel**: Datum och tid för händelsen som identifierats av primärnyckeln
        - **Händelse (aktivitetsnamn)**: Namnet på händelsen som du vill använda
        - **Detaljer (belopp eller värde)**: Information om kundaktiviteten

- Föreslagna dataegenskaper:
    - Tillräckliga tidigare data: Minst ett år med transaktionsdata. Helst två till tre års transaktionsdata för att få CLV att använda ett år.
    - Flera köp per kund: Vilket minst två till tre transaktioner per kund-ID, helst över flera datum.
    - Antal kunder: Minst 100 kunder, helst fler än 10 000 kunder. Modellen fungerar inte med färre än 100 kunder och det finns för få tidigare data
    - Datafullständighet: Mindre än 20 % saknade värden i obligatoriska fält i indata

> [!NOTE]
> - För modellen krävs kundens transaktionshistorik. Det går bara att konfigurera en entitet för transaktionshistorik för tillfället. Om det finns flera entiteter för inköp/transaktion kan du sammanföra dem i Power Query före datainmatningen.
> - Om du vill ha ytterligare aktivitetsdata (valfritt) kan du lägga till så många kundaktivitetsentiteter du vill ha med i modellen.

## <a name="create-a-customer-lifetime-value-prediction"></a>Skapa en förutsägelse av kundens livstidsvärde

1. Gå till **Intelligens** > **Prediktioner**.

1. Välj panelen **Kundens livstidsvärde** och välj **Använd modell**. 

1. I rutan **Kundlivstidsvärde** väljer du **Kom igång**.

1. **Ge modellen** och **utdataentiteten ett namn** för att särskilja dem från andra modeller eller entiteter.

1. Välj **Nästa**.

### <a name="define-model-preferences"></a>Definiera modellinställningar

1. Ange en **tidsperiod för förutsägelse** för att definiera hur långt in i framtiden som du vill förutse kundens livstidsvärde.    
   Som standard anges enheten som månader. Du kan ändra det till år för att se längre fram.

   > [!TIP]
   > För att korrekt kunna förutse kundens livstidsvärde för den tidsperiod du anger behöver du en jämförbar period av historiska data. Om du till exempel vill förutse CLV för de kommande 12 månaderna rekommenderar vi att du har minst 18–24 månaders historisk information.

1. Ange vad **aktiva kunder** betyder för företaget. Ange tidsramen inom vilken en kund måste ha minst en transaktion för att anses vara aktiv. Modellen förutser endast kundens livstid för aktiva kunder. 
   - **Låt modellen beräkna inköpsintervall (rekommenderas)**: Modellen analyserar dina data och fastställer en tidsperiod utifrån tidigare köp.
   - **Ange intervall manuellt**: Om du har en specifik affärsdefinition av en aktiv kund väljer du det här alternativet och anger tidsperioden därefter.

1. Definiera percentilen för **kunder med högt värde** för att aktivera modellen och ge resultat som passar affärsdefinitionen.
    - **Modellberäkning (rekommenderas)**: Modellen analyserar dina data och fastställer vad en kund med högt värde kan innebära för din verksamhet baserat på kundens transaktionshistorik. Modellen använder en heuristisk regel (inspirerad av 80/20-regeln eller pareto-principen) för att hitta en proportion av kunder med högt värde. Den procentandel kunder som under den historiska perioden har bidragit med 80 % av den kumulativa omsättningen för företaget betraktas som kunder med högt värde. Normalt bidrar mindre än 30–40 % av kunderna till en kumulativ omsättning på 80 %. Antalet kan dock variera beroende på ditt företag och din bransch.    
    - **Procent av de mest aktiva kunderna**: Definiera kunder med högt värde för företaget som en percentil av de mest aktiva betalande kunderna. Du kan till exempel använda det här alternativet om du vill definiera kunder med högt värde som de 20 % högst betalande kunderna.

    Om ditt företag definierar kunder med högt värde på ett annat sätt, [meddela oss, då vi gärna vill veta om det](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Välj **Nästa** för att gå vidare till nästa steg.

### <a name="add-required-data"></a>Lägg till obligatoriska data

1. I steget **Data som krävs** väljer du **Lägg till data** för **Kundtransaktionshistorik** och väljer den entitet som innehåller transaktionshistoriken enligt beskrivningen i [kraven](#prerequisites).

1. Mappa de semantiska fälten till attribut i entiteten för inköpshistorik och välj **Nästa**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Bild på konfigurationssteget för att mappa dataattribut för de data som krävs.":::
 
1. Om fälten nedan inte är ifyllda konfigurerar du relationen från entiteten för inköpshistorik till entiteten *Kund* och väljer **Spara**.
    1. Välj entiteten Transaktionshistorik.
    1. Välj det fält som identifierar en kund i entiteten för inköpshistorik. Detta måste relatera till primärt kund-ID för entiteten Kund.
    1. Välj den entitet som matchar din primära kundentitet.
    1. Ange ett namn som beskriver relationen.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Bild på konfigurationssteget för att definiera relationen till kundens entitet.":::

1. Välj **Nästa**.

### <a name="add-optional-activity-data"></a>Lägg till valfri aktivitetsdata

För data som återspeglar viktiga kundinteraktioner (som webb-, kundtjänst- och händelseloggar) läggs sammanhang till i transaktionsposter. Fler mönster i dina kundaktivitetsdata kan förbättra precisionen för förutsägelserna.

1. I steget **Ytterligare data (valfritt)** väljer du **Lägg till data** under **Skapa bättre modellinsikter med ytterligare aktivitetsdata**. Välj den kundaktivitetsentitet som tillhandahåller information om kundaktivitet enligt beskrivningen i [kraven](#prerequisites).

1. Mappa de semantiska fälten till attribut i entiteten för kundaktivitet och välj **Nästa**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Bild på konfigurationssteget för att mappa fält för ytterligare data.":::

1. Välj en aktivitetstyp som överensstämmer med den typ av kundaktivitet du lägger till. Välj bland befintliga aktivitetstyper eller lägg till en ny aktivitetstyp.

1. Konfigurera relationen från kundaktivitetsentiteten till entiteten *Kund*.

    1. Välj det fält som identifierar kunden i tabellen för kundaktivitet. Den kan vara direkt relaterad till det primära kund-ID för entiteten *Kund*.
    1. Välj den *Kundentitet* som matchar den primära *Kundentiteten*.
    1. Ange ett namn som beskriver relationen.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Bild på steget i konfigurationsflödet för att lägga till ytterligare data och konfigurera aktiviteten med ifyllda exempel.":::

1. Välj **Spara**.
    Lägg till ytterligare data om det finns andra kundaktiviteter du vill ta med.

1. Lägg till valfria kunddata eller välj **Nästa**.

### <a name="add-optional-customer-data"></a>Lägg till ytterligare kunddata

Välj bland de 18 vanliga kundprofilattribut som ska ingå som indata i modellen. De här attributen kan leda till mer anpassade, relevanta och användbara modellresultat för ärenden som används i företaget.

Exempel: Contoso Coffee vill rikta kundens livstidsvärde till kunder med ett anpassat erbjudande om lanseringen av den nya automaten. Contoso använder CLV-modellen och lägger till alla 18 kundprofilattribut för att se vilka faktorer som påverkar kundernas högsta värde. De tycker att kundens plats är den mest inflytelserika faktorn för dessa kunder.
Med den här informationen ordnar de en lokal händelse för lanseringen av maskinen och samarbetar med lokala leverantörer för personliga erbjudanden och en speciell upplevelse på händelse. Utan den här informationen kanske Contoso bara har skickat generiska marknadsföringsmeddelanden och missade möjligheten att anpassa för detta lokala segment av deras kunder med högt värde.

1. I steget **Ytterligare data (valfritt)** väljer du **Lägg till data** under **Skapa bättre modellinsikter med ytterligare kunddata**.

1. För **Entitet**, välj **Kund : CustomerInsights** för att välja den enhetliga kundprofiltabellen som mappas till kundattributdata. För **Kund-ID**, välj **System.Customer.CustomerId**.

1. Mappa fler fält om data är tillgängliga i dina enhetliga kundprofiler.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exempel på mappade fält för kundprofildata.":::

1. Välj **Spara** efter att ha mappat de attribut som modellen ska använda för att hjälpa kundernas livstidsvärde.

1. Välj **Nästa**.

### <a name="set-update-schedule"></a>Ange uppdateringsschema

1. I steget **Datauppdateringsschema** väljer du hur ofta modellen ska uppdateras baserat på senaste data. Den här inställningen är viktig för att uppdatera precisionen för förutsättningar eftersom nya data förs in i Customer Insights. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

### <a name="review-and-run-the-model-configuration"></a>Granska och köra modellkonfigurationen

1. I steget **Granska modellinformationen** verifierar du konfigurationen av förutsägelsen. Du kan gå tillbaka till valfri del av förutsägelsekonfigurationen genom att välja **Redigera** under visat värde. Du kan också välja ett konfigurationssteg från förloppsindikatorn.

1. Om alla värden är korrekt konfigurerade väljer du **Spara och kör** för att starta modellen. Under fliken **Mina förutsägelser** kan du se statusen för förutsägelseprocessen. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

## <a name="review-prediction-status-and-results"></a>Granska förutsägelsens status och resultat

### <a name="review-prediction-status"></a>Granska förutsägelsens status

1.  Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.
2.  Välj den prediktion du vill granska.

- **Förutsägelsens namn**: Namnet på förutsägelsen som angavs när den skapades.
- **Förutsägelsetyp**: Den modelltyp som används för förutsägelse
- **Utdataentitet**: Namnet på den entitet där utdata för förutsägelsen ska lagras. Gå till **Data** > **Entiteter** för att söka efter entiteten med detta namn.
- **Förutsagt fält**: Det här fältet fylls endast i för vissa typer av förutsägelser och används inte i förutsägelser av kundens livstidsvärde.
- **Status**: Status för förutsägelsekörningen.
    - **Köade**: Förutsägelse väntar på att andra processer ska slutföras.
    - **Uppdatera**: Förutsägelse körs för närvarande för att skapa resultat som ska flöda till utdataentiteten.
    - **Misslyckades**: Förutsägelsekörningen misslyckades. [Granska loggar](manage-predictions.md#troubleshoot-a-failed-prediction) för mer information.
    - **Lyckades**: Förutsägelsen har slutförts. Välj **Vy** under de vertikala ellipserna om du vill granska förutsägelseresultat.
- **Redigerad**: Det datum då konfigurationen för förutsägelsen ändrades.
- **Senaste uppdatering**: Det datum då förutsägelsen uppdaterade resultat i utdataenheten.

### <a name="review-prediction-results"></a>Granska förutsägelsens resultat

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Välj den förutsägelse som du vill granska resultaten för.

Det finns tre primära dataområden på resultatsidan.

- **Utbildningsmodellens prestanda**: A, B eller C är möjliga betyg. Det här betyget indikerar prestandan för förutsägelsen och kan hjälpa dig att fatta beslutet att använda de resultat som är lagrade i utdataentiteten. Välj **Lär dig mer om poängen** för att bättre förstå de underliggande måtten för modellprestandan och hur det slutliga modellprestandabetyget sattes.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Bild på rutan med information om modellpoäng tillsammans med betyg A.":::

  Med hjälp av definitionen av kunder med högt värde som angavs vid konfigurationen av förutsägelsen bedömer systemet hur AI-modellen presterade i förutsägelsen av kunder med högt värde jämfört med en grundmodell.    

  Betyg fastställs utifrån följande regler:
  - **A** när modellen korrekt förutsade minst 5 % fler kunder med högt värde jämfört med grundmodellen.
  - **B** när modellen korrekt förutsade mellan 0 och 5 % fler kunder med högt värde jämfört med grundmodellen.
  - **C** när modellen korrekt förutsade färre kunder med högt värde än grundmodellen.

  I rutan **Modellbetyg** visas ytterligare information om AI-modellens prestanda och grundmodellen. Grundmodellen bygger på en icke-AI-baserad metod för beräkning av kundens livstidsvärde, främst baserat på tidigare köp som gjorts av kunder.     
  Standardformeln som används för att beräkna kundens livstidsvärde enligt grundmodellen:    

  _**Kundens livstidsvärde för varje kund** = Genomsnittligt månatligt köp som gjorts av kunden i det aktiva kundfönstret * Antal månader i perioden för förutsägelse av kundens livstidsvärde *Övergripande kvarhållning av alla kunder*_

  AI-modellen jämförs med grundmodellen utifrån två prestandamått.
  
  - **Andel lyckade försök med att förutse kunder med högt värde**

    Se skillnaden mellan att förutse kunder med högt värde med AI-modellen jämfört med grundmodellen. En framgångsfrekvens på 84 % innebär till exempel att av alla kunder med högt värde i utbildningsdata kunde AI-modellen samla in 84 %. Sedan jämför vi den här framgångsfrekvensen med grundmodellens framgångsfrekvens och rapporterar den relativa förändringen. Det här värdet används för att tilldela modellen ett betyg.

  - **Felmått**
    
    Ett annat mått gör att du kan granska modellens övergripande prestanda när det gäller fel vid förutsägelse av framtida värden. Vi använder det övergripande RMSE-måttet (Root Mean Squared Error) för att utvärdera felet. RMSE är ett standardiserat sätt att mäta fel i en modell när det gäller att förutse kvantitativa data. AI-modellens RMSE jämförs med RMSE för grundmodellen och den relativa skillnaden rapporteras.

  AI-modellen prioriterar korrekt rangordning av kunder enligt det värde de ger verksamheten. Endast framgångsfrekvensen för förutsägelse av kunder med högt värde används för att få det slutliga modellbetyget. RMSE-måttet är känsligt för extremvärden. Om det finns en mindre procentandel kunder med extremt stora köpvärden kanske det övergripande RMSE-måttet inte ger en fullständig bild av modellens prestanda.   

- **Kundernas värde efter percentil**: Med hjälp av definitionen för kunder med högt värde grupperas kunderna i lågt värde och högt värde, baserat på förutsägelser av kundens livstidsvärde, och visas i ett diagram. Genom att hålla markören över staplarna i histogrammet kan du se antalet kunder i varje grupp och det genomsnittliga kundlivstidsvärdet för gruppen. Dessa data kan vara till hjälp om du vill [skapa kundsegment](segments.md) utifrån förutsägelser av kundens livstidsvärde.

- **Mest inflytelserika faktorer**: Olika faktorer beaktas när du skapar förutsägelser av kundens livstidsvärde baserat på indata till AI-modellen. Betydelsen för var och en av faktorerna beräknas för de ansamlade förutsägelser som skapas av en modell. Du kan använda dessa faktorer för att validera resultatet av en förutsägelse. Dessa faktorer ger också en bättre inblick i de mest inflytelserika faktorerna som bidrog till förutsägelsen av kundens livtidsvärde för alla dina kunder.

## <a name="manage-predictions"></a>Hantera förutsägelser

Det är möjligt att optimera, felsöka, uppdatera eller ta bort förutsägelser. Granska en användbarhetsrapport för indata för att ta reda på hur du gör en prediktion snabbare och mer tillförlitlig. Mer information finns i [Hantera förutsägelser](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
