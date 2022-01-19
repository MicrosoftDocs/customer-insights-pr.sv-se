---
title: Semantisk analys för kundfeedback
description: Lär dig hur du använder en modell för attitydanalys på kundfeedback i Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951091"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analysera sentiment i kundfeedback (förhandsversion)

Kunderna förväntar sig produkter, tjänster och erfarenheter av hög kvalitet nuförtiden. Särskilt kunder som delar med sig av sin feedback. Det är mycket svårt för organisationer att analysera en ökande volym data utan att minska precisionen och öka arbetskostnaden. Dynamics 365 Customer Insights innehåller en modell för attitydanalys för kundfeedback som gör det möjligt för organisationer att analysera sina data bättre och till en lägre kostnad.

Med attitydanalys kan du identifiera kundsentiment och affärsaspekter som möjligheter till förbättringar. Med Customer Insights-funktionen kan du förstå vad som fungerar bra och vad du behöver åtgärda. Fokusera på de mest relevanta och genomslagskraftiga affärsområdena för att förbättra upplevelsen för dina kunder. I slutändan kan det hjälpa dig att driva affärsåtgärder som möjliggör erfarenheter som resulterar i hög kundnöjdhet och lojalitet.

## <a name="overview"></a>Översikt

Med funktionen för attitydanalys genereras två härledda insikter per kund-ID. Med en sentimentpoäng (mellan -5 och 5) och en lista över tillämpliga affärsaspekter (affärsområden) kan du få en bättre förståelse av kundernas feedback. 

Denna information kan hjälpa dig att uppnå följande resultat: 
- Få en översikt över kundsentiment mot ett varumärke eller en organisation
- Identifiera kunder med negativa sentiment för att fokusera kampanjer och åtaganden och optimera för högre avkastning  
- Identifiera affärsaspekter med problem som påpekats av kunder  
- Segmentera kunder utifrån deras inställning och kör anpassade kampanjer med riktade åtgärder för försäljning, marknadsföring och support
- Optimera affärsverksamheten genom att åtgärda problem som kunderna har nämnt
- Uppmärksamma affärsaspekter som går bra och uppmärksamma nöjda kunder genom lojalitets- och kampanjprogram

För att säkerställa att du kan betrodda resultat från dessa modeller ger vi detaljerad information om hur modeller fattar beslut. Du får en lista med ord som påverkade modellens beslut att tilldela kommentarer i feedback en viss sentimentpoäng eller affärsaspekt.  

Vi använder två **modeller för bearbetning av naturligt språk (NLP)**: Den första tilldelar varje feedbackkommentar en sentimentpoäng. Den andra modellen kopplar varje feedback till alla tillämpliga affärsaspekter. Modellen är utbildad i offentliga data från källor i sociala medier, återförsäljning, restaurang, konsumentprodukter och branscher.    
  
- Fördefinierade affärsaspekter som modellen kan associera med feedbackdata är:
-   Kontohantering
-   Utcheckning och betalning
-   Kundsupport
-   Upphämtning i butik
-   Förpackningsleverans och hämtning
-   Förbeställning
-   Pris
-   Sekretess och säkerhet
-   Erbjudanden och förmåner
-   Kvitto och garanti
-   Returnera växel och annullera
-   Orderuppfyllandets precision
-   Webbplats/appkvalitet

> [!NOTE]
> För tillfället har vi bara stöd för sentimentanalyser på feedback från engelska kunder. Vi kommer att stödja fler språk i framtiden. Om feedback på andra språk överförs kommer modellen fortfarande att returnera resultat. Resultaten blir dock inte korrekta. 

## <a name="prerequisites"></a>Förutsättningar

Sentimentanalys baseras på textfeedbackdata som har gått igenom [föreningsprocessen för data](data-unification.md). Vi rekommenderar att du [konfigurerar dina entiteter för feedbackdata som entiteter för aktivitetstyper](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (feedbacktyp) i förväg. 

Om du vill konfigurera en modell för attitydanalys måste du ha minst [Bidragsgivarbehörigheter](permissions.md).

Customer Insights kan bearbeta upp till 10 miljoner feedbackposter för en enskild modellkörning. Modellen kan analysera feedbackkommentarer på upp till 128 ord. Om en feedbackkommentar är längre beaktas bara de första 128 sökorden i analysen.

### <a name="data-requirements"></a>Datakrav
  
Följande dataattribut krävs:
- Unified Customer ID (UCID) för att matcha poster för textfeedbackdata till en enskild kund. Detta ID är ett resultat av [föreningsprocessen för data](data-unification.md).
- Feedback-ID
- Feedback tidsstämpel
- Feedbacktext   

> [!TIP]
> Attitydanalys kräver textfeedback från kunderna. Det går bara att konfigurera en entitet för feedback för tillfället. Om det finns flera entiteter för feedback kan du ändra dem i Power Query innan datainmatning börjar.

## <a name="configure-a-sentiment-analysis"></a>Konfigurera en attitydanalys 

1. I Customer Insights, gå till **Intelligens** > **Prediktioner**.

1. I panelen **Attitydanalys för kund**, välj **Använd modell**.

1. I rutan **Attitydanalys för kund (förhandsversion)**, välj **Komma igång**.

1. I steget **Modellnamn** ange ett **Namn** för analysen. 

1. Ange **Namn på utdataenhet för affärsaspekt** och **Namn på entitetsutdata för sentimentpoäng**, välj sedan **Nästa**.

1. I **Obligatoriska data**, välj **Lägg till data**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Lägg till dataflöde i modellen för attitydanalys.":::

1. I fönstret **Lägg till data**, välj den semantiska typen **Feedback** från listan.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurationssteg för att välja feedbackaktiviteter för attitydanalys.":::

1. Välj de aktiviteter du vill använda för denna attitydanalys och välj sedan **Nästa**.
 
1. Mappa attributen i dina data till modellattributen. Välj **Spara** för att tillämpa dina val. 

1. Du ser status för datamappning. Fortsätt genom att klicka på **Nästa**. 

1. I steget **Granska modellinformationen** verifierar du konfigurationen av attitydanalys. Du kan gå tillbaka till valfri del av prediktionskonfigurationen. Välj **Spara och kör** för att starta analysen. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Granska steget för sentimentmodellen som visar alla konfigurerade objekt.":::

1. Välj **Klar** om du vill lämna konfigurationsupplevelsen. Processen kan ta flera timmar att slutföra beroende på mängden data som används. 

## <a name="review-analysis-status"></a>Granska analysstatus

1.  Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.
2.  Välj den prediktion du vill granska.
- **Förutsägelsens namn**: Namnet på förutsägelsen som angavs när den skapades.
- **Förutsägelsetyp**: Den modelltyp som används för förutsägelse.
- **Utdataentitet**: Namnet på den entitet där utdata för förutsägelsen ska lagras. Gå till **Data** > **Entiteter** för att söka efter entiteten med detta namn.
- **Förutsagt fält**: Det här fältet fylls endast i för vissa typer av förutsägelser och används inte i förutsägelser av kundens livstidsvärde.
- **Status**: Status för förutsägelsekörningen.
  - **Köade**: Förutsägelse väntar på att andra processer ska slutföras.
  - **Uppdatera**: Förutsägelse körs för närvarande för att skapa resultat som ska flöda till utdataentiteten.
  - **Misslyckades**: Förutsägelsekörningen misslyckades. Granska loggar för mer information.
  - **Lyckades**: Förutsägelsen har slutförts. Välj Vy under de vertikala ellipserna om du vill granska förutsägelseresultat.
- **Redigerad**: Det datum då konfigurationen för förutsägelsen ändrades.
- **Senast uppdaterad**: Datumet då prediktion uppdaterade resultaten i utdataentiteten.

## <a name="manage-sentiment-analysis"></a>Hantera attitydanalys

Du kan optimera, felsöka, uppdatera eller ta bort prediktioner. Granska en användbarhetsrapport för indata för att ta reda på hur du gör en prediktion snabbare och mer tillförlitlig. Mer information finns i [Hantera förutsägelser](manage-predictions.md).

## <a name="review-analysis-results"></a>Granska analysresultat
 
1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**. 
1. Välj namnet på den prediktion du vill granska resultat för. I det här fallet väljer du den attitydanalys du vill granska. 

### <a name="summary-tab"></a>Fliken sammanfattning 

Det finns fyra primära dataavsnitt på resultatsidan. 

- **Genomsnittspoäng för sentiment**: Gör det lättare att förstå det allmänna sentimentet för alla kunder. Sentimentpoäng är grupperade i tre kategorier: 
  1.    Negativ (-5 > 2)
  2.    Neutral (-1 > 1)
  3.    Positiv (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuell representation av den övergripande kundsentimentet.":::

- **Kunddistribution efter sentimentpoäng**: Kunderna kategoriseras till negativa, negativa och positiva grupper utifrån deras sentimentpoäng. Håll markören över staplarna i histogrammet om du vill visa antalet kunder och genomsnittspoäng för sentiment i varje grupp. Med hjälp av den här informationen kan du [skapa segment med kunder](segments.md) utifrån deras sentimentpoäng.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Stapeldiagram visar kundsentiment i de tre sentimentgrupperna.":::

- **Genomsnittlig sentimentpoäng över tid**: Kundsentiment kan ändras med tiden. Vi tillhandahåller trender i kundernas sentiment för dina datas tidsintervall. Med den här vyn kan du mäta hur reklamkampanjer, produktlanseringar eller andra tidsbundna reklamkampanjer påverkar kundernas sentiment. Visa diagrammet genom att välja ett år av intresse i listrutan. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historikdiagram med sentimentpoängen över tid representerad som en rad.":::
 
- **Sentiment i olika affärsaspekter**: I den här tabellen visas genomsnittsentimentet i olika affärsaspekter. Den kan hjälpa dig att mäta vilka aspekter av företaget som redan är viktiga kunder eller aspekter som kräver mer uppmärksamhet. Feedback-poster som inte anpassar sig till några affärsaspekter som stöds kategoriseras under **Annat**. Tabellen sorteras som standard i bokstavsordning. Du kan ändra sorteringen genom att välja en tabellrubrik.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista över affärsaspekter med associerade sentimentvärde och antalet kunder som nämnt det.":::
 
  Välj namnet på en affärsaspekt om du vill se ytterligare information om hur en affärsaspekt identifieras av modellen. Det finns två delar i den här rutan: 

  - **Ord med påverkan**: Visar de vanligaste orden som påverkade AI-modellens identifiering av en affärsaspekt i kundfeedback. 
    Vis **a olika ord**: Du kan ta med ord från original feedbackdata från kunderna. Funktionen är normalt inte aktiv.  Stötande ordmaskering drivs av en AI-modell och kanske inte upptäcker alla stötande ord. Vi fortsätter att iterera och träna klassificeraren för optimal prestanda. Om du upptäcker ett stötande ord som inte filtrerades som förväntat, låt oss veta. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista över förord som används för att visa eller dölja ord.":::
 
  - **Exempel på feedback**: Visar faktiska feedbackposter i dina data. Ord färgkodas efter hur de påverkar identifieringen av en affärsaspekt. 


### <a name="influential-words-analysis-tab"></a>Fliken för inflytelserik ordanalys

Det finns tre avsnitt med ytterligare information som förklarar hur sentimentmodellen fungerar.
  
1. **Översta ord som bidrar till en positiv sentiment**: Visar de översta ord som används för att identifiera AI-modellens identifiering av positiva sentiment i kundfeedback.  
2. **Översta ord som bidrar till en negativ sentiment**: Visar de översta ord som används för att identifiera AI-modellens identifiering av negativa sentiment i kundfeedback.  
3. **Exempel på feedback**: Visar faktiska feedbackposter, en med en negativ sentiment och en med en positiv inställning. Ord i feedbackposterna anpassas efter hur de bidrar till den tilldelade sentimentpoängen. Ord som bidrar till en positiv sentimentpoäng blir gröna. Ord som bidrar till en negativ poäng är rödmarkerade.
   Välj **Mer information** för att ladda fler feedbackprover som ger mer information och sammanhang för hur sentimentmodellen fungerar.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exempel på sentimentanalys på feedback från kunder.":::
 
Vis **a olika ord**: Du kan ta med ord från original feedbackdata från kunderna. Funktionen är normalt inte aktiv.  Stötande ordmaskering drivs av en AI-modell och kanske inte upptäcker alla stötande ord. Vi fortsätter att iterera och träna klassificeraren för optimal prestanda. Om du upptäcker ett stötande ord som inte filtrerades som förväntat, låt oss veta. 

## <a name="act-on-analysis-results"></a>Aktiva på analysresultat

Du kan enkelt börja skapa nya kundsegment från resultatsidan för sentimentanalys genom att välja **Skapa segment** överst på modellens resultatsida.

:::image type="content" source="media/create-segment-model.png" alt-text="Kommandofält med alternativ på prediktionsmodeller.":::
 
## <a name="potential-bias"></a>Potentiella problem

Som med alla funktioner som använder prediktiv artificiell intelligens, bör du vara medveten om potentiell fördom i den data du använder för att förutsäga kundernas sentiment. Om du till exempel bara samlar in feedback digitalt kan du sakna feedback från kunder som primärt gör affärer med dig personligen, vilket kan påverka utdata för funktionen.

Eftersom den här funktionen använder automatiserade metoder för att utvärdera data och göra prognoser utifrån dessa data, kan den därför användas som en profilmetod, eftersom den termen definieras av allmänna dataskyddsförordningen ("GDPR"). Din användning av den här funktionen för att bearbeta data kan omfattas av GDPR eller andra lagar och förordningar. Du är ansvarig för att se till att din användning av Dynamics 365 Customer Insights, inklusive sentimentanalys, följer alla tillämpliga lagar och förordningar, inklusive lagar som gäller sekretess, personliga data, sekretess och dataskydd.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

