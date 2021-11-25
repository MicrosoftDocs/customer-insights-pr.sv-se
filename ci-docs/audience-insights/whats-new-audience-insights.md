---
title: Nya och kommande funktioner
description: Information om nya funktioner, förbättringar och felkorrigeringar.
ms.date: 11/04/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: f7e2645e1608ea83b5d3af1073a5d6f6e97eec8f
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753139"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Vad är nytt i funktionen målgruppsinsikter i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi är glada över att kunna meddela våra senaste uppdateringar! Denna artikel sammanfattar funktioner för allmänt tillgänglig förhandsversion, förbättringar av allmän tillgänglighet och funktionsuppdateringar. Om du vill se de långsiktiga funktionsplanerna, se [utgivningsplaner för Dynamics 365 och Power Platform](/dynamics365/release-plans/).

Vi lanserar uppdateringar en region i taget. Vissa regioner kan se funktioner före andra. Om inget annat anges behöver du inte vidta några åtgärder så uppdateras appen automatiskt utan driftsavbrott.

> [!TIP]
> Skicka in och rösta på funktioner som efterfrågas och produktförslag går du till [Dynamics 365-programmets idéportal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="october-2021-updates"></a>Uppdateringar i oktober 2021

Uppdateringarna i oktober 2021 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="b-to-b"></a>B2B

Från och med oktober 2021 kan du arbeta med affärskonton och deras relaterade kontakter i Customer Insights. Tidigare har appen främst skräddarsytts för enskilda användare. Flera funktionsområden har uppdaterats för att stödja B2B-scenarier utöver den nya miljötypen. En översikt över B2B-funktioner som stöds finns i [Arbeta med affärskonton i målgruppinsikter](work-with-business-accounts.md).

I följande avsnitt framhävs några av de viktigaste områdena som har anpassats för att stödja verksamhetskonton och enskilda åtgärder.

#### <a name="export-segments-based-on-business-accounts"></a>Exportera segment utifrån affärskonton

Alla segmentexporter i målgruppinsikter är tillgängliga när det gäller affärskonton. De flesta segmentexporter kräver extra konfigurations- och [kontaktinformation som projiceras](segment-builder.md#create-a-new-segment) i de underliggande segmenten för att kunna användas för affärskonton. Mer information finns i [Exportera segments](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Använd export av LinkedIn-annonser med affärskonton

Exporten av LinkedIn-annonser kan nu göras tillgänglig för målgruppsanpassning för kontakter och företag i samband med affärskonton. När du väljer målgrupp för företag som primärt fokus i LinkedIn-exporten kan du exportera segment som bygger på affärskonton utan att det krävs någon projektkontaktinformation. Mer information finns i dokumentet om [export av LinkedIn-annonser](export-linkedin-ads.md) och skillnaden mellan [kontaktanpassning](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) och [företagsanpassning](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Skapa åtgärder utifrån affärskonton och deras hierarki

Med måttverktyget kan du skapa mått runt affärskonton och om du vill kan du använda hierarkiinformationen. Hierarkiinformation används för att skapa en måttberäkning för ett konto och alla dess relaterade underkonton. Du kan till exempel skapa mått som totalintäkt för varje grupp affärskonton som identifieras med hjälp av deras hierarki. Mer information finns i [Definiera och hantera mått](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Skapa segment utifrån affärskonton och deras hierarki

Med segmentverktyget kan du skapa segment av affärskonton som eventuellt innehåller kontaktinformation för varje konto i ett segment. Om du har ställt in kontohierarkin kan du använda kontohierarkiinformation när du skapar ett segment. Mer information finns i [Skapa ett nytt segment](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Behåll dina affärskonton med djupare insikter för deras förakt

Nu har prediktionsmodell för kundomsättning också stöd för affärskonton. Du kan utvärdera risken för att det inte bara gäller ett konto utan även för en kombination av ett konto och en produkt eller tjänstkategori som de köper från dig. Detta gör det lättare att förstå om det är troligare att ett konto slutar köpa från dig i allmänhet eller bara för en viss kategori varor eller tjänster. För att ytterligare hjälpa dig att använda den här AI-modellen anger den också orsaker till varför ett konto sannolikt kommer att förlora. Mer information finns i [Prediktion av transaktionsomsättning (förhandsversion)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Visa kontakter för ett affärskonto i kundvyn

Om affärskonton är mappade till relaterade konton visas dessa relaterade kontakter i appen Customer Insights som en del av vyn med kundinformation. Mer information finns i [Kundprofiler](customer-profiles.md).


## <a name="september-2021-updates"></a>Uppdatering i september 2021

Uppdateringarna i september 2021 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="activities"></a>Aktiviteter

- **Förbättringar av aktivitetstidsvyn** Vi har utökat filtren för aktivitetstidslinjen för kundprofiler. Dessutom kan du använda det nya filtret för att filtrera efter aktivitetstyp och datum. Datum kan filtreras under andra villkor. Mer information finns i [Visa tidslinjer för aktiviteter för kundprofiler](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relationer

- **Stöd för multi-hop-relation** Använd multi-hop relationer när du konfigurerar aktiviteter och definierar relationer mellan enheter. Multi-hop relationships använda en mellanliggande entitet för att ansluta två enheter. När du konfigurerar en aktivitet kan du använda en multi-hop-relation för att ansluta aktivitetsentiteten till en mellanliggande entitet och sedan till en kundentitet. Du kan kombinera flera multi-hop-relationer med relationer med flera vägar. Mer information finns i [Multi-hop-relation](relationships.md#multi-hop-relationship).

- **Stöd för relation med flera vägar** Använd relation med flera vägar när du konfigurerar aktiviteter och definierar relationer mellan enheter. Relationer med flera vägar relaterar en källentitet till fler än en entitet. När du konfigurerar en aktivitet kan du använda en relation med flera vägar för att ansluta aktivitetsentiteten till mer än en kundentitet. Du kan kombinera relationer med flera vägar med multi-hop-relationer. Mer information finns i [relationer med flera vägar](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Uppdatering augusti 2021

Uppdateringarna i juli och augusti 2021 innehåller en ny funktion, prestandauppgraderingar och felkorrigeringar.

### <a name="extensibility"></a>Utbyggbar

- **Exportera segment till Klaviyo** Vi har utökat våra [exportmål till att omfatta Klaviyo](export-klaviyo.md). Du kan nu exportera segment i syfte att skapa kampanjer, bedriva e-postmarknadsföring samt använda specifika kundgrupper med Klaviyo. 


## <a name="june-2021-updates"></a>Uppdatering i juni 2021

Uppdateringarna i juni 2021 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="data-ingestion"></a>Datainsamling

- **Förbättrade förloppsuppdateringar för datasamordning** Du kan nu visa mer detaljerade och förbättrade dynamiska statusuppdateringar i stegen för [datasamordningsprocess](data-unification.md). Med den här funktionen kan du hålla reda på det detaljerade förloppet i syfte att förstå processflödet och vidta åtgärder om några steg behöver uppmärksammas.

### <a name="extensibility"></a>Utbyggbar

- **Exportera segment och andra data till Salesforce Marketing Cloud** Vi har utökat våra exportmål till att omfatta [Salesforce Marketing Cloud](export-salesforce.md). Du kan nu exportera segment och andra typer av data till Salesforce Marketing Cloud via en märkt SFTP-export . Dataimport kan automatiseras helt i Salesforce och användas för att skapa effektivare marknadsföringskampanjer.  
 
- **Exportera segment till ActiveCampaign** Vi har utökat våra exportmål till att omfatta [Active Campaign](export-active-campaign.md). Du kan nu exportera segment i syfte att generera kampanjer, köra e-postmarknadsföring och arbeta med specifika kundgrupper i ActiveCampaign.
 
- **Exportera segment till Sendinblue** Vi har utökat våra exportmål till att omfatta [Sendinblue](export-sendinblue.md). Du kan nu exportera segment i syfte att generera kampanjer, köra e-postmarknadsföring och arbeta med specifika kundgrupper med Sendinblue.
 
### <a name="ux-updates"></a>UX--uppdateringar 

- **Ny och förbättrad kundsida och sida för profilinformation** Vi har gjort om vår kundsida och sidan för profilinformation i syfte att kunna erbjuda bättre användarupplevelse och bättre prestanda. Med dessa ändringarna kan du visa, sortera, söka och filtrera kunder. Filter representeras nu i webbadressen för att sömlöst dela sökresultaten med andra användare. Sökresultat kan också sparas som ett segment.    
  Informationssidan för kundprofiler grupperar nu data i olika underavsnitt, till exempel demografisk information, ID och andra profilattribut för bättre läsbarhet. Andra avsnitt på sidan med profilinformation är nu mer interaktiva. I avsnittet med aktiviteter tillåts exempelvis nu filtrering och sortering.


## <a name="may-2021-updates"></a>Uppdateringar maj 2021

Uppdateringarna i maj 2021 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="data-ingestion"></a>Datainsamling

- **Visa eller ändra metadata eller entitetsdefinition när du bifogar data från din Azure Data Lake Storage** Du kan nu visa och redigera metadata- eller entitetsdefinition i målgruppsinsikter när du bifogar data från en Common Data Model i Azure Data Lake Storage. Den här funktionen ger feedback i realtid, modellvalidering och felkontroll. Det låter dig redigera både model.json och manifest.json sömlöst.

### <a name="extensibility"></a>Utbyggbar

- **Förbättrad segmentexport, anpassat schema och duplicering** Du kan nu [se alla exporter för ett visst segment](export-destinations.md#view-exports-and-export-details) i en lista. Den här nya vyn hjälper till att hantera hur ett visst segment används och anpassa befintlig eller skapa ny export.    
  Du kan [definiera anpassade uppdateringsscheman](export-destinations.md#schedule-and-run-exports) för enskilda exporter eller flera exporter samtidigt. Hittills har all export körts med varje systemuppdatering.    
  I stället för att skapa en ny export från grunden kan du börja baserat på en befintlig för att spara lite tid.

- **Exportera segment till Microsoft Advertising** Nu har exportmålen utökats till att omfatta Microsoft Advertising. Skapa Customer Match-målgrupper i Microsoft Advertising med dina enhetliga kundprofildata, och använd målgrupperna för dina kampanjer och annonser. Mer information finns i [Exportera segment till Microsoft Advertising](export-microsoft-advertising.md).

- **Exportera segment till LinkedIn Ads** Vi har utökat våra exportdestinationer till att omfatta LinkedIn Ads och gör det möjligt för dig att låsa upp kontaktinriktning och företagsinriktning via LinkedIn genom att exportera dina enhetliga kundprofildata. Mer information finns i [Exportera segment till LinkedIn Ads](export-linkedin-ads.md).


- **Exportera segment till Omnisend** Nu har exportmålen utökats till att omfatta Omnisend. Använd segmenten som skapas i målgruppsinsikter för att generera kampanjer, skapa e-postmarknadsföring och dra nytta av specifika kundgrupper med Omnisend. Mer information finns i [Exportera segment till Omnisend](export-omnisend.md)

### <a name="predictions"></a>Prediktioner

- **Användbarhetsrapport för indata** Rapporten om användbarhet av indata ger en konsoliderad vy över de fel och varningar som dina färdiga förutsägelser kan generera. Det ger också rekommendationer om hur man förbättrar modellens prestanda.    
  Rapporten är tillgänglig när en modell har slutfört sin utbildningsprocess. Den skapas för varje modell separat, oavsett om den har slutförts eller inte.
  För närvarande fungerar den här funktionen bara för transaktionsomsättningsmodellen. Mer information finns i [Användbarhetsrapport av indata](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relationer

- **Relationsvisualisering** Vyn i relationsvisualiseraren låter dig se alla befintliga relationer mellan entiteter och deras kardinalitet. Relationer ordnas nu i grupper: användarskapade, system och ärvda relationer. Du kan också exportera en vy som en bild. Mer information finns i [Visa relationer](relationships.md#view-relationships). 

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

- **Exportera segment till RollWorks** Nu har exportmålen utökats till att omfatta RollWorks. Nu kan du exportera segment från Customer Insights till RollWorks-målgrupper och använda dem som baslinje för din B2B-annonsering.    
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

  Administratörer kan kopiera miljökonfigurationer till en ny miljö i samma organisation. Med den här funktionen utvidgas kopieringsmiljöns funktioner för ärenden där datakällor som bygger på en Microsoft Dataverse-hanterad datasjö eller Common Data Model-mapp används.

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