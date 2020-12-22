---
title: Berika kundprofiler med Microsoft Graph
description: Använd patentskyddade data från Microsoft Graph för att utöka dina kunddata med varumärkes- och intressetillhörigheter .
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407073"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Utöka kundprofiler med varumärkes- och intressetillhörighet (förhandsversion)

Använd patentskyddade data från Microsoft Graph för att utöka dina kunddata med varumärkes- och intressetillhörigheter . Dessa intressetillhörigheter bestäms utifrån data från personer som har liknande demografiska kunder. Med hjälp av den här informationen kan du bättre förstå och segmentera dina kunder utifrån deras tillhörigheter till särskilda varumärken och intressen.

I målgruppsinsikter går du till **Data** > **Berikning** för att [konfigurera och visa berikningar](enrichment-hub.md).

Om du vill konfigurera berikning för varumärkestillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Varumärken**.

Om du vill konfigurera berikning av intressetillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Intressen**.

   > [!div class="mx-imgBorder"]
   > ![Paneler för varumärken och intressen](media/BrandsInterest-tile-Hub.png "Paneler för varumärken och intressen")

## <a name="about-microsoft-graph"></a>Om Microsoft Graph

Vi använder online-sökdata från Microsoft Graph för att hitta tillhörigheter för varumärken och intressen i olika demografiska segment (bestämda efter ålder, kön eller plats). Om du söker online efter ett varumärke eller en ränta bestäms hur mycket tillhörighet som ett demografiskt segment ska jämföras med andra segment, det vill säga det varumärket.

[Läs mer om Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Tillhörighetspoäng och förtroende

**Tillhörighetspoängen** beräknas på en skala på 100 punkter med 100 som representerar det segment som har den högsta tillhörigheten för ett varumärke eller intresse.

**Tillhörighetsförtroendet** beräknas också på en 100-punkts skala. Den anger systemets konfidensnivå som ett segment har en tillhörighetsnivå för varumärket eller räntan. Konfidensnivå bygger på storleken på segmentet och i segmentets granularitet. Segmentstorleken bestäms av mängden data som det aktuella segmentet har. Segmentgranularitet bestäms av hur många attribut (ålder, kön, plats) som är tillgängliga i en profil.

Vi normaliserar inte poängen för datauppsättning. Därför kanske du inte ser alla möjliga tillhörighetsvärden för datauppsättning. Det kan till exempel finnas ingen berikad kundprofil med tillhörighet 100 i dina data. Det är möjligt om det inte finns några kunder i det demografiska segmentet som gav resultatet 100 för ett visst varumärke eller en viss ränta.

> [!TIP]
> När [skapar segment](segments.md) med tillhörighetspoäng granskar du fördelningen av tillhörighetsresultat för datauppsättning innan du bestämmer dig för lämpliga poängtröskelvärden. Ett tillhörighetspoäng på 10 kan till exempel betraktas som signifikant i ett datauppsättning som har högst 25 poäng för ett visst varumärke eller intresse.

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Vi stöder för närvarande följande alternativ för land: Australien, Kanada (engelska), Frankrike, Tyskland, Storbritannien och USA (engelska).

Om du vill välja ett land öppnar du **varumärken** eller **intressen** och väljer **ändra** bredvid **land/region**. I fönstret **inställningar för land/region** väljer du ett alternativ och väljer **tillämpa**.

### <a name="implications-related-to-country-selection"></a>Effekter relaterade till val av land

- När du [väljer egna varumärken](#define-your-brands-or-interests) ger vi förslag utifrån det valda landet/den regionen.

- När [du väljer en bransch](#define-your-brands-or-interests) kommer vi att identifiera de mest relevanta varumärken eller intressen som baseras på det valda landet/regionen.

- När du [mappar fälten](#map-your-fields) och fältet land inte är mappat används Microsoft Graph-data från det valda landet för att utöka dina kundprofiler. Vi använder också den här markeringen för att utöka dina kundprofiler som inte har tillgängliga lands- eller regionsdata.

- När [du utökar profiler](#refresh-enrichment) utökas alla kundprofiler som vi har Microsoft Graph-data för och som är tillgängliga för valda varumärken och intressen, inklusive profiler som inte finns i det valda landet/regionen. Om du till exempel valde Tyskland utökas profiler som finns i USA om Microsoft Graph-data är tillgängliga för de valda varumärkena och intressena i USA.

## <a name="configure-enrichment"></a>Konfigurera berikning

Att konfigurera berikning av varumärken eller intressen består av två steg:

### <a name="define-your-brands-or-interests"></a>Definiera dina varumärken eller intressen

Välj ett av följande alternativ:

- **Bransch**: Systemet identifierar de främsta varumärkena och intressena som är relevanta för din bransch, och berikar dina kunddata med dem.
- **Välj en egen**: Välj upp till fem objekt i en lista med varumärken eller intressen som är mest relevanta för organisationen.

Om du vill lägga till ett varumärke eller ett intresse anger du det i inmatningsområdet för att få förslag utifrån matchande termer. Om vi inte visar ett varumärke eller intresse som du letar efter kan du skicka feedback med hjälp av **föreslå** länk.

### <a name="map-your-fields"></a>Mappa dina fält

Mappa fält från entiteten enhetlig kund till minst två attribut för att definiera det demografiska segment som du vill att vi ska använda för att utöka kunddata. Välj **redigera** om du vill definiera mappningen av fälten och välj **Tillämpa** när du är klar. Välj **Spara** för att slutföra fältmappningen.

Följande format och värden stöds är värden inte skiftlägeskänsliga:

- **Födelsedatum**: Vi rekommenderar att födelsedatumet konverteras till typen DateTime under datainmatning. Det kan också vara en sträng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatet "åååå-MM-dd" eller "åååå-MM-ddTHH:mm:ssZ".
- **Kön**: man, kvinna, okänd
- **Postnummer**: femsiffriga postnummer för oss, standard postnummer i övriga
- **Ort**: Ortens namn på engelska
- **Region**: en förkortning på två bokstäver för USA och Kanada. Två eller tre bokstavsförkortningar för Australien. Gäller inte för Frankrike, Tyskland eller Storbritannien.
- **Land/region**:

  - USA: Amerikas förenta stater, Förenta staterna, USA, US och Amerika
  - CA: Kanada, CA
  - GB: Förenade kungariket, Storbritannien, GB, Förenade kungariket av Storbritannien och Nordirland, Förenade kungariket av Storbritannien
  - AU: Australien, AU, Australiska statsförbundet
  - FR: Frankrike, FR, Republiken Frankrike
  - DE: Tyskland, tyska, Deutschland, Allemagne, DE, Förbundsrepubliken Tyskland

## <a name="refresh-enrichment"></a>Uppdatera berikning

Kör berikningen när du har konfigurerat varumärken, intressen och fältmappningen för demografiska mål. Starta processen genom att välja **Kör** på konfigurationssidan för varumärket eller intresset. Du kan även låta systemet köra anrikningen automatiskt som en del av en schemalagd uppdatering.
Beroende på storleken på kundens data kan det ta flera minuter innan en anrikning har slutförts.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="enrichment-results"></a>Berikningsresultat

När du har kört berikningsprocessen går du till **Mina berikningar** för att granska det totala antalet berikade kunder och en uppdelning av varumärken eller intressen ii de berikade kundprofilerna.

:::image type="content" source="media/my-enrichments.png" alt-text="Förhandsgranskning av resultatet efter att processen har körts":::

Granska utökad data genom att välja **Visa utökad data** i diagrammet. Berikad data för varumärken skickas till entiteten **BrandAffinityFromMicrosoft**. Data för intressen finns i entiteten **InterestAffinityFromMicrosoft**. Du hittar också de här entiteterna i gruppen **Berikande** i **Data** > **Entiteter**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Visa berikande data på kundkortet

Varumärkes- och räntetillhörigheter kan också visas på enskilda kundkort. Gå till **kunder** och välj en kundprofil. På kundkortet hittar du diagram för de varumärken eller intressen som personer i den kundens demografiska profil har tillhörighet för.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundkort med berikad data":::

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.
