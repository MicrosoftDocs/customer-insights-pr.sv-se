---
title: Förutse produktrekommendationer
description: Förutse produkterna som kunder sannolikt köper eller interagerar med.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610304"
---
# <a name="predict-product-recommendations"></a>Förutse produktrekommendationer

Med produktrekommendationsmodellen skapas uppsättningar med förutsägelse av produktrekommendationer. Rekommendationer baseras på tidigare köpbeteende och kunder med liknande köpmönster. Modellen används för enskilda användare (B2C).

Du måste ha affärskunskap för att förstå olika typer av produkter för ditt företag och hur kunderna interagerar med dem. Vi ger stöd åt att rekommendera produkter som tidigare köpts av dina kunder eller rekommendationer för nya produkter.

Produktrekommendationer kan omfattas av lokala lagar och regler och kundförväntningar, som modellen inte är utformad för att specifikt ta hänsyn till. Därför måste du **gå igenom rekommendationerna innan du levererar dem till dina kunder** för att se till att du följer tillämpliga lagar och regler och kundförväntningar för vad du kan rekommendera.

Utdata från den här modellen ger rekommendationer baserat på produkt-ID. Leveransmekanismen måste mappa de befintliga produkt-ID:erna till rätt innehåll så att kunderna kan ta hänsyn till lokalisering, bildinnehåll och annat företagsspecifikt innehåll eller beteende.

> [!TIP]
> Testa förutsägelse av produktrekommendationer med exempeldata: [Guide för förutsägelse av produktrekommendationer](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md)
- Minst 100 kunder, helst fler än 10 000 kunder.
- Kundidentifierare, en unik identifierare som matchar transaktioner till en enskild kund
- Minst ett års transaktionsdata, helst två till tre år för att få med viss giltighet. Helst minst tre eller fler transaktioner per kund-ID. Transaktionshistoriken måste innehålla:
  - **Transaktions-ID**: En unik identifierare för ett inköp eller en transaktion.
  - **Transaktionsdatum**: Datumet för köpet eller transaktionen.
  - **Värde för transaktionen**: Det numeriska värdet för köpet eller transaktionen.
  - **Unikt produkt-ID**: ID för den produkt eller tjänst som köpts om dina data finns på en radartikelnivå.
  - **Köp eller retur**: Ett booleskt true/false värde där *true* anger att en transaktionen var en retur. Om data för Inköp eller Retur inte tillhandahålls av modellen och **värdet för transaktionen** är negativt drar vi nytta av en retur.
- En entitet för produktkatalogdata som ska användas som produktfilter.

> [!NOTE]
> - Modellen kräver transaktionshistorik för kunderna där transaktionen är data som beskriver interaktionen mellan användare och produkt. Till exempel köpa en produkt, ta en klass eller delta i ett evenemang.
> - Det går bara att konfigurera en entitet för transaktionshistorik. Om det finns flera entiteter för inköp kan du kombinera dem i Power Query före datainmatningen.
> - Om order och orderinformation är olika entiteter sammanfogar du dem innan du använder dem i modellen. Modellen fungerar inte med ett order-ID eller inleverans-ID för en entitet.

## <a name="create-a-product-recommendation-prediction"></a>Skapa en förutsägelse av produktrekommendationer

Välj **Spara utkast** om du vill prediktion utkast. Förutsägelseutkastet visas i fliken **Mina förutsägelser**.

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Produktrekommendationsmodell (förhandsversion)**.

1. Välj **Komma igång**.

1. **Ge modellen** och **utdataentiteten ett namn** för att särskilja dem från andra modeller eller entiteter.

1. Välj **Nästa**.

### <a name="define-product-recommendation-preferences"></a>Definiera inställning av produktrekommendation

1. Ange **antalet produkter** som du vill rekommendera till en kund. Värdet beror på hur leveranssättet fyller i data.

1. Välj om du vill ta med produkter som kunder nyligen har köpt i fältet **Upprepade inköp som förväntas**.

1. Ange **Fönstret Titta bakåt** med tidsramen som modellen tar i beaktande innan produkten rekommenderas till användaren igen. Ange till exempel att en kund köper en bärbar dator vartannat år. Modellen tittar på inköpshistoriken för de senaste två år och om de hittar ett objekt filtreras objektet från rekommendationerna.

1. Välj **Nästa**

### <a name="add-purchase-history"></a>Lägg till inköpshistorik

1. Välj **Lägg till data** för **Historik för kundtransaktioner**.

1. Välj typ av semantisk aktivitet **SalesOrderLine** som innehåller transaktions- eller inköpshistorik informationen. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var semantiskt mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="En sidoruta som anger specifika aktiviteter under semantiktypen.":::

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Välj **Nästa**.

### <a name="add-product-information-and-filters"></a>Lägg till produktinformation och filter

Ibland är det bara vissa produkter som är lämpliga för den typ av prediktion du bygger. Med produktfilter kan du identifiera en deluppsättning produkter med specifika egenskaper som du kan rekommendera till kunderna. I modellen används alla tillgängliga produkter för att lära sig mönster, men endast produkterna som matchar produktfiltret används i utdata.

1. Lägg till entiteten för produktkatalogen som innehåller information för varje produkt. Mappa den information som krävs för att välja **Spara**.

1. Välj **Nästa**.

1. Välj **Produktfilter**:

   - **Inga filter**: Använd alla produkter i produktrekommendationen prediktion.

   - **Definiera specifika produktfilter**: Använd specifika produkter i produktrekommendationen prediktion. I rutan **Produktkatalogattribut** väljer du de attribut från entiteten produktkatalog som du vill ta med i filtret.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Sidruta som visar att produktkatalogentiteten ska väljas för produktfilter.":::

1. Välj om du vill att produktfiltret ska använda **and** **or** för att på ett logiskt sätt kombinera dina val av attribut från produktkatalogen.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Exempelkonfiguration av produktfilter i kombination med logiska AND-kopplingar.":::

1. Välj **Nästa**.

### <a name="set-update-schedule"></a>Ange uppdateringsschema

1. Välj en frekvens för att träna om modellen. Denna inställning är viktig för att uppdatera precisionen i förutsägelser när nya data hämtas till Customer Insights. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

### <a name="review-and-run-the-model-configuration"></a>Granska och köra modellkonfigurationen

Steget **Granska och kör** visar en sammanfattning av konfigurationen och ger en chans att göra ändringar innan du skapar förutsägelse.

1. Välj **Redigera** på något av stegen för att granska och göra eventuella ändringar.

1. Om du är nöjd med dina val, välj **Spara och kör** för att starta modellen. Välj **Klar**. Fliken **Mina prognoser** visas när prediktion skapas. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visa förutsägelsens resultat

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Mina förutsägelser**, välj den förutsägelse du vill visa.

Det finns fem primära dataavsnitt på resultatsidan.

- **Modellprestanda:** Betyget A, B eller C indikerar prestandan för förutsägelsen och kan hjälpa dig att fatta beslutet att använda de resultat som är lagrade i utdataentiteten.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Bild på modellprestandaresultat med betyg A.":::

  Betyg fastställs utifrån följande regler:
  - **A** när "Framgång @ K"-måttet är minst 10 % mer än baslinjen.
  - **B** när "Framgång @ K"-måttet är minst 0 % till 10 % mer än baslinjen.
  - **C** när "Framgång @ K"-måttet är mindre än baslinjen.
  - **Grundnivå**: de mest rekommenderade produkterna från antalet köp av alla kunder + inlärda regler som identifierats av modellen = en uppsättning rekommendationer för kunderna. Därefter jämförs förutsägelserna med de bästa produkterna, beräknat på antalet kunder som köpt produkten. Om en kund har minst en produkt i sina rekommenderade produkter som också fanns bland de produkter som köpts mest, betraktas de som en del av grundnivån. Om t.ex. tio av dessa kunder hade köpt en rekommenderad produkt av 100 kunder skulle grundnivån vara 10 %.
  - **Framgång @ K**: Rekommendationer skapas för alla kunder och jämförs med valideringsuppsättningen av transaktionsperioder. För en tolvmånadersperiod kan exempelvis månad 12 åsidosättas som en datauppsättning för validering. Om modellen förutser minst en sak som du skulle köpa i månad 12, baserat på vad den lärt sig de senaste 11 månaderna, skulle kunden öka måttet "Framgång vid K".

- **De flesta produkter som föreslogs (med summa):** De fem bästa produkterna som kunderna kunde använda.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graf som visar de fem mest rekommenderade produkterna.":::

- **Viktiga rekommendationsfaktorer:** I modellen används kundernas transaktionshistorik för att ge produktrekommendationer. Man lär sig mönster utifrån tidigare köp och hittar likheter mellan kunder och produkter. Dessa likheter används sedan för att skapa produktrekommendationer.
  Följande faktorer kan påverka produktrekommendationen från modellen.
  - **Tidigare transaktioner**: En rekommenderad produkt baserades på tidigare köpmönster. Modellen kan till exempel rekommendera en *Surface Arc Mouse* om någon nyligen har köpt en *Surface Book 3* och en *Surface Pen*. Modellen lärde sig att historiskt sett hade många kunder köpt en *Surface Arc Mouse* efter köp av en *Surface Book 3* och en *Surface Pen*.
  - **Kundlikhet**: En rekommenderad produkt har tidigare köpts av andra kunder med liknande köpmönster. John rekommenderades till exempel för *Surface hörlurar 2* eftersom Jennifer och Brad nyligen köpte *Surface hörlurar 2*. Modellen tror att John påminner om Jennifer och Brad eftersom de tidigare har liknande köpmönster.
  - **Produktlikhet**: En rekommenderad produkt liknar andra produkter som kunden tidigare köpt. Modellen betraktar två produkter som liknande om de liknade varandra eller av liknande kunder. Någon får till exempel en rekommendation för en *USB lagringsenhet* eftersom de tidigare har köpt en *USB-C till USB-adapter* och modellen tror att *USB lagringsenhet* liknar *USB-C till USB-adapter* baserat på historiska köpmönster.

  Varje produktrekommendation beror på en eller flera av dessa faktorer. Procentandelen rekommendationer som visualiseras i ett diagram när varje faktor har betydelse för en roll. I följande exempel används 100 % av rekommendationerna för tidigare transaktioner, 60 % av kundlikheten och 22 % av produktlikhet. Håll markören över staplarna i diagrammet om du vill se den exakta procentsatsen för var faktorerna har bidragit.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Viktiga faktorer som rekommenderas av modellen när det gäller att skapa produktrekommendationer.":::

- **Datastatistik**: En översikt över antalet transaktioner, kunder och produkter som modellen omfattar. Den baseras på indata som har använts för att lära sig mönster och skapa produktrekommendationer.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Datastatistik runt indata som används av modellen för att lära sig mönster.":::
  
  Modellen använder alla tillgängliga data för att lära sig mönster. Om du använder produktfiltrering i modellkonfigurationen visas därför det totala antal produkter som modellen har analyserats för att lära sig mönster, vilket kan skilja sig från antalet produkter som matchar de definierade filtreringsvillkoren. Filtrering tillämpas på den utdata som genereras av modellen.

- **Exempel på produktrekommendationer** Ett exempel på rekommendationer som modellen tror att kunden sannolikt kommer att köpa. Om en produktkatalog läggs till ersätts produkt-ID:erna med produktnamn.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lista med förslag med hög konfidens för en utvald uppsättning enskilda kunder.":::

> [!NOTE]
> I utdataenheten för denna modell visar *Poäng* det kvantitativa måttet på rekommendationen. I modellen rekommenderas produkter med högre poäng över produkter med lägre poäng. För att visa poängen, gå till **Data** > **Entiteter** och visa datafliken för den utdataenhet som du definierade för den här modellen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
