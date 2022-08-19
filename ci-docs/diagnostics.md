---
title: Exportera diagnostikloggar (förhandsversion)
description: Lär dig hur du skickar loggar till Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245947"
---
# <a name="export-diagnostic-logs-preview"></a>Exportera diagnostikloggar (förhandsversion)

Vidarebefordra loggar från Customer Insights med Azure Monitor. Azure Monitor resursloggar gör att du kan övervaka och skicka loggar till [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) eller strömma dem till [Azure händelsehubben](https://azure.microsoft.com/services/event-hubs/).

Customer Insights skickar följande händelseloggar:

- **Granskningshändelser**
  - **APIEvent** – aktiverar ändringsspårning via Dynamics 365 Customer Insights-användargränssnittet.
- **Verksamhetsevenemang**
  - **WorkflowEvent** – gör det möjligt att konfigurera [datakällor](data-sources.md), [ena](data-unification.md), [berika](enrichment-hub.md) och [exportera](export-destinations.md) data till andra system. Dessa steg kan göras enskilt (t.ex. utlösa en enskild export). De kan också köras organiserade (till exempel uppdatera data från datakällor som utlöser föreningsprocessen, som hämtar berikningar och exporterar alla data till ett annat system). För mer information [WorkflowEvent-schema](#workflow-event-schema).
  - **APIEvent** – skickar alla API-anrop för kundinstansen till Dynamics 365 Customer Insights. För mer information [APIEvent-schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Konfigurera diagnosinställningar

### <a name="prerequisites"></a>Förutsättningar

- En aktiv [Azure-prenumeration](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administratör](permissions.md#admin)-behörighet i Customer Insights..
- [Rollen Deltagare och Administratör för användaråtkomst](/azure/role-based-access-control/role-assignments-portal) på destinationsresursen på Azure. Resursen kan vara ett Azure Data Lake Storage-konto, en händelsehubb för Azure eller en Azure Log Analytics-arbetsyta. Denna behörighet är nödvändig när du konfigurerar diagnostikinställningarna i Customer Insights, men den kan ändras efter installation.
- [Destinationskraven](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) för Azure Storage, Azure Event eller Azure Hub eller Azure Log Analytics är uppfyllda.
- Minst rollen **Läsare** i den resursgrupp resursen tillhör.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Konfigurera diagnostik med Azure Monitor

1. I Customer Insights, gå till **Admin** > **System** och välj fliken **Diagnostik**.

1. Välj **Lägg till destination**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Diagnostikanslutning.":::

1. Ange ett namn i fältet **Namn för diagnostikdestination**.

1. Välj **Resurstyp** (lagringskonto, händelsehubben eller logganalys).

1. Välj **Prenumeration**, **Resursgrupp** och **Resurs** för målresursen. Se [Konfiguration för målresursen](#configuration-on-the-destination-resource) för behörighets- och logginformation.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Anslut till system** om du vill ansluta till målresursen. Loggarna börjar visas i destinationen efter 15 minuter, om API:et används och genererar händelser.

## <a name="configuration-on-the-destination-resource"></a>Konfiguration för målresursen

Beroende på vilken resurstyp du väljer sker följande ändringar automatiskt:

### <a name="storage-account"></a>Storage account

Customer Insights-tjänstens huvudobjekt får **Deltagare för lagringskonto** behörighet för den valda resursen och skapar två behållare under det valda namnområdet:

- `insight-logs-audit` innehåller **granskningshändelser**
- `insight-logs-operational` som innehåller **verksamhetshändelser**

### <a name="event-hub"></a>Händelsehubben

Customer Insights-tjänstens huvudobjekt får **Azure händelsehubb dataägare** behörighet för den valda resursen och skapar två händelsehubbar under det valda namnområdet:

- `insight-logs-audit` innehåller **granskningshändelser**
- `insight-logs-operational` som innehåller **verksamhetshändelser**

### <a name="log-analytics"></a>Log Analytics

Customer Insights-tjänstens huvudkonto får behörigheten **Logga analysdeltagare** för resursen. Loggarna är tillgängliga under **Loggar** > **Tabeller** > **Hantering av loggar** på den valda Log Analytics-arbetsytan. Expandera lösningen **Logghantering** och leta upp tabellerna `CIEventsAudit` och `CIEventsOperational`.

- `CIEventsAudit` innehåller **granskningshändelser**
- `CIEventsOperational` som innehåller **verksamhetshändelser**

Under fönstret **Frågor** expanderar du lösningen **Granskning** och letar upp exempelfrågor som tillhandahålls genom att söka efter `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Ta bort en diagnostikdestination

1. Gå till **Admin** > **System** och välj fliken **Diagnostik**.

1. Välj diagnostikmålet i listan.

   > [!TIP]
   > När du tar bort målet stoppas vidarebefordringen av loggar, men resursen tas inte bort i Azure-prenumerationen. Om du vill ta bort resursen i Azure, väljer du länken i kolumnen **Åtgärder** om du vill öppna Azure-portalen för den valda resursen och ta bort den där. Därefter tar du bort diagnostikmålet.

1. I kolumnen **Åtgärder** välj ikonen **Ta bort**.

1. Bekräfta borttagningen för att ta bort målet och stoppa vidarebefordringen av loggar.

## <a name="log-categories-and-event-schemas"></a>Loggkategorier och händelsescheman

För närvarande stöds [API-händelser](apis.md) och arbetsflödeshändelser och följande kategorier och scheman gäller.
Loggschemat följer [Azure Monitors vanliga schema](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorier

Customer Insights innehåller två kategorier:

- **Granska händelser**: [API-händelser](#api-event-schema) för att spåra konfigurationsändringar för tjänsten. `POST|PUT|DELETE|PATCH`-åtgärder går in i den här kategorin.
- **Verksamhetshändelser**: [API events](#api-event-schema) eller [arbetsflödeshändelser](#workflow-event-schema) som genereras när tjänsten används.  Exempelvis förfrågningar `GET` eller körningshändelser för ett arbetsflöde.

## <a name="event-schemas"></a>Händelsescheman

API-händelser och arbetsflödeshändelser har en gemensam struktur, men med några skillnader. Mer information finns i [händelseschema för API](#api-event-schema) eller [händelseschema för arbetsflöde](#workflow-event-schema).

### <a name="api-event-schema"></a>API-händelseschema

| Fält             | DataType  | Krävs/valfritt | Description       | Exempel        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Tidsstämpel | Obligatoriskt          | Tidsstämpel för händelsen (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obligatoriskt          | ResourceId för den instans som genererade händelsen         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obligatoriskt          | Namnet på den åtgärd som händelsen representerar.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obligatoriskt          | Loggkategori för händelsen. Antingen `Operational` eller `Audit`. Alla POST/PUT/PATCH/DELETE HTTP-förfrågningar är taggade med `Audit`, allt annat med`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obligatoriskt          | Status för händelsen. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Valfri          | Resultatstatus för händelsen. Om åtgärden motsvarar ett REST-API är det HTTP-statuskoden.        | `200`             |
| `durationMs`      | Long      | Valfri          | Varaktigheten för åtgärd i milisekunder.     | `133`     |
| `callerIpAddress` | String    | Valfri          | IP-adress för uppringare, om åtgärden motsvarar ett API-anrop som kommer från en offentlig IP-adress.                                                 | `144.318.99.233`         |
| `identity`        | String    | Valfri          | JSON-objekt som beskriver identiteten för den användare eller det program som har gjort åtgärden.       | Se avsnittet [Identitet](#identity-schema).     |  
| `properties`      | String    | Valfri          | JSON-objekt med fler egenskaper för den specifika händelsekategorin.      | Se avsnittet [Egenskaper](#api-properties-schema).    |
| `level`           | String    | Obligatoriskt          | Händelsens allvarlighetsgrad.    | `Informational`, `Warning`, `Error` eller `Critical`.           |
| `uri`             | String    | Valfri          | URI för absolut begäran.    |               |

#### <a name="identity-schema"></a>Identitetsschema

`identity` JSON-objektet har följande struktur

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Fält                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Tilldelad roll för användaren eller appen. Mer information finns i [användarbehörigheter](permissions.md).                                     |
| `Authorization.RequiredRoles` | Obligatoriska roller för att göra åtgärden. `Admin` rollen kan göra alla åtgärder.                                                    |
| `Claims`                      | Anspråk på användaren eller appen JSON-webbtoken (JWT). Anspråksegenskaperna varierar beroende på organisation och Azure Active Directory konfiguration. |

#### <a name="api-properties-schema"></a>Schema för API-egenskaper

[API-händelser](apis.md) har följande egenskaper.

| Fält                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Markera alltid `ApiEvent` logghändelsen som API-händelse.                                                                 |
| `properties.userAgent`       | Webbläsaragent som skickar förfrågan eller `unknown`.                                                                        |
| `properties.method`          | HTTP-metod: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Förfrågans relativa sökväg.                                                                                          |
| `properties.origin`          | URI som anger var en fetch kommer från eller `unknown`.                                                                  |
| `properties.operationStatus` | `Success` för HTTP-statuskod < 400 <br> `ClientError` för HTTP-statuskod < 500 <br> `Error` för HTTP->= 500 |
| `properties.tenantId`        | Organisations-ID                                                                                                        |
| `properties.tenantName`      | Namn på organisationen.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId för anroparen.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Händelseschema för arbetsflöde

Arbetsflödet innehåller flera steg. [Mata in datakällor](data-sources.md), [ena](data-unification.md), [berika](enrichment-hub.md) och [exportera](export-destinations.md) data. Alla dessa steg kan köras enskilt eller enligt följande processer.

#### <a name="operation-types"></a>Åtgärdstyper

| OperationType     | Grupp                                     |
| ----------------- | ----------------------------------------- |
| Inmatning         | [Datakällor](data-sources.md)           |
| DataPreparation   | [Datakällor](data-sources.md)           |
| Mappa               | [Dataförening](data-unification.md)   |
| Matchning             | [Dataförening](data-unification.md)   |
| Slå ihop             | [Dataförening](data-unification.md)   |
| ProfileStore      | [Kundprofiler](customer-profiles.md) |
| Sök            | [Kundprofiler](customer-profiles.md) |
| Aktivitet          | [Aktiviteter](activities.md)                  |
| AttributeMeasures | [Segment och mått](segments.md)      |
| EntityMeasures    | [Segment och mått](segments.md)      |
| Mått          | [Segment och mått](segments.md)      |
| Segmentering      | [Segment och mått](segments.md)      |
| Berikning        | [Berikning](enrichment-hub.md)                                          |
| Intelligens      | [Prediktioner](predictions-overview.md)                                          |
| AiBuilder         | [Prediktioner](predictions-overview.md)                                          |
| Insikter          | [Prediktioner](predictions-overview.md)                                          |
| Export            | [Exporter](export-destinations.md)                                          |
| ModelManagement   | [Prediktioner](custom-models.md)                                           |
| Relation      | [Dataförening](relationships.md)                                           |

#### <a name="field-description"></a>Fältbeskrivning

| Fält           | DataType  | Krävs/valfritt | Description                                                                                                                                                   | Exempel                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Tidsstämpel | Obligatoriskt          | Tidsstämpel för händelsen (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obligatoriskt          | ResourceId för den instans som genererade händelsen.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obligatoriskt          | Namnet på den åtgärd som händelsen representerar. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Se [Åtgärdstyper](#operation-types) för referens. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obligatoriskt          | Loggkategori för händelsen. Alltid `Operational` för arbetsflödeshändelser                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Obligatoriskt          | Status för händelsen. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Valfri          | Varaktigheten för åtgärd i milisekunder.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Valfri          | JSON-objekt med fler egenskaper för den specifika händelsekategorin.                                                                                        | Se underavsnitt [Arbetsflödesegenskaper](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obligatoriskt          | Händelsens allvarlighetsgrad.                                                                                                                                  | `Informational`, `Warning` eller `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Schema för arbetsflödesegenskaper

Arbetsflödeshändelser har följande egenskaper.

| Fält              | Workflow | Aktivitet | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Markera alltid `WorkflowEvent` logghändelsen som arbetsflödeshändelse.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Identifierare för arbetsflödet som körs. Alla arbetsflödes- och uppgiftshändelser i arbetsflödeskörningen har samma `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Identifierare för åtgärden finns i [Åtgärdstyper](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ja      | No   | Endast arbetsflöde. Antal uppgifter för arbetsflödesutlösare.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | No   | Valfritt. Endast arbetsflödeshändelse. Azure Active Directory [objectId för användaren](/azure/marketplace/find-tenant-object-id#find-user-object-id) som utlöste arbetsflödet, se även `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | No   | `full` eller `incremental` uppdatera.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | No   | `OnDemand` eller `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | No   | `Running` eller `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC tidsstämpel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC tidsstämpel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC tidsstämpel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ja  | - För OperationType = `Export` är identifieraren guid för exportkonfigurationen. <br> - För OperationType = `Enrichment` är det guid för berikande <br> - För OperationType `Measures` och `Segmentation` är identifieraren enhetsnamnet. |
| `properties.friendlyName`                    | No       | Ja  | Användarvänligt namn på exporten eller den entitet som bearbetas.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ja  | Valfritt. Felmeddelande med mer information.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ja  | Valfritt. Endast för `Export` OperationType. Identifierar typen av export. Mer information finns i [Översikt över exportmål](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ja  | Valfritt. Endast för `Export` OperationType. Innehåller en lista över konfigurerade entiteter under exporten.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ja  | Valfritt. Endast för `Export` OperationType. Detaljerat meddelande för exporten.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ja  | Valfritt. Endast för `Segmentation` OperationType. Anger det totala antalet medlemmar som avsnittet har.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
