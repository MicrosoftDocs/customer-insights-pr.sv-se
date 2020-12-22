---
title: Nya och kommande funktioner
description: Information om nya funktioner, förbättringar och felkorrigeringar.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650026"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Vad är nytt i funktionen målgruppsinsikter i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi är glada över att kunna meddela våra senaste uppdateringar! Denna artikel sammanfattar funktioner för allmänt tillgänglig förhandsversion, förbättringar av allmän tillgänglighet och funktionsuppdateringar. Om du vill se de långsiktiga funktionsplanerna, se [utgivningsplaner för Dynamics 365 och Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Du kan också titta på följande video om du vill veta mer om de funktioner som har planerats för de senaste sex månaderna.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Vi lanserar uppdateringar en region i taget. Vissa regioner kan se funktioner före andra. Om inget annat anges behöver du inte vidta några åtgärder så uppdateras appen automatiskt utan driftsavbrott.

> [!TIP]
> Skicka in och rösta på funktioner som efterfrågas och produktförslag går du till [Dynamics 365-programmets idéportal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Uppdateringar i november 2020

Uppdateringarna i november 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-november-2020"></a>Nya och uppdaterade funktioner i november 2020

#### <a name="data-enrichment"></a>Databerikande

- **Ta med egna berikande data via anpassad SFTP-import (Secure File Transfer Protocol)**
  
  Anpassad SFTP-import gör det möjligt att importera berikande data som inte behöver gå igenom dataförening. Läs mer om anpassad FTP-import.

  Mer information finns i [Berika kundprofiler med anpassade data (förhandsversion)](enrichment-SFTP-custom-import.md).
 
- **Berika dina kunddata med platsdata från HERE Technologies**

  Med HERE Technologies databerikande tjänster kan du få en mer exakt förståelse för kundens plats, med adress, latitud och longitud och så vidare. Läs mer om hur du berikar med HERE Technologies.

  Mer information finns i [Berika kundprofiler med HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Dataförening

- **Flexibilitet för att aktivera dataprofilering på utvalda entiteter och fält från ditt lagringskonto**

  Du kan ange vilka dataentiteter och fält från en Common Data Model-mapp i ditt Azure Data Lake-lagringskonto du vill aktivera dataprofilering för som en del av datainmatningsprocessen.

  Mer information finns i [Ansluta till en Common Data Model-mapp](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Utbyggbar

- **Aktivera dina segment via Google Ads**

  Exportera segment till Google Ads målgruppslista och använd listan för att annonsera i Google Sök, Googles Display-nätverk, YouTube och Gmail. Läs mer om hur du aktiverar dina segment via Google Ads.

  Mer information finns i [Anslutningsprogram för Google Ads](export-google-ads.md).

- **Aktivera dina segment via Marketo**

  Exportera segment till Marketo-målgrupper och använd dessa målgrupper för automatiserad marknadsföring. Läs mer om hur du aktiverar dina segment via Marketo. 

  Mer information finns i [Anslutningsprogram för Marketo](export-marketo.md).

- **Aktivera dina segment via DotDigital**

  Exportera segment till DotDigital och använd dem i marknadsföringssyfte. Läs mer om hur du aktiverar dina segment via DotDigital. 

  Mer information finns i [Anslutningsprogram för DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Prediktioner

- **Förutsäga transaktionell omsättning**

  Förutsägelse av transaktionell omsättning gör det möjligt för dig att, utan hjälp av en datavetare, förutsäga sannolikheten för att en kund slutar köpa produkter eller tjänster.  Med hjälp förutsägelsepoängen kan du kombinera annan information om dina kunder, som kundvärde, för att skapa segment av hög omsättningsrisk eller kunder med högt värde. Använd det här segmentet för att direkt rikta in dig på kunder genom marknadsföringsaktiviteter, kundsupport och andra scenarier för att minska omsättningsrisken.
 
  Konfigurera definitionen av omsättning som ett tidsbaserat fönster som är specifikt för ditt företag och definiera när kunder anses vara omsatta. Till exempel, en livsmedelsbutik kanske vill se en kund som omsatt om de inte har köpt något under de senaste 30 dagarna.
 
  När du fortsätter att skapa förutsägelsen guidar vi dig genom vilka data som behövs och gör det möjligt för dig att mappa data om ditt företag till fält som krävs för att förutsäga omsättning för dina kunder. Du kan också ange ett schema för att omskola modellen baserat på ny information i ditt system för att anpassa sig till förändrade affärsmässiga omständigheter.
 
  Mer information finns i [Förutsägelse av transaktionell omsättning (förhandsversion)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Systemadministration

- **Återställ miljö**

  Återställ allt i en miljö av en vald instans för att börja om från början.

  Mer information finns i [Återställ en befintlig miljö](manage-environments.md#reset-an-existing-environment).


- **Ansluta till ditt Azure Data Lake-lagringskonto med hjälp av ett huvudkonto för tjänsten**

  Skriv datautdata till och läsa data från ditt lagringskonto med hjälp av ett huvudkonto för Azure-tjänsten. Befintliga anslutningar för lagringskonto kan fortsätta att använda kontonyckeln. De erbjuder också ett uppgraderingsalternativ för att använda huvudkontot för tjänsten i framtiden. Nya anslutningar kommer att baseras på autentiseringsmetoden för ditt lagringskonto.

  Mer information finns i [Ansluta till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto för målgruppsinsikter](connect-service-principal.md).

## <a name="october-2020-updates"></a>Uppdateringar i oktober 2020

Uppdateringarna i oktober 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-october-2020"></a>Nya och uppdaterade funktioner i oktober 2020

#### <a name="extensibility"></a>Utbyggbar

- **Export till MailChimp**

Exportera segment till befintliga målgruppslistor i Mailchimp för att ge en personlig e-postupplevelse för dina kunder.

Mer information finns i [Anslutningsprogram för Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Databerikande

- **Deduplicera källposterna i en matchningsentitet**

Ange dedupliceringsregler på entiteter som används i matchningsprocessen för att identifiera dubblettposter. Sammanfoga dem till en post och länka alla källposter till den här sammanslagna posten. Den här deduplicerade posten används sedan i den entitetsöverskridande matchningsprocessen.

Mer information finns i [Definiera deduplicering på en matchningsentitet](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Systemadministration

- **Orkestrering: Nytt uppdateringsalternativ i sammanslagning**

Fram till idag, när du kör sammanslagningsprocessen, körde systemet alla de nedströmsprocesser som är beroende av sammanslagning och efterföljande processer. Du kan nu verifiera utdata för sammanfogningsprocessen (den enhetliga kundentiteten) innan du använder den i nedströmsbearbetning som segment eller mått.
På sidan för sammanslagning kan du nu välja att endast köra sammanslagningssteget och endast köra den här processen. Om du vill uppdatera alla nedströmsprocesserna också kan du välja att köra sammanslagning och nedströmsprocesser. 

## <a name="september-2020-updates"></a>Uppdatering i september 2020

Uppdateringarna i september 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-september-2020"></a>Nya och uppdaterade funktioner i september 2020

#### <a name="activities"></a>Aktiviteter

- **Intelligent prediktion av attributsemantik**

Den nya funktionen förutsäger de semantiska typer av indatavärden som skickas till dataföreningsprocessen. Den använder maskininlärningsmodeller som förbättrar precisionen och sparar tid.

#### <a name="enrichments"></a>Berikningar

- **Demografisk berikning från Experian**

Den demografiska berikningen av Experian finns nu tillgänglig för förhandsgranskning. Experian är en global ledare inom konsument- och affärskreditrapportering och marknadsföringstjänster. Med [Experians databerikningstjänster](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) kan du skapa en djupare förståelse för dina kunder genom att berika dina kundprofiler med demografiska uppgifter som hushållsstorlek, inkomst och mer.

Om du vill använda den här funktionen måste du ha en aktiv Experian-prenumeration.

Mer information finns i [utöka kundprofiler med demografisk information från Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Systemadministration

- **Fönstret uppgiftsinformation**

Med fönstret uppgiftsinformations kan du visa information om uppgifter som systemet kör. Det är ett praktiskt sätt att identifiera problem med konfigurations- och söklösningar.
Läs om hur du åtgärdar potentiella problem i felmeddelandena.
 
- **Bearbeta information som lagts till ytterligare sidor**

Den här förbättringen lägger till information om status för entiteterna på sidan **entiteter** och **kunder**.
 
Dessutom hittar du information om processernas status tillsammans med uppgiftsinformationen på båda sidorna.

- **Förbättringar av sidan systemstatus**

Vi förbättrade strukturen i statusinformationstabellen för **System** > **Status** när du granskar dataexporten.
 
Dessutom är fel i kolumnen **detaljer** mer detaljerade och åtgärdsbara. 
 
- **Avbryt återställer jobb till tidigare tillstånd**

När du avbryter en uppgift, till exempel i matchningsprocessen, kommer den att återgå till det senaste tillståndet. Om matchningsprocessen till exempel slutförts i igår och du avbryter den i dag, återgår den till förfaller i igår.


## <a name="august-2020-updates"></a>Uppdatering augusti 2020

Uppdateringarna i augusti 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-august-2020"></a>Nya och uppdaterade funktioner i augusti 2020

#### <a name="data-unification"></a>Dataförening

- **Förbättrade funktioner för kartskedet under dataförening**

  Med upplevelsen för kartsteget i dataföreningsprocess kan du välja entiteter, attribut och definiera semantiskt på ett mer sömlöst sätt.

  Ändringar inkluderar:
  
  - färre interaktioner som krävs för att lägga till entiteter och fält
  - förbättrade sökfunktioner på mappningssidan
  - visuell och enkel identifiering av den föreslagna fälttypen

#### <a name="enrichment"></a>Berikning

- **Intressetillhörigheter som är tillgängliga på ytterligare marknader**

  Vi utökar tillgängligheten av intressetillhörigheter bortom USA och fem ytterligare marknader: Kanada, Australien, Storbritannien, Frankrike och Tyskland. Med det här tillägget kan du utöka dina kunddata med ytterligare intressen som gäller för dessa marknader. Vi ska också berika dina kundprofiler som finns på dessa marknader med hjälp av lokala patentskyddade data från Microsoft Graph.
  Mer information finns i [berika kundprofiler med samhörigheter med varumärke och intresse](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Uppdatering i juli 2020

Uppdateringarna i juli 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-july-2020"></a>Nyheter och uppdaterade funktioner i juli 2020.

#### <a name="extensibility"></a>Utökningsbarhet

- **Power Automate utlöser slutförd föreningsprocess**

  Vi har utökat våra utlösare för Power Automate och du kan skapa ett meddelande eller en åtgärd när en uppdatering av föreningsprocessen (mappa, matcha, slå samman) har slutförts.    
  Mer information finns i [Power Automate anslutningsprogram](export-power-automate.md)

#### <a name="enrichment"></a>Berikande

- **Berikning av samhörigheter med varumärke som är tillgängliga på ytterligare marknader**

  Vi utvidgar tillgängligheten av samhörigheter med varumärke bortom USA och ytterligare fem marknader: Kanada, Australien, Storbritannien, Frankrike och Tyskland. Med det här tillägget kan du utöka dina kunddata med lokala varumärken på dessa marknader. Vi ska också berika dina kundprofiler som finns på dessa marknader med hjälp av lokala patentskyddade data från Microsoft Graph.
  Mer information finns i [berika kundprofiler med samhörigheter med varumärke och intresse](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Uppdatering i juni 2020

Uppdateringarna i juni 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-june-2020"></a>Nyheter och uppdaterade funktioner i juni 2020.

#### <a name="enrichment"></a>Berikande

- **Berikning av företagsdata från Leadspace**
  
  Definiera fält i enhetliga kundprofiler som används för att slå upp relaterade företagsdata från Leadspace. När du har kört berikningsprocessen har B2B-profiler ökats med ytterligare attribut, bland annat företagsstorlek, plats, bransch och mycket mer.    
  Det här samarbetet gör det möjligt att förbättra kvaliteten på dina data med indata från tjänster från tredje part. Om du vill använda denna berikning måste du ha en licens från Leadspace för att få tillgång till B2B-företagsdata. Systemet kommer att använda den licensen så att dina data berikas kontinuerligt.    
  Mer information finns i [Berika företagsprofiler med Leadspace](enrichment-leadspace.md).

- **Sidan för berikningsnav**

  Alla tillgängliga data som framställs av tredjepartsleverantörer från första och tredje part konfigureras på samma plats. Konfigurering av databerikning är en sömlös upplevelse som hanteras från en gemensam plats.    
  Mer information finns i [berikning av kundprofiler](enrichment-hub.md).

- **Särskild berikning av samhörigheter med varumärke och intresse**

  Samhörigheter med varumärke och intresse är nu tillgängliga som två oberoende berikningar. Separerade berikningar ger flexibiliteten att konfigurera och hantera dem individuellt, beroende på dina affärskrav eller behov.    
  Mer information finns i [berika kundprofiler med samhörigheter med varumärke och intresse](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Utökningsbarhet

- **Klickbara URL-adresser för enhetliga aktiviteter på kundkorttillägget för Dynamics 365**

  De enhetliga aktiviteterna i tillägget Customer Card visar nu klickbara URL:er om sådana URL:er har definierats under konfigurationen av aktiviteter.    
  Mer information finns i [Tillägg för kundkort](customer-card-add-in.md).

- **Samhörigheter med varumärke och intresse som är tillgängliga på kundkortstillägget för Dynamics 365**

  Med en ny kontroll på kundkortstillägget för Dynamics 365 kan du visa dina kontakters berikningar av varumärke och intresse i appar för kundengagemang i Dynamics 365.    
  Mer information finns i [Tillägg för kundkort](customer-card-add-in.md).

- **Ytterligare Power Automate utlösare**

  Vi har utökat våra utlösare för Power Automate och lagt till följande utlösare:
  - Hämta ett meddelande eller utföra en åtgärd när en automatisk fullständig uppdatering (datakällor, sammanslagning, segment, mått, export) har slutförts
  - Definiera ett tröskelvärde för ett affärsmått. Du kan till exempel skapa ett meddelande som skickas när det angivna tröskelvärdet passeras. Dessutom ger utlösaren information som gör det möjligt att bygga upp mer komplexa arbetsflöden i Power Automate.    
  Mer information finns i [Power Automate anslutningsprogram](export-power-automate.md)

- **Exportera till Facebook Ads Manager**
  
  Med den här funktionen kan du exportera segment till Facebook Ads Manager. Segment exporteras som anpassade målgrupper för att använda enhetliga kundprofiler i marknadsföringskampanjer och annonser på Facebook. De anpassade målgrupperna kan också användas för att skapa kampanjer på Instagram via Facebook Ads Manager.    
  Mer information finns i [anslutningsprogram för Facebook Ads Manager](export-facebook.md).

#### <a name="predictions"></a>Prediktioner

- **Omsättningsprediktion för abonnemang**

  Följ en guidad upplevelse för att skapa omsättningsprediktion i prenumerationsområden som molntjänster, kundmedlemskap och andra sektorer. 

  Med funktionen för omsättningsprediktion för abonnemang kan du förutse sannolikheten för att en kund stoppar användningen av prenumerationsprodukter eller tjänster utan att behöva en datatekniker. Med hjälp av prediktionspoängen kan du kombinera annan information om kunderna för att skapa segment av hög omsättningsrisk. Med hjälp av det här segmentet kan du direkt rikta dig till kunder i marknadsföring, kundsupport och andra scenarier för att minska risken för omsättning för specifika kunder för att förbättra intäkterna och minska kostnaderna.

  I upplevelsen kan du konfigurera definitionen av omsättningen som ett tidsbaserat fönster som är specifikt för din verksamhet. En verksamhet för videoströmning som har en månatlig prenumerationsprocess kanske vill anse till att en kund har omsatts efter 15 dagar efter det att prenumerationen gått ut.

  När du fortsätter igenom prediktion guidar vi dig igenom vilka data som behövs och du kan mappa data om företaget till fält som krävs för att förutse omsättningen för kunderna. När affärsinformationen ändras kan du också ange ett schema för att omutbilda den nya informationen i systemet för att anpassa sig efter föränderliga affärssituationer.    
  Mer information finns i [Omsättningsprediktion för abonnemang (förhandsversion)](predict-subscription-churn.md).

#### <a name="segments"></a>Segments

- **Sök efter liknande kunder**
  
  Hitta liknande kunder i kundbasen med hjälp av artificiell intelligens. En maskininlärningsmodell för binär klassificering tilldelar en likhetspoäng för kunderna i det expanderade segmentet. Poängen baseras på likheten med kunder i källsegmentet. Beroende på likhetspoängen läggs kundprofilerna till i ett nyskapat segment.

  I vissa fall kallas för den för dubbelgångarmodell i digital marknadsföring, en AI-modell som hjälper dig att hitta kunder som liknar ett annat segment av dina kunder genom att använda ytterligare attribut. Du kan inte bara välja attributen, men du kan också ange det maximala antalet kunder som ska finnas i det nya segmentet. AI-modellen beräknar sedan likhetspoäng för varje kund utifrån de valda attributen och söker efter kunder med det övre medelvärdet för likhetspoäng. Det resulterande segmentet omfattar kunder som ser ut ungefär som kunden i det ursprungliga segmentet.    
  Mer information finns i [Liknande kunder](find-similar-customer-segments.md).

- **Överlappningar och differentieringar av segment**

  Med överlappning kan du se hur många och vilka kunder som är gemensamma för två eller flera segment. Exempelvis överlappar ett högt utgiftssegment med ett segment av hög tillfredsställelse eller hur ett överlappande kundsegment överlappar ett segment med kunder som inte är speciellt nöjda. Dessutom kan du analysera hur överlappningen ändras utifrån ett ytterligare attribut som du väljer.

  Segmentdifferentieringar avslöjar vad som skiljer ett segment från övriga kunder eller från ett annat segment. Allt du behöver göra är att identifiera ett segment och systemet identifierar profilmappar och mått som särskiljer segmentet i form av en rangordnad lista med differentieringar, från den starkaste differentieringen till den svagaste.    
  Mer information finns i [Segmentinsikter (förhandsversion)](segment-insights.md).

- **Segment livstid**
  
  Definiera ett schema för aktivering eller inaktivering av ett segment.    
  Mer information finns i [Hantera befintliga segment](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Uppdateringar maj 2020

Uppdateringarna i maj 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-may-2020"></a>Nya och uppdaterade funktioner i maj 2020

#### <a name="data-ingestion"></a>Datainsamling

- **Datainmatning i realtid: historikvyer**

  När du använder vår API för att inmatning av uppdateringar i realtid kan du se upp till 30 dagars samlad historik för uppdateringarna. Du har tillgång till mängder av alla lyckade eller misslyckade API-anrop, inklusive resultat, källsystem och andra användbara metadata.    
  Mer information finns i [Datainmatning i realtid](real-time-data-ingestion.md).

- **Datainmatning i realtid: profiluppdateringar**

  Med det här tillägget av datainmatning i realtid kan du se de olika fält för användarprofil inom några sekunder.    
  Förutom realtidsfunktionen för aktiviteter stöder systemet uppdateringar med låg latens av profilfält. Uppdatering i realtid för profil fält har en förfallotid och är därför inte en ersättning för schemalagda uppdateringar.    
  Mer information finns i [Datainmatning i realtid](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Utökningsbarhet

- **Tidslinje och sidbrytning har uppdaterats i tillägget för kundkortet**

  Tidslinjen för tilläggslösningen Customer Card matchar aktivitetens tidslinje. Sidnumreringen förbättras och visar upp till 50 aktiviteter på samma gång. Det går också att läsa in ytterligare aktiviteter på tidslinjen.    
  Mer information finns i [Tillägg för kundkort](customer-card-add-in.md).

- **Power Automate utlösare för segmentändringar**

  Utlösare för Power Automate definierar vad du kan skapa ett flöde från. Den nyligen tillagda utlösaren kan definiera ett tröskelvärde för ett segment. Du kan till exempel skapa ett meddelande som skickas när det angivna tröskelvärdet passeras.    
  Mer information finns i [Power Automate anslutningsprogram](export-power-automate.md).

- **Stöd för fler innehavare för anpassade modeller**

  Konfigurera arbetsflöden för anpassade modeller med en webbtjänst för en annan Azure Machine Learning-klientorganisation. Du kan logga in på Azure Machine Learning-klientorganisationen när du skapar ett nytt arbetsflöde för anpassade modeller. Den här funktionen är ett tillägg till den befintliga funktionen för integrering med din egen anpassade Azure Machine Learning-webbtjänst.    
  Mer information finns i [anpassade maskininlärningsmodeller](custom-models.md).

#### <a name="segments"></a>Segment

- **Automatisering av entitetens sökväg**

  När du skapar ett segment behöver användarna definiera entitetssökvägen. Den här funktionen tar ett första steg genom att automatisera definitionen av entitetens sökväg så att du kan fokusera på de segmentkriterier du har i åtanke.    
  Om den entitet som du vill segmentera dina kunder efter är direkt relaterad till entiteten för Enhetlig kund, behöver du inte ange entitetens sökväg längre. Men om det finns mer än en möjlig entitets sökväg måste du definiera den manuellt.

- **Åtgärder på flera segment**
  
  Du kan markera flera segment och utföra åtgärder på dem, t.ex. om du vill uppdatera segmenten, med en enkel klickning.    

- **Uppdatera segment**

  Användare kan uppdatera ett enskilt segment eller endast markera de segment som de vill uppdatera.    

  
- **Förbättringar av sammansatta segment**

  Användare kan skapa, redigera och ta bort segment som bygger på andra segment. Till exempel ett segment som är konstruerat på ett annat segment och byggts på ett tredje segment.    

- **Listsida för segment**

  Den nya designen av sidan segment har ett listformat som gör att du kan visa fler segment samtidigt. Ett sökfält läggs till för att hitta segment snabbt. Användarna kan nu tillämpa åtgärder som att ladda ned eller ta bort flera segment samtidigt. En ny trendupplevelse införs för att snabbt identifiera viktiga förändringar i segment.    
  Mer information finns i [Skapa och hantera segment](segments.md).

#### <a name="system-administration"></a>Systemadministration

- **Customer Insights tillgänglig i Microsoft Dynamics 365 Online Government**

  Med fler och fler kanaler för interaktioner är medborgarna i ett utspritt system i myriad system som leder till silor och en fragmenterad vy med information om medborgarnas interaktioner. Utan en komplett bild av de olika medborgarnas interaktioner mellan olika kanaler är det omöjligt för regeringarna att modernisera i skala. Microsoft värnar om att stödja de tekniska behoven hos myndigheter för att kunna hålla sig uppdaterade med medborgarnas förväntningar.    
  Med 2020 utgivningsvåg 1 blir Dynamics 365 Customer Insights tillgänglig för Government Community Cloud (GCC), en miljö byggd för att uppfylla de högre kraven för Förenta staternas myndigheter. Organen får en enhetlig vy över medborgarna och använder inbyggd AI för att få insikter som förbättrar samverkan, ger personalen och omvandlar gemenskaperna, samtidigt som det minskar IT-komplexiteten och uppfyller de krav som gäller för USA och säkerhetsnormer. Dynamics 365 Government uppfyller de krävande kraven för det amerikanska federala riskhanteringsprogrammet (FedRAMP), vilket gör det möjligt för USA federala myndigheter att dra nytta av kostnadsbesparingar och rigorös säkerhet i Microsoft Cloud.

## <a name="april-2020-updates"></a>Uppdatering april 2020

Uppdateringarna i april 2020 innehåller flera funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="new-and-updated-features-in-april-2020"></a>Nya och uppdaterade funktioner i april 2020

#### <a name="activities"></a>Aktiviteter

- **Mappa aktivitetsentitet till standard aktivitetstyp**
  
  Aktivitetskonfiguration och lagringsutrymme baseras för närvarande på en statisk design för att visa dem på en tidslinje. En semantisk betydelse för aktiviteter, som har potential för flera användnings fall i AI-modeller, används inte fullt ut just nu. Du planerar att göra aktivitetstidslinjen mer dynamisk, utifrån aktivitetstypen och bättre semantisk förståelse för aktiviteterna. Med den här funktionen kan du identifiera aktivitetstypen enligt definitionen i Common Data Model för eventuell insamlingsaktivitet.
  Mer information finns i [Kundaktiviteter](activities.md).

#### <a name="data-ingestion"></a>Datainsamling

- **Datainmatning i realtid: aktiviteter**
  
  Datainmatning i realtid ger data omedelbart för förbrukning, tills den efterföljande schemalagda uppdateringen hämtar dessa data från datakällan.    
  Mer information finns i [Datainmatning i realtid](real-time-data-ingestion.md).

- **Förbättringar av förberedelse av data**
  
  Läs mer om datainmatning i en entitet. Med hjälp av datasammanfattningen kan du förstå de datakvalitetsegenskaper som kan vara till hjälp för att vidta lämpliga åtgärder.    
  Mer information finns i [Utforska entitetsdata](entities.md#exploring-a-specific-entitys-data).

- **Mata in analysdata från Dynamics 365 med Common Data Service**
  
  Common Data Service finns som ett sätt att skapa datakällor. Befintliga Dynamics 365-kunder kan mata in analysentiteter från Common Data Service till Customer Insights. En enda datakälla åt gången kan använda samma Common Data Service-hanterade sjö i en Customer Insights-miljö.    
  Mer information finns i [ansluta till data i en Common Data Service hanterad datasjö](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Utökningsbarhet

- **Exportera till LiveRamp**

  Aktivera dina data i LiveRamp® om du vill ansluta med över 500 plattformar över digitala, sociala och TV-ekosystem. Använd dina data i LiveRamp för att rikta, utelämna och anpassa annonskampanjer.    
  Mer information finns i [LiveRamp&reg; anslutningsprogram](export-liveramp.md).

- **Tillägget Customer Insights Teams**
  
  Roboten har uppslagsfunktioner för enhetliga kundprofiler. Ett kort med upp till 15 fält visas i den resulterande kundprofilen. Flera matchningar returnerar en resultatlista där du kan välja en profil.    
  Mer information finns i [Teams-robot för Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mått

- **Listsidan Mått**
  
  Förbättringarna av sidan mått är stöd för åtgärder på ett och samma mått och på flera mått samtidigt. Dessutom hittar du ett sökfält för att snabbt hitta och spåra mått.    
  Mer information finns i [Skapa och hantera segment](segments.md).

- **Förbättringar av sammansatta mått**
  
  Användare kan skapa, redigera och ta bort mått som bygger på andra mått. Till exempel ett mått som är konstruerat på ett annat mått och byggts på ett tredje mått.

#### <a name="segments"></a>Segments

- **Ytterligare operator**
  
  Den infällda operatorn gör det möjligt att segmentera för kunder efter flera möjliga strängvärden. Innan operatorn lades till var du tvungen att konstruera sådana segment med flera OR-villkor. Med den infällda operatorn kan du göra det med ett enda villkor.    
  Mer information finns i [Skapa och hantera segment](segments.md).

#### <a name="system-administration"></a>Systemadministration

- **Kopiera konfigurationsinställningar till en ny miljö**
  
  Kopiera konfigurationen från en miljö till en annan. När du skapar en ny miljö kan du välja en befintlig miljö som du vill kopiera konfigurationen från. Vi stöder för närvarande datakällor, dataförening, relationer, mått och segment som ska kopieras. Datakälla autentiseringsuppgifter och verkliga data kopieras inte.    
  Mer information finns i [Hantera miljöer](manage-environments.md).
