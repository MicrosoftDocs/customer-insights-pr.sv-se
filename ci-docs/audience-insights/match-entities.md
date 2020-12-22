---
title: Matcha entiteter för datasammanslutningen
description: Matcha entiteter för att skapa enhetliga kundprofiler.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407102"
---
# <a name="match-entities"></a>Matcha entiteter

När du har slutfört mappningsfasen är du klar att matcha entiteterna. Matchningsfasen anger hur dina datauppsättningar kombineras till en enhetlig kundprofil datauppsättning. Matchningsfasen kräver minst [två mappade entiteter](map-entities.md).

## <a name="specify-the-match-order"></a>Ange matchningsordningen

Gå till **förena** > **matchning** och välj **ange ordning** för att starta matchningsfasen.

Varje matchning förenar två eller fler entiteter till en enda entitet och behåller varje unik kundpost. I följande exempel valde vi tre entiteter: **ContactCSV: TestData** som **primär** entitet, **WebAccountCSV: TestData** som **entitet 2** och **CallRecordSmall: TestData** som **entitet 3**. Diagrammet ovanför valen illustrerar hur matchningsordningen ska köras.

> [!div class="mx-imgBorder"]
> ![Redigera datamatchningens ordning](media/configure-data-match-order-edit-page.png "Redigera datamatchningens ordning")
  
Den **primära** entiteten matchas med **Entitet2**. Den datauppsättning som resulterar av den första matchningen matchas med **Entitet 3**.
I det här exemplet valde vi bara två matchningar, men systemet har stöd för fler.

> [!IMPORTANT]
> Den entitet som du väljer som **primär** entitet ska utgöra grund för den enhetliga huvuddatauppsättningen. Ytterligare entiteter som väljs under matchningsfasen läggs till i den här entiteten. Samtidigt betyder detta att den enhetliga entiteten ska innehålla *alla* data som ingår i entiteten.
>
> Det finns två saker som du kan använda för att välja hierarkin för dina entiteter:
>
> - Vilken entitet anser du att du har den bästa och pålitliga informationen om dina kunder?
> - Har entiteten du just identifierat attribut som även delas av andra entiteter (t.ex. namn, telefonnummer eller e-postadress)? Annars väljer du den näst tillförlitliga entiteten.

Välj **klart** om du vill spara matchningsordern.

## <a name="define-rules-for-your-first-match-pair"></a>Definiera regler för ditt första matchningspar

När du har angett matchningsordningen visas de definierade matchningarna på sidan **matcha**. De paneler som visas högst upp på skärmen är tomma tills du kör en matchningsordning.

> [!div class="mx-imgBorder"]
> ![Definiera regler](media/configure-data-match-need-rules.png "Definiera regler")

Varningen **Regler behövs** föreslår att ingen matchningsregel har definierats för ett matchningspar. Matchningsregler anger den logik som ett specifikt par med entiteter ska matchas mot.

1. Om du vill definiera den första regeln öppnar du rutan **Regeldefinition** genom att markera motsvarande matchningsrad i matchningstabellen (1) och sedan välja **skapa ny regel** (2).

   > [!div class="mx-imgBorder"]
   > ![Skapa ny regel](media/configure-data-match-new-rule2.png "Skapa ny regel")

2. I rutan **redigera regel** konfigurerar du villkoren för den regeln. Varje villkor representeras av två rader som innehåller obligatoriska alternativ.

   > [!div class="mx-imgBorder"]
   > ![Panelen Ny regel](media/configure-data-match-new-rule-condition.png "Panelen Ny regel")

   Entitet/fält (första) – ett attribut som ska användas för matchning från den första matchningsparets entitet. Exempel kan vara ett telefonnummer eller en e-postadress. Välj ett attribut som troligen är unikt för kunden.

   > [!TIP]
   > Undvik matchningar utifrån attribut av aktivitetstyp. Om ett attribut verkar vara en aktivitet kan det till andra ord finnas ett dåliga villkor att matcha.  

   Entitet/fält (andra) – ett attribut som ska användas för matchning från den andra matchningsparets entitet.

   Normalisering - **normaliseringsmetod**: olika normaliseringsalternativ är tillgängliga för de valda attributen. Du kan till exempel ta bort punkter och ta bort blanksteg

   I normalisering organisationsnamn (förhandsgranskning) kan du också välja **Typ (telefon, namn, organisation)**

   > [!div class="mx-imgBorder"]
   > ![Normalisering-B2B](media/match-normalization-b2b.png "Normalisering-B2B")

   Precisionsnivå – precisionsnivån som används för det här villkoret. Inställning av en precisionsnivå för ett matchningsvillkor kan ha två typer: **grundläggande** och **anpassad**.  
   - Grundläggande: du kan välja mellan följande fyra alternativ: låg, medium, hög och exakt. Välj **exakt** om du endast vill matcha poster som matchar 100 procent. Välj en av de andra nivåerna för att matcha poster som inte är 100 procent identiska.
   - Anpassa: Använd skjutreglaget för att definiera ett anpassat procentvärde som poster behöver matcha eller ange ett värde i det **anpassade** fältet. Systemet kommer endast att matcha poster som uppfyller detta tröskelvärde som ihopslagna matchningspar. Värden på skjutreglaget är mellan 0 och 1. Så 0,64 representerar 64 procent.

3. Välj **Klar** för att spara regeln.

### <a name="add-multiple-conditions"></a>Lägg till flera villkor

Om du vill att entiteterna endast ska stämma överens om flera villkor uppfylls lägger du till fler villkor som är länkade via operatorn AND.

1. I rutan **Redigera regel**, välj **Lägg till villkor**. Du kan också ta bort villkor genom att klicka på knappen Ta bort bredvid ett befintligt villkor.

2. Välj **Klar** för att spara regeln.

## <a name="add-multiple-rules"></a>Lägga till flera regler

Varje villkor gäller för ett enskilt par, medan regler representerar villkorsuppsättningar. Om du vill att entiteterna matchas efter olika uppsättningar med attribut kan du lägga till fler regler.

1. I målgruppsinsikter går du till **Data** > **Slå samman** > **Matcha**.

2. Välj den enhet du vill uppdatera och välj **Lägg till regler**.

3. Följ proceduren som beskrivs i [definiera regler för det första matchningsparet](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Regelordningsfrågor. Matchningsalgoritmen försöker matcha baserat på den första regeln och fortsätter till den andra regeln endast om inga matchningar identifierades under den första regeln.

## <a name="define-deduplication-on-a-match-entity"></a>Definiera deduplicering på en matchningsentitet

Tillsammans med att ange entitetsöverskridande matchningsregler enligt vad som beskrivs i ovanstående avsnitt, kan du också ange dedupliceringsregler. *Deduplicering* är en process. Den identifierar dubblettposter, sammanfogar dem till en post och länkar alla källposter till den här sammanfogade posten med alternativa ID till den sammanfogade posten.

När en deduplicerad post har identifierats kommer den posten att användas i den entitetsöverskridande matchningsprocessen. Deduplicering implementeras på entitetsnivå och kan tillämpas på varje entitet som används i matchningsprocessen.

### <a name="add-deduplication-rules"></a>Lägg till dedupliceringsregler

1. I målgruppsinsikter går du till **Data** > **Slå samman** > **Matcha**.

1. I avsnittet **Sammanfogade dubbletter** väljer du **Ange entiteter**.

1. I avsnittet **Sammanfoga preferenser** sväljer du de entiteter som du vill tillämpa deduplicering på.

1. Ange hur du ska sammanfoga de duplicerade posterna och välj ett av tre sammanfogningsalternativ:
   - *Mest fyllda*: Identifierar posten med flest ifyllda attribut som vinnarpost. Det här är standardalternativet för sammanfogning.
   - *Senaste*: Identifierar vinnarpost baserat på aktualitet. Kräver ett datum eller ett numeriskt fält för att definiera aktualitet.
   - *Minst aktuell*: Identifierar vinnarpost baserat på lägsta aktualitet. Kräver ett datum eller ett numeriskt fält för att definiera aktualitet.
 
   > [!div class="mx-imgBorder"]
   > ![Dedupliceringsregler steg 1](media/match-selfconflation.png "Dedupliceringsregler steg 1")
 
1. När entiteterna har valts och deras inställningar för sammanslagning har angetts väljer du **Skapa ny regel** för att definiera dedupliceringsreglerna på en entitetsnivå.
   - **Välj fält** listar alla tillgängliga fält från den entiteten du vill deduplicera källdata på.
   - Ange inställningarna för normalisering och precision på liknande sätt som anges i den entitetsöverskridande matchningen.
   - Du kan definiera ytterligare villkor genom att välja **Lägg till villkor**.
 
   > [!div class="mx-imgBorder"]
   > ![Dedupliceringsregler steg 2](media/match-selfconflation-rules.png "Dedupliceringsregler steg 2")

  Du kan skapa flera dedupliceringsregler för en entitet. 

1. Att köra matchningsprocessen grupperar nu posterna baserat på de villkor som definierats i dedupliceringsreglerna. Efter att ha grupperat posterna tillämpas sammanslagningsprincipen för att identifiera vinnarposten.

1. Denna vinnarpost förs sedan vidare till den entitetsöverskridande matchningen.

1. Eventuella anpassade matchningsregler som definierats för matchar alltid och matchar aldrig åsidosätter dedupliceringsregler. Om en dedupliceringsregel identifierar matchande poster och en anpassad matchningsregel är inställd på att aldrig matcha dessa poster, matchas inte dessa två poster.

1. Efter att ha kört matchningsprocessen ser du dedupliceringsstatistiken.
   
> [!NOTE]
> Det är inte obligatoriskt att ange dedupliceringsregler. Om inga sådana regler konfigureras tillämpas de systemdefinierade reglerna. De komprimerar alla poster som delar samma värdekombination (exakt matchning) från primärnyckel och fälten i matchningsreglerna till en enda post innan de för entitetsdata till entitetsöversskridande matchning för förbättrad prestanda och systemsundhet.

## <a name="run-your-match-order"></a>Kör din matchningsorder

När du har definierat matchningsreglerna, inklusive regler för entitetsöverskridande matchning och deduplicering, kan du köra matchningsordern. På sidan **matchning** väljer du **Kör** för att starta processen. Det kan ta en stund att slutföra matchningsalgoritmen. Du kan inte ändra egenskaperna på sidan **matchning** förrän matchningsprocessen har slutförts. Du hittar den enhetliga entiteten för kundprofilen som skapades på sidan **entiteter**. Din enhetliga entitet för kund kallas **ConflationMatchPairs : CustomerInsights**.

Om du vill göra ytterligare ändringar och köra steget igen kan du avbryta en pågående matchning. Välj **Uppdatera...** text och välj **Avbryt jobb** längst ned på sidorutan som visas.

När matchningsprocessen är klar kommer texten **Uppdaterar ...** ändras till **Klart** och du kan använda alla funktioner på sidan igen.

Den första matchningsprocessen resulterar i att en enhetlig huvudentitet skapas. Alla efterföljande matchningar leder till att den här entiteten utökas.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="review-and-validate-your-matches"></a>Granska och verifiera dina matchningar

Utvärdera kvaliteten för dina matchningspar och omdefiniera den:

- På sidan **matchning** hittar du två paneler som visar inledande insikter om dina data.

  - **Unika kunder**: visar antalet unika profiler som systemet identifierat.
  - **Matchade poster**: visar antalet matchningar för alla matchningspar.

- I tabellen **matchningsordning** kan du utvärdera resultatet av varje matchningspar genom att jämföra antalet poster som kom från den här matchningsparets entitet mot procentandelen av poster som har matchats.

- I avsnittet **regler** för en entitet i tabellen **matchningsordning** hittar du en procentandel av de poster som har matchats på regelnivå. Genom att markera tabellsymbolen bredvid en regel kan du Visa alla de här posterna på regelnivån. Vi rekommenderar att du granskar en delmängd av posterna för att kontrollera att de matchades korrekt.

- Experimentera med olika precisionströsklar för att identifiera det optimala värdet.

  1. Markera tre punkter (...) för matchningsparregeln du vill experimentera med och välj **redigera**.

  2. Välj det villkor som du vill experimentera med. Varje villkor representeras av en rad i rutan **matchningsregel**.

  3. Vad som visas på sidan **Förhandsgranskning av villkor** beror på vilken precisionsnivå du har valt för ett villkor. Hitta antalet matchade och omatchade poster för det valda villkoret.

     Bli en rik förståelse för effekterna av olika tröskelvärden. Du kan jämföra hur många poster som ska matchas under var och en av tröskelnivåerna och visa posterna under varje alternativ. Markera alla paneler och granska data i avsnittet tabell.

## <a name="optimize-your-matches"></a>Optimera dina matchningar

Öka kvaliteten genom att konfigurera om en del av dina matchningsparametrar:

- **Ändra matchningsordningen** genom att välja **redigera** och ändra matchningsorderfälten.

  > [!div class="mx-imgBorder"]
  > ![Redigera datamatchningens ordning](media/configure-data-match-order-edit.png "Redigera datamatchningens ordning")

- **Ändra ordning på reglerna** om du har definierat flera regler. Du kan ändra ordning på matchnings reglerna genom att välja alternativen **flytta upp** och **flytta upp** i rutnätet för matchningsregler.

  > [!div class="mx-imgBorder"]
  > ![Ändra regelordning](media/configure-data-change-rule-order.png "Ändra regelordning")

- **Duplicera dina regler** om du har definierat en matchningsregel och vill skapa en liknande regel med ändringar. Gör så genom att välja **dubblett**.

  > [!div class="mx-imgBorder"]
  > ![Dubblera en regel](media/configure-data-duplicate-rule.png "Dubblera en regel")

- **Redigera reglerna** genom att välja symbolen **redigering**. Du kan tillämpas göra följande ändringar:

  - Ändra attribut för ett villkor: Välj nya attribut inom den angivna villkorsraden.
  - Ändra tröskelvärdet för ett villkor: Justera skjutreglaget för precision.
  - Ändra normaliseringsmetoden för ett villkor: uppdatera normaliseringsmetoden.

## <a name="specify-your-custom-match-records"></a>Ange dina anpassade matchningsposter

Du kan ange villkor för att vissa poster alltid ska matcha eller aldrig matcha. Dessa regler kan överföras i bulk till matchningsprocessen.

1. Välj alternativet **anpassad matchning** på skärmen **matchningsordning**.

   > [!div class="mx-imgBorder"]
   > ![Skapa en anpassad matchning](media/custom-match-create.png "Skapa en anpassad matchning")

2. Om du inte har uppladdat entiteter visas en ny dialogruta **anpassad matchning** som kräver att du fyller i vissa uppgifter. Om du har angett dessa uppgifter tidigare går du vidare till steg 8.

   > [!div class="mx-imgBorder"]
   > ![Dialogrutan Ny anpassad matchning](media/custom-match-new-dialog-box.png "Dialogrutan Ny anpassad matchning")

3. Välj **Fyll i mallen** för att få en mallfil som kan ange vilka poster som entiteterna alltid ska matcha eller aldrig matcha. Du måste fylla i posterna "alltid stämma" och "aldrig" i två olika filer separat.

4. Mallen innehåller fält som används för att ange entiteten och de primär nyckelvärden som ska användas i den anpassade matchningen. Om du till exempel vill att den primära nyckeln 12345 från entiteten försäljning ska stämma överens med den primära nyckeln 34567 från entiteten kontakt måste du ange följande:
    - Entitet1: Försäljning
    - Enhetsnyckel1: 12345
    - Entitet2: Kontakt
    - Enhetsnyckel2: 34567

   Samma mallfil kan ange anpassade matchningsposter från flera entiteter.

5. När du har lagt till alla åsidosättningar som du vill använda sparar du mallfilen.

6.Gå till **Data** > **Datakällor** och mata in mallfilerna som nya entiteter. När du har hämtat den kan du använda dem för att ange matchningskonfigurationen.

7. När du har överfört filerna och entiteterna tillgängliga väljer du alternativet för **anpassad matchning**. Du kommer att se alternativen för att ange vilka entiteter du vill ta med. Välj den erforderliga entiteten i listrutan.

   > [!div class="mx-imgBorder"]
   > ![Anpassad matchning åsidosättningar](media/custom-match-overrides.png "Anpassad matchning åsidosättningar")

8. Välj de entiteter som du vill använda för **Matcha alltid** och **Matcha aldrig**, välj **Klar**.

9. Välj **spara** på sidan **matcha** för den anpassade matchningskonfiguration du har angett.

10. Välj **kör** på sidan **matcha** för att starta matchningsprocessen och att konfigurationen av anpassade matchningar börjar gälla. Alla regler som matchas av systemet åsidosätts av konfigurationsuppsättningen.

11. När matchningen är slutförd kan du kontrollera entiteten **ConflationMatchPair** för att bekräfta att åsidosättningarna tillämpas i de sammanslagningens matchningar.

## <a name="next-step"></a>Nästa steg

När matchningsprocessen för minst ett matchningspar har slutförts kan du åtgärda eventuella motstridiga data genom att gå igenom ämnet [**sammanslå**](merge-entities.md).
