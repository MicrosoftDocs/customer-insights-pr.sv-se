---
title: OData-frågeexempel för API:er för Customer Insights
description: Vanliga exempel på öppna dataprotokoll (OData) för att fråga API:erna för Customer Insights för att granska data.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387224"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>OData-frågeexempel för API:er för Customer Insights

Open Data Protocol (OData) är ett protokoll för dataåtkomst som bygger på kärnprotokoll som HTTP. För den används vanliga metoder som REST för webben. Det finns olika typer av bibliotek och verktyg som kan användas för att använda OData-tjänster.

För att hjälpa dig bygga dina egna implementeringar baserat på [Customer Insights API:er](apis.md), granska några ofta efterfrågade exempelfrågor.

Ändra frågeexempel så att de fungerar i målmiljöerna:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` var {instanceId} är GUID för den Customer Insights-miljö du vill fråga. Med [åtgärden ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) kan du hitta de {InstanceId} du har åtkomst till.
- {CID}: GUID för en enhetlig kundpost. Exempel: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifierare för den primära nyckeln för en kundpost i en datakälla. Exempel: `CNTID_1002`
- {DSname}: Sträng med entitetsnamnet för en datakälla som förs in i Customer Insights. Exempel: `Website_contacts`.
- {SegmentName}: Sträng med utdataentitetsnamnet för ett segment i Customer Insights. Exempel: `Male_under_40`.

## <a name="customer"></a>Kunder

Exempelfrågor för entiteten *kund*.

|Frågetyp |Exempel  | Kommentar  |
|---------|---------|---------|
|Ett kund-ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternativ nyckel    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternativa nycklar finns kvar i en enhetlig kundentitet       |
|Markera   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Om    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternativ nyckel + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Sök  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Returnerar de tio översta resultaten för en söksträng      |
|Segmentmedlemskap  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Returnerar ett antal rader från segmenteringsentiteten.      |
|Segmentmedlemskap för en kund | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Returnerar kundprofilen om de är medlemmar i det angivna avsnittet     |

## <a name="unified-activity"></a>Enhetlig aktivitet

Exempelfrågor för entiteten *UnifiedActivity*.

|Frågetyp |Exempel  | Kommentar  |
|---------|---------|---------|
|Aktivitet för CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Visar aktiviteter för en specifik kundprofil |
|Aktivitet för tidsram    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktiviteter i en kundprofil i en tidsram       |
|Aktivitetstyp    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivitet efter visningsnamn     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Aktivitetssortering    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortera aktiviteter i stigande eller fallande       |
|Aktivitet expanderad från segmentmedlemskap  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Andra exempel

Exempelfrågor för andra entiteter.

|Frågetyp |Exempel  | Kommentar  |
|---------|---------|---------|
|Mått för CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Berikade varumärken av CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Berikade intressen för CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|I sats + Expandera     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>OData-frågor som inte stöds

Följande frågor stöds inte av Customer Insights:

- `$filter` på införlivade källentiteter. Du kan endast köra $filter-frågor på systementiteter som Customer Insights skapar.
- `$expand` från en `$search`-fråga. Exempel: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` från `$select` om endast en deluppsättning attribut har markerats. Exempel: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` förädlat varumärke eller intresse för en viss kund. Exempel: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Ställ fråga till utdataentiteter för prediktionsmodell via alternativ nyckel. Exempel: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
