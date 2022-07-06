---
title: Använda enhetliga profiler i Dynamics 365 Marketing
description: Läs om hur du integrerar enhetliga profiler och segment med Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054454"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Använda enhetliga kundprofiler i Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) förhöjer kundupplevelsen, så att du kan orkestrera personliga resor över alla beröringspunkter för att stärka relationer och tjäna lojalitet. Dynamics 365 Marketing-appen fungerar sömlöst med Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams och andra produkter, och låter dig fatta snabbare och bättre beslut med hjälp av kraften i data och AI.

Genom att ansluta Customer Insights-data till Marketing kan du:

- Rikta in dig på enhetliga kundprofiler och segment. Detta gör att du kan engagera varje kund, oavsett var kundens data finns.
- Basera dynamiskt innehåll (till exempel anpassade token) i e-postmeddelanden, SMS och push-meddelanden om åtgärder som lojalitetsstatus, datum för prenumerationsförnyelse, överordnat konto eller något annat mått som du har hämtat i den enhetliga Customer Insights-profilen.
- Läsa in data från Marketing till Customer Insights och kombinera dem med kunddata från andra källor.
- Använda Customer Insights verktyg för datarensning, berikning och fuzzy-matchning.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Använd rika kundprofiler och segment i realtidsmarknadsföring

Med realtidsmarknadsföring kan du skapa [anpassade utlösare](/dynamics365/marketing/real-time-marketing-custom-triggers) som startar kundresor baserat på alla kundåtgärder. Ju mer personlig dina data är, desto mer relevanta och personliga kommer dina resor att vara. Det är det som gör kombinationen av Marketing och Customer Insights så kraftfull. Du kan [förena data](data-unification.md) från vilken källa som helst och sedan använda den för att driva extremt anpassade kundresor.

Läs mer: [Använd Customer Insights-profiler och segment i realtidsmarknadsföring](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Använda enhetliga segment med utgående kundresor

Customer Insights låter dig förfina data från många källor och kombinera dem till aggregerade kundsegment. Genom att [koppla Customer Insights till utgående marknadsföring](export-dynamics365-marketing.md) visas dessa segment automatiskt *och* uppdateras automatiskt i kundens färd designer.

Läs mer: [Använd segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Hämta data från din egen Azure Data Lake Storage

Du är inte begränsad till molnlagring om du vill använda Customer Insights-data med Marketing. Om du redan har din egen Azure Data Lake Storage-konfiguration kan du ansluta till Customer Insights och sedan dela data med Marketing-appen precis som du skulle göra med en molnbaserad installation.

Läs mer: [Aktivera datadelning med Dataverse från din egen Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)