---
title: Nya och kommande funktioner
description: Information om nya funktioner, förbättringar och felkorrigeringar.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547694"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Vad är nytt i funktionen målgruppsinsikter i Dynamics 365 Customer Insights

Vi är glada över att kunna meddela våra senaste uppdateringar! Denna artikel sammanfattar funktioner för allmänt tillgänglig förhandsversion, förbättringar av allmän tillgänglighet och funktionsuppdateringar. Om du vill se de långsiktiga funktionsplanerna, se [utgivningsplaner för Dynamics 365 och Power Platform](/dynamics365/release-plans/).

Vi lanserar uppdateringar en region i taget. Vissa regioner kan se funktioner före andra. Om inget annat anges behöver du inte vidta några åtgärder så uppdateras appen automatiskt utan driftsavbrott.

> [!TIP]
> Skicka in och rösta på funktioner som efterfrågas och produktförslag går du till [Dynamics 365-programmets idéportal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

För mer information, se [Aktivera datadelning med Dataverse från en egen Azure Data Lake Storage (förhandsversion)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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
  
Under övergångsperioden strömmas händelser fortfarande till ansluten Data Lake. När den här funktionen är inaktiverad stoppas datadelning mellan engagemangsinsikter och målgruppsinsikter och inga nya händelser skickas till det anslutna lagringsutrymmet.
Kontakta ditt Microsoft-kontoteam direkt om du har frågor om slutet på förhandsversionen av funktionerna. Ditt kontoteam håller dig uppdaterad om kommande lanseringar. 

## <a name="january-2022-updates"></a>Uppdateringar januari 2022

Uppdateringarna i januari 2022 innehåller nya funktioner, prestandauppgraderingar och felkorrigeringar.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Attitydanalys av din kunds feedback

Customer Insights innehåller en ny AI-driven funktion som kan syntetisera kundattityder och identifiera specifika affärsaspekter som affärsmöjligheter för målinriktade förbättringar. Genom att analysera den skriftliga feedbacken från dina kunder kan du få korrekta insikter till låg kostnad. Attitydanalys med NLP-modeller (Natural Language Processing) som genererar två härledda insikter för varje kund-ID. En attitydpoäng (från –5 till 5) och en lista över tillämpliga affärsaspekter. 

Mer information finns i [Analysera attityd i kundfeedback (förhandsversion)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]