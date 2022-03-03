---
title: Visa datarapporter
description: Använd de tillgängliga rapporterna om du vill visa aktiviteten i realtid på webbplatsen.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 03b0b4bab0d5d9c2ae641c85aac8174ec1668d45
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229762"
---
# <a name="view-reports"></a>Visa rapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En rapport är en samling datavisualiseringar som använder data insamlad genom SDK, som hjälper dig att mäta och förstå användarbeteende. Dynamics 365 Customer Insights-engagemangsinsikter innehåller färdiga rapporter (out-the-box) för webb- och mobila projekt.  

## <a name="web-reports"></a>Webbrapporter

Du kan komma åt webbrapporter under **Identifiera** i det vänstra navigeringsfönstret.

:::image type="content" source="media/report-menu.png" alt-text="Navigering som visar listan över tillgängliga rapporter.":::

### <a name="real-time-usage-report"></a>Användningsrapport i realtid

Rapporten **Användning i realtid** ger en översikt över aktuell aktivitet på webbplatsen som uppdateras automatiskt varje minut. Använd realtidsanvändning för att övervaka marknadsföringskampanjer, presshändelser och andra scenarier som påverkar webbplatsens trafik.

### <a name="key-metrics-reports"></a>Rapporter för nyckelmått

- **Sidvyer** listar sidvyerna för enskilda sidor tillsammans med antalet totala sidvyer sett över den valda tidsramen.

- **Besök** visar information om antalet besök och dessas varaktighet.

- **Besökare** informerar om nya och återkommande unika besökare på webbplatsen.

### <a name="content-reports"></a>Innehållsrapporter

- **Länkar** visar information om antal och typ av klick.

- **Utgångssidor** listar de länkar som besökarna klickat på för att lämna webbplatsen.

### <a name="traffic-sources-reports"></a>Rapporter om trafikkällor

- **Refererare** listar de domäner och URL:er som refererade besökare till webbplatsen.

- **Spårningskoder** innehåller information om spårningskoderna i länkarna som förde besökare till webbplatsen.

### <a name="visitor-profiles-reports"></a>Rapporter över besöksprofiler

- **Enheter** listar de fysiska enheter som använts för att komma åt webbplatsen.

- **Operativsystem och webbläsare** ger insikter i de operativsystem och webbläsare som kördes när du kom åt webbplatsen.

- **Platser** visar information om besökare efter land, region och ort.

- **Språk** listar sidovisningar efter besökarens önskade språk.

## <a name="mobile-reports"></a>Mobilrapporter

Mobilrapporter grupperas i realtidsanvändning, app och användarkategorier. Du kan komma åt mobilrapporter under **Identifiera** i det vänstra navigeringsfönstret.   

:::image type="content" source="media/mobile-reports.png" alt-text="Användargränssnitt för engagemangsinsikter som visar användningsrapporten i realtid som renderar data i diagram och listor.":::   

### <a name="real-time-usage"></a>Användning i realtid

**Realtidsanvändning** ger en översikt över aktuell aktivitet i mobilappen som uppdateras automatiskt varje minut. Använd realtidsanvändning för att övervaka antalet användare och sessioner som för närvarande är aktiva i appen och de översta skärmvyerna.

### <a name="app-reports"></a>Apprapporter

- **Skärmvyer** listar skärmvyer för enskilda skärmar i en app och det totala antalet skärmvyer över en vald tidsram. Du kan visa skärmvyer efter skärmnamn eller skärmrubrik.

- **Sessioner** visar information om antalet sessioner och dessas varaktighet.

- **Returfrekvens** grupperar sessionsräkningar efter antal dagar sedan den senaste sessionen.

- **Användare** visar nya och återkommande användare i mobilappen.

- **Händelser** listar alla händelser som samlas in från appen, plus det totala antalet för varje evenemang.

### <a name="user-reports"></a>Användarrapporter

- **Appversioner** listar de versioner av mobilappen som används av användarbasen.

- **Enheter och OS-versioner** ger insikter i vilka enheter och operativsystem som kör mobilappen.

- **Platser** visar information om appanvändare efter land, region och ort.

## <a name="filter-by-time-or-date-range"></a>Filtrera efter tid eller datumintervall

Du kan välja tidsram eller datumintervall i en webb- eller mobilrapport om du vill fokusera på ett värde eller en tidsperiod. 

- Välj en tidsram genom att välja ett värde i den nedrullningsbara listan i rapporten längst upp till höger i rapportvyn. Du kan också välja ett **Fast datumintervall**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filtrera efter tid eller datumintervall.":::   

- I de flesta rapporter väljer du ett värde i ett diagram eller en lista för att filtrera rapporten.

> [!NOTE]
> Val av tidsintervall är inaktiverat för en användningsrapport i realtid. Tidsintervallet för en användningsrapport i realtid är "nu".


[!INCLUDE[footer-include](../includes/footer-banner.md)]
