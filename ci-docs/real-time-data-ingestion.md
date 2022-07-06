---
title: Datainmatning i realtid (förhandsversion)
description: Allmän information om realtidsfunktioner i Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 39d68011df9e4341244af627bb71f4e3635256bb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082007"
---
# <a name="real-time-data-ingestion-preview"></a>Datainmatning i realtid (förhandsversion)

Med funktionen nästan i realtid kan du se inom några sekunder de senaste interaktionerna som dina kunder har gjort med dina produkter eller tjänster.

[Schemalagda uppdateringar](system.md#schedule-tab) omfattar ett stort antal poster och flera komplexa operationer. Först hämtas data från datakällan. Därefter är informationen enhetlig och sedan utökad med ytterligare information. Alla körningar av den här processen kan ta minuter till timmar.

Realtidsfunktionen ger data omedelbart för förbrukning, tills den efterföljande schemalagda uppdateringen hämtar dessa data från datakällan.

Uppdateringar i realtid har en förfallotid efter att de inte längre ersätter värdet från datakälla:

- Profiluppdateringar sparas i 4 timmar
- Aktiviteter sparas i 30 dagar

Dessa värden är parametrar för API-anrop som du kan ändra. De syftar till att se till att dina källdata förblir källan för sanningen. Om du vill att uppdateringar i realtid ska ingå längre, måste du lägga till dem i en datakälla så att de hämtas under nästa schemalagda uppdatering.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Uppdatering i realtid av fälten för en enhetlig kundprofil

Uppdaterade profiler kommer att visas i kundkortsvyn, eller någon annan visualisering, inom några sekunder.

Eftersom realtidsåtgärder utförs efter att dataföreningen har inträffat gäller de bara för enhetliga kundprofiler. Ändringar i realtidsprofilen uppdaterar därför inte åtgärder, segmentmedlemskap och berikningar.

### <a name="limitations"></a>Begränsningar

- Kundprofiler kan uppdateras men inte skapas eller tas bort.
- Det är inte möjligt att exportera uppdateringar i realtid till externa system Power BI just nu.

## <a name="real-time-creation-of-activities"></a>Skapande av aktiviteter i realtid

Med realtids-API kan du publicera en ny aktivitet från ditt källsystem (en enskild källpost) till en enhetlig kundprofil. Den nya aktiviteten blir tillgänglig som en enhetlig aktivitet i den enhetliga kundprofilens tidslinje inom några sekunder. Du kan se tidslinjen i kundkortsvyn eller någon annan tidslinjeintegrering som du konfigurerade.

> [!NOTE]
>
> - Aktiviteter är oföränderliga. De ändras inte när de har skapats.
> - För närvarande uppdateras inte segment och mått baserat på den nya aktiviteten.
> - Aktiviteter som endast lagts till via API i realtid ingår inte i exporten och visas inte i PowerBI.

Du kan ansluta till realtids-API:et på två sätt:

- [indirekt](#connect-via-the-dynamics-365-customer-insights-connector) med hjälp av [Dynamics 365 Customer Insights koppling](/connectors/customerinsights/)
- [direkt](#connect-directly-to-the-real-time-api), med kod

Båda sätten delar följande förutsättningar:

- En Customer Insights-miljö
- Enhetliga kundprofiler
- Aktiviteter som har konfigurerats och körs
- Verifiera ditt konto genom att deltagare eller administratörsbehörigheter

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Anslut via Dynamics 365 Customer Insights kopplingen

API i realtid kan hämta data från en dedikerad Power Platform-koppling, [Dynamics 365 Customer Insights-koppling](/connectors/customerinsights/) utan att någon kod behöver skrivas och distribueras.    
Kopplingen kan utföra samma realtidsåtgärder som API. Du behöver en giltig licens för Premium-anslutningar. Mer information finns i [Vanliga frågor om licensiering för Power Apps och Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps och/eller Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Mer information om hur du skapar flöden finns i [Power Automate-dokumentationen](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Anslut direkt till API i realtid

Du kan använda realtidsfunktionerna genom att bygga en egen pipeline och ansluta direkt till realtids-API:et.    
Du kan publicera en aktivitet i formatet för ditt källsystem eller i UnifiedActivity-format. Visa formatet genom att göra ett API-anrop till /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Detaljer om detta API, inklusive parametrar och svar, finns i avsnittet **EntityData** på [referensen Customer Insights-API:er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Mer information finns i [Arbeta med Customer Insights-API:er](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Förstå din realtidsförbrukning med telemetri

Få en översikt över volymen av begäranden till realtids-API och information om problem som systemet kan stöta på. Du kan [komma åt telemetri i realtid](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]