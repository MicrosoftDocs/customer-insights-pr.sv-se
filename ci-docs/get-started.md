---
title: Komma igång med Dynamics 365 Customer Insights
description: En översikt över Customer Insights hjälper resurser att komma igång snabbt.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 68c26eb0ad0da787a9f594b4aebe679588b0d6bf
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833597"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Komma igång med Dynamics 365 Customer Insights

Customer Insights kan hjälpa dig att bygga upp en djupare förståelse för dina kunder. Anslut data från olika transaktions-, beteende- och observationskällor om du vill skapa en 360-graders kundvy. Använd dessa insikter för att driva kundinriktade upplevelser och processer. Förena och förstå kunddata och utnyttja dem för intelligenta insikter och åtgärder.

## <a name="step-1-create-an-environment"></a>Steg 1: Skapa en miljö

Skapa först en miljö att arbeta i. Om din organisation redan har köpt en licens finns mer information i [Skapa en miljö](create-environment.md). Om du vill starta en utvärderingsversion av Customer Insights, se [Konfigurera en utvärderingsmiljö](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Steg 2: Utforska Customer Insights

Första gången du loggar in i Customer Insights kan du konfigurera inställningar och utforska produkten.

1. [Logga in på Customer Insights](https://home.ci.ai.dynamics.com) med ditt Microsoft Azure Active Directory (AAD) användarkonto.

1. Ändra miljön för att visa demodata och [utforska Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Steg 3: Mata in, förena och konfigurera relationer för dina data

Enhetliga profiler är grunden till att få insikter och vidta åtgärder för dessa data. Hämta data från olika källor och kör processen för datasamordning för att kombinera enhetliga profiler. Ange relationer mellan införlivade entiteter och lägg till information i profilerna med hjälp av tilläggsfunktioner.

1. Mata in data genom att skapa datakällor från flera alternativ. Välj mellan [Power Query-anslutningar](connect-power-query.md), en [Common Data Model-mapp](connect-common-data-model.md) eller [Microsoft Dataverse](connect-dataverse-managed-lake.md).

1. Kör [föreningsprocessen för data](data-unification.md) genom att identifiera [källfälten](map-entities.md), ta bort [dubbletter](remove-duplicates.md), [matchningsvillkor](match-entities.md), och [förenande fält](merge-entities.md)

1. Bekanta dig med de [entiteter som systemet skapar](entities.md) och skapa [relationer mellan de inmatade entiteterna](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Steg 4: Förbättra enhetliga profiler genom förutsägelser, aktiviteter och mått

Med enhetliga profiler konfigurerade kan du förbättra dina data och ytterligare öka den information de tillhandahåller.

1. Välj bland ett expanderande bibliotek med utökningsleverantörer om du vill [utöka dina kunddata](enrichment-hub.md).

1. Använd [färdiga modeller](predictions-overview.md) för att förutsäga omsättningssannolikhet eller förväntad omsättning.

1. [Konfigurera aktiviteter](activities.md) utifrån inmatade data och visualisera interaktioner med dina kunder i en kronologisk tidslinje.

1. [Versionsmått](measures.md) för att mäta affärsmål och KPI:er.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Steg 5: Skapa segment och aktivera data med hjälp av olika exportalternativ

Nu när dina data är klara och innehåller en mängd information om dina kunder kan du leta efter sätt att vidta åtgärder för dessa data.

1. [Skapa segment](segments.md), underuppsättningar av kundbasen, för att se till att åtgärderna är relevanta för målgruppen.

1. Bläddra i den expanderande katalogen med [exportalternativ](export-destinations.md) där du kan använda kunddata. Du kan till exempel använda data för att hantera kampanjer och nå ut med digital marknadsföring.

1. Granska integrationsalternativen, till exempel andra Dynamics 365-appar med [tillägget Kundkort](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
