---
title: Segment som föreslås genom maskininlärning
description: Låt maskininlärning hjälpa dig att hitta nya och intressant segment baserat på kundattribut.
ms.date: 02/01/2021
ms.reviewer: jimsonc
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 54655d57f4f0f723b497fe47891fd397ccb9dbf4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268248"
---
# <a name="suggested-segments-preview"></a>Föreslagna segment (förhandsversion)

Identifiera intressanta segment för dina kunder med hjälp av en AI-modell. Maskininlärningsfunktionen föreslår segment baserat på mått eller kundattribut. Den kan förbättra KPI:er eller ge dig en bättre förståelse av attributens påverkan på andra attribut. 

> [!NOTE]
> Funktionen för föreslagna segment använder automatiserade metoder för att utvärdera data och göra förutsägelser utifrån dessa data och har därför möjlighet att användas som metod för profilering, eftersom den termen definieras av allmänna dataskyddsförordningen ("GDPR"). Din användning av den här funktionen för att bearbeta data kan omfattas av GDPR eller andra lagar och förordningar. Du ansvarar för att din användning av Dynamics 365 Customer Insights, inklusive denna funktion, följer alla tillämpliga lagar och förordningar, inklusive lagar som rör sekretess, personuppgifter, biometriska data, dataskydd och sekretess för kommunikation.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Sidan Förslag på segment i Customer Insights som visar information om ett förslag i ett sidofönster.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Förslag på segment för att förbättra KPI:er

Som användare av målgruppsinsikter har du sannolikt en serie [skapade mått](measures.md) som hjälper dig att spåra nyckeltal (KPI:er). Det är viktigt att du förstår hur vissa attribut påverkar KPI:et när du skapar segment och kör en riktad kampanj.   
Du spårar till exempel ett mått som kallas *TotalSpendPerCustomer*. Som ett företag skulle du vilja se det här antalet växa. Om du väljer ett mått som primärt attribut kan du välja vilka attribut du vill utvärdera för påverkan. Låt säga *medlemsskapsnivå*, *medlemsskapsperiod* och *arbete*. Customer Insights kan sedan föreslå ett segment som informerar dig om vem som har den största påverkan på måttet. Till exempel *revisorer* som är *Guld*-medlemmar och som har varit lojala till ditt företag i *minst fem år* är den största påverkaren för *TotalSpendPerCustomer*. Du får en beräknad segmentstorlek för varje förslag. Du kan använda den här informationen om du vill skapa kampanjer för en särskild målgrupp.

## <a name="understand-what-influences-a-customer-attribute"></a>Förstå vad som påverkar ett kundattribut

Du kan välja ett kundattribut i stället för ett mått som det primära attributet. Baserat på ditt val av påverkande attribut skapar AI-modellen ett antal förslag som visar hur de valda attributen påverkar det primära attributet.   
Du kan till exempel välja *Rewards-medlem (Ja/Nej)* som primärt attribut. *Fast anställning*, *Arbete* och *Antal supportärenden* anges som andra påverkande attribut. AI-modellen kan föreslå segment som pekar på att de flesta Rewards-medlemmar är IT-experter som har haft fast anställning i mer än två år. Ett annat förslag skulle kunna peka på att revisorer som har haft fast anställning i mer än ett år och har färre än tre supportärenden är Rewards-medlemmar. 

## <a name="artificial-intelligence-usage"></a>Användning av artificiell intelligens

Med hjälp av det primära attributet och påverkande attribut föreslår en beslutsträdsalgoritm intressanta segment. Förslagen bygger på regler eller mönster som har hämtats av AI-algoritmen. Endast segment som skiljer sig markant från genomsnittspopulationen visas som förslag. Jämförelsen med genomsnittspopulationen baseras på det valda måttet eller det primära attributet.

### <a name="responsible-ai"></a>Ansvarsfull AI

Med hjälp av segment som föreslås kan du välja attribut för att skapa nya segment och bearbeta de data du väljer. När du väljer attribut, inklusive känsliga attribut som etnicitet, sexuell läggning eller kön, måste du se till att du kan och bör bearbeta dessa data. Du är ansvarig för att följa alla lagar som gäller för din organisation och följa organisationens principer och sekretesspolicyer.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Olika resultat för primära attribut med kategoriska och numeriska värden

Segmentförslag skiljer sig om du väljer ett numeriskt attribut eller ett kategoriskt attribut som primärt attribut. Värden i ett kategoriskt attribut innehåller två eller flera kategorier eller typer. Ett numeriskt attribut innehåller kvantitativt innehåll och har ett mått associerat till det.

Med ett numeriskt attribut som *årsinkomst* eller *medlemsskapsperiod* som primärt attribut föreslår systemet segment som har ett högre eller lägre medelvärde för det numeriska attributet i jämförelse med alla kunder.

Ett kategoriskt attribut som *kundnöjdhet* som primärt attribut leder till föreslagna segment som har en högre eller lägre andel av kunder som tillhör en viss kategori i jämförelse med andelen av alla kunder som tillhör samma kategori. Exempel: *Kundnöjdhet* väljs som primärt attribut och består av tre kategorier (*Låg*, *Medel* och *Hög*). För varje kategori föreslås segment som har en betydligt högre eller lägre andel kunder som tillhör kategorin i jämförelse med andelen av alla kunder i samma kategori. Om 22 % av alla kunder har *Hög* nöjdhet föreslås endast segment som har en betydligt högre eller lägre andel kunder med *Hög* nöjdhet i jämförelse med 22 % för den kategorin. På samma sätt föreslås segment för var och en av de andra kategorierna (*Låg* och *Medel*) om de är statistiskt betydelsefulla.

> [!NOTE]
> För tillfället har vi bara stöd för primära kategoriska attribut som har upp till 10 kategorier. Om du vill visa segmentförslag som bygger på ett primärt attribut med mer än 10 kategorier rekommenderar vi att du grupperar några av kategorierna så att antalet kategorier blir 10 eller färre. Den här begränsningen gäller endast primära attribut. För påverkande kategoriska attribut har vi för närvarande stöd för maximalt 100 kategorier.

## <a name="generate-suggested-segments"></a>Generera föreslagna segment

1. Gå till **Segment**.

1. Välj fliken **Förslag (förhandsversion)**.

1. Välj **Få nya förslag** för att starta den guidade upplevelsen.

1. Välj ett mått eller ett kundattribut som det primära attributet och välj **Nästa**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Välja det primära attributet för förslag i de föreslagna segmenten.":::

1. Välj de påverkande attributen och välj **Spara**.
   
   > [!TIP]
   > Om du väljer flera påverkande attribut ökar chansen för att utvärdera hur de påverkar det primära attributet. Ta inte med attribut som inte påverkar det primära attributet. Om till exempel alla kunder är från ett visst land ska du inte ta med attributet *land* eftersom det inte påverkar utdata.

1. Beroende på antalet kundprofiler och valda attribut kan det ta några minuter att bearbeta de valda attributen. 

## <a name="view-details-of-a-suggested-segment"></a>Visa information om föreslaget segment

När AI-modellen har genererat förslagen hittar du dem i **Segment** > **Förslag (förhandsgranskning)**.
 
Välj ett föreslaget segment om du vill granska informationen om det förslaget, inklusive en jämförelse av genomsnittsvärdet och antalet segmentmedlemmar. Du kan också granska attributvärdena eller reglerna som AI-modellen har lärt sig för att föreslå det valda segmentet.

## <a name="save-a-suggestion-as-a-segment"></a>Spara ett förslag som ett segment

1. Gå till **Segment** > **Förslag (förhandsgranskning)**.

1. Välj det segment som du vill spara. 

1. I sidofönstret väljer du **Spara som segment**. 

1. När du har sparat segmentet visas det i listan över segment under fliken **Alla segment**. Det kan nu [uppdateras, redigeras eller raderas precis som andra segment](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Uppdatera eller redigera en uppsättning förslag

1. Gå till **Segment** > **Förslag (förhandsgranskning)**.

1. Välj **Uppdatera förslag** för att uppdatera förslagen samtidigt som du behåller konfigurerade attribut. Eller välj **Redigera attribut** för att ändra de konfigurerade attributen. Systemet kör AI-modellen på nytt, genererar segmentförslag utifrån senaste data och ersätter de aktuella förslagen.

## <a name="limitations"></a>Begränsningar

1. Beräknad matchning för segmentstorlek: Om du väljer ett primärt attribut som innehåller tomma värden kan det påverka den beräknade segmentstorleken i segmentförslagen. När du sparar ett sådant segment kan den faktiska segmentstorleken vara annorlunda än den ursprungliga uppskattningen.
 
2. Primära attribut av boolesk typ fungerar inte: För närvarande har vi endast stöd för strängtyper och numeriska typer av data som primärt attribut.

3. De föreslagna segmenten är inte tillräckligt olika: Tänk på att de valda attributen och fördelningen av värdena för dessa attribut påverkar resultatet. Du kan ändra dina påverkande attribut eller till och med det primära attributet om du vill få olika resultat.



[!INCLUDE[footer-include](../includes/footer-banner.md)]