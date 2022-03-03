---
title: Komma igång med funktionen engagemangsinsikter
description: En översikt över hjälpresurser som hjälper dig att snabbt komma igång.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225628"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Komma igång med funktionen Dynamics 365 Customer Insights engagemangsinsikter (allmänt tillgänglig förhandsversion)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med funktionen för Engagemangsinsikter kan du samla in och mäta kundbeteende på webbplatsen. Den integrerar målgruppinsikter så att du kan se funktionsanalyser i realtid tillsammans med kundprofilrapporter. Länkarna i den här artikeln hjälper dig att snabbt konfigurera och konfigurera miljön.

## <a name="step-1-review-prerequisites"></a>Steg 1: Granska krav

Först måste du ha ett aktivt Microsoft Azure Active Directory-användarkonto (AAD). Läs sedan följande artiklar innan du anger en arbetsyta med engagemangsinsikter.

- Granska och godkänna [tjänstvillkoren](terms-of-service.md) med Microsoft.  
- Läs artikeln [Hantera cookies och användarmedgivande](user-consent-storage.md). Utvärdera sedan om du behöver uppdatera ditt meddelande om användargodkännande. Om du tidigare inte hade några "icke-nödvändiga" cookies kommer du troligen att behöva uppdatera din webbplatspolicy.
- Läs [ordlistan](glossary.md) och få en snabb introduktion till viktiga termer och begrepp.

## <a name="step-2-explore-engagement-insights"></a>Steg 2: Utforska engagemangsinsikter

Första gången du besöker engagemangsinsikterna kan du konfigurera inställningar, granska policyer och utforska funktionen.

1. Logga in på [funktionsportalen för engagemangsinsikter](https://home.ci.ai.dynamics.com/app/engagement-insights) med ditt Microsoft AAD-konto (skola eller arbete).

1. Markera din region och markera sedan kryssrutan om du vill få uppdateringar och erbjudanden via e-post.

1. Granska **Användarvillkoren** för engagemangsinsikter (förhandsversion) samt **Sekretesspolicyn** och välj sedan **Utforska demonstrationen** för att godkänna dessa inställningar.

1. Utforska produkten med hjälp av en uppsättning exempeldata.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Steg 3: Konfigurera en arbetsyta och skapa rapporter

På en arbetsyta kan du visa användaraktiviteter i realtid, samt lagra och hantera rapporter. Lägg till kod på webbplatsen för att börja samla in *händelser*, aktivitetsdata som kommer in från användare.

1. [Skapa ett arbetsyta](create-workspace.md) och lägg till medlemmar.

1. Lägg till kod på [webbplatsen](instrument-website.md) eller i [mobilappen](developer-resources.md#capture-events-from-mobile-apps) om du vill visa användaraktivitet som kommer till arbetsytan.

1. Visa en [realtidsrapport](view-reports.md) som visar aktiva användare efter webbläsare, enhet, operativsystem, plats och språk. Du kan också skapa [anpassade rapporter](custom-reports.md) för att skapa dina egna visualiseringar.

1. Skapa [dimensioner](dimensions.md) för att sortera besökare efter nya och återkommande användare, [mått](metrics.md) för att bättre förstå användarens beteende och [segment](segments.md) för att identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner.
    
## <a name="step-4-export-data-to-other-channels"></a>Steg 4: Exportera data till andra kanaler

Du kan skapa *förfinade händelser* (en virtuell vy) med dina webbanalysdata. Filtrera sedan och exportera data till Azure Data Lake Storage. Du kan hitta exporterade data som en datakälla.

1. [Skapa förfinade händelser](refined-events.md) för export.

1. [Exportera data](export-events.md) till Azure Data Lake Storage.

1. [Skapa en länk mellan målgruppsinsikter och engagemangsinsikter](integrate-audience-insights-engagement-insights.md) om du vill dela data mellan de två funktionerna.

1. [Identifiera webbhändelser från tidigare autentiserade användare](unknown-to-known.md) med funktionen **okända till kända**.

1. Lär dig hur du [tar bort och exporterar händelsedata som innehåller personuppgifter](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Steg 5: Skapa och hantera trattrapporter

I en trattrapport samlas information om de steg som sker i samband med kundens färd via webbplatsen eller mobilappen. Förutom att skapa färdiga profilrapporter och anpassade rapporter kan du skapa en trattrapport för att identifiera vilka sökvägar kunderna tar innan de gör ett köp. 

1. [Skapa en trattrapport](funnel-reports.md) för att informera om beslut och identifiera områden för optimering och processförbättringar.

1. Skapa kanaltrattrapporter när du har instrumenterat mobilappen med engagemangsinsikter [Android SDK](get-started-android.md) eller [iOS SDK](get-started-ios.md).

1. Använd [trattinsikter](funnel-reports.md#funnel-insights) om du vill få en djupare inblick i kundbeteendet om stegen i trattrapporten.
 
## <a name="step-6-stay-connected"></a>Steg 6: Var uppkopplad

Vi uppskattar ditt aktiva deltagande och överväger all relevant feedback när vi utvecklar framtida versioner. Dela dina feedback- och rapportproblem via någon av dessa kanaler:
- [Webbgrupp](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Ge feedback](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Begära support](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
