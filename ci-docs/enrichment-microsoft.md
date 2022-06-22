---
title: Utöka kundprofiler med data om företagsintressen och intressen från Microsoft
description: Använd tillverkarspecifika data från Microsoft för att utöka dina kunddata med samhörigheter och Share of Voice.
ms.date: 03/02/2022
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
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953787"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Utöka kundprofiler med samhörigheter och Share of Voice (förhandsversion)

Använd tillverkarspecifika data från Microsoft för att utöka dina kunddata med varumärkesaffiniteter, intresseaffiniteter och Share of Voice (SoV). Dessa samhörigheter och SoV baseras på data från personer med demografi som liknar dina kunder. Denna information hjälper dig att bättre förstå och segmentera dina kunder baserat på deras affinitet eller SoV till specifika varumärken och intressen.

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

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

   - Om du vill konfigurera varumärkessamhörigheter och SoV-berikning välj **Utöka mina data** på panelen **Varumärken**.

   - Om du vill konfigurera intressesamhörigheter och SoV-berikning välj **Utöka mina data** på panelen **Intressen**.

   > [!div class="mx-imgBorder"]
   > ![Paneler för varumärken och intressen.](media/BrandsInterest-tile-Hub.png "Paneler för varumärken och intressen")

1. Gå igenom översikten och välj sedan **Nästa**.

1. Om du vill ändra ditt land eller din region väljer du **Ändra** bredvid **Land/region**. I rutan **Inställningar för land/region**, välj en [land eller en region som stöds](#supported-countriesregions) och välj **Tillämpa**.

   > [!NOTE]
   > När du väljer dina ega märken ger systemet förslag utifrån valt land eller vald region. När du väljer en bransch får du de mest relevanta märkena eller intressena utifrån valt land eller vald region.

1. Välj upp till fem varumärken eller intressen med ett eller båda av dessa alternativ:

   - **Bransch**: Välj din bransch i listrutan och välj sedan bland de främsta varumärkena eller intressena för den branschen.
   - **Välj ditt eget**: Ange ett varumärke eller intresse som är relevant för din organisation och välj sedan bland matchande förslag. Om vi inte visar ett varumärke eller intresse som du letar efter kan du skicka feedback med hjälp av **föreslå** länk.

1. Välj **Nästa** och granska standardinställningarna för utökande åtgärder och uppdatera dem efter behov.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skärmbild av fönstret med inställningar för berikning.":::

1. Välj **Nästa**.

1. Välj **Kunddatauppsättning** och välj profilen eller segmentet du vill berika med data från Microsoft. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Välj **Nästa**.

1. Mappa dina fält från entiteten enhetlig kund till Microsoft-data.

   > [!NOTE]
   > Minst födelsedatum eller könsattribut krävs. Land/region och minst Ort (och delstat/provins) eller Postnummer krävs. Vi rekommenderar att datum för spridning konverteras till DateTime-typ under datainmatning. Det kan också vara en sträng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-format "åååå-mm-mm" eller "åååå-mm-ddTHH:mm:ss".

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett namn för anrikningen. **Utdataentitetens namn** väljs automatiskt.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Sidan för intressegranskning och namn.":::

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

   När profiler utökas utökar vi alla kundprofiler för vilka vi får data för valda varumärken och intressen, inklusive profiler som inte finns i valt land eller vald region. Om du till exempel valde Tyskland utökar vi profiler i USA om det finns tillgängliga data för valda tillverkare och intressen i USA.

## <a name="enrichment-results"></a>Berikningsresultat

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Förhandsgranskning av resultatet efter det att förbättringsprocessen har körts.":::

Resultaten omfattar **Tillhörighetsnivå** eller diagram **Share of Voice**.

Entiteterna som skapats från anrikningarna listas under gruppen **Berikning** i **Data** > **Entiteter**. Berikad data för varumärken går till entiteterna **BrandAffinityFromMicrosoft** och **BrandShareOfVoiceFromMicrosoft**. Data för intressen finns i entiteterna **InterestAffinityFromMicrosoft** och **InterestShareOfVosoftMicrosoft**. 

## <a name="see-enrichment-data-on-the-customer-card"></a>Visa utökande data på kundkortet

Varumärke och intresse SoV kan också visas på enskilda kundkort. Gå till **kunder** och välj en kundprofil. På kundkorten hittar du diagram för varumärket eller kundens intresse SoV baserat på personer i den kundens demografiska profil.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundkort med förbättrade data.":::

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
