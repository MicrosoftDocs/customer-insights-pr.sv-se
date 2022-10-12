---
title: Analysera sentiment i kundfeedback (förhandsversion)
description: Lär dig hur du använder en modell för attitydanalys på kundfeedback i Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610488"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analysera sentiment i kundfeedback (förhandsversion)

Med attitydanalys kan du identifiera kundsentiment och affärsaspekter som möjligheter till förbättringar. Med Customer Insights-funktionen kan du förstå vad som fungerar bra och vad du behöver åtgärda. Det kan hjälpa dig att driva affärsåtgärder som möjliggör erfarenheter som resulterar i hög kundnöjdhet och lojalitet.

## <a name="overview"></a>Översikt

Med funktionen för attitydanalys genereras två härledda insikter per kund-ID. Med en sentimentpoäng (mellan -5 och 5) och en lista över tillämpliga affärsaspekter (affärsområden) kan du få en bättre förståelse av kundernas feedback.

Denna analys hjälper dig:
- Få en översikt över kundsentiment mot ett varumärke eller en organisation
- Identifiera kunder med negativa sentiment för att fokusera kampanjer och åtaganden och optimera för högre avkastning  
- Identifiera affärsaspekter med problem som påpekats av kunder  
- Segmentera kunder utifrån deras inställning och kör anpassade kampanjer med riktade åtgärder för försäljning, marknadsföring och support
- Optimera affärsverksamheten genom att åtgärda problem som kunderna har nämnt
- Uppmärksamma affärsaspekter som går bra och uppmärksamma nöjda kunder genom lojalitets- och kampanjprogram

Modellen ger en lista med ord som påverkade modellens beslut att tilldela kommentarer i feedback en viss sentimentpoäng eller affärsaspekt.  

Vi använder två **modeller för bearbetning av naturligt språk (NLP)**: Den första tilldelar varje feedbackkommentar en sentimentpoäng. Den andra modellen kopplar varje feedback till alla tillämpliga affärsaspekter. Modellen är utbildad i offentliga data från källor i sociala medier, återförsäljning, restaurang, konsumentprodukter och branscher.
  
Fördefinierade affärsaspekter som modellen kan associera med feedbackdata är:
- Kontohantering
- Utcheckning och betalning
- Kundsupport
- Upphämtning i butik
- Förpackningsleverans och hämtning
- Förbeställning
- Pris
- Sekretess och säkerhet
- Erbjudanden och förmåner
- Kvitto och garanti
- Returnera växel och annullera
- Orderuppfyllandets precision
- Webbplats/appkvalitet

> [!NOTE]
> För tillfället har vi bara stöd för sentimentanalyser på feedback från engelska kunder. Vi kommer att stödja fler språk i framtiden. Om feedback på andra språk överförs kommer modellen fortfarande att returnera resultat. Resultaten blir dock inte korrekta.

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md)
- [Enhetlig](data-unification.md) feedbackinformation för text. Vi rekommenderar att du [konfigurerar dina entiteter för feedbackdata som entiteter för aktivitetstyper](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (feedbacktyp).
- Unified Customer ID (UCID) från dataförening för att matcha poster för textfeedbackdata till en enskild kund.
- Feedback-ID
- Feedback tidsstämpel
- Feedbacktext

Customer Insights kan bearbeta upp till 10 miljoner feedbackposter för en enskild modellkörning. Modellen kan analysera feedbackkommentarer på upp till 128 ord. Om en feedbackkommentar är längre beaktas bara de första 128 sökorden i analysen.

> [!NOTE]
> Det går bara att konfigurera en entitet för feedback. Om det finns flera entiteter för feedback kan du kombinera dem i Power Query före datainmatningen.

## <a name="configure-a-sentiment-analysis"></a>Konfigurera en attitydanalys

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Attitydanalys för kund (förhandsversion)**.

1. Välj **Komma igång**.

1. Ge analysen ett **Namn** och ge **Namn på utdataenhet för affärsaspekt** och **Namn på entitetsutdata för sentimentpoäng**.

1. Välj **Nästa**.

1. Välj **Lägg till data** för **Kundfeedback**.

1. Välj typen av semantisk aktivitet **Feedback** som innehåller dina feedbackdata. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurationssteg för att välja feedbackaktiviteter för attitydanalys.":::

1. Välj de aktiviteter du vill använda för denna attitydanalys och välj sedan **Nästa**.

1. Mappa attributen i dina data till modellattributen. 

1. Välj **Spara**.

1. Välj **Nästa**. Steget **Granska och kör** visar en sammanfattning av konfigurationen och ger en chans att göra ändringar innan du skapar analysen.

1. Välj **Redigera** på något av stegen för att granska och göra eventuella ändringar.

1. Om du är nöjd med dina val, välj **Spara och kör** för att starta modellen. Välj **Klar**. Fliken **Mina prognoser** visas när prediktion skapas. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Visa analysresultat

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Mina förutsägelser**, välj den förutsägelse du vill visa.

Det finns två flikar med resultat.

### <a name="sumary-tab"></a>Fliken Sammanfattning

Det finns fyra primära dataavsnitt på resultatsidan.

- **Genomsnittspoäng för sentiment**: Sentimentpoäng gör det enklare att förstå det allmänna sentimentet för alla kunder.
  - **Negativ** (-5 > 2)
  - **Neutral** (-1 > 1)
  - **Positiv** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuell representation av den övergripande kundsentimentet.":::

- **Kunddistribution efter sentimentpoäng**: Kunderna kategoriseras till negativa, negativa och positiva grupper utifrån deras sentimentpoäng. Håll markören över staplarna i histogrammet om du vill visa antalet kunder och genomsnittspoäng för sentiment i varje grupp. Med hjälp av den här informationen kan du [skapa segment med kunder](prediction-based-segment.md) utifrån deras sentimentpoäng.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Stapeldiagram visar kundsentiment i de tre sentimentgrupperna.":::

- **Genomsnittlig sentimentpoäng över tid**: Kundsentiment kan ändras med tiden. Vi tillhandahåller trender i kundernas sentiment för dina datas tidsintervall. Med den här vyn kan du mäta hur reklamkampanjer, produktlanseringar eller andra tidsbundna reklamkampanjer påverkar kundernas sentiment. Visa diagrammet genom att välja ett år av intresse i listrutan.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historikdiagram med sentimentpoängen över tid representerad som en rad.":::

- **Sentiment i olika affärsaspekter**: Med hjälp av genomsnitt sentiment i olika affärsaspekter kan du mäta vilka aspekter av företaget som redan förser kunder med kunder eller där det krävs mer uppmärksamhet. Feedback-poster som inte anpassar sig till några affärsaspekter som stöds kategoriseras under **Annat**. Sortera data genom att markera valfri kolumn.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista över affärsaspekter med associerade sentimentvärde och antalet kunder som nämnt det.":::

  Välj namnet på en affärsaspekt om du vill se hur en affärsaspekt identifieras av modellen:

  - **Ord med påverkan**: De vanligaste orden som påverkade AI-modellens identifiering av en affärsaspekt i kundfeedback.
    Vis **a olika ord**: Du kan ta med ord från original feedbackdata från kunderna. Funktionen är normalt inte aktiv.  Stötande ordmaskering drivs av en AI-modell och kanske inte upptäcker alla stötande ord. Om du upptäcker ett stötande ord som inte filtrerades som förväntat, låt oss veta.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista över förord som används för att visa eller dölja ord.":::

  - **Exempel på feedback**: Faktiska feedbackposter i dina data. Ord färgkodas efter hur de påverkar identifieringen av en affärsaspekt.

### <a name="influential-words-analysis-tab"></a>Fliken för inflytelserik ordanalys

Det finns tre avsnitt med ytterligare information som förklarar hur sentimentmodellen fungerar.
  
- **Översta ord som bidrar till en positiv sentiment**: Översta ord som används för att identifiera AI-modellens identifiering av positiva sentiment i kundfeedback.  

- **Översta ord som bidrar till en negativ sentiment**: Översta ord som används för att identifiera AI-modellens identifiering av negativa sentiment i kundfeedback.

- **Exempel på feedback**: Faktiska feedbackposter, en med en negativ sentiment och en med en positiv inställning. Ord i feedbackposterna anpassas efter hur de bidrar till den tilldelade sentimentpoängen. Ord som bidrar till en positiv sentimentpoäng blir gröna. Ord som bidrar till en negativ poäng är rödmarkerade.
   Välj **Se fler** om du vill ladda upp fler exempel på feedback.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exempel på sentimentanalys på feedback från kunder.":::

Vis **a olika ord**: Du kan ta med ord från original feedbackdata från kunderna. Funktionen är normalt inte aktiv.  Stötande ordmaskering drivs av en AI-modell och kanske inte upptäcker alla stötande ord. Om du upptäcker ett stötande ord som inte filtrerades som förväntat, låt oss veta.

## <a name="act-on-analysis-results"></a>Aktiva på analysresultat

För att skapa nya kundsegment från resultatsidan för sentimentanalys genom att välja **Skapa segment** överst på modellens resultatsida.

## <a name="potential-bias"></a>Potentiella problem

Som med alla funktioner som använder prediktiv artificiell intelligens, bör du vara medveten om potentiell fördom i den data du använder för att förutsäga kundernas sentiment. Om du till exempel bara samlar in feedback digitalt kan du sakna feedback från kunder som primärt gör affärer med dig personligen, vilket kan påverka utdata för funktionen.

Eftersom den här funktionen använder automatiserade metoder för att utvärdera data och göra prognoser utifrån dessa data, kan den därför användas som en profilmetod, eftersom den termen definieras av allmänna dataskyddsförordningen ("GDPR"). Din användning av den här funktionen för att bearbeta data kan omfattas av GDPR eller andra lagar och förordningar. Du är ansvarig för att se till att din användning av Dynamics 365 Customer Insights, inklusive sentimentanalys, följer alla tillämpliga lagar och förordningar, inklusive lagar som gäller sekretess, personliga data, sekretess och dataskydd.

[!INCLUDE [footer-include](includes/footer-banner.md)]

