---
title: Arbeta med affärskonton
description: Lär dig om affärskonton som primär målgrupp i Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303938"
---
# <a name="work-with-business-accounts"></a>Arbeta med affärskonton

Med Dynamics 365 Customer Insights kan du konfigurera miljön för olika primära målgrupper: enskilda konsumenter (B2C) och affärskonton (B2B). I B2C-scenarier är informationen centrerad kring enskilda personer. För B2B är den primära målgruppen konton – organisationer eller företag – och kontakter. Den här artikeln innehåller information om hur du kommer igång med en miljö för företagskonton. Den visar skillnaderna mellan funktionsområdena i Customer Insights, beroende på ditt miljöfokus. Mer information om skillnader finns i dokument för funktionsområdena. 

## <a name="create-an-environment-for-business-accounts"></a>Skapa en miljö för företagskonton

Administratörer kan [skapa en miljö i en befintlig organisation](create-environment.md). Ett steg i processen med att skapa en ny miljö ber administratörer om miljöns primära målgrupp. Om det är den första konfigurationen efter att du har köpt en licens, hjälper en guidad upplevelse med skapandet av den första miljön.

Därefter kan du [hämta data](data-sources.md) för affärskonton och relaterade kontakter som datakällor från alla källor som stöds.

 [Förena](data-unification.md) dina kontodata följt av kontaktdata genom att koppla kontakt- och kontoentiteter.

## <a name="switch-between-primary-target-audience"></a>Växla mellan primär målgrupp

Om organisationen har miljöer för enskilda kunder och affärskonton kan du använda växlaren i den vänstra rutan för att välja den primära målgruppen.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Växlare för att ändra den primära målgruppen mellan enskilda kunder och affärskonton.":::

## <a name="supported-feature-areas"></a>Funktionsområden som stöds

- [Aktiviteter](activities.md): Stöd för konton och relaterade kontakter för att skapa aktiviteter och visa dem i en tidslinje.
- [Relationer](relationships.md): Med aktivitetsguiden kan du skapa relationer mellan entiteterna så att alla aktiviteter från kontakter kan visas i kontovyn. Kontaktpersoner kan öka detaljvyn för att visa kontaktvyn och hierarkier kan användas för sammansättning av kontoaktivitet.
- [Mått](measures.md): Stöd för mått som skapats från måttverktyget med en beräkning. En valfri inställning tillåter sammanslagning för underkonton när åtgärder skapas.
- [Segment](segments.md): Stöd för segment som skapas från grunden med segmentverktyget. Segment kan grundas på konton eller kontakter.
- [Datainmatning](data-sources.md): Alla funktioner i det här området är samma för affärskonton och enskilda kunder.
- B2B-data är mycket lika med B2C-data, men har ytterligare ett steg för att ena kontakterna efter kontot. Se [Företagskonton (B2B)](data-unification.md).
- [Berikning](enrichment-hub.md): Vissa berikningstyper är endast tillgängliga för enskilda kundscenarier medan andra är endast tillgängliga för affärskonton.
- [Prediktioner och färdiga modeller](predictions-overview.md): Prediktion innehåller ytterligare steg för affärskonton. Andra prognoser är endast tillgängliga för enskilda kunder.
- [Aktivering och export](export-destinations.md): Export är tillgängliga för företagskonton och enskilda kunder. För vissa exporter krävs extra konfigurations- och kontaktinformation som projiceras i de underliggande segmenten för att kunna användas för affärskonton.
- [Systeminställningar](system.md) och [användarhantering](permissions.md): Alla funktioner i det här området är samma för affärskonton och enskilda kunder.

[!INCLUDE [footer-include](includes/footer-banner.md)]
