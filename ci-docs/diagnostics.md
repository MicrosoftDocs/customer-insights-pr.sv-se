---
title: Logga in i Dynamics 365 Customer Insights med Azure Monitor (förhandsgranskning)
description: Lär dig hur du skickar loggar till Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8c72df7054a682244215bbee54968d6aef4bbf59
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052675"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Logga in i Dynamics 365 Customer Insights med Azure Monitor (förhandsgranskning)

Dynamics 365 Customer Insights ger en direkt integrering med Azure Monitor. Azure Monitor resursloggar gör att du kan övervaka och skicka loggar till [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) eller strömma dem till [Azure händelsehubben](https://azure.microsoft.com/services/event-hubs/).

Customer Insights skickar följande händelseloggar:

- **Granskningshändelser**
  - **APIEvent** - aktiverar ändringsspårning som görs via Dynamics 365 Customer Insights användargränssnittet.
- **Verksamhetsevenemang**
  - **WorkflowEvent** - Med arbetsflödet kan du konfigurera [Datakällor](data-sources.md), [ena](data-unification.md) och [berika](enrichment-hub.md) och slutligen [exportera](export-destinations.md) data till andra system. Alla de stegen kan göras enskilt (t.ex. utlösa en enskild export). Kan också köras organiserade (till exempel uppdatera data från datakällor som utlöser föreningsprocessen, som hämtar utdata och sedan har exporterat alla data till ett annat system). För mer information [WorkflowEvent-schema](#workflow-event-schema).
  - **APIEvent** - alla API-anrop till kundinstansen till Dynamics 365 Customer Insights. För mer information [APIEvent-schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Konfigurera diagnosinställningar

### <a name="prerequisites"></a>Förutsättningar

Om du vill konfigurera diagnos Customer Insights, måste följande krav uppfyllas:

- Du måste ha en aktiv [Azure-prenumeration](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Du har [Administratör](permissions.md#admin) behörighet i Customer Insights..
- Du har rollen **Deltagare** och **Administratör för användaråtkomst** på destinationsresursen på Azure. Resursen kan vara ett Azure Data Lake Storage-konto, en händelsehubb för Azure eller en Azure Log Analytics-arbetsyta. Mer information finns i [Lägga till eller ta bort Azure-rolltilldelningar via Azure-portalen](/azure/role-based-access-control/role-assignments-portal). Denna behörighet är nödvändig när du konfigurerar diagnostikinställningarna i Customer Insights och kan ändras efter installation.
- [Destinationskraven](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) för Azure Storage, Azure Event eller Azure Hub eller Azure Log Analytics har uppfyllts.
- Du har minst rollen **Läsare** i den resursgrupp resursen tillhör.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Konfigurera diagnostik med Azure Monitor

1. I Customer Insights, välj **System** > **Diagnos** om du vill se diagnostikmålen som konfigurerat den här instansen.

1. Välj **Lägg till destination**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikanslutning](media/diagnostics-pane.png "Diagnostikanslutning")

1. Ange ett namn i fältet **Namn för diagnostikdestination**.

1. Välj en **klientorganisation** för Azure-prenumerationen med målresursen och välj **logga in**.

1. Välj **resurstyp** (lagringskonto, händelsehubben eller logganalys).

1. Välj **Prenumeration** för målresursen.

1. Välj **Resursgrupp** för målresursen.

1. Välj **Resurs**.

1. Bekräfta **sekretesspolicyn för data och regelefterlevnad**.

1. Välj **Anslut till system** om du vill ansluta till målresursen. Loggarna börjar visas i destinationen efter 15 minuter, om API:et används och genererar händelser.

### <a name="remove-a-destination"></a>Flytta ett mål

1. Gå till **System** > **Diagnos**.

1. Välj diagnostikmålet i listan.

1. I kolumnen **Åtgärder** välj ikonen **Ta bort**.

1. Bekräfta borttagningen för att stoppa vidarebefordran av loggen. Resursen i Azure-prenumerationen tas inte bort. Du kan välja länken i kolumnen **Åtgärder** om du vill öppna Azure-portalen för den valda resursen och ta bort den där.

## <a name="log-categories-and-event-schemas"></a>Loggkategorier och händelsescheman

För närvarande stöds [API-händelser](apis.md) och arbetsflödeshändelser och följande kategorier och scheman gäller.
Loggschemat följer [Azure Monitors vanliga schema](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorier

Customer Insights innehåller två kategorier:

- **Granska händelser**: [API-händelser](#api-event-schema) för att spåra konfigurationsändringar för tjänsten. `POST|PUT|DELETE|PATCH`-åtgärder går in i den här kategorin.
- **Verksamhetshändelser**: [API events](#api-event-schema) eller [arbetsflödeshändelser](#workflow-event-schema) som genereras när tjänsten används.  Exempelvis förfrågningar `GET` eller körningshändelser för ett arbetsflöde.

## <a name="configuration-on-the-destination-resource"></a>Konfiguration för målresursen

Beroende på vilken resurstyp du väljer gäller följande steg automatiskt:

### <a name="storage-account"></a>Storage account

Customer Insights-tjänstens huvudobjekt får **Deltagare för lagringskonto** behörighet för den valda resursen och skapar två behållare under det valda namnområdet:

- `insight-logs-audit` innehåller **granskningshändelser**
- `insight-logs-operational` som innehåller **verksamhetshändelser**

### <a name="event-hub"></a>Händelsehubben

Customer Insights-tjänstens huvudobjekt får **Azure händelsehubb dataägare** behörighet för den valda resursen och skapar två händelsehubbar under det valda namnområdet:

- `insight-logs-audit` innehåller **granskningshändelser**
- `insight-logs-operational` som innehåller **verksamhetshändelser**

### <a name="log-analytics"></a>Log Analytics

Customer Insights-tjänstens huvudkonto får behörigheten **Logga analysdeltagare** för resursen. Loggarna kommer att vara tillgängliga under **Loggar** > **Tabeller** > **Hantering av loggar** på den valda Log Analytics-arbetsytan. Expandera lösningen **Logghantering** och leta upp tabellerna `CIEventsAudit` och `CIEventsOperational`.

- `CIEventsAudit` innehåller **granskningshändelser**
- `CIEventsOperational` som innehåller **verksamhetshändelser**

Under fönstret **Frågor** expanderar du lösningen **Granskning** och letar upp exempelfrågor som tillhandahålls genom att söka efter `CIEvents`.

## <a name="event-schemas"></a>Händelsescheman

API-händelser och arbetsflödeshändelser har en gemensam struktur och information om var de skiljer sig, se [API-händelseschema](#api-event-schema) eller [schema för arbetsflödeshändelse](#workflow-event-schema).

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
|                 |

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
