---
title: Visa systemkonfiguration
description: Läs mer om systeminställningar i Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396023"
---
# <a name="view-system-configuration"></a>Visa systemkonfiguration

Visa systeminformation, systemstatus och API-användning.

## <a name="view-api-usage"></a>Visa API-användning

Visa information om API-användningen i realtid och se vilka händelser som har inträffat i en viss tidsram.

1. Gå till **Admin** > **System** och välj fliken **API-användning**.

1. **Välj en tidsram** för att visa.

   Sidan **API-användning** innehåller tre avsnitt:

   - **API-anrop** – ett diagram som visualiserar det sammanlagda antalet anrop till API:et inom den valda tidsramen.
   - **Dataöverföring** – ett diagram som visar mängden data som överfördes via API:et i den valda tidsramen.
   - **Åtgärder** – en tabell med rader för varje tillgänglig API-åtgärd och information om hur åtgärderna används. Välj ett åtgärdsnamn för att gå till [API-referensen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Visa systeminformation

Visa miljöns visningsnamn, ID, region, typ och sessions-ID.

1. Gå till **Admin** > **System** och välj fliken **Om**.

1. Välj fliken **Allmänt** om du vill visa språket och landet/regionen.

### <a name="update-preferred-language-or-countryregion"></a>Uppdatera önskat språk eller land/region

Customer Insights [har stöd för många språk](/dynamics365/get-started/availability). Appen använder din språkinställning för att visa element som menyn, etikettext och systemmeddelanden på det språk du föredrar.

Importerade data och information som du har angett manuellt översätts inte.

1. Gå till **Admin** > **System** och välj fliken **Allmänt**.

1. Om du vill ändra önskat språk väljer du ett **språk** i listrutan.

1. Om du vill ändra förvald formatering för datum, tid och tal använder du listrutan **Land/region-format**. En förhandsgranskning av formatet visas. Systemet kommer automatiskt att föreslå ett urval när du väljer ett nytt språk.

1. Välj **Spara**.

## <a name="view-system-status"></a>Visa systemstatus

Spåra förlopp för uppgifter, dataexporter och flera andra viktiga produktprocesser. Granska informationen för att säkerställa att dina aktiva uppgifter och processer är fullständiga.

1. Gå till **Admin** > **System** och välj fliken **Status**.

   Visar status och bearbetningsinformation för olika processer. Visa uppgiftens **Namn**, **Status** för dess senaste körning och när den **Senast uppdaterades**.

1. Visa information om de senaste körningarna genom att markera uppgifts- eller processnamnet.

1. Markera statusen om du vill visa information om förlopp för en uppgift. Rutan **Förloppsinformation** visas.

   :::image type="content" source="media/system-progress-details.png" alt-text="Informationsfönstret Systemförlopp":::

1. Om du vill visa förloppsinformation för alla uppgifter markerar du **Hela arbetsflödet**.

### <a name="status-definitions"></a>Statusdefinitioner

I systemet används följande statusar för uppgifter och processer:

|Status  |Definition  |
|---------|---------|
|Avbruten |Uppgiften eller processen avbröts av användaren innan den slutfördes.   |
|Misslyckad   |Fel uppstod i uppgiften eller processen.         |
|Misslyckades  |Uppgiften eller processen har misslyckats.  |
|Inte startat   |Datakällan har inga inmatade data än eller så är uppgiften fortfarande i utkastläge.         |
|Bearbetas  |Uppgift eller process pågår.  |
|Uppdaterar    |Uppgift eller process pågår. Avbryt åtgärden genom att välja **Uppdatera** och **Avbryt jobb**. Om du stoppar uppdateringen av en uppgift eller process återställs den till dess senaste uppdateringstillstånd.       |
|Hoppades över  |Uppgift eller process har hoppats över. En eller flera processer längre fram som denna uppgift är beroende av fallerar eller hoppas över.|
|Klart  |Uppgiften eller förloppet har slutförts. För datakällor anger du att data har tagits bort om en tid anges i kolumnen **Uppdaterad**.|
|I kö | Bearbetningen köas och startar när alla uppgifter och processer har slutförts. Mer information, se [uppdatera förlopp](#refresh-processes).|

### <a name="refresh-processes"></a>Uppdatera förlopp

Uppdatering för uppgifter och processer körs enligt det [konfigurerade schemat](schedule-refresh.md).

|Bearbeta  |Beskrivning  |
|---------|---------|
|Aktivitet  |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. Insikter beror på behandlingen.|
|Analyskoppling |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Analysförberedelse |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Dataförberedelse   |En entitet måste köras. Datakälla entiteter är beroende av inmatning. Förädlade entiteter är beroende av berikande. Entiteten Kund är beroende av koppling.  |
|Datakällor   |Är inte beroende av någon annan process. Matchningen beror på att processen har slutförts.  |
|Berikningar   |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. |
|Exporterar mål |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Insikter |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Intelligens   |Är beroende av sammanslagning.   |
|Matchning |Är beroende av behandlingen av datakällor som används i matchningsdefinitionen.      |
|Mått  |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen.  |
|Sammanslå   |Beror på att matchningsprocessen har slutförts. Segment, mått, berikning, sökning, aktiviteter, prediktion och dataförberedelse är beroende av att processen har slutförts.   |
|Profiler   |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. |
|Search   |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. |
|Segment  |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. Insikter beror på behandlingen.|
|System   |Beror på att matchningsprocessen har slutförts. Segment, mått, berikning, sökning, aktiviteter, prediktion och dataförberedelse är beroende av att processen har slutförts.   |
|Användare  |Körs manuellt (engångsuppdatering). Beroende av entiteter.  |

Markera status för en process om du vill visa förloppsinformationen för hela jobbet som den fanns i. Uppdateringsprocesserna ovan kan hjälpa dig att förstå vad du kan göra för att ta itu med en **Hoppades över** eller **Köad** uppgift eller process.


[!INCLUDE [footer-include](includes/footer-banner.md)]
