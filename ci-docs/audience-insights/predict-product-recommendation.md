---
title: Förutsägelse av produktrekommendationer
description: Förutse produkterna som kunder sannolikt köper eller interagerar med.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e46e31131a2dd5235af8221eafcd2e1d1394f3d4
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906786"
---
# <a name="product-recommendation-prediction-preview"></a>Förutsägelse av produktrekommendationer (förhandsversion)

Med produktrekommendationsmodellen skapas uppsättningar med förutsägelse av produktrekommendationer. Rekommendationer baseras på tidigare köpbeteende och kunder med liknande köpmönster. Du kan skapa nya förutsägelser av produktrekommendationer på sidan **Intelligens** > **Förutsägelser**. Välj **Mina förutsägelser** för att se andra förutsägelser som du har skapat.

Produktrekommendationer kan omfattas av lokala lagar och regler och kundförväntningar, som modellen inte är utformad för att specifikt ta hänsyn till.  Som användare av denna funktion måste du **gå igenom rekommendationerna innan du levererar dem till dina kunder** för att se till att du följer tillämpliga lagar och regler och kundförväntningar för vad du kan rekommendera. 

Dessutom ger utdata från den här modellen rekommendationer baserat på produkt-ID. Leveransmekanismen måste mappa de befintliga produkt-ID:erna till rätt innehåll så att kunderna kan ta hänsyn till lokalisering, bildinnehåll och annat företagsspecifikt innehåll eller beteende.

## <a name="sample-guide"></a>Exempelguide

Om du vill prova den här funktionen men inte har några data för att uppfylla kraven nedan kan du [skapa en exempelimplementering](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Förutsättningar

- Minst [Deltagarbehörighet](permissions.md) i Customer Insights.

- Affärskunskap för att förstå olika typer av produkter för ditt företag och hur kunderna interagerar med dem. Vi ger stöd åt att rekommendera produkter som tidigare köpts av dina kunder eller rekommendationer för nya produkter.

- Data om transaktioner, inköp och deras historik:
    - Transaktionsidentifierare för att särskilja inköp och transaktioner.
    - Kundidentifierare för att mappa transaktioner till dina kunder.
    - Datum för transaktionshändelser som definierar datumen då transaktionen genomfördes.
    - Produkt-ID-information för transaktionen.
    - (Valfritt) En entitet för produktkatalogdata som ska användas som produktfilter.
    - (Valfritt) Om en transaktionen är en retur eller inte.
    - Det semantiska dataschemat kräver följande information:
        - **Transaktions-ID:** En unik identifierare för ett inköp eller en transaktion.
        - **Transaktionsdatum:** Datumet för köpet eller transaktionen.
        - **Värde för transaktionen:** Det numeriska värdet för köpet eller transaktionen.
        - **Unikt produkt-ID:** ID för den produkt eller tjänst som köpts om dina data finns på en radartikelnivå.
        - (Valfritt) **Köp eller retur:** Ett booleskt fält där värdet *sant* anger att en transaktionen var en retur. Om data för Inköp eller Retur inte tillhandahålls av modellen och **värdet för transaktionen** är negativt, använder vi även den här informationen för att dra nytta av en retur.
- Föreslagna dataegenskaper:
    - Tillräckliga tidigare data: Minst ett års transaktionsdata, helst två till tre år för att få med viss giltighet.
    - Flera köp per kund: Tre eller flera transaktioner per kund-ID
    - Antal kunder: Minst 100 kunder, helst fler än 10 000 kunder. Modellen fungerar inte med färre än 100 kunder.

> [!NOTE]
> - För modellen krävs kundens transaktionshistorik. Definitionen av en transaktionen är ganska flexibel. Alla data som beskriver interaktionen mellan användare och produkt kan fungera som indata. Till exempel köpa en produkt, ta en klass eller delta i ett evenemang.
> - Det går bara att konfigurera en entitet för transaktionshistorik för tillfället. Om det finns flera köpentiteter måste du se Power Query innan datainmatning.
> - Om order och orderinformation är olika entiteter sammanfogar du dem innan du använder dem i modellen. Modellen fungerar inte med ett order-ID eller inleverans-ID för en entitet.


## <a name="create-a-product-recommendation-prediction"></a>Skapa en förutsägelse av produktrekommendationer

1. I Customer Insights, gå till **Intelligens** > **Prediktioner**.

1. Välj panelen **Produktrekommendationsmodell (förhandsversion)** och välj **Använd denna modell**.
   > [!div class="mx-imgBorder"]
   > ![Panelen Produktrekommendationsmodell med knappen Använd den här modellen](media/product-recommendation-usethismodel.PNG "Panelen Produktrekommendationsmodell med knappen Använd den här modellen")

1. Läs informationen om modellkraven. Om du har de data som krävs väljer du **Kom igång**.

### <a name="name-model"></a>Namnge modell

1. Ange ett namn för modellen om du vill särskilja den från andra modeller.

1. Ange ett namn för utdataentiteten med enbart bokstäver och siffror, utan blanksteg. Detta är det namn som modellentiteten kommer att använda. Välj sedan **Nästa**.

### <a name="define-product-recommendation-configuration"></a>Definiera konfiguration av produktrekommendation

1. Ange **antalet produkter** som du vill rekommendera till en kund. Värdet beror på hur leveranssättet fyller i data. Om du kan rekommendera tre produkter anger du detta värde.
   
   >[!TIP]
   > Du kan välja att **Spara och stänga** när som helst när du vill spara förutsägelsen som ett utkast. Förutsägelseutkastet finns under fliken **Mina förutsägelser**.

1. Välj om du vill **föreslå produkter som kunder nyligen har köpt**.

1. Om du har valt att *inte* rekommendera nyligen köpta produkter ställer du in **fönstret Se tillbaka**. Den här inställningen anger tidsramen som modellen tar i beaktande innan produkten rekommenderas till användaren igen. Ange till exempel att en kund köper en bärbar dator vartannat år. I det här fönstret visas inköpshistoriken för de senaste två år och om de hittar ett objekt filtreras objektet från rekommendationerna.

1. Välj **Nästa**

### <a name="add-required-data"></a>Lägg till obligatoriska data

1. Välj **Lägg till data** för **Kundtransaktionshistorik** och välj den entitet som innehåller information om transaktions-/inköpshistorik enligt beskrivningen i [kraven](#prerequisites).

1. Mappa de semantiska fälten till attribut i entiteten för inköpshistorik och välj **Nästa**. För beskrivningar av fälten, läs igenom [kraven](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definiera entitetsrelation](media/product-recommendation-purchasehistorymapping.PNG "Sidan Köphistorik som visar attribut som är mappade till fält i den valda inköpshistorikentiteten")

1. Om fälten inte är ifyllda konfigurerar du relationen från entiteten för inköpshistorik till entiteten *Kund*.
    1. Välj **entiteten Inköpshistorik**.
    1. Välj det **fält** som identifierar kunden i entiteten för inköpshistorik. Detta måste relatera till primärt kund-ID för entiteten *Kund*.
    1. Välj den **Kundentitet** som matchar den primära kundentiteten.
    1. Ange ett namn som beskriver relationen.
       > [!div class="mx-imgBorder"]
       > ![Sidan Inköpshistorik visar skapandet av en relation till kunden](media/model-purchase-join.png "Sidan Inköpshistorik visar skapandet av en relation till kunden")

1. Välj **Spara**.

1. Välj **Nästa**.

### <a name="configure-product-filters"></a>Konfigurera produktfilter

Ibland är det bara vissa produkter som är lämpliga för den typ av prediktion du bygger. Med produktfilter kan du identifiera en deluppsättning produkter med specifika egenskaper som du kan rekommendera till kunderna. I modellen används alla tillgängliga produkter för att lära sig mönster, men endast produkterna som matchar produktfiltret används i utdata.

1. I steget **Lägg till produktinformation** lägger du till produktkatalogen med information för varje produkt. Mappa den information som krävs för att välja **Nästa**.

3. I steget **Produktfilter**, välj mellan följande alternativ.

   * **Inga filter**: Använd alla produkter i produktrekommendationen prediktion.

   * **Definiera specifika produktfilter**: Använd specifika produkter i produktrekommendationen prediktion.

1. Välj **Nästa**.

1. Om du väljer att definiera ett produktfilter måste du definiera det nu. I rutan **Produktkatalogattribut** väljer du de attribut från *entiteten produktkatalog* som du vill ta med i filtret.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Sidruta som visar att produktkatalogentiteten ska väljas för produktfilter.":::

1. Välj om du vill att produktfiltret ska använda kopplingarna **and** **or** för att på ett logiskt sätt kombinera dina val av attribut från produktkatalogen.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Exempelkonfiguration av produktfilter i kombination med logiska AND-kopplingar.":::

1. Välj **Nästa**.

### <a name="set-update-schedule-and-review-configuration"></a>Ange uppdateringsschema och granska konfigurationen

1. Ange en frekvens för att träna om modellen. Denna inställning är viktig för att uppdatera precisionen i förutsägelser när nya data importeras till Customer Insights. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

1. Granska konfigurationen. Du kan gå tillbaka till valfri del av förutsägelsekonfigurationen genom att välja **Redigera** under visat värde. Du kan också välja ett konfigurationssteg via förloppsindikatorn.

1. Om alla värden är korrekt konfigurerade väljer du **Spara och kör** för att starta förutsägelseprocessen. På fliken **Mina förutsägelser** visas statusen för dina förutsägelser. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

## <a name="review-a-prediction-status-and-results"></a>Granska en förutsägelsestatus och resultat

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.
   > [!div class="mx-imgBorder"]
   > ![Vy över sidan Mina förutsägelser](media/product-recommendation-mypredictions.PNG "Vy över sidan Mina förutsägelser")

1. Välj den prediktion du vill granska.
   - **Namn på förutsägelse:** Det namn på förutsägelsen som angavs när den skapades.
   - **Förutsägelsetyp:** Den typ av modell som används för förutsägelsen
   - **Utdataentitet:** Namnet på den entitet där utflödet för förutsägelsen ska lagras. Du kan söka efter en entitet med det här namnet på **Data** > **Entiteter**.    
      *Poäng* i utdataenheten är ett mått på rekommendationen. I modellen rekommenderas produkter med högre poäng över produkter med lägre poäng.
   - **Predicerad fälttyp:** Det här fältet fylls i endast för vissa typer av prognoser och används inte i produktrekommendationen prediktion.
   - **Status:** Aktuell status för förutsägelsens körning.
        - **Köade:** Förutsägelsen väntar för närvarande på att andra processer ska köras.
        - **Uppdaterar:** Förutsägelsen kör i nuläget processtadiet "resultat" för att generera resultat som ska skickas till utdataenheten.
        - **Slutfördes ej:** förutsägelsen misslyckades. Välj **Loggar** om du vill ha mer information.
        - **Slutfördes:** förutsägelsen har slutförts. Välj **Visa** under de lodräta punkterna för att granska förutsägelsen
   - **Redigerad:** Det datum då konfigurationen för förutsägelsen ändrades.
   - **Senaste uppdatering:** Det datum då förutsägelsen uppdaterade resultat i utdataenheten.

1. Markera de lodräta punkterna bredvid den förutsägelse som du vill granska resultat för och välj **Visa**.
   > [!div class="mx-imgBorder"]
   > ![Vy över alternativ på menyn med lodräta punkter för en förutsägelse, bland annat redigera, uppdatera, visa, loggar och ta bort](media/product-recommendation-verticalellipses.PNG "Vy över alternativ på menyn med lodräta punkter för en förutsägelse, bland annat redigera, uppdatera, visa, loggar och ta bort")

1. Det finns fem primära dataavsnitt på resultatsidan:
    1. **Prestanda för övningsmodell** A, B eller C är möjliga poäng. Detta resultat anger förutsägelsens prestanda och kan hjälpa dig att fatta beslutet att använda resultaten som lagras i utdataenheten.
        - Poängen bestäms utifrån följande regler:
            - **A** Modellen anses ha kvalitet **A** om måttet "Framgång vid K" är minst 10 % över grundnivån. 
            - **B** Modellen anses ha kvalitet **B** om måttet "Framgång vid K" är 0 till 10 % över grundnivån.
            - **C** Modellen anses ha kvalitet **C** om måttet "Framgång vid K" är mindre än grundnivån.
               
               > [!div class="mx-imgBorder"]
               > ![Vy över modellprestandaresultat](media/product-recommendation-modelperformance.PNG "Vy över modellprestandaresultat")
            - **Grundnivå**: Modellen tar de mest rekommenderade produkterna från antalet köp av alla kunder och använder inlärda regler som identifierats av modellen för att skapa en uppsättning rekommendationer för kunderna. Därefter jämförs förutsägelserna med de bästa produkterna, beräknat på antalet kunder som köpt produkten. Om en kund har minst en produkt i sina rekommenderade produkter som också fanns bland de produkter som köpts mest, betraktas de som en del av grundnivån. Om tio av dessa kunder hade köpt en rekommenderad produkt av 100 kunder skulle grundnivån vara 10 %.
            - **Framgång vid K**: Genom en uppsättning tidsperioder av transaktioner för validering skapas rekommendationer för alla kunder och jämförs med transaktionsuppsättningen för validering. För en tolvmånadersperiod kan exempelvis månad 12 åsidosättas som en datauppsättning för validering. Om modellen förutser minst en sak som du skulle köpa i månad 12, baserat på vad den lärt sig de senaste 11 månaderna, skulle kunden öka måttet "Framgång vid K".
    
    1. **De flesta produkter som föreslogs (med summa):** De fem bästa produkterna som kunderna kunde använda.
       > [!div class="mx-imgBorder"]
       > ![Graf som visar de fem mest rekommenderade produkterna](media/product-recommendation-topproducts.PNG "Graf som visar de fem mest rekommenderade produkterna")
    
    1. **Viktiga rekommendationsfaktorer:** I modellen används kundernas transaktionshistorik för att ge produktrekommendationer. Man lär sig mönster utifrån tidigare köp och hittar likheter mellan kunder och produkter. Dessa likheter används sedan för att skapa produktrekommendationer.
    Följande faktorer kan påverka produktrekommendationen från modellen. 
        - **Tidigare transaktioner**: Tidigare köpmönster har använts av modellen för att skapa produktrekommendationer. Modellen kan till exempel rekommendera en _Surface Arc Mouse_ om någon nyligen har köpt en _Surface Book 3_ och en _Surface Pen_. Modellen lärde sig att historiskt sett hade många kunder köpt en _Surface Arc Mouse_ efter köp av en _Surface Book 3_ och en _Surface Pen_.
        - **Kundlikhet**: En rekommenderad produkt har tidigare köpts av andra kunder med liknande köpmönster. John rekommenderades till exempel för _Surface hörlurar 2_ eftersom Jennifer och Brad nyligen köpte _Surface hörlurar 2_. Modellen tror att John påminner om Jennifer och Brad eftersom de tidigare har liknande köpmönster.
        - **Produktlikhet**: En rekommenderad produkt liknar andra produkter som kunden tidigare köpt. Modellen betraktar två produkter som liknande om de liknade varandra eller av liknande kunder. Någon får till exempel en rekommendation för en _USB lagringsenhet_ eftersom de tidigare har köpt en _USB-C till USB-adapter_ och modellen tror att _USB lagringsenhet_ liknar _USB-C till USB-adapter_ baserat på historiska köpmönster.

        Varje produktrekommendation beror på en eller flera av dessa faktorer. Procentandelen rekommendationer som visualiseras i ett diagram när varje faktor har betydelse för en roll. I följande exempel används 100 % av rekommendationerna för tidigare transaktioner, 60 % av kundlikheten och 22 % av produktlikhet. Håll markören över staplarna i diagrammet om du vill se den exakta procentsatsen för var faktorerna har bidragit.

        > [!div class="mx-imgBorder"]
        > ![Viktiga rekommendationsfaktorer](media/product-recommendation-keyrecommendationfactors.png "Viktiga faktorer som rekommenderas av modellen när det gäller att skapa produktrekommendationer")
       
     
   1. **Datastatistik**: Ger en översikt över antalet transaktioner, kunder och produkter som modellen omfattar. Den baseras på indata som har använts för att lära sig mönster och skapa produktrekommendationer.

      > [!div class="mx-imgBorder"]
      > ![Datastatistik](media/product-recommendation-datastatistics.png "Datastatistik runt indata som används av modellen för att lära sig mönster")

      I det här avsnittet visas information om datapunkter som använts av modellen för att lära sig mönster och skapa produktrekommendationer. Filtrering, som konfigurerats i modellkonfigurationen, tillämpas på utdata från modellen. Men i modellen används alla tillgängliga data för att lära sig mönster. Om du använder produktfiltrering i modellkonfigurationen visas därför det totala antal produkter som modellen har analyserats för att lära sig mönster, vilket kan skilja sig från antalet produkter som matchar de definierade filtreringsvillkoren.

   1. **Produktrekommendationer med hög säkerhet** Ett antal rekommendationer för dina kunder som modellen tror att kunden sannolikt kommer att köpa.    
      Om en produktkatalog läggs till ersätts produkt-ID:erna med produktnamn. Produktnamn ger en mer användbar och intuitiv information om prognoserna.
       > [!div class="mx-imgBorder"]
       > ![Lista med förslag med hög säkerhet för en utvald uppsättning enskilda kunder](media/product-recommendation-highconfidence.PNG "Lista med förslag med hög säkerhet för en utvald uppsättning enskilda kunder")

## <a name="fix-a-failed-prediction"></a>Åtgärda en misslyckad förutsägelse

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.

1. Välj den förutsägelse du vill visa felloggar för och välj **Loggar**.

1. Granska alla fel. Det finns flera typer av fel som kan inträffa, och dessa beskriver vilket villkor som orsakat problemet. Ett fel som exempelvis innebär att det inte finns tillräckligt med data för att korrekt kunna lösa problem kan vanligtvis lösas genom att fler data läses in i Customer Insights.

## <a name="refresh-a-prediction"></a>Uppdatera en förutsägelse

Förutsägelser uppdateras automatiskt enligt samma [schema som data uppdateras](system.md#schedule-tab) enligt konfigurationen i inställningarna.

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.

1. Markera de lodräta punkterna bredvid den förutsägelse du vill uppdatera.

1. Välj **Uppdatera**.

## <a name="delete-a-prediction"></a>Ta bort en förutsägelse

Om du tar bort en förutsägelse tas även dess utdataentitet bort.

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.

1. Markera de lodräta punkterna bredvid den förutsägelse du vill ta bort.

1. Välj **Ta bort**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
