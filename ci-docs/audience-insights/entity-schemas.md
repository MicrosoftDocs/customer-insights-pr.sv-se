---
title: Entitetsschema i Customer Insights i Common Data Model
description: Arbeta med entiteter i Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596383"
---
# <a name="entity-schemas-in-common-data-model"></a>Entitetsscheman i Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) är en deklarativ specifikation och en definition av standardenheter som representerar vanligt använda koncept och aktiviteter i olika affärs- och produktivitetsapplikationer. Denna modell utökas till att även omfatta observations- och analysuppgifter. Common Data Service tillhandahåller väldefinierade, modulära och utökningsbara affärsentiteter som Konto, Affärsenhet, Ärende, Kontakt, Lead, Affärsmöjlighet och Produkt, samt interaktioner mellan leverantörer, anställda och kunder (till exempel aktiviteter och serviceavtal). Alla kan bygga på och utöka Common Data Model-definitioner för att samla in fler affärsspecifika idéer.

Det här är en delad datamodell som gör att program och dataintegrerare kan samarbeta enklare genom att skapa en enhetlig definition av data. Common Data Model innehåller ett avancerat metadatasystem med standardentiteter, relationer, hierarkier, egenskaper och mycket mer. Det härstammar från Dynamics 365-appar och har öppnats på GitHub med över 260 standardentiteter. Ett stort system för interna och externa partner bidrar branschspecifika koncept till den Common Data Model.

Flera system och plattformar implementerar Common Data Model i dag, inklusive Power BI dataflöden och Azure Data Services. Det stöds redan i Common Data Service, Dynamics 365, Power Apps, Power BI och kommande Azure Data Services, direkt tillfalla värde mot [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Entitetsscheman för Customer Insights

För att skapa en 360-gradersvy av kunden och göra Customer Insights-modeller tillgängliga i Common Data Model för utvidgning har vi publicerat följande enhetsscheman:

| Entitet | Beskrivning |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | En aktivitet som utförs av en användare och har ett observationsvärde till företaget. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | En person eller organisation som antingen utförts eller har möjlighet att delta i en affärsaktiviteter. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definition av KPI:er partitionerade efter noll eller fler dimensioner (t.ex. månatliga aktiva användare, totala utgifter per kund, genomsnittlig kostnad för kundanskaffning) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definierar en grupp med medlemmar med gemensamma egenskaper. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Medlemmar som ingår i ett visst segment. |

Mer information finns i dokumentationen om [Entitetsscheman för Customer Insights i Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Visa entiteter med hjälp av entitetsnavigering för Common Data Model

Du kan visa entiteter i [Common Data Models entitetsnavigeringsverktyg](https://microsoft.github.io/CDM/). Välj **Läs in från GitHub!** och navigera till **foundationCommon** > **crmCommon** > **lösningar** > **customerInsights** där du hittar listan med Customer Insights-entiteter och deras definitioner.
> [!div class="mx-imgBorder"]
> ![CDM entitetsnavigeringsverktyget visar entiteten CustomerActivity](media/CDM-entity-navigator.png "CDM entitetsnavigeringsverktyget visar entiteten CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]