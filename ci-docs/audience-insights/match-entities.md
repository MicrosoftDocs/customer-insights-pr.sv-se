---
title: Matcha entiteter för datasammanslutningen
description: Matcha entiteter för att skapa enhetliga kundprofiler.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376944"
---
# <a name="match-entities"></a>Matcha entiteter

Matchningsfasen anger hur dina datauppsättningar kombineras till en enhetlig kundprofil datauppsättning. När du har slutfört [mappningssteget](map-entities.md) i datasammanslutningsprocessen är du redo att matcha dina entiteter. Matchningsfasen kräver minst två mappade entiteter.

Matchningssidan består av tre avsnitt: 
- Viktiga mått som sammanfattar antalet matchande poster
- Matcha ordning och regler för entitetsöverskridande matchning
- Regler för dubblering av matchningsentiteter

## <a name="specify-the-match-order"></a>Ange matchningsordningen

Varje matchning kombinerar två eller flera entiteter till en enda konsoliderad entitet. Samtidigt behålls de unika kundposterna. Matchningsordningen anger i vilken ordning systemet försöker matcha posterna.

> [!IMPORTANT]
> Den entitet som du väljer som primär entitet ska utgöra grund för datauppsättningen för dina sammanslutna profiler. Ytterligare entiteter som väljs under matchningsfasen läggs till i den här entiteten. Detta betyder inte att den enhetliga entiteten omfattar *alla* data som ingår i entiteten.
>
> Det finns två saker som du kan använda för att välja hierarkin för dina entiteter:
>
> - Välj entiteten med de mest fullständiga och tillförlitliga profildata om dina kunder som primär entitet.
> - Välj den entitet som har flera attribut som delas av andra entiteter (t.ex. namn, telefonnummer eller e-postadress) som primär entitet.

1. Gå till **Data** > **Förena** > **Matcha** och välj **Ange ordning** för att starta matchningsfasen.
1. Välj **Entitetsordning**. Välj till exempel **eCommerce:eCommerceContacts** som primär entitet och **LoyaltyScheme:loyCustomers** som sekundär entitet. 
1. Om du vill att alla poster i entiteten är en unik kund och matchas till alla efterföljande entiteter, väljer du **Inkludera alla**.
1. Välj **Utfört**. 

När du har angett matchningsordningen visas de angivna matchningsparen i avsnittet **Information om matchade poster** på **Data** > **Förena** > **Matcha**. De viktigaste måtten är tomma tills matchningsprocessen är klar.

:::image type="content" source="media/match-page.png" alt-text="Skärmbild av sidan Matchning i området Sammanslutning i datasammanslutningsprocessen .":::
  
Den primära entiteten *eCommerce:eCommerceContacts* matchas med nästa entitet *LoyaltyScheme:loyCustomers*. Datauppsättningen som resulterar från det första matchningssteget matchas med följande enhet om du har fler än två enheter.

## <a name="define-rules-for-match-pairs"></a>Definiera regler för matchningspar

Matchningsregler anger den logik som ett specifikt par med entiteter ska matchas mot.

Varningen **Behöver regler** bredvid ett entitetsnamn innebär att inga matchningsregler har definierats för ett matchningspar. 

:::image type="content" source="media/match-rule-add.png" alt-text="Skärmbild av avsnittet Information om matchade poster med kontroll för att lägga till regler.":::

1. Välj **Lägg till regel** under en entitet i avsnittet **Information om matchade poster** om du vill definiera matchningsregler.

1. I fönstret **Skapa regel** konfigurerar du villkoren för regeln.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Skärmbild av en öppen matchningsregel med villkor tillagda.":::

   - **Entitet/fält (första raden)**: Välj en relaterad entitet och ett attribut för att specificera en postegenskap som sannolikt är unik för en kund. Till exempel ett telefonnummer eller en e-postadress. Undvik att matcha efter aktivitetstypattribut. Ett köp-ID hittar troligen ingen matchning i andra posttyper.

   - **Entitet/fält (andra raden)**: Välj ett attribut som relaterar till attributet för den entitet som specificerats i första raden.

   - **Normalisera**: Välj bland följande normaliseringsalternativ för de valda attributen. 
     - Siffror: Konverterar andra numeriska system, t.ex. romerska tecken till arabiska siffror. *VIII* blir *8*.
     - Symboler: Tar bort alla symboler och specialtecken. *Head&Shoulder* blir *HeadShoulder*.
     - Text till gemener: Konverterar alla tecken till gemener. *ALLA VERSALER och rubriker* blir *alla versaler och rubriker*.
     - Typ (telefon, namn, adress, organisation): Standardiserar namn, titlar, telefonnummer, adresser osv. 
     - Unicode till ASCII: Konverterar unicode-notation till ASCII-tecken. */u00B2* blir *2*.
     - Tomt utrymme: Tar bort alla blanksteg. *Hej   världen* blir *Hejvärlden*.

   - **Precision**: Ange vilken precisionsnivå som ska tillämpas för detta villkor. 
     - **Grundläggande**: Välj mellan *Låg*, *Medel*, *Hög* och *Exakt*. Välj **Exakt** om du endast vill matcha poster som matchar 100 procent. Välj en av de andra nivåerna för att matcha poster som inte är 100 procent identiska.
     - **Anpassad**: Ange en procentandel som posterna måste matcha. Systemet matchar endast poster som passerar tröskelvärdet.

1. Ange ett **Namn** för regeln.

1. [Lägg till fler villkor](#add-conditions-to-a-rule) eller välj **Klart** för att slutföra regeln.

1. Alternativt kan du [lägga till fler regler](#add-rules-to-a-match-pair).

1. Välj **Spara** för att införa ändringarna.

### <a name="add-conditions-to-a-rule"></a>Lägg till villkor till en regel

Om du endast vill matcha entiteter om attributen uppfyller flera villkor lägger du till fler villkor i en matchningsregel. Villkoren är kopplade till en logisk OCH-operator och körs därför endast om alla villkor uppfylls.

1. Gå till **Data** > **Förena** > **Matcha** och välj **Redigera** för den regel som du vill lägga till villkor för.

1. I rutan **Redigera regel**, välj **Lägg till villkor**.

1. Välj **Klar** för att spara regeln.

### <a name="add-rules-to-a-match-pair"></a>Lägga till regler till ett matchningspar

Matchningsregler representerar uppsättningar av villkor. Om du vill matcha entiteter efter villkor baserat på flera attribut lägger du till fler regler.

1.  Gå till **Data** > **Förena** > **Matcha** och välj **Lägg till regel** för den entitet som du vill lägga till regler för.

2. Följ anvisningarna i [Definiera regler för matchningspar](#define-rules-for-match-pairs).

> [!NOTE]
> Regelordningen är viktig. Matchningsalgoritmen försöker matcha baserat på den första regeln och fortsätter endast till den andra regeln om inga matchningar identifierades med den första regeln.

### <a name="change-the-entity-order-in-match-rules"></a>Ändra entitetsordningen i matchningsregler

Du kan ändra ordningen på entiteter för matchningsregler om du vill ändra i vilken ordning de bearbetas. Regler som står i konflikt på grund av en ändrad order tas bort. Du måste återskapa borttagna regler med en uppdaterad konfiguration.

1. Gå till **Data** > **Förena** > **Matcha** och välj **Redigera**.

1. I rutan **Redigera regel** markerar du kontrollen **Flytta upp/ned** entiteter för att ändra ordningen.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Alternativ för att ändra i vilken ordning entiteter bearbetas i matchningsfasen.":::

1. Välj **Klar** för att spara regeln.

## <a name="define-deduplication-on-a-match-entity"></a>Definiera deduplicering på en matchningsentitet

Utöver [regler för entitetsöverskridande matchning](#define-rules-for-match-pairs) kan du även specificera dedupliceringsregler. *Deduplicering* är en annan process när poster matchas. Den identifierar dubblettposter och slår samman dem till en post. Källposter länkas till den sammanslagna posten med alternativa ID.

Deduplicerade poster används i matchningsprocessen för flera entiteter. Deduplicering sker på enskilda entiteter och kan konfigureras för varje entitet som används i matchningspar.

Det är inte obligatoriskt att ange dedupliceringsregler. Om inga sådana regler konfigureras tillämpas de systemdefinierade reglerna. De kombinerar alla poster till en enskild post innan de skickar entitetsdata till entitetsöverskridande matchning för bättre prestanda.

### <a name="add-deduplication-rules"></a>Lägg till dedupliceringsregler

1. Gå till **Data** > **Förena** > **Matcha**.

1. I avsnittet **Information om deduplicerade poster** väljer du **Ange entiteter**. I händelse av att dedupliceringsregler redan har skapats väljer du **Redigera**.

1. I fönstret **Sammanfogningspreferenser** väljer du de entiteter som du vill tillämpa deduplicering på.

   1. Ange hur du ska kombinera de duplicerade posterna och välj ett av tre alternativ:
      - **Mest ifylld**: Identifierar posten med flest ifyllda attributfält som vinnarpost. Det här är standardalternativet för sammanfogning.
      - **Senaste**: Identifierar vinnarpost baserat på aktualitet. Kräver ett datum eller ett numeriskt fält för att definiera aktualitet.
      - **Minst aktuell**: Identifierar vinnarpost baserat på lägsta aktualitet. Kräver ett datum eller ett numeriskt fält för att definiera aktualitet.

   1. Alternativt väljer du **Avancerat** om du vill definiera dedupliceringsregler för enskilda attribut i en entitet. Du kan till exempel välja att behålla den senaste e-postadressen OCH den mest fullständiga adressen från olika poster. Expandera entiteten om du vill visa alla attribut och definiera vilket alternativ som ska användas för enskilda attribut. Om du väljer ett recency-baserat alternativ måste du också ange ett datum- och tidsfält som definierar recency. 
 
      > [!div class="mx-imgBorder"]
      > ![Dedupliceringsregler steg 1.](media/match-selfconflation.png "Dedupliceringsregler steg 1")

   1. Välj **Klar** om du vill använda kopplingsinställningarna för deduplicering.
 
1. När entiteterna har valts och deras inställningar för sammanslagning har angetts väljer du **Lägg till regel** för att definiera dedupliceringsreglerna på en entitetsnivå.
   - I **Välj fält** anges alla tillgängliga fält från den entiteten. Välj det fält du vill söka i efter dubbletter. Välj fält som troligen är unika för varje enskild kund. Till exempel en e-postadress eller kombinationen av namn, ort och telefonnummer.
   - Ange normaliserings- och precisionsinställningar.
   - Definiera ytterligare villkor genom att välja **Lägg till villkor**.
 
   > [!div class="mx-imgBorder"]
   > ![Dedupliceringsregler steg 2.](media/match-selfconflation-rules.png "Dedupliceringsregler steg 2")

  Du kan skapa flera dedupliceringsregler för en entitet. 

1. Att köra matchningsprocessen grupperar nu posterna baserat på de villkor som definierats i dedupliceringsreglerna. Efter att ha grupperat posterna tillämpas sammanslagningsprincipen för att identifiera vinnarposten.

1. Denna vinnarpost förs sedan vidare till den entitetsöverskridande matchningen, tillsammans med icke-vinnande poster (till exempel alternativa ID) för att förbättra matchningskvaliteten.

1. Alla anpassade matchningsregler som har definierats skriver över dedupliceringsregler. Om en dedupliceringsregel identifierar matchande poster och en anpassad matchningsregel är inställd på att aldrig matcha dessa poster, matchas inte dessa två poster.

1. När du har [kört matchningsprocessen](#run-the-match-process) visas dedupliceringen i de viktigaste måttpanelerna.

### <a name="deduplication-output-as-an-entity"></a>Dedupliceringsutdata som en entitet

Med dedupliceringsprocessen skapas en ny entitet för varje entitet från matchningsparen för att identifiera de deduplicerade posterna. Dessa entiteter finns tillsammans med **ConflationMatchPairs:CustomerInsights** i avsnittet **System** på sidan **Entiteter**, med namnet **Deduplication_DataSource_Entity**.

En utdataenhet för deduplicering innehåller följande information:
- ID/Nycklar
  - Primärnyckelfält och dess alternativa ID-fält. Fältet Alternativa ID består av alla alternativa ID som identifieras för en post.
  - Deduplication_GroupId visar gruppen eller klustret som identifieras i en entitet som grupperar alla liknande poster utifrån de angivna dedupliceringsfälten. Det används för systembearbetning. Om det inte finns några manuella dedupliceringsregler som anges och systemdefinierade dedupliceringsregler gäller kanske inte det här fältet finns i entiteten för dedupliceringsutdata.
  - Deduplication_WinnerId: Det här fältet innehåller vinnande ID från de identifierade grupperna eller klustren. Om Deduplication_WinnerId är samma värde som primärnyckeln för en post innebär det att posten är vinnarposten.
- Fält som används för att definiera dedupliceringsreglerna.
- Regel- och poängfält som anger vilka av dedupliceringsregler som tillämpats och poängen som returneras av den matchande algoritmen.
 
## <a name="include-enriched-entities-preview"></a>Inkludera utökade entiteter (förhandsgranskning)

Om du har utökat entiteter på datakälla nivå markerar du dem innan du kör matchningsprocessen. De utökade entiteterna kan förbättra sammanslagningsresultaten. Mer information: [Berikande för datakällor](data-sources-enrichment.md). 

Den utökade entiteten innehåller de ursprungliga datakälla och de utökade fälten. Om du väljer att arbeta med den utökade entiteten påverkas inte den befintliga konfigurationen. Du kan dock behöva uppdatera matchningsreglerna så att de utökade fälten används i stället.

1. Gå till **Data** > **Ena** > **Match** och välj **Använd utökade entiteter** överst på sidan.

1. Från rutan **Använd berikade entiteter** välj en eller flera berikade entiteter.

1. Välj **Utfört**. Oavsett var källentiteten används (till exempel matchningsordning eller regler) ändras den automatiskt till den utökade entiteten.
  
## <a name="run-the-match-process"></a>Kör matchningsprocessen

Med konfigurerade matchningsregler, inklusive regler för entitetsöverskridande matchning och deduplicering, kan du köra matchningsprocessen. 

Gå till **Data** > **Förena** > **Matcha** och välj **Kör** för att starta processen. Matchningsalgoritmen tar en stund att slutföra och du kan inte ändra konfigurationen förrän den är klar. Om du vill göra ändringar kan du avbryta körningen. Välj status för jobbet och välj **Avbryt jobb** i fönstret **Förloppsinformation**.

Resultatet av en lyckad körning, en entitet för en enhetlig kundprofil, visas på sidan **Entiteter**. Din enhetliga kundentitet kallas **Kunder** i avsnittet **Profiler**. Vid den första lyckade matchningskörningen skapas den enhetliga *Kund*-entiteten. Alla efterföljande matchningskörningar visar den entiteten.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Granska och verifiera dina matchningar

Gå till **Data** > **Förena** > **Matcha** för att utvärdera kvaliteten på matchningsparen och förfina dem om så krävs.

I panelerna överst på sidan visas viktiga mått som summerar antalet matchande poster och dubbletter.

:::image type="content" source="media/match-KPIs.png" alt-text="En liten skärmbild av de viktigaste måtten på sidan Matchning med siffror och detaljer.":::

- **Unika källposter** visar antalet enskilda källposter som behandlades i förra matchningskörningen.
- **Matchade och icke-matchade poster** visar hur många unika poster som finns kvar efter bearbetningen av matchningsreglerna.
- **Endast matchade poster** visar antalet matchningar för alla dina matchningspar.

Du kan utvärdera resultaten för varje matchningspar och dess regler i tabellen **Information om matchade poster**. Jämför antalet poster som kommer från ett matchningspar med procentandelen poster som har matchats korrekt.

Granska reglerna för ett matchningspar för att se procentandelen poster som har matchats korrekt på regelnivån. Välj ellipsen (...) och sedan **Matchningsförhandsgranskning** för att visa alla dessa poster på regelnivån. Vi rekommenderar att du tar en titt på några poster för att verifiera att de matchats korrekt.

Prova olika precisionströskelvärden under särskilda villkor för att hitta det optimala värdet.

  1. Välj ellipsen (...) för regeln som du vill experimentera med och välj **Redigera**.

  2. Ändra precisionsvärdena i de villkor som du vill ändra.

  3. Välj **Förhandsgranskning** för att se antalet matchade och omatchade poster för det valda villkoret.

## <a name="manage-match-rules"></a>Hantera matchningsregler

Du kan konfigurera om och finjustera de flesta matchningsparametrarna.

:::image type="content" source="media/match-rules-management.png" alt-text="Skärmbild av listrutan med alternativ för matchningsregel.":::

- **Ändra ordning på reglerna** om du har definierat flera regler. Du kan ändra ordningen på matchningsreglerna genom att välja alternativen **Flytta upp** och **Flytta ned** eller genom att dra och släppa.

- **Ändra regelvillkoren** genom att välja **Redigera** och välja olika fält.

- **Inaktivera en regel** om du vill behålla en matchningsregel och utesluta den från matchningsprocessen.

- **Duplicera reglerna** om du har definierat en matchningsregel och vill skapa en liknande regel med modifikationer, välj **Duplicera**.

- **Ta bort en regel** genom att välja symbolen **Ta bort**.

## <a name="advanced-options"></a>Avancerade alternativ

### <a name="add-exceptions-to-a-rule"></a>Lägga till undantag för en regel

I de flesta fall leder entitetsmatchningen till unika användarprofiler med konsoliderade data. Om du vill hantera undantagsfall med falskt positiva och falskt negativa resultat dynamiskt kan du definiera undantag för en matchningsregel. Undantag tillämpas efter bearbetning av matchningsreglerna och undviker att matcha alla poster som uppfyller undantagsvillkoren.

Till exempel, om din matchningsregel kombinerar efternamn, stad och födelsedatum, identifierar systemet tvillingar med samma efternamn som bor i samma stad som samma profil. Du kan ange ett undantag som inte matchar profilerna om de förnamn i entiteterna du kombinerar inte är samma.

1. Gå till **Data** > **Förena** > **Matcha** och välj **Redigera** för den regel som du vill lägga till villkor för.

1. I fönstret **Redigera regel**, välj **Lägg till undantag**.

1. Ange undantagsvillkor. 

1. Välj **Klar** för att spara regeln.

### <a name="specify-custom-match-conditions"></a>Ange anpassade matchningsvillkor

Det går att ange villkor som åsidosätter standardinställd matchningslogik. Det finns fyra alternativ: 

|Option  |Description |Exempel  |
|---------|---------|---------|
|Matcha alltid     | Definiera värden som alltid matchas.         |  Matcha alltid *Mike* och *MikeR*.       |
|Matcha aldrig     | Definiera värden som aldrig matchas.        | Matcha aldrig *John* och *Jonathan*.        |
|Anpassad överhoppning     | Definierar värden som systemet alltid måste ignorera i matchningsfasen. |  Ignorera värdena *11111* och *Okänt* under matchning.        |
|Aliasmappning    | Definierar värden som systemet måste anse vara samma värde.         | Anse att *Joe* är lika med *Joseph*.        |

1. Gå till **Data** > **Förena** > **Matcha** och välj **Anpassad matchning** i avsnittet **Information om matchade poster**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Skärmbild av avsnittet Matchningsregler med kontroll för anpassad matchning markerad.":::

1. Öppna fliken **Poster** i fönstret **Anpassat**.

1. Välj standardalternativet för matchning i listrutan **Anpassad typ** och välj **Ladda ned mall**. Du måste ha en separat mall för varje matchningsalternativ.

1. Öppna den hämtade mallfilen och fyll i informationen. Mallen innehåller fält som används för att ange entiteten och de primär nyckelvärden som ska användas i den anpassade matchningen. Om du till exempel vill att primärnyckeln *12345* från entiteten *Försäljning* alltid matchar primärnyckeln *34567* från entiteten *Kontakt*, fyller du i mallen:
    - Entitet1: Försäljning
    - Enhetsnyckel1: 12345
    - Entitet2: Kontakt
    - Enhetsnyckel2: 34567

   Samma mallfil kan ange anpassade matchningsposter från flera entiteter.
   
   Om du vill ange anpassad matchning för deduplicering för en entitet anger du samma entitet som både Entitet 1 och Entitet 2 och anger de olika primärnyckelvärdena.

1. Spara mallfilen när du har lagt till alla åsidosättningar.

1. Gå till **Data** > **Datakällor** och matar in mallfilerna som nya entiteter.

1. När du har överfört filerna och entiteterna tillgängliga väljer du alternativet för **anpassad matchning**. Du kommer att se alternativen för att ange vilka entiteter du vill ta med. Välj obligatoriska entiteter på den nedrullningsbara menyn och välj **Klart**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Skärmbild av dialogrutan för åsidosättning för ett anpassat matchningsscenario.":::

1. Användning av den anpassade matchningen beror på matchningsalternativet som du vill använda. 

   - Gå till nästa steg för **Matcha alltid** eller **Matcha aldrig**.
   - Välj **Redigera** för **Anpassad åsidosättning** eller **Aliasmappning** på en befintlig matchningsregel eller skapa en ny regel. Välj alternativet **Anpassad åsidosättning** eller **Aliasmappning** i listrutan Normaliseringar och välj **Klart**.

1. Välj **Spara** på sidan **Matcha** för att tillämpa den anpassade matchningskonfigurationen.

1. Välj **Kör** på sidan **Matcha** för att starta matchningsprocessen. Andra angivna matchningsregler åsidosätts av den anpassade matchningskonfigurationen.

#### <a name="known-issues"></a>Kända problem

- Självsammanslagning visar inte normaliserad data i avdupliceringsentiteter. Det använder dock normalisering internt under avduplicering. Det är inbyggt för alla normaliseringar. 
- Om den semantiska typinställningen tas bort i fasen **Mappa** när en matchningsregel använder Aliasmappning eller Anpassad åsidosättning, använd inte normaliseringen. Det händer endast om du rensar den semantiska typen efter konfiguration av normaliseringen i matchningsregeln eftersom den semantiska typen blir okänd.


## <a name="next-step"></a>Nästa steg

Fortsätt till steget [**Sammanfoga**](merge-entities.md) när du har slutfört matchning för minst ett matchningspar.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
