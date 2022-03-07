---
title: Berika kundprofiler med data från Microsoft
description: Använd tillverkarspecifika data från Microsoft för att berika kunddata med intresse och varumärke.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3b10fb23cca03ed918aa7fd46478b568d5ebbf1a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555513"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Utöka kundprofiler med varumärkes- och intressetillhörighet (förhandsversion)

Använd tillverkarspecifika data från Microsoft för att berika kunddata med intresse och varumärke. Dessa samhörigheter baseras på data från personer med demografiska egenskaper som liknar dina kunders. Med hjälp av den här informationen kan du bättre förstå och segmentera dina kunder utifrån deras tillhörigheter till särskilda varumärken och intressen.

I målgruppsinsikter går du till **Data** > **Berikning** för att [konfigurera och visa berikningar](enrichment-hub.md).

Om du vill konfigurera berikning för varumärkestillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Varumärken**.

Om du vill konfigurera berikning av intressetillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Intressen**.

   > [!div class="mx-imgBorder"]
   > ![Paneler för varumärken och intressen.](media/BrandsInterest-tile-Hub.png "Paneler för varumärken och intressen")

## <a name="how-we-determine-affinities"></a>Så här avgör vi intresse

Vi använder Microsofts onlinesökningsdata för att hitta intressegrupper och intressen i olika demografiska segment (definierade efter ålder, kön eller plats). Om du söker online efter ett varumärke eller en ränta bestäms hur mycket tillhörighet som ett demografiskt segment ska jämföras med andra segment, det vill säga det varumärket.

## <a name="affinity-level-and-score"></a>Tillhörighetsnivå och poäng

I varje berikad kundprofil tillhandahåller vi två relaterade värden – tillhörighetsnivå och tillhörighetspoäng. Dessa värden hjälper dig att avgöra hur starkt tillhörigheten är för den profilens demografiska segment, för ett varumärke eller intresse, jämfört med andra demografiska segment.

*Tillhörighetsnivå* består av fyra nivåer och *tillhörighetspoäng* beräknas på en skala med 100 poäng som mappas till tillhörighetsnivåerna.


|Tillhörighetsnivå |Tillhörighetspoäng  |
|---------|---------|
|Mycket högt     | 85–100       |
|Högt     | 70–84        |
|Medium     | 35–69        |
|Lågt     | 1–34        |

Beroende på vilken granularitet du vill använda för att mäta tillhörigheten kan du använda antingen tillhörighetsnivå eller poäng. Med tillhörighetspoäng får du mer exakt kontroll.

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Vi stöder för närvarande följande alternativ för land: Australien, Kanada (engelska), Frankrike, Tyskland, Storbritannien och USA (engelska).

Om du vill välja ett land eller en region öppnar du **Varumärkesberikning** eller **Intresseberikning** och **Ändra** bredvid **Land/Region**. I fönstret **inställningar för land/region** väljer du ett alternativ och väljer **tillämpa**.

### <a name="implications-related-to-country-selection"></a>Effekter relaterade till val av land

- När [du väljer dina ega märken](#define-your-brands-or-interests) ger systemet förslag utifrån valt land eller vald region.

- När [du väljer en bransch](#define-your-brands-or-interests) får du de mest relevanta märkena eller intressena utifrån valt land eller vald region.

- När [profiler berikas](#refresh-enrichment) berikar vi alla kundprofiler för vilka vi får data för valda varumärken och intressen, inklusive profiler som inte finns i valt land eller vald region. Om du till exempel valde Tyskland utökar vi profiler i USA om det finns tillgängliga data för valda tillverkare och intressen i USA.

## <a name="configure-enrichment"></a>Konfigurera berikning

En guidad upplevelse hjälper dig genom konfigurationen av berikningar. 

### <a name="define-your-brands-or-interests"></a>Definiera dina varumärken eller intressen

Välj upp till fem varumärken eller intressen med ett eller båda av dessa alternativ:

- **Bransch**: Välj din bransch i listrutan och välj sedan bland de främsta varumärkena eller intressena för den branschen.
- **Välj ditt eget**: Ange ett varumärke eller intresse som är relevant för din organisation och välj sedan bland matchande förslag. Om vi inte visar ett varumärke eller intresse som du letar efter kan du skicka feedback med hjälp av **föreslå** länk.

### <a name="review-enrichment-preferences"></a>Granska inställningar för berikning

Gå igenom standardinställningarna för berikning och uppdatera dem efter behov.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skärmbild av fönstret med inställningar för berikning.":::

### <a name="select-entity-to-enrich"></a>Välj en entitet att berika

Välj **Berikad entitet** och välj den datauppsättning du vill berika med företagsdata från Microsoft. Du kan välja entiteten Kund för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.

### <a name="map-your-fields"></a>Mappa dina fält

Mappa fält från en enhetlig kundentitet och definiera det demografiska segment som du vill att systemet ska använda för att berika kunddata. Mappa land/region och åtminstone attributen Födelsedatum eller Kön. Du måste också mappa minst en av Ort (och Region) eller Postnummer. Välj **redigera** om du vill definiera mappningen av fälten och välj **Tillämpa** när du är klar. Välj **Spara** för att slutföra fältmappningen.

Följande format och värden stöds (värden är inte skiftlägeskänsliga):

- **Födelsedatum**: Vi rekommenderar att födelsedatumet konverteras till typen DateTime under datainmatning. Det kan också vara en sträng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-format "åååå-mm-mm" eller "åååå-mm-ddTHH:mm:ss".
- **Kön**: man, kvinna, okänd.
- **Postnummer**: Femsiffriga postnummer för USA, standardnummer för alla andra platser.
- **Ort**: Ortens namn på engelska.
- **Region**: en förkortning på två bokstäver för USA och Kanada. Förkortningar med två eller tre bokstäver för Australien. Gäller inte för Frankrike, Tyskland eller Storbritannien.
- **Land/region**:

  - USA: Amerikas förenta stater, Förenta staterna, USA, US och Amerika
  - CA: Kanada, CA
  - GB: Förenade kungariket, Storbritannien, GB, Förenade kungariket av Storbritannien och Nordirland, Förenade kungariket av Storbritannien
  - AU: Australien, AU, Australiska Statsförbundet
  - FR: Frankrike, FR, Republiken Frankrike
  - DE: Tyskland, tyska, Deutschland, Allemagne, DE, Förbundsrepubliken Tyskland

## <a name="review-and-name-the-enrichment"></a>Granska och ge berikningen ett namn

Slutligen får du granska informationen och ange ett namn för berikning.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Sidan för intressegranskning och namn.":::

## <a name="refresh-enrichment"></a>Uppdatera berikning

Kör berikningen när du har konfigurerat varumärken, intressen och fältmappningen för demografiska mål. Starta processen genom att välja **Kör** på konfigurationssidan för varumärket eller intresset. Du kan även låta systemet köra anrikningen automatiskt som en del av en schemalagd uppdatering.

Beroende på storleken på kundens data kan det ta flera minuter innan en anrikning har slutförts.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Visa detaljerad information** för en av uppgifterna för jobbet hittar du ytterligare information: bearbetningstid, senaste bearbetningsdatum samt alla fel och varningar som hör till uppgiften.

## <a name="enrichment-results"></a>Berikningsresultat

När du har kört berikningsprocessen går du till **Mina berikningar** för att granska det totala antalet berikade kunder och en uppdelning av varumärken eller intressen ii de berikade kundprofilerna.

:::image type="content" source="media/my-enrichments.png" alt-text="Förhandsgranskning av resultatet efter det att förbättringsprocessen har körts.":::

Granska utökad data genom att välja **Visa utökad data** i diagrammet. Berikad data för varumärken skickas till entiteten **BrandAffinityFromMicrosoft**. Data för intressen finns i entiteten **InterestAffinityFromMicrosoft**. Du hittar också de här entiteterna i gruppen **Berikande** i **Data** > **Entiteter**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Visa berikande data på kundkortet

Varumärkes- och räntetillhörigheter kan också visas på enskilda kundkort. Gå till **kunder** och välj en kundprofil. På kundkortet hittar du diagram för de varumärken eller intressen som personer i den kundens demografiska profil har tillhörighet för.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundkort med förbättrade data.":::

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md) och [mått](measures.md) och till och med [exportera datan](export-destinations.md) för att leverera anpassade upplevelser till dina kunder.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
