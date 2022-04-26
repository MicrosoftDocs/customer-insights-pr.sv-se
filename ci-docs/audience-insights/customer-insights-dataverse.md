---
title: Customer Insights-data i Microsoft Dataverse
description: Använd Customer Insights-entiteter som tabeller i Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547648"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeta med Customer Insights-data i Microsoft Dataverse

Customer Insights ger möjlighet att göra utdataenheter tillgängliga i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denna integration möjliggör enkel datadelning och anpassad utveckling genom en metod med lite kod/ingen kod. [Utdataentiteterna](#output-entities) är tillgängliga som tabeller i en Dataverse-miljö. Du kan använda data för val annat program baserat på Dataverse-tabeller. Dessa tabeller möjliggör scenarier som automatiserade arbetsflöden genom Power Automate eller att skapa appar med Power Apps. Den aktuella implementeringen stöder i huvudsak uppslag där data från tillgängliga entiteter för Customer Insights kan hämtas för ett visst kund-ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Koppla en Dataverse-miljö till Customer Insights

**Befintlig organisation**

Administratörer kan konfigurera Customer Insights för [att använda en befintlig Dataverse-miljö](create-environment.md) när de skapar en Customer Insights-miljö. Genom att tillhandahålla webbadressen till Dataverse-miljön kopplas den till deras nya målgruppsinsiktsmiljö. Customer Insights och Dataverse-miljöer måste finnas i samma region. 

Om du inte vill använda en befintlig Dataverse-miljö skapar systemet en ny miljö för Customer Insights data i din klientorganisation. 

> [!NOTE]
> Om dina organisationer redan använder Dataverse i klientorganisationen är det viktigt att komma ihåg att [Dataverse-miljöskapande kontrolleras av en administratör](/power-platform/admin/control-environment-creation). Om du till exempel konfigurerar en ny målgruppsinsiktsmiljö med ditt organisationskonto och administratören har inaktiverat skapande av Dataverse-utvärderingsmiljöer för alla utom administratörer, kan du inte skapa en ny utvärderingsmiljö.
> 
> Dataverse-utvärderingsmiljöerna som skapats i Customer Insights har 3 GB lagringsutrymme som inte räknas in i den totala kapaciteten för klientorganisationen. Betalda prenumerationer ger Dataverse-berättigande till 15 GB för databas och 20 GB för fillagring.

**Ny organisation**

Om du skapar en ny organisation när du ställer in Customer Insights skapas automatiskt en ny Dataverse-miljö i din organisation åt dig.

## <a name="output-entities"></a>Utdataentiteter

Vissa utdataentiteter från målgruppsinsikter är tillgängliga som tabeller i Dataverse. Avsnitten nedan beskriver det förväntade schemat för dessa tabeller.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Berikning](#enrichment)
- [Prediktion](#prediction)
- [Segmentmedlemskap](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Den här tabellen innehåller den enhetliga kundprofilen från Customer Insights. Schemat för en enhetlig kundprofil beror på vilka entiteter och attribut som används i sammanslagningsprocessen. Ett kundprofilschema innehåller vanligtvis en delmängd av attributen från [definitionen av Common Data Model för CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabellen AlternateKey innehåller nycklar för entiteterna, som deltog i sammanslagningsprocessen.

|Column  |Type  |Beskrivning  |
|---------|---------|---------|
|DataSourceName    |String         | Datakällans namn. Till exempel: `datasource5`        |
|EntityName        | String        | Namnet på entiteten i målgruppsinsikter. Till exempel: `contact1`        |
|AlternateValue    |String         |Alternativt ID som mappas till kund-ID. Exempel: `cntid_1078`         |
|KeyRing           | Flerradig text        | JSON-värde  </br> Exempel: [{"dataSourceName":" datasource5 ",</br>"entityName":" kontakt1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID för den enhetliga kundprofilen.         |
|AlternateKeyId     | GUID         |  AlternateKey deterministiskt GUID baserat på msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exempel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Den här tabellen innehåller aktiviteter som görs av användare som är tillgängliga i Customer Insights.

| Column            | Type        | Beskrivning                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Kundprofil-ID                                                                      |
| ActivityId        | String      | Internt ID för kundaktiviteten (primärnyckel)                                       |
| SourceEntityName  | String      | Källentitetens namn                                                                |
| SourceActivityId  | String      | Primärnyckel från källentiteten                                                       |
| ActivityType      | String      | Semantisk aktivitetstyp eller namn på anpassad aktivitet                                        |
| ActivityTimeStamp | DATETIME    | Tidsstämpel för aktivitet                                                                      |
| Title             | String      | Rubrik eller namn för aktiviteten                                                               |
| Beskrivning       | String      | Aktivitetsbeskrivning                                                                     |
| URL               | String      | Länk till en extern URL som är specifik för aktiviteten                                         |
| SemanticData      | JSON-sträng | Innehåller en lista över nyckelvärdespar för semantiska mappningsfält som är specifika för typen av aktivitet |
| RangeIndex        | String      | Unix tidsstämpel som används för sortering av aktivitetstidslinje och effektiva intervallfrågor |
| mydynci_unifiedactivityid   | GUID | Internt ID för kundaktiviteten (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Den här tabellen innehåller utdata för kundattributbaserade mått.

| Column             | Type             | Beskrivning                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Kundprofil-ID        |
| Mått           | JSON-sträng      | Innehåller en lista över nyckelvärdespar för måttnamn och värden för den angivna kunden | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Kundprofil-ID |


### <a name="enrichment"></a>Berikning

Den här tabellen innehåller utdata från anrikningsprocessen.

| Column               | Type             |  Beskrivning                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Kundprofil-ID                                 |
| EnrichmentProvider   | String           | Namn för leverantören av anrikningen                                  |
| EnrichmentType       | String           | Typ av anrikning                                      |
| Värden               | JSON-sträng      | Lista över attribut som produceras av anrikningsprocessen |
| msdynci_enrichmentid | GUID             | Deterministiskt GUID genererat från msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediktion

Den här tabellen innehåller utdata från modellförutsägelser.

| Column               | Type        | Beskrivning                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Kundprofil-ID                                  |
| ModelProvider        | String      | Namn för leverantören av modellen                                      |
| Modell                | String      | Modellnamn                                                |
| Värden               | JSON-sträng | Lista över attribut som produceras av modellen |
| msdynci_predictionid | GUID        | Deterministiskt GUID genererat från msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentmedlemskap

Den här tabellen innehåller kundprofilernas information om segmentmedlemskap.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kundprofil-ID        |
| SegmentProvider      | String       | App som publicerar segmenten. Standard: Målgruppsinsikter         |
| SegmentMembershipType | String       | Kundtyp som det här segmentmedlemskapet registrerar. Stöder flera typer, såsom kund, kontakt eller konto. Standard: kund  |
| Segment       | JSON-sträng  | Lista med unika segment där kundprofilen är medlem      |
| msdynci_identifier  | String   | Unik identifierare för det här segmentmedlemskapets post. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministiskt GUID genererat från `msdynci_identifier`          |
