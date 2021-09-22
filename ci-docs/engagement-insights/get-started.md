---
title: Komma igång med funktionen engagemangsinsikter
description: En översikt över hjälpresurser som hjälper dig att snabbt komma igång.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405380"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Komma igång med funktionen Dynamics 365 Customer Insights engagemangsinsikter (allmänt tillgänglig förhandsversion)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med funktionen för Engagemangsinsikter kan du samla in och mäta kundbeteende på webbplatsen. Den integrerar målgruppinsikter så att du kan se funktionsanalyser i realtid tillsammans med kundprofilrapporter. Länkarna i den här artikeln hjälper dig att snabbt konfigurera och konfigurera miljön.

## <a name="step-1-review-prerequisites"></a>Steg 1: Granska krav

Först måste du ha ett aktivt Microsoft Azure Active Directory-användarkonto. Läs sedan följande artiklar innan du anger en arbetsyta med engagemangsinsikter.

- Granska och godkänna [tjänstvillkor](terms-of-service.md) med Microsoft.  
- Läs artikeln [Hantera cookies och användarmedgivande](user-consent-storage.md). När du har granskat den här artikeln bör du utvärdera om du måste uppdatera din avisering om användarmedgivande. Om du tidigare inte hade några "icke-nödvändiga" cookies kommer du troligen att behöva uppdatera din webbplatspolicy.
- Läs [ordlistan](glossary.md) och få en snabb introduktion till viktiga termer och begrepp.

## <a name="step-2-explore-engagement-insights"></a>Steg 2: Utforska engagemangsinsikter

Första gången du besöker engagemangsinsikter kan du konfigurera inställningar, granska principer och utforska produkten.

1. Logga in på [portalen för engagemangsinsikter](https://pi.dynamics.com) med ditt Microsoft Azure Active Directory-konto. (Det kan vara ditt skol- eller arbetskonto.)

1. Markera din region och använd kryssrutan för att ange om du vill få uppdateringar och erbjudanden via e-post.

1. Granska **Engagementinsikter (förhandsversion) användningsvillkoren** och **Sekretesspolicy** och välj sedan **Utforska demonstrationen** för att acceptera.

1. Utforska produkten med hjälp av en uppsättning exempeldata.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Steg 3: Konfigurera en arbetsyta och lägg till kod på webbplatsen

På arbetsytan kan du visa användaraktiviteter i realtid och lagra och hantera rapporter. Lägg till kod på webbplatsen för att börja samla in *händelser*, aktivitetsdata som kommer in från användare.

1. [Skapa ett arbetsyta](create-workspace.md) och lägg till medlemmar.

1. [Lägg till kod på webbplatsen](instrument-website.md) eller i [mobilappen](developer-resources.md#capture-events-from-mobile-apps) om du vill visa användaraktivitet som kommer till arbetsytan.

1. Visa en [realtidsrapport](view-reports.md) visar aktiva användare efter webbläsare, enhet, operativsystem, plats och språk. Du kan också skapa [anpassade rapporter](custom-reports.md) för att skapa dina egna visualiseringar.
    
## <a name="step-4-export-data-to-other-channels"></a>Steg 4: Exportera data till andra kanaler

Du kan skapa *förfinade händelser* (en virtuell vy) med dina webbanalysdata. Filtrera sedan och exportera data till Azure Data Lake Storage. Du kan hitta exporterade data som en datakälla. Mer information finns i [Skapa en länk mellan målgruppsinsikter och engagemangsinsikter](integrate-audience-insights-engagement-insights.md).

1. [Skapa förfinade händelser](refined-events.md) för export.

1. [Exportera data](export-events.md) till Data Lake Storage.

1. Lär dig hur du [tar bort och exporterar händelsedata som innehåller personuppgifter](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Steg 5: Var uppkopplad

Vi uppskattar ditt aktiva deltagande och planerar att överväga all relevant feedback när vi utvecklar framtida versioner. Dela dina feedback- och rapportproblem via någon av dessa kanaler:
- [Webbgrupp](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Ge feedback](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Begära support](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
