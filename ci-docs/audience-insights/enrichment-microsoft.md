---
title: Utöka kundprofiler med data från Microsoft
description: Använd tillverkarspecifika data från Microsoft för att utöka dina kunddata med samhörigheter och Share of Voice.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 77972475c9a448186cee3b1b62eeda7b1996edfc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355351"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Utöka kundprofiler med samhörigheter och Share of Voice (förhandsversion)

Använd tillverkarspecifika data från Microsoft för att utöka dina kunddata med varumärkesaffiniteter, intresseaffiniteter och Share of Voice (SoV). Dessa samhörigheter och SoV baseras på data från personer med demografi som liknar dina kunder. Denna information hjälper dig att bättre förstå och segmentera dina kunder baserat på deras affinitet eller SoV till specifika varumärken och intressen.

I målgruppsinsikter går du till **Data** > **Berikning** för att [konfigurera och visa berikningar](enrichment-hub.md).

Om du vill konfigurera varumärkessamhörigheter och SoV-berikning går du till fliken **Upptäck** och väljer **Utöka mina data** på panelen **Varumärken**.

Om du vill konfigurera intressesamhörigheter och SoV-berikning går du till fliken **Upptäck** och väljer **Utöka mina data** på panelen **Intressen**.

   > [!div class="mx-imgBorder"]
   > ![Paneler för varumärken och intressen.](media/BrandsInterest-tile-Hub.png "Paneler för varumärken och intressen")

## <a name="how-we-determine-affinities-and-sov"></a>Så här avgör vi samhörigheter och SoV

Vi använder Microsofts onlinesökningsdata för att hitta samhörigheter och SoV för varumärken och intressen i olika demografiska segment (definierade efter ålder, kön eller plats). Sökvolym online för ett varumärke eller intresse utgör grunden för att fastställa samhörighet eller SoV. Men var och en ger ett annat perspektiv för att förstå dina kunder.

- Samhörighet kan jämföras med demografisk segment. Du kan använda den här informationen för att identifiera målgruppssegment som har den högsta tillhörigheten för ett visst varumärke eller intresse jämfört med andra segment.

- Share of voice är en jämförelse mellan dina valda varumärken eller intressen. Med hjälp av den här informationen kan du identifiera vilket varumärke eller intresse som har den högsta Share Of Voice i ett visst målgruppssegment, jämfört med andra varumärken eller intressen du valt.

## <a name="affinity-level-and-score"></a>Tillhörighetsnivå och poäng

I varje utökad kundprofil tillhandahåller vi två relaterade värden – tillhörighetsnivå och tillhörighetspoäng. Dessa värden hjälper dig att avgöra hur starkt tillhörigheten är för den profilens demografiska segment, för ett varumärke eller intresse, jämfört med andra demografiska segment.

*Tillhörighetsnivå* består av fyra nivåer och *tillhörighetspoäng* beräknas på en skala med 100 poäng som mappas till tillhörighetsnivåerna.


|Tillhörighetsnivå |Tillhörighetspoäng  |
|---------|---------|
|Mycket högt     | 85–100       |
|Högt     | 70–84        |
|Medium     | 35–69        |
|Lågt     | 1–34        |

Beroende på vilken granularitet du vill använda för att mäta tillhörigheten kan du använda antingen tillhörighetsnivå eller poäng. Med tillhörighetspoäng får du mer exakt kontroll.

## <a name="share-of-voice-sov"></a>Share of voice (SoV)

Vi beräknar SoV på en 100-punktsskala. Den totala SoV för alla varumärken eller intressen för varje berikad kundprofil blir 100. Till skillnad från samhörigheter är SoV relativt till de intressen du väljer. SoV-värdena för Microsoft kan exempelvis vara annorlunda om de valda värdena är (Microsoft, "GitHub") och (Microsoft, LinkedIn).

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Vi stöder för närvarande följande alternativ för land: Australien, Kanada (engelska), Frankrike, Tyskland, Storbritannien och USA (engelska).

Om du vill välja ett land eller en region öppnar du **Varumärkesberikning** eller **Intresseberikning** och **Ändra** bredvid **Land/Region**. I fönstret **inställningar för land/region** väljer du ett alternativ och väljer **tillämpa**.

### <a name="implications-related-to-country-selection"></a>Effekter relaterade till val av land

- När [du väljer dina ega märken](#define-your-brands-or-interests) ger systemet förslag utifrån valt land eller vald region.

- När [du väljer en bransch](#define-your-brands-or-interests) får du de mest relevanta märkena eller intressena utifrån valt land eller vald region.

- När [profiler utökas](#refresh-enrichment) utökar vi alla kundprofiler för vilka vi får data för valda varumärken och intressen, inklusive profiler som inte finns i valt land eller vald region. Om du till exempel valde Tyskland utökar vi profiler i USA om det finns tillgängliga data för valda tillverkare och intressen i USA.

## <a name="configure-enrichment"></a>Konfigurera berikning

En guidad upplevelse hjälper dig genom konfigurationen av berikningar. 

### <a name="define-your-brands-or-interests"></a>Definiera dina varumärken eller intressen

Välj upp till fem varumärken eller intressen med ett eller båda av dessa alternativ:

- **Bransch**: Välj din bransch i listrutan och välj sedan bland de främsta varumärkena eller intressena för den branschen.
- **Välj ditt eget**: Ange ett varumärke eller intresse som är relevant för din organisation och välj sedan bland matchande förslag. Om vi inte visar ett varumärke eller intresse som du letar efter kan du skicka feedback med hjälp av **föreslå** länk.

### <a name="review-enrichment-preferences"></a>Granska inställningar för berikning

Gå igenom standardinställningarna för berikning och uppdatera dem efter behov.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skärmbild av fönstret med inställningar för berikning.":::

### <a name="select-entity-to-enrich"></a>Välj en entitet att utöka

Välj **Berikad entitet** och välj den datauppsättning du vill berika med data från Microsoft. Du kan välja entiteten Kund för att utöka alla dina kundprofiler eller välja en segmentsentitet för att endast utöka kundprofiler i det segmentet.

### <a name="map-your-fields"></a>Mappa dina fält

Mappa fält från en enhetlig kundentitet och definiera det demografiska segment som du vill att systemet ska använda för att utöka kunddata. Mappa land/region och åtminstone attributen Födelsedatum eller Kön. Du måste också mappa minst en av Ort (och Region) eller Postnummer. Välj **redigera** om du vill definiera mappningen av fälten och välj **Tillämpa** när du är klar. Välj **Spara** för att slutföra fältmappningen.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Berikningsresultat

När du har kört berikningsprocessen går du till **Mina berikningar** för att granska det totala antalet utökade kunder och en uppdelning av varumärken eller intressen ii de utökade kundprofilerna.

:::image type="content" source="media/my-enrichments.png" alt-text="Förhandsgranskning av resultatet efter det att förbättringsprocessen har körts.":::

Du hittar ett diagram med antalet utökade kundprofiler över tid och förhandsgranskningar av de utökade entiteterna. Granska berikade data genom att välja diagrammen **Visa mer** i **Samhörighetsnivån** eller **Share of Voice**. Berikad data för varumärken går till entiteterna **BrandAffinityFromMicrosoft** och **BrandShareOfVoiceFromMicrosoft**. Data för intressen finns i entiteterna **InterestAffinityFromMicrosoft** och **InterestShareOfVosoftMicrosoft**.  Du hittar också de här entiteterna i gruppen **Utökande** i **Data** > **Entiteter**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Visa utökande data på kundkortet

Varumärke och intresse SoV kan också visas på enskilda kundkort. Gå till **kunder** och välj en kundprofil. På kundkorten hittar du diagram för varumärket eller kundens intresse SoV baserat på personer i den kundens demografiska profil.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundkort med förbättrade data.":::

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
