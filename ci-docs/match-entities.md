---
title: Matchningsvillkor för dataförening
description: Matcha entiteter för att skapa enhetliga kundprofiler.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: e3e4e37d5b4c9caf2520a789d5f78ef33b491793
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139725"
---
# <a name="match-conditions-for-data-unification"></a>Matchningsvillkor för dataförening

I det här steget definieras matchningsordningen och reglerna för matchning mellan entiteter. För det här steget krävs minst två entiteter.

> [!NOTE]
> När du har skapat matchningsvillkoren och valt **Nästa** kan du inte ta bort en markerad entitet eller ett markerat attribut. Välj **Tillbaka** om det behövs om du vill granska de valda entiteterna och attributen innan du går vidare.

## <a name="include-enriched-entities-preview"></a>Inkludera utökade entiteter (förhandsgranskning)

Om du har förädlat entiteter på datakälla nivå för att förbättra resultaten markerar du dem. Mer information: [Berikande för datakällor](data-sources-enrichment.md). Om du har markerat utökade entiteter på sidan **Dubblettposter** behöver du inte markera dem igen.

1. På sidan **Matchande villkor**, välj **Använd berikade entiteter** högst upp på sidan.

1. Från rutan **Använd berikade entiteter** välj en eller flera berikade entiteter.

1. Välj **Utfört**.

## <a name="specify-the-match-order"></a>Ange matchningsordningen

Varje matchning kombinerar två eller flera entiteter till en enda konsoliderad entitet. Samtidigt behålls de unika kundposterna. Matchningsordningen anger i vilken ordning systemet försöker matcha posterna.

> [!IMPORTANT]
> Den första entiteten i listan kallas den primära entiteten. Den primära entiteten fungerar som bas för dina enhetliga profiler datauppsättning. Ytterligare entiteter som är markerade läggs till i entiteten.
>
> Viktiga överväganden:
>
> - Välj entiteten med de mest fullständiga och tillförlitliga profildata om kunderna som primär entitet.
> - Välj den entitet som har flera attribut som delas av andra entiteter (t.ex. namn, telefonnummer eller e-postadress) som primär entitet.

1. På sidan **Matchande villkor** pilarna för att flytta upp och ner för att flytta enheterna i den ordning du vill, eller dra och släpp dem. Välj till exempel **Contacts:eCommerce** som primär entitet och **CustomerLoyalty:Loyalty** som sekundär entitet.

1. Om du vill att alla poster i entiteten är en unik kund oavsett om en matchning hittas, välj **Inkludera alla poster**. Alla poster i entiteten som inte matchar med poster i andra entiteter ingår i den enhetliga profilen. Poster som inte har någon matchning kallas singleton-instans.
  
Den primära entiteten *Contacts:eCommerce* matchas med nästa enhet *CustomerLoyalty:Loyalty*. Datauppsättningen som resulterar från det första matchningssteget matchas med följande enhet om du har fler än två enheter.

:::image type="content" source="media/m3_match.png" alt-text="Skärmbild av den valda matchningsordningen för entiteterna." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definiera regler för matchningspar

Matchningsregler anger den logik som ett specifikt par med entiteter ska matchas mot. En regel består av ett eller flera villkor.

Varningen bredvid ett entitetsnamn innebär att ingen matchningsregel har definierats för ett matchningspar.

1. Välj **Lägg till regel** för ett enhetspar om du vill definiera matchningsregler.

1. I fönstret **Lägg till regel** konfigurera villkoren för regeln.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Skärmbild av rutan Lägg till regel.":::

   - **Välj entitet/fält (första raden)**: Välj en relaterad entitet och ett attribut för att ange en postegenskap som troligen är unik för en kund. Till exempel ett telefonnummer eller en e-postadress. Undvik att matcha efter aktivitetstypattribut. Ett köp-ID hittar troligen ingen matchning i andra posttyper.

   - **Välj entitet/fält (andra raden)**: Välj ett attribut som är relaterat till attributet för entiteten som anges på den första raden.

   - **Normalisera**: Välj bland följande normaliseringsalternativ för de valda attributen.
     - **Siffror**: Konverterar andra numeriska system, t.ex. romerska tecken till arabiska siffror. *VIII* blir *8*.
     - **Symboler**: Tar bort alla symboler och specialtecken. *Head&Shoulder* blir *HeadShoulder*.
     - **Text till gemener**: Konverterar alla tecken till gemener. *ALLA VERSALER och rubriker* blir *alla versaler och rubriker*.
     - **Typ (telefon, namn, adress, organisation)**: Standardiserar namn, titlar, telefonnummer, adresser och organisationer.
     - **Unicode till ASCII**: Konverterar unicode-notation till ASCII-tecken. */u00B2* blir *2*.
     - **Tomt utrymme**: Tar bort alla blanksteg. *Hej   världen* blir *Hejvärlden*.

   - **Precision**: Ange vilken precisionsnivå som ska tillämpas för detta villkor.
     - **Grundläggande**: Välj mellan *Låg (30 %)*, *Medel (60 %)*, *Hög (80 %)* och *Exakt (100 %)*. Välj **Exakt** om du endast vill matcha poster som matchar 100 procent.
     - **Anpassad**: Ange en procentandel som posterna måste matcha. Systemet matchar endast poster som passerar tröskelvärdet.

   - **Namn**: Namn för regeln.

1. Om du endast vill matcha entiteter om attributen uppfyller flera villkor **Lägg till** > **Lägg till villkor** om du vill lägga till fler villkor i en matchningsregel. Villkoren är kopplade till en logisk OCH-operator och körs därför endast om alla villkor uppfylls.

1. Alternativt kan du överväga avancerade alternativ som [undantag](#add-exceptions-to-a-rule) eller [anpassade matchningsvillkor](#specify-custom-match-conditions).

1. Välj **Klar** för att slutföra regeln.

1. Alternativt kan du [lägga till fler regler](#add-rules-to-a-match-pair).

1. Klicka på **Nästa**.

> [!div class="nextstepaction"]
> [Nästa steg: Förena fält](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Lägga till regler till ett matchningspar

Matchningsregler representerar uppsättningar av villkor. Om du vill matcha entiteter efter villkor baserat på flera attribut lägger du till fler regler.

1. Välj **Lägg till regel** för den entitet där du vill lägga till regler.

1. Följ anvisningarna i [Definiera regler för matchningspar](#define-rules-for-match-pairs).

> [!NOTE]
> Regelordningen är viktig. Den matchande algoritmen försöker matcha en viss kundpost utifrån den första regeln och fortsätter endast till den andra regeln om inga matchningar identifierades med den första regeln.

## <a name="advanced-options"></a>Avancerade alternativ

### <a name="add-exceptions-to-a-rule"></a>Lägga till undantag för en regel

I de flesta fall leder entitetsmatchningen till unika kundprofiler med konsoliderade data. Om du vill hantera undantagsfall med falskt positiva och falskt negativa resultat dynamiskt kan du definiera undantag för en matchningsregel. Undantag tillämpas efter bearbetning av matchningsreglerna och undviker att matcha alla poster som uppfyller undantagsvillkoren.

Till exempel, om din matchningsregel kombinerar efternamn, stad och födelsedatum, identifierar systemet tvillingar med samma efternamn som bor i samma stad som samma profil. Du kan ange ett undantag som inte matchar profilerna om de förnamn i entiteterna du kombinerar inte är samma.

1. I fönstret **Redigera regel** välj **Lägg till** > **Lägg till undantag**.

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

1. Välj **Kund**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Knappen Anpassa":::

1. Välj **Anpassad typ** och välj **Hämta mall**. Du måste ha en separat mall för varje matchningsalternativ.

1. Öppna den hämtade mallfilen och fyll i informationen. Mallen innehåller fält som används för att ange entiteten och de primär nyckelvärden som ska användas i den anpassade matchningen. Om du till exempel vill att primärnyckeln *12345* från entiteten *Försäljning* alltid matchar primärnyckeln *34567* från entiteten *Kontakt*, fyller du i mallen:
    - Entitet1: Försäljning
    - Enhetsnyckel1: 12345
    - Entitet2: Kontakt
    - Enhetsnyckel2: 34567

   Samma mallfil kan ange anpassade matchningsposter från flera entiteter.

   Om du vill ange anpassad matchning för deduplicering för en entitet anger du samma entitet som både Entitet 1 och Entitet 2 och anger de olika primärnyckelvärdena.

1. Spara mallfilen när du har lagt till alla åsidosättningar.

1. Gå till **Data** > **Datakällor** och matar in mallfilerna som nya entiteter.

1. När du har överfört filerna väljer du alternativet **Anpassa** igen. Välj obligatoriska entiteter på den nedrullningsbara menyn och välj **Klart**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Skärmbild av dialogrutan för åsidosättning för ett anpassat matchningsscenario.":::

1. Användning av den anpassade matchningen beror på matchningsalternativet som du vill använda.

   - Gå till nästa steg för **Matcha alltid** eller **Matcha aldrig**.
   - För **Hoppa över** eller **Aliasmappning**, välj **Redigera** på en befintlig matchningsregel eller skapa en ny regel. Välj alternativet **Anpassad åsidosättning** eller **Aliasmappning** i listrutan Normaliseringar och välj **Klart**.

1. Välj **Klar** i den **anpassade** rutan om du vill använda den anpassade matchningskonfigurationen.

> [!div class="nextstepaction"]
> [Nästa steg: Förena fält](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
