---
title: Komma igång med affärskonton som primär målgrupp
description: Lär dig om affärskonton som primär målgrupp Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353565"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Arbeta med affärskonton i målgruppsinsikter

Med målgruppsinsikter i Dynamics 365 Customer Insights kan du konfigurera miljön för olika primära målgrupper: enskilda konsumenter (B2C) och affärskonton (B2B). I B2C-scenarier är informationen centrerad kring enskilda personer. För B2B är den primära målgruppen konton – organisationer eller företag – och kontakter. Den här artikeln innehåller information om hur du kommer igång med en miljö för företagskonton. Den visar skillnaderna mellan funktionsområdena i målgruppsinsikter, beroende på ditt miljöfokus. Mer information om skillnader finns i dokument för funktionsområdena. 

## <a name="create-an-environment-for-business-accounts"></a>Skapa en miljö för företagskonton

Administratörer kan [skapa en miljö i en befintlig organisation](create-environment.md). Ett steg i processen med att skapa en ny miljö ber administratörer om miljöns primära målgrupp. Om det är den första konfigurationen av målgruppsinsikter efter att du har köpt en licens, hjälper en guidad upplevelse med skapandet av den första miljön.

Därefter kan du [hämta data](data-sources.md) för affärskonton och relaterade kontakter som datakällor från alla källor som stöds.

När data har enats [anger du kontohierarkier](relationships.md#set-up-account-hierarchies) som en del av relationskonfigurationen. Du kan också [konfigurera semantiska mappningar](semantic-mappings.md) för att ansluta entiteter för kontakter och konton. 

## <a name="switch-between-primary-target-audience"></a>Växla mellan primär målgrupp

Om organisationen har miljöer för enskilda kunder och affärskonton kan du använda växlaren i den vänstra rutan för att välja den primära målgruppen.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Växlare för att ändra den primära målgruppen mellan enskilda kunder och affärskonton.":::

## <a name="supported-feature-areas"></a>Funktionsområden som stöds

- [Aktiviteter](activities.md): Stöd för konton och relaterade kontakter för att skapa aktiviteter och visa dem i en tidslinje.
- [Relationer](relationships.md): Med aktivitetsguiden kan du skapa relationer mellan entiteterna så att alla aktiviteter från kontakter kan visas i kontovyn. Kontaktpersoner kan öka detaljvyn för att visa kontaktvyn och hierarkier kan användas för sammansättning av kontoaktivitet.
- [Mått](measures.md): Stöd för mått som skapats från måttverktyget med en beräkning. En valfri inställning tillåter sammanslagning för underkonton när åtgärder skapas.
- [Segment](segments.md): Stöd för segment som skapas från grunden med segmentverktyget. Nya operatorer kan införliva kontohierarki när segment byggs.
- [Datainmatning](data-sources.md): Alla funktioner i det här området är samma för affärskonton och enskilda kunder.
- [Samordning av data](data-unification.md): Alla funktioner i det här området är samma för affärskonton och enskilda kunder.
- [Berikning](enrichment-hub.md): Vissa berikningstyper är endast tillgängliga för enskilda kundscenarier medan andra är endast tillgängliga för affärskonton.
- [Prediktioner och färdiga modeller](predictions-overview.md): Prediktion innehåller ytterligare steg för affärskonton. Andra prognoser är endast tillgängliga för enskilda kunder.
- [Aktivering och export](export-destinations.md): Export är tillgängliga för företagskonton och enskilda kunder. För vissa exporter krävs extra konfigurations- och kontaktinformation som projiceras i de underliggande segmenten för att kunna användas för affärskonton.
- [Systeminställningar](system.md) och [användarhantering](permissions.md): Alla funktioner i det här området är samma för affärskonton och enskilda kunder.

