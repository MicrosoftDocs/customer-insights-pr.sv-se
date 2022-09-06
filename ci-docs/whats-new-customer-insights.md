---
title: Nyheter i Dynamics 365 Customer Insights
description: Information om nya funktioner, förbättringar och felkorrigeringar.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 1e734464cec1f66428c3a2a2e403437a2a9d8500
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387316"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Nyheter i Dynamics 365 Customer Insights

Vi är glada över att kunna meddela våra senaste uppdateringar! Denna artikel sammanfattar funktioner för allmänt tillgänglig förhandsversion, förbättringar av allmän tillgänglighet och funktionsuppdateringar. Om du vill se de långsiktiga funktionsplanerna, se [utgivningsplaner för Dynamics 365 och Power Platform](/dynamics365/release-plans/).

Vi lanserar uppdateringar en region i taget. Vissa regioner kan se funktioner före andra. Om inget annat anges behöver du inte vidta några åtgärder så uppdateras appen automatiskt utan driftsavbrott.

> [!TIP]
> Skicka in och rösta på funktioner som efterfrågas och produktförslag går du till [Dynamics 365-programmets idéportal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>Uppdatering augusti 2022

Uppdateringarna i augusti 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="contact-unification-in-b-to-b-environments"></a>Kontakt i B2B-miljöer

B2B-miljöer i Customer Insights har nu stöd för en förbättrad datamiljö.

Nu kan du ena kontakter och konton om du vill få en fullständig vy över dina affärskontakter. Enade kontakter är associerade med enhetliga konton och listas nu på kundkorten. 

Mer information finns i [Skapa en enhetlig kontaktprofil](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Skapa och exportera segment utifrån enhetliga kontakter

Tack vare den nya kontakten kan du skapa kontaktsegment med villkor från antingen kontakter, konton eller både och. Dessa segment kan exporteras för aktivering i andra tjänster.

Mer information finns i [Översikt över exporter](export-destinations.md).

## <a name="july-2022-updates"></a>Uppdatering i juli 2022

Uppdateringarna i juli 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="export-to-moengage"></a>Exportera till MoEngage

Exportera segment med enhetliga kundprofiler till MoEngage och använd dem för e-postmarknadsföring i MoEngage.

Mer information finns i [Exportera segment till MoEngage](export-moengage.md)

### <a name="ssh-support-for-sftp-based-exports"></a>SSH-stöd för SFTP-baserade exporter

Välj om du vill autentisera via SSH eller användarnamn/lösenord för anslutningar till SFTP-exportmål

Mer information finns i [Exportera data till SFTP-värdar](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Anpassa erfarenheter med data om kända och okända användare

Att hantera kunddata är ingen ny utmaning, men det är allt svårare för användarna att navigera i de olika digitala kanalerbjudandet. En användare som är känd (autentiserad) i en kanal blir okänd (oautentisering) i en annan om den inte är inloggad. Problemet är ofta att oautentiserade (okända) användare inte har ett gemensamt ID. Den kan användas för att associera meningsfulla profilattribut och skapa enhetliga kundprofiler. Customer Insights hjälper dig att lösa det här problemet genom att samla in data från spårningsmetoder i dina källsystem.

Mer information finns i [Anpassa dina erfarenheter med data om kända och okända användare](unknown-to-known.md).

## <a name="june-2022-updates"></a>Uppdatering i juni 2022

Uppdateringarna i juni 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Uppdaterad användarupplevelse för datakällor och datainmatning

Att importera data från en rad olika datakällor är grunden för att kunna börja använda kunddata i Dynamics 365 Customer Insights. Vi har skapat användarupplevelsen för import och anslutning av datakällor. Uppdateringen underlättar för dig att få tillgång till Customer Insights.

Mer information finns i [Översikt över datakällor](data-sources.md).

### <a name="export-to-inmobi"></a>Exportera till InMobi

Med InMobi får han hjälp att förstå, identifiera, engagera sig och skaffa sig ett intresse. Du kan exportera segment och andra data till InMobi-tjänsten via Azure Blob Storage-konton.

Mer information finns i [Exportera till InMobi (förhandsversionen)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Databas support i Customer Insights

Customer Lockbox innehåller ett gränssnitt för att granska och godkänna (eller avvisa) förfrågningar om dataåtkomst. Dessa förfrågningar uppstår när dataåtkomst till kunddata behövs för att lösa ett supportärenden.

För mer information, se [Få säker åtkomst till kunddata med Customer Lockbox (förhandsversion)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Anslut till dina data med hjälp av Azure Private Link

Azure Private Link låter Customer Insights ansluta till ditt Azure Data Lake Storage-konto via en privat slutpunkt i ditt virtuella nätverk. För data i ett lagringskonto, som inte är synligt för det offentliga Internet, aktiverar Private Link anslutningen till det begränsade nätverket.

Mer information finns i [Använd privat länk i Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Uppdateringar maj 2022

Uppdateringarna i maj 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="updated-data-unification-experience"></a>Uppdaterad upplevelse av datasammanslutning

 Dataförening låter dig förena en gång disparata datakällor till en enda huvuddatauppsättning som ger en enhetlig vy av dessa data. Data kan vara enhetliga på samma entitet eller flera entiteter. Först [väljer du entiteter och källfält](map-entities.md), [tar bort dubblettposter](remove-duplicates.md), anger regler för [matchande villkor](match-entities.md) och definierar vilka [fält som ska tas med i de enhetliga kundprofilerna](merge-entities.md).

Mer information finns i [Översikt över datasammanslutning](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Uppdaterad startsida i Customer Insights

**Start** guidar dig genom konfigurationsprocessen för viktiga funktioner och får en översikt över segment, mått och berikande data. Vi har uppdaterat upplevelsen för att ge en översikt av mer relevant information.

Mer information finns i [Utforska Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Spåra användning av ett segment

Nu kan du [spåra användning av segment](segments.md#track-usage-of-a-segment) i appar som är baserade på Dataverse organisation som är kopplad till Customer Insights. För [Customer Insights-segment som används i kundens färd inom Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) informerar systemet dig om hur detta segment används.

### <a name="export-to-criteo"></a>Exportera till Criteo

Criteo är en onlineplattform som hjälper användare att hantera digital annonsering. Du kan nu exportera segment för enhetliga kundprofiler för att generera kampanjer, tillhandahålla e-postmarknadsföring och utnyttja specifika kundgrupper med Criteo.

Mer information finns i [Exportera segment till Criteo (förhandsversionen)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Förfinad dokumentationsstruktur för miljöskapande

Vi har fört fram hjälpdokumenten som handlar om att skapa och hantera miljöer i Customer Insights. Artiklarna grupperas nu under noden Miljöer i innehållsförteckningen. De nya artiklarna ger bättre vägledning för de olika sätten att konfigurera miljöer och har en tydligare struktur. Om du har feedback som du kan dela med dig av, meddela oss via kontrollerna i slutet av hjälpartiklarna.

Mer information finns i [Skapa en ny miljö](create-environment.md).

## <a name="april-2022-updates"></a>Uppdatering april 2022

Uppdateringarna i april 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet-berikning (förhandsversion)

Dun & Bradstreet tillhandahåller kommersiella data, analyser och insikter för företag. Det gör det möjligt för kunder med enhetliga kundprofiler för företag att berika sina data. Utöka inkluderar attribut, till exempel DUNS-nummer, företagsstorlek, plats, bransch med mera.

Mer information finns i [Berika företagsprofiler med Dun & Bradstreet (förhandsversion)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Ange måttyp när du skapar ett nytt mått

Nu kan du skilja mellan mått för enskilda profiler och mått i hela företaget. Även om affärsåtgärder visas på startsidan för Customer Insights visas kundåtgärderna i de detaljerade kundvyerna.

Mer information finns i [Använda måttverktyget för att skapa mått från grunden](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Dokumentation för att konsolidera Customer Insights

Vi har fört fram våra dokumentationsartiklar och tagit bort omnämnanden om engagemangsinsikter och målgruppinsikter. Framåt kommer vi konsekvent att hänvisa till produktnamnet Customer Insights när vi skriver om programmets huvudfunktioner. Den här förändringen leder också till att innehållsförteckningen, URL-strukturen och sökvägarna till filen i den underliggande dokumentationsdatabasen blir viktiga. Alla bokmärken eller befintliga länkar fungerar fortfarande och omdirigeras till de uppdaterade URL:erna.

Om du vill meddela oss hur du ser att något som inte fungerar som förväntat ändras eller upptäcks, kan du meddela oss genom att [skicka feedback för den här sidan](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Uppdateringar i mars 2022

Uppdateringarna i mars 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="liveramp-abilitec-enrichment-preview"></a>Berikning av LiveRamp AbiliTec (förhandsversion)

LiveRamp anger identitetsmatchning och konsoliderar kunddata. Du kan mappa personliga identifierare i dina kunddata till identitetsdiagrammet AbiliTec och ta emot AbiliTec ID. Därefter kan du använda de här ID:erna för att bättre ta fram kunddata.

Mer information finns i [Berika kundprofiler med identitetsdata för LiveRamp (förhandsversion)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Ordna segment och mått med taggar och filter

Om organisationen har många segment eller åtgärder kan det ibland kännas svårt att hitta rätt. Med den nya funktionen kan du ordna listor med hjälp av taggar och kolumner. Det hjälper dig att snabbt och enkelt hitta data och anpassa vyerna.

Mer information finns i [Arbeta med taggar och kolumner](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Aktivera datadelning med Dataverse när du använder ditt eget lagringskonto

Om din miljö använder Azure Data Lake Storage för att lagra Customer Insights-data, kommer datadelning med Microsoft Dataverse att kräva viss extra konfiguration.
Tidigare kunde du bara aktivera datadelning med Dataverse när dina data lagrades i vår hanterade datasjö.

För mer information, se [Aktivera datadelning med Dataverse från en egen Azure Data Lake Storage (förhandsversion)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nya exportmål: Iterable och Braze

Vi fortsätter att utöka vårt ekosystem av exportdestinationer med nya förbindelser. Nu kan du exportera segment till Iterable och Braze för att använda deras aktiveringstjänster.

Mer information finns i [Exportera segment till iterable (förhandsversion)](export-iterable.md) och [Exportera segment till Braze (förhandsversion)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Förbättringar av exporten av Marketo och Google Ads

Om API:er för anslutna tjänster ändras leder det till att uppdateringar för anslutningar körs som de ska. Vi har gett ut några uppdateringar för exporten till Marketo- och Google Ads-tjänster:

- Google Ads: Den nya versionen av exportkontakten för Google Ads förenklar autentiseringen och nu kan du skapa nya Google Ads-målgrupper automatiskt. 
- Marketo: Den nya versionen av Marketo-exportkontakten ger stöd för Marknads-ID:t, så att du kan undvika dubbletter, uppdatera befintliga poster och skapa nya poster i Marketo. 

## <a name="february-2022-updates"></a>Uppdateringar i februari 2022

Uppdateringarna i februari 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="general-availability-for-prediction-models"></a>Allmän tillgänglighet för prediktionsmodeller

Färdiga prediktionsmodeller, inklusive **prenumerationsomsättning**, **transaktionell omsättning** och **Kundens livstidsvärde (CLV)** bli allmänt tillgänglig som en del av Customer Insights. 

Mer information finns i [Översikt över prediktioner](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Ny datakälla: Integrering med Azure Synapse Analytics (förhandsgranskning)

Azure Synapse Analytics är en företagsanalystjänst som skyndar på tiden till insikter i datalager och stordatasystem.

Organisationer som redan använder Azure Synapse Analytics kan hämta data till Customer Insights. 

Mer information, se [Ansluta en Azure Synapse datakälla (förhandsversion)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Berikning av LiveRamp (förhandsversion)

LiveRamp anger identitetsmatchning och konsoliderar kunddata. Du kan mappa personliga identifierare i dina kunddata till identitetsdiagrammet AbiliTec och ta emot AbiliTec ID. Därefter kan du använda de här ID:erna för att bättre ta fram kunddata.

Mer information finns i [Berika kundprofiler med identitetsdata för LiveRamp (förhandsversion)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Berika för datakällor (förhandsversion)

Använd data från källor som Microsoft och andra partner för att utöka dina kunddata innan data förenas. Berikning av datakälla ger bättre dataresultat och högre kvalitet som kan hjälpa till att uppnå bättre resultat när dina data har förenats.

Mer information: [Berikande för datakällor (förhandsversion)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Byt ägare till miljön

Flera användare kan ha administratörsbehörigheter i Customer Insights, men bara en användare är ägare till en miljö. En bättre upplevelse innebär att du kan byta ägare till en miljö och göra anspråk på ägarskap om en tidigare ägare har lämnat organisationen. 

Mer information finns i [Ändra ägaren till en miljö](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Dataförberedelseprocessen visar orsaker till skadade poster

Dataförberedelse visar nu orsaken till att alla fält med skadade data används. Informationen tillhandahålls på individuell postnivå för enkel identifiering. 

Mer information: [Skadad datakälla](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Slutet på förhandsgranskning för rapportfunktioner i funktionerna för engagemangsinsikter

Förhandsversionen med engagemangsinsikter i Dynamics 365 Customer Insights tog slut den 15 februari 2022.  
Den här förändringen innebär att utvärderingsversionen av Customer Insights inte längre omfattar möjligheten att skapa trattar eller andra rapporteringsfunktioner.

Vi bjuder in dig att utforska och utvärdera de många andra funktionerna i [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), Microsofts plattform för kunddata (CDP).    
 
Under en övergångsperiod har befintliga förhandsversionsdeltagare fortfarande tillgång till vissa förhandsversionsfunktioner:

- Hämta kod till instrument för en webbplats eller mobilapp 
- Visa händelser och händelseegenskaper 
- Förbättra enhetliga profiler med inmatade och förfinade händelser för att dra nytta av det fullständiga värdet av deras kunddata
  
Under övergångsperioden strömmas händelser fortfarande till ansluten Data Lake. När den här funktionen är inaktiverad stoppas datadelning och inga nya händelser skickas till det anslutna lagringsutrymmet.
Kontakta ditt Microsoft-kontoteam direkt om du har frågor om slutet på förhandsversionen av funktionerna. Ditt kontoteam håller dig uppdaterad om kommande lanseringar. 

## <a name="january-2022-updates"></a>Uppdateringar januari 2022

Uppdateringarna i januari 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Attitydanalys av din kunds feedback

Customer Insights innehåller en ny AI-driven funktion som kan syntetisera kundattityder och identifiera specifika affärsaspekter som affärsmöjligheter för målinriktade förbättringar. Genom att analysera den skriftliga feedbacken från dina kunder kan du få korrekta insikter till låg kostnad. Attitydanalys med NLP-modeller (Natural Language Processing) som genererar två härledda insikter för varje kund-ID. En attitydpoäng (från –5 till 5) och en lista över tillämpliga affärsaspekter. 

Mer information finns i [Analysera attityd i kundfeedback (förhandsversion)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]