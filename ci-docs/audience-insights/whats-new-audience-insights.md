---
title: Nya och kommande funktioner
description: Information om nya funktioner, förbättringar och felkorrigeringar.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988942"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Vad är nytt i funktionen målgruppsinsikter i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi är glada över att kunna meddela våra senaste uppdateringar! Denna artikel sammanfattar funktioner för allmänt tillgänglig förhandsversion, förbättringar av allmän tillgänglighet och funktionsuppdateringar. Om du vill se de långsiktiga funktionsplanerna, se [utgivningsplaner för Dynamics 365 och Power Platform](/dynamics365/release-plans/).

Vi lanserar uppdateringar en region i taget. Vissa regioner kan se funktioner före andra. Om inget annat anges behöver du inte vidta några åtgärder så uppdateras appen automatiskt utan driftsavbrott.

> [!TIP]
> Skicka in och rösta på funktioner som efterfrågas och produktförslag går du till [Dynamics 365-programmets idéportal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="april-2021-updates"></a>Uppdatering april 2021

Uppdateringarna i april 2021 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="data-unification"></a>Dataförening
 
- **Förbättrad koppling av data**    
  
   Nu får vi en bättre användarupplevelse när det gäller att sammanfoga konfigurationen av datakonfigureringen. Ändringarna omfattar intuitiv ordning på de kopplade fälten och detaljerad statistik om kombinerade fält och enskilda fält.

- **Entitetsordning och konfiguration av alla källposter i entiteten Kund**  
      
   Du kan nu ordna om och ta bort enheter från en befintlig sammanslagningsplan i dataföreningsprocessen. Det ger flexibilitet att ändra ordningen på entiteterna i matchningsprocessen efter företagets behov. Dessutom aktiverar vi att alla icke-matchande poster inkluderas i den slutliga entiteten *Kund*, där de kan definiera sin kundprofil datauppsättning definition.

### <a name="enrichments"></a>Berikningar

 - **Ny berikning: utökade adresser**    
  
   Vi är glada för att kunna införa ett nytt utökande för att förbättra adresser i dina kunddata. Adresser i dina data kan vara oadresserade, ofullständiga eller felaktiga. Denna funktion använder Microsoft-modeller kan du normalisera och utöka adresserna i formatet Common Data Model för bättre precision och insikter.
 
   Mer information finns i [Utöka kundprofiler med förbättrade adresser](enrichment-enhanced-addresses.md).

- **Guidad konfigurationsupplevelse för utökande**    
  
   Vi förde fram konfigurationsupplevelsen för förbättringar med en enkel, guidad upplevelse. Nu har du en tydlig steg-för-steg-process för att skapa och redigera berikningar.
 
   Dessutom separerade vi konfigurationen av anslutningar för tillägg från tredje part för att göra det möjligt att använda samma anslutning vid flera tillägg. Endast administratörer kan konfigurera nya anslutningar, men de skapade anslutningarna är alltid tillgängliga för både administratörer och deltagare.    

   Mer information finns i [Anslutningsöversikt](connections.md).

- **Flera berikningar av samma typ**    
  
   Nu tillåter vi användare att skapa och hantera flera berikningar av samma berikningstyp. Nu kan du till exempel skapa två separata adressberikningar för att utöka två olika kundsegment. Gränser gäller för hur många berikningar av samma typ som kan skapas och varierar beroende på berikningstyp.
  
   Mer information finns i [berikning av kundprofiler](enrichment-hub.md).

## <a name="march-2021-updates"></a>Uppdateringar i mars 2021

Uppdateringarna i mars 2021 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="activities"></a>Aktiviteter

- **Aktivitetsguiden och typer av aktivitetstyper**

   Vi har nu förbättrat och uppdaterat vår aktivitetsmappningserfarenhet för att vägleda och förenkla skapandet av aktivitetsmappning. I den här nya upplevelsen får användarna en guidad upplevelse som hjälper dig att slutföra varje steg i processen. Vid aktivitetsmappningssteget kan användaren, förutom att välja bland många aktivitetstyper, välja att semantiskt mappa data för *Prenumeration* och/eller *SalesOrderLine* till branschstandardscheman, som kan användas för nedströmsförbrukning.   

   Mer information finns i [Kundaktiviteter](activities.md).

### <a name="data-ingestion"></a>Datainsamling

- **Anslut till lokala datakällor med Power Platform dataflöden och gateways** Vi ser fram till att kunna presentera förhandsgranskning av Power Platform dataflöden och lokal anslutning via gateways i Customer Insights med en associerad Power Platform eller Dataverse miljö. Alla nya datakällor som skapas i en Customer Insights-miljö med en länkad Dataverse-miljö kommer att standardinställas till Power Platform dataflöden och ta med lokal dataanslutning och en mängd anslutnings- och omvandlingsfunktioner.

### <a name="extensibility"></a>Utbyggbar

- **Exporter ordnade i anslutningar och exporter** Vi har bytt namn på sidan **Exportera destinationer** till **Anslutningar** och lagt till en separat sida för **Exporter**. Som en del av den här uppdateringen övergår vi befintlig export till par i en anslutning och en export med den anslutningen. Administratörerna har nu större tydlighet i fråga om utgående data på sidan **Anslutningar**. Alla användarroller har åtkomst till sidan **Export**, men bara administratörer kan välja att tillåta deltagare att redigera specifik export med delade anslutningar.     
  Mer information finns i [Översikt över anslutningar](connections.md) och [Exportöversikt](export-destinations.md).

- **Exportera segment till Campaign Monitor** Nu har exportmålen utökats till att omfatta Campaign Monitor. Nu kan du exportera segment från Customer Insights till listor med Campaign Monitor och använda dem som grund för dina marknadsföringskampanjer.    
   Mer information finns i [Exportera data till Campaign Monitor](export-campaign-monitor.md).

- **Exportera segment till Constant Contact** Nu har exportmålen utökats till att omfatta Constant Contact. Nu kan du exportera segment från Customer Insights till listor med Constant Contact och använda dem som grund för dina marknadsföringskampanjer.   
   Mer information finns i [Exportera data till Constant Contact](export-constant-contact.md).

- **Exportera segment till RollWorks** Nu har exportmålen utökats till att omfatta RollWorks. Nu kan du exportera segment från Customer Insights till listor med RollWorks och använda dem som grund för din B2B-reklam.    
   Mer information finns i [Exportera data till RollWorks](export-rollworks.md).

- **Exportera segment till Snapchat** Nu har exportmålen utökats till att omfatta Snapchat. Nu kan du exportera segment från Customer Insights till listor med Snapchat och använda dem som grund för din reklam.     
   Mer information finns i [Exportera data till Snapchat](export-snapchat.md).

### <a name="predictions"></a>Prediktioner

- **Använd produktfilter i rekommenderade produktrekommendationer** Vi har lagt till möjligheten att använda produktfilter i vår produktrekommendationsmodell. Nu kan du skapa en prediktion som endast använder en delmängd av dina produkter.    
   Mer information finns i [Konfigurera produktfilter](predict-product-recommendation.md#configure-product-filters).

- **Skapa segment utifrån modellprognoser** Vi har lagt till ett snabbt sätt att skapa segment med resultatet av en prediktionsmodell. På resultatsidan för modellen kan du enkelt skapa ett nytt segment genom att välja det nya alternativet **Skapa segment**.    
  Mer information finns i [Skapa ett segment utifrån en prediktion modell](prediction-based-segment.md).

- **Förklaringar för produktrekommendationer** Vi har lagt till information som förklarar de nyckelfaktorer som AI-modellen har lärt sig för att generera produktrekommendationer och i vilken grad dessa faktorer bidrar till produktrekommendationerna. Den här informationen läggs till i resultatskärmen för modellen.    
   Mer information finns i [Granska en förutsägelsestatus och resultat](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Uppdateringar i februari 2021

Uppdateringarna i februari 2021 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

#### <a name="extensibility"></a>Utbyggbar

- **Exportera segment till AdRoll**

  Vi har utökat våra exportmål för att inkludera AdRoll. Nu kan du exportera segment från Customer Insights till AdRoll-målgrupper och använda dem som baslinje för din annonsering. Mer information finns i [Anslutningsprogram för AdRoll](export-adroll.md).

#### <a name="segments"></a>Segment
 
- **Duplicera ett segment**
  
  Om du vill skapa ett nytt segment utifrån ett befintligt segment kan du nu duplicera ett segment och redigera det duplicerade segmentet för att förfina det ytterligare. 

- **Lägga till ytterligare attribut till ett segment**

  Nu kan du ta med attribut i ditt segment även om de här attributen inte är en del av kundprofilen. Du kan till exempel inkludera prenumerations-ID i ett segment även om det är en del av prenumerationsentiteten som har en M:1-relation med kundentiteten. Så länge attributet tillhör en entitet som relaterar till kundentiteten kan du nu ta med dessa attribut.  

#### <a name="predictions"></a>Prediktioner

- **Skapa prediktiva produktrekommendationer**

  Att förstå vad kunderna är intresserade av att köpa är ett av de första stegen för att förbättra affärsintäkterna och öka kundlojaliteten genom personlig anpassning och kontakt. Genom att tillhandahålla rekommendationer för produkter som inte är anpassade efter kundens intressen kan du skapa en känsla av avstånd mellan kunden och din verksamhet, och slutligen begränsa den övergripande potentiella omsättningen och upplevelsen för en kund. 

  Med hjälp av dina egna data kan du nu skapa prognoser för vilka produkter kunderna kommer att köpa i framtiden. Mer information finns i [Produktrekommendationsförutsägelse](predict-product-recommendation.md).

#### <a name="system-administration"></a>Systemadministration

- **Kopiera miljöstöd för fler typer av datakällor**

  Administratörer kan kopiera miljökonfigurationer till en ny miljö i samma organisation. Den här funktionen utökar funktionen för kopiering av miljön i fall där datakällor baserade på en Common Data Service-datasjö eller en Common Data Model-mapp används.

## <a name="january-2021-updates"></a>Uppdateringar januari 2021

Uppdateringarna i januari 2021 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

#### <a name="extensibility"></a>Utbyggbar

- **Utökade funktioner och förbättrade prestanda för SFTP-export** Du kan nu exportera alla utdataentiteter från Customer Insights till en SFTP-värd. Tidigare begränsades exporten till segmententiteter. Dessutom tillåter prestanda för SFTP-export mer datavolym på kortare tid, beroende på prestanda för din SFTP-värd.    
  Mer information finns i [Anslutningsprogram för SFTP (förhandsversion)](export-sftp.md).  

#### <a name="segments"></a>Segment

- **Segment som föreslås genom maskininlärning för att förbättra mått** Det finns ett nytt sätt att identifiera och skapa segment. Systemet använder en AI-modell för att föreslå segment som kan hjälpa till att förbättra KPI:et (måttet) som du redan spårar. Vi visar i vilken utsträckning attribut som du väljer för ett mått eller ett annat primärt attribut. Med hjälp av den här informationen kan du hitta potentiella affärsmöjligheter.    
  Mer information finns i [Föreslagna segment (förhandsversion)](suggested-segments.md).

#### <a name="data-unification"></a>Dataförening

- **Förbättrad matchningsupplevelse** I dataföreningsområdet uppdaterades matchningsupplevelsen. Du kan konfigurera och visa matchningsreglerna, inklusive detaljerad information om hur matchning fungerar. Det finns alternativ för att inaktivera en matchningsregel så att den inte längre är aktiv samtidigt som du behåller konfigurationen, drar och släpper matchningsregler med mera.
  För mer information se [Matcha entiteter](match-entities.md).

- **Dedupliceringsutdata från matchningsprocessen är tillgänglig som en entitet** Utdata från dedupliceringsprocessen från matchningsprocessen skrivs nu i en separat entitet för vidare analys. Entiteten består av fälten som används i dedupliceringsprocessen och den vinnande posten och motsvarande alternativa poster som slås samman med den vinnande posten.
  Mer information finns i [Dedupliceringsutdata som en entitet](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Systemadministration

- **Dela data sömlöst till Microsoft Dataverse** Du kan nu dela Customer Insights-utdata med Microsoft Dataverse-program med hjälp av Microsoft Dataverse-hanterad Data Lake. När du har kopplat en Dataverse-miljö till Customer Insights har du möjlighet att aktivera datadelning.
  Mer information finns i [Hantera miljöer](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]