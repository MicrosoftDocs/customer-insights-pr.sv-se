---
title: Hantera okända profiler med Customer Insights
description: Arbeta med okända kundprofiler som skapas och hanteras i Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556418"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Hantera okända profiler med Customer Insights

Internetanvändare är ofta oidentifierade och anonyma online. Om de inte är inloggade eftersom de använder olika enheter eller kanaler är det till och med sant för de mest lojala kunderna. Om tredjeparts cookies snart kommer bort är det viktigt att du hanterar användarinställningar utifrån informationen från första part för att få till en personligt anpassad upplevelse. För många är kända och autentiserade användare de föraktade, trots de ökande kundförväntningarna när det gäller personlig anpassning. Det är bra för företag att veta vilka deras kunder är, baserade på tillförlitliga, detaljerade och enhetliga data.

För personlig anpassning av kundernas behov beror det på om dina kunddata och Customer Insights är fullständiga och hjälper dig att uppnå dessa mål. Du behöver inte begränsa eller stoppa användningen av data som samlas in i början av kundens färd. Med Customer Insights kan du hämta dina egna data för att skapa en kundprofil för okända användare. Du kan sedan använda den profilen för ytterligare åtgärder, trots att kontaktinformation saknas. Importera data från första part från källor som webb-, mobil- eller CRM-system till Customer Insights för att kontinuerligt utöka kundprofiler. När du enar fler interaktioner kan du [göra den *okända* kunden till en *känd* kund](unknown-to-known.md).

## <a name="sample-scenario"></a>Exempelscenario

E-handeln är den snabbast växande kanalen under den senaste tiden. Anta att en användare använder sin mobila enhet för att bläddra på e-handelsplatsen. På webbplatsen tilldelas besökaren "mobile_guest123" som en unik identifierare och du börjar samla in beteendeaktiviteter baserat på deras onlineaktivitet. Till exempel vilka sidor de har besökt, hur mycket tid de lade ned på sidorna eller vilka länkar de klickade på. Du känner inte till deras namn eller e-postadress, men dessa data kan hjälpa till att ge viktiga insikter om den här specifika användaren. Du kan i sin tur sätta dessa insikter i arbete nästa gång användaren besöker webbplatsen. Fråga Customer Insights efter mobile_guest123 om du vill hämta användarens segmentlista, till exempel "mobila förbeställningskunder", "kunder med högt värde", eller hämta profilen för att skapa anpassade webbupplevelser. Du kan också exportera data till ett aktiveringssystem för att göra samma sak.

## <a name="prerequisites"></a>Förutsättningar

- Mata in data från första part i Customer Insights
- Varje entitet har ett unikt ID som anges som primärnyckel
- Varje entitet med en primärnyckel för personlig anpassning är enhetlig
- Innehållets hanteringssystem på din webbplats kan använda API:er (för webbanpassning utifrån direkt kommunikation med Customer Insights)

I följande tabell visas ett förenklat exempel på hur webbhändelser med högt värde kan fångas in.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Produktvy|
|2|09-18-2022 10:05:00|abc123|CookieID1|Produktvy|
|3|09-18-2022 10:10:00|abc123|CookieID1|Lägg till i vagn|
|4|09-21-2022 09:05:00|abc123|CookieID1|Produktvy|

## <a name="data-ingestion"></a>Datainsamling

För mer information om tillgängliga alternativ för datainmatning, se [Översikt över datakällor](data-sources.md).

## <a name="data-unification"></a>Dataförening

Mer information om att ena dina kundprofiler finns i [Översikt över datasammanslutning](data-unification.md).

## <a name="get-insights"></a>Skaffa insikter

[Utöka](enrichment-hub.md) data, skapa [mått](measures.md) och skapa segment [för](segments.md) ytterligare aktivering.

Du kan till exempel skapa segment av okända användare som bläddrade på samma produktsidor men som aldrig slutförde utcheckningen.

## <a name="activation"></a>Aktivering

Med dina data i Customer Insights och dina insikter redo att börja arbeta kan du använda Customer Insights för personlig anpassning:

1. Använd [OData API](apis.md) för att hämta ett segmentmedlemskap eller kundprofil. För fler exempel, se [OData-frågeexempel för Customer Insights API:er](odata-examples.md).

1. [Exportera](export-destinations.md) data till dina aktiveringssystem.

Exempel: En okänd användare besöker en webbplats flera gånger och besöker produktsidor för olika modellexempel. Med de data som finns tillgängliga i Customer Insights kan du inkludera den okända användaren i det segment av personer som är intresserade av att bli Customer Insights. Använd det här avsnittet om du vill informera din webbplats om hur du skapar personlig anpassning för återkommande besökare. Vid nästa besök känner webbplatsen igen den okände användaren och kan erbjuda dem en tioprocentig rabatt på skador.

[!INCLUDE [footer-include](includes/footer-banner.md)]
