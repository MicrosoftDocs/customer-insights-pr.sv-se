---
title: Komma igång med funktionen för målgruppsinsikter i Dynamics 365 Customer Insights
description: En översikt över målgruppsinsikter hjälper resurser att komma igång snabbt.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466599"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Komma igång med funktionen för målgruppsinsikter i Dynamics 365 Customer Insights

Målgruppsinsikter kan hjälpa dig att bygga en djupare förståelse för dina kunder. Anslut data från olika transaktions-, beteende- och observationskällor om du vill skapa en 360-graders kundvy. Använd dessa insikter för att driva kundinriktade upplevelser och processer. Förena och förstå kunddata och utnyttja dem för intelligenta insikter och åtgärder.

## <a name="step-1-create-an-environment"></a>Steg 1: Skapa en miljö

Till att börja med måste du först skapa en miljö att arbeta i. Om din organisation redan har köpt en licens går du till [Komma igång med en betalad prenumeration](get-started-paid.md). Om du vill starta en utvärderingsversion för målgruppsinsikter, se [Konfigurera en utvärderingsmiljö](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>Steg 2: Utforska målgruppinsikter

Första gången du loggar in bland målgruppsinsikterna kan du konfigurera inställningar och utforska produkten.

1. [Logga in bland målgruppsinsikter](https://home.ci.ai.dynamics.com) med ditt Microsoft Azure Active Directory-användarkonto (AAD).

1. [Ändra miljön](manage-environments.md#switch-environments) om du vill visa demodata och [utforska målgruppsinsikter](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Steg 3: Mata in, förena och konfigurera relationer för dina data

Enhetliga profiler är grunden till att få insikter och vidta åtgärder för dessa data. Hämta data från olika källor och kör processen för datasamordning för att kombinera enhetliga profiler. Ange relationer mellan de inmatade entiteterna med hjälp av utökande funktioner för att lägga till information i profilerna. 

1. Mata in data genom att skapa datakällor från flera alternativ. Välj mellan [Power Query-anslutningsprogram](connect-power-query.md), en [Common Data Model-mapp](connect-common-data-model.md) eller [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Kör [datasamordningsprocessen](data-unification.md) genom att gå igenom faserna [mappa](map-entities.md), [matcha](match-entities.md) och [sammanslå](merge-entities.md).

1. Bekanta dig med de [entiteter som systemet skapar](entities.md) och skapa [relationer mellan de inmatade entiteterna](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Steg 4: Förbättra enhetliga profiler genom förutsägelser, aktiviteter och mått

Med enhetliga profiler konfigurerade kan du förbättra dina data och ytterligare öka den information de tillhandahåller.

1. Välj bland ett expanderande bibliotek med utökningsleverantörer om du vill [utöka dina kunddata](enrichment-hub.md).

1. Använd [färdiga modeller](predictions-overview.md) för att förutsäga omsättningssannolikhet eller förväntad omsättning.

1. [Konfigurera aktiviteter](activities.md) utifrån inmatade data och visualisera interaktioner med dina kunder i en kronologisk tidslinje. 

1. [Versionsmått](measures.md) för att mäta affärsmål och KPI:er.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Steg 5: Skapa segment och aktivera data med hjälp av olika exportalternativ

Nu när dina data är klara och innehåller en mängd information om dina kunder är det dags att leta efter sätt att vidta åtgärder för dessa data. 

1. [Skapa segment](segments.md), underuppsättningar av kundbasen, för att se till att åtgärderna är relevanta för målgruppen.

1. Bläddra i den expanderande katalogen med [exportalternativ](export-destinations.md) där du kan använda kunddata. Du kan till exempel använda data för att hantera kampanjer och nå ut med digital marknadsföring.

1. Granska integreringsalternativ, till exempel med [direkt anslutning till engagemangsinsikter](../engagement-insights/integrate-audience-insights-engagement-insights.md) eller andra Dynamics 365-appar med [tillägget Kundkort](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]