---
title: Förutsägelse av transaktionell omsättning
description: Förutse om det finns en risk med att kunden inte längre vill köpa dina produkter eller tjänster.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906878"
---
# <a name="transactional-churn-prediction-preview"></a>Förutsägelse av transaktionell omsättning (förhandsversion)

Förutsägelse av transaktionell omsättning hjälper till att förutsäga om en kund inte längre kommer att köpa dina produkter eller tjänster i ett visst tidsfönster. Du kan skapa nya omsättningsförutsägelser i **Intelligens** > **Förutsägelser**. Välj **Mina förutsägelser** för att se andra förutsägelser som du har skapat.

> [!TIP]
> Testa självstudierna för en förutsägelse av transaktionell omsättning med exempeldata: [Guide för förutsägelse av transaktionell omsättning (förhandsversion)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.
- Affärskunskaper för att förstå vad omsättningen innebär för företaget. Vi har stöd för tidsbaserade omsättningsdefinitioner, vilket innebär att en kund anses ha omsatts efter en period där inga inköp gjorts.
- Data om dina transaktioner/inköp och deras historik:
    - Transaktionsidentifierare för att särskilja inköp och transaktioner.
    - Kundidentifierare för att matcha transaktioner mot dina kunder.
    - Datum för transaktionshändelser, som definierar datumen då transaktionen genomfördes.
    - Det semantiska dataschemat för inköp/transaktioner kräver följande information:
        - **Transaktions-ID:** En unik identifierare för ett inköp eller en transaktion.
        - **Transaktionsdatum:** Datumet för köpet eller transaktionen.
        - **Värde för transaktionen:** Valutan/det numeriska värdet för transaktionen/artikeln.
        - (Valfritt) **Unikt produkt-ID:** ID för den produkt eller tjänst som köpts om dina data finns på en radartikelnivå.
        - (Valfritt) **Om transaktionen var en retur:** Ett sant/falskt-fält som identifierar om transaktionen returnerades. Om **värdet för transaktionen** är negativt används även den här informationen för att härleda en retur.
- (Valfri) Data om kundaktiviteter:
    - Aktivitetsidentifierare för att särskilja aktiviteter av samma typ.
    - Kundidentifierare för att mappa aktiviteter mot dina kunder.
    - Aktivitetsinformation som innehåller namnet och datumet för aktiviteten.
    - Det semantiska dataschemat för kundaktiviteter omfattar:
        - **Primärnyckel:** En unik identifierare för en aktivitet. Exempelvis kan ett besök på en webbplats eller en användningspost som visar att kunden testade ett exempel på din produkt.
        - **Tidsstämpel:** Datum och tid för händelsen som identifierats av primärnyckeln.
        - **Händelse:** Namnet på den händelse som du vill använda. Ett fält med namnet "UserAction" i en livsmedelsbutik kan till exempel vara en kuponganvändning av kunden.
        - **Detaljer:** Detaljerad information om händelsen. Ett fält med namnet "CouponValue" i en livsmedelsbutik kan till exempel vara valutavärdet på kupongen.
- Föreslagna dataegenskaper:
    - Tillräckliga tidigare data: Transaktionsdata för minst dubbla det valda tidsfönstret. Helst två till tre års prenumerationsdata. 
    - Flera inköp per kund: helst minst två transaktioner per kund.
    - Antal kunder: Minst 10 kundprofiler, helst mer än 1 000 unika kunder. Modellen fungerar inte med färre än 10 kunder och det finns för få tidigare data.
    - Datafullständighet: Mindre än 20 % av de värden som saknas i entitetens datafält.

> [!NOTE]
> För ett företag med hög kundinköpsfrekvens (varannan vecka) bör du välja en kortare prediktion definition för fönster och kund. För låg inköpsfrekvens (med några månader eller en gång per år) väljer du en längre prediktion och omsättningsdefinitionen.

## <a name="create-a-transactional-churn-prediction"></a>Skapa en förutsägelse av transaktionell omsättning

1. I Customer Insights, gå till **Intelligens** > **Prediktioner**.

1. Välj panelen **Kundomsättningsmodell (förhandsversion)** och välj **Använd denna modell**.
   
1. I fönstret **Kundomsättningsmodell** väljer du **Transaktionell** och sedan **Kom igång**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Skärmbild med valt transaktionsalternativ i fönstret Kundomsättningsmodell.":::

### <a name="name-model"></a>Namnge modell

1. Ange ett namn för modellen om du vill särskilja den från andra modeller.

1. Ange ett namn för entiteten för utdata med endast bokstäver och siffror utan blanksteg. Detta är det namn som modellentiteten kommer att använda. 

1. Välj **Nästa**.

### <a name="define-customer-churn"></a>Definiera kundomsättning

1. Ange ett antal dagar som omsättnings ska förutsägas för i fältet **Identifiera kunder som kan omsättas inom de kommande**. Du kan till exempel förutse risken för omsättning av dina kunder under de kommande 90 dagarna för att anpassa dina marknadsföringsinsatser för att behålla kunder. Om du förutser omsättningrisker under en längre eller kortare tid kan det bli svårare att åtgärda faktorerna i din omsättningsriskprofil, men det beror på dina specifika affärskrav. 
   >[!TIP]
   > Du kan välja att **Spara och stänga** när som helst när du vill spara förutsägelsen som ett utkast. Du hittar utkastförutsägelsen i fliken **Mina förutsägelser** om du vill fortsätta med den.

1. Ange antalet dagar som du vill definiera omsättningen för i fältet **En kund har omsatts om han/hon inte har genomfört något köp på:**. Om en kund exempelvis inte har gjort några inköp under de senaste 30 dagarna kan han/hon betraktas som omsatt. 

1. Fortsätt **Nästa** för att fortsätta

### <a name="add-required-data"></a>Lägg till obligatoriska data

1. Välj **Lägg till data** för **Inköpshistorik** och välj den entitet som innehåller information om transaktions-/inköpshistorik enligt beskrivningen i [kraven](#prerequisites).

1. Mappa de semantiska fälten till attribut i entiteten för inköpshistorik och välj **Nästa**. För beskrivningar av fälten, läs igenom [kraven](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mappa semantiska fält i inköpsentiteten.":::

1. Om fälten nedan inte är ifyllda konfigurerar du relationen från entiteten för inköpshistorik till entiteten Kund.
    1. Välj **entiteten Inköpshistorik**.
    1. Välj det **fält** som identifierar kunden i entiteten för inköpshistorik. Detta måste relatera till primärt kund-ID för entiteten Kund.
    1. Välj den **Kundentitet** som matchar den primära kundentiteten.
    1. Ange ett namn som beskriver relationen.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Sidan Inköpshistorik visar skapandet av en relation till kunden.":::
   
1. Välj **Nästa**.

1. Alternativt kan du välja **Lägg till data** för **Kundaktiviteter**. Välj den entitet som tillhandahåller information om kundaktivitet enligt beskrivningen i kraven.

1. Mappa de semantiska fälten till attribut i entiteten för kundaktivitet och välj **Nästa**. För beskrivningar av fälten, läs igenom [kraven](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mappa kundfält för transaktionsdata.":::

1. Välj en aktivitetstyp som överensstämmer med den typ av kundaktivitet som du konfigurerar. Välj **Skapa ny** och välj en tillgänglig aktivitetstyp eller skapa en ny typ.

1. Du måste konfigurera relationen mellan entiteten för kundaktivitet och entiteten Kund.
    1. Välj det fält som identifierar kunden i tabellen för kundaktivitet. Den kan vara direkt relaterad till det primära kund-ID för entiteten Kund.
    1. Välj den kundentitet som matchar den primära kundentiteten
    1. Ange ett namn som beskriver relationen.

1. Välj **Spara**.

1. Om du har andra kundaktiviteter som du vill ta med upprepar du stegen ovan.

1. Välj **Nästa**.

### <a name="set-schedule-and-review-configuration"></a>Ange schema och granska konfigurationen

1. Ange en frekvens för att träna om modellen. Den här inställningen är viktig för att uppdatera noggrannheten i förutsägelser när nya data matas in. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

1. Granska konfigurationen av förutsägelsen. Du kan gå tillbaka till föregående steg genom att välja **Redigera** under visat värde. Du kan också välja ett konfigurationssteg via förloppsindikatorn.

1. Om alla värden är korrekt konfigurerade väljer du **Spara och kör** för att starta förutsägelseprocessen. På fliken **Mina förutsägelser** visas statusen för dina förutsägelser. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

## <a name="review-a-prediction-status-and-results"></a>Granska en förutsägelsestatus och resultat

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Välj den prediktion du vill granska.
   - **Förutsägelsens namn:** Namnet på förutsägelsen som angavs när den skapades.
   - **Förutsägelsetyp:** Den modelltyp som används för förutsägelse
   - **Utdataentitet:** Namnet på den entitet där utflödet för förutsägelsen ska lagras. Du kan söka efter en entitet med det här namnet på **Data** > **Entiteter**.    
     I utdataentiteten är *ChurnScore* är den förutsagda sannolikheten för omsättning och *IsChurn* är en binär etikett baserad på *ChurnScore* med 0,5 tröskel. Standardtröskeln kanske inte fungerar för ditt scenario. [Skapa ett nytt segment](segments.md#create-a-new-segment) med önskad tröskel.
     Alla kunder behöver inte vara aktiva kunder. En del av dem kanske inte har haft någon aktivitet under en längre tid och betraktas som redan nedtonade, baserat på din definition. Det är inte användbart att ta risken för kunder som redan har börjat använda programmet eftersom de inte publik av intresse.
   - **Förutsagt fält:** Det här fältet fylls endast i för vissa typer av förutsägelser och används inte i omsättningsförutsägelser.
   - **Status:** Status för förutsägelsekörningen.
        - **Köade** Förutsägelse väntar på att andra processer ska köras.
        - **Uppdatera:** Förutsägelse körs för närvarande för att producera resultat som ska flöda till utdataentiteten.
        - **Misslyckades:** Förutsägelsekörningen misslyckades. [Granska loggar](#troubleshoot-a-failed-prediction) för mer information.
        - **Lyckades:** Förutsägelsen har slutförts. Välj **Visa** under de lodräta punkterna för att granska förutsägelsen
   - **Redigerad:** Det datum då konfigurationen för förutsägelsen ändrades.
   - **Senaste uppdatering:** Det datum då förutsägelsen uppdaterade resultat i utdataenheten.

1. Markera de lodräta punkterna bredvid den förutsägelse som du vill granska resultat för och välj **Visa**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Visa kontroll om du vill visa resultatet av en förutsägelse.":::   

1. Det finns tre primära dataområden på resultatsidan:
    1. **Prestanda för övningsmodell** A, B eller C är möjliga poäng. Detta resultat anger förutsägelsens prestanda och kan hjälpa dig att fatta beslutet att använda resultaten som lagras i utdataenheten. Poängen bestäms utifrån följande regler:
         
         - **A** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är större än baslinjen med minst 10 %.
            
         - **B** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är upp till 10 % större än baslinjen.
            
         - **C** När modellen korrekt förutsäger mindre än 50 % av det totala antalet förutsägelser, eller när procentandelen av korrekta förutsägelser för kunder som har omsatts är mindre än baslinjen.
               
         - **Baslinjen** tar tidsintervallet för förutsägelse för modellen (till exempel 1 år) och modellen skapar olika tidsintervall genom att dela det med 2 tills det når 1 månad eller mindre. De mindre tidsintervallen används för att skapa en affärsregel för kunder som inte har köpt något i denna tidsram. Dessa kunder betraktas som omsatta. Den tidsbaserade affärsregeln med den högsta förmågan att förutse vem som sannolikt omsätts väljs som baslinjemodell.
            
    1. **Sannolikhet för omsättning (antal kunder):** Kundgrupper utifrån deras förutsedda omsättningsrisk. Den här informationen kan hjälpa dig senare om du vill skapa ett kundsegment med hög omsättningsrisk. Sådana segment hjälper dig att förstå var avgränsarna bör finnas för segmentmedlemskap.
       
    1. **Faktorer med störst påverkan:** Det finns många faktorer som bör beaktas när du skapar en förutsägelse. Var och en av faktorerna har en betydelse beräknad för de aggregerade förutsägelserna som skapas av en modell. Du kan använda dessa faktorer för att validera resultatet av en förutsägelse. Du kan också använda den här informationen senare om du vill [skapa segment](segments.md) som kan påverka omsättningsrisken för en kund.

## <a name="troubleshoot-a-failed-prediction"></a>Felsöka en misslyckad förutsägelse

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Välj de lodräta ellipserna bredvid den förutsägelse som du vill visa felloggarna för.

1. Välj **Loggar**.

1. Granska alla fel. Det finns flera typer av fel som kan inträffa, och dessa beskriver vilket villkor som orsakat problemet. Ett fel som till exempel innebär att det inte finns tillräckligt med data för att förutsäga problemet korrekt löses vanligtvis genom att ytterligare data läses in i Customer Insights.

## <a name="refresh-a-prediction"></a>Uppdatera en förutsägelse

Förutsägelser uppdateras automatiskt i samma [schema som dina data uppdaterar](system.md#schedule-tab) enligt konfigurationen i inställningarna. Du kan uppdatera dem manuellt.

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Markera de lodräta punkterna bredvid den förutsägelse du vill uppdatera.

1. Välj **Uppdatera**.

## <a name="delete-a-prediction"></a>Ta bort en förutsägelse

Om du tar bort en förutsägelse tas även dess utdataentitet bort.

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Markera de lodräta punkterna bredvid den förutsägelse du vill ta bort.

1. Välj **Ta bort**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
