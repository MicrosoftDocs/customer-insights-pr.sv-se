---
title: Arbeta med Customer Insights-data i Microsoft Dataverse
description: Lär dig hur du ansluter Customer Insights och Microsoft Dataverse och förstå utdataentiteterna som exporteras till Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671273"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeta med Customer Insights-data i Microsoft Dataverse

Customer Insights ger möjlighet att göra utdataenheter tillgängliga i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denna integration möjliggör enkel datadelning och anpassad utveckling genom en metod med lite kod/ingen kod. [Utdataentiteterna](#output-entities) är tillgängliga som tabeller i en Dataverse-miljö. Du kan använda data för val annat program baserat på Dataverse-tabeller. Dessa tabeller möjliggör scenarier som automatiserade arbetsflöden genom Power Automate eller att skapa appar med Power Apps.

Om du ansluter till din Dataverse-miljö kan du [även hämta data från lokala datakällor med Power Platform-dataflöden och gateways](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Förutsättningar

- Customer Insights och Dataverse-miljöer måste finnas i samma region.
- Konfigurera en global administratörsroll i Dataverse-miljön. Kontrollera att denna [Dataverse-miljö är associerad](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) med vissa säkerhetsgrupper, samt kontrollera att du har lagts till i dessa säkerhetsgrupper.
- Ingen annan Customer Insights-miljö har redan associerats med den Dataverse-miljö du vill ansluta. Lär dig hur du [tar bort en befintlig anslutning till en Dataverse-miljö](#remove-an-existing-connection-to-a-dataverse-environment).
- En Microsoft Dataverse-miljö som är ansluten till ett enda lagringskonto om du konfigurerar miljön för att [använda din Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse lagringskapacitet, berättigande

En Customer Insights-prenumeration berättigar dig till extra kapacitet för organisationens befintliga [Dataverse lagringskapacitet](/power-platform/admin/capacity-storage). Vilken kapacitet som läggs till beror på antalet profiler som används i prenumerationen.

**Exempel:**

Förutsatt att du får 15 GB databaslagring och 20 GB fillagring per 100 000 kundprofiler. Om din prenumeration innehåller 300 000 kundprofiler är den totala lagringskapaciteten 45 GB (3 x 15 GB) databaslagring och 60 GB fillagring (3 x 20 GB). På samma sätt gäller att om du har en B-till-B-prenumeration med 30 000 konton är den totala lagringskapaciteten 45 GB (3 x 15 GB) databaslagring och 60 GB fillagring (3 x 20 GB).

Loggkapaciteten åtgärdas inte för organisationen.

Mer information om licenser finns i berättiganden av detaljerad kapacitet se [Licensieringsguide för Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Ansluta en Dataverse-miljö till Customer Insights

I steget **Microsoft Dataverse** kan du koppla Customer Insights till din Dataverse-miljö när du [skapar en Customer Insights-miljö](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="-datadelning med Microsoft Dataverse automatiskt aktiverat för nya miljöer.":::

1. Ange URL-adressen till Dataverse-miljön eller lämna den tom om du vill att en ska skapas åt dig.

   > [!NOTE]
   > Efter att ha upprättat kopplingen mellan Customer Insights och Dataverse, ändra inte organisationens namn för Dataverse-miljö. Namnet på organisationen används i Dataverse URL:en och ett ändrat namn bryter anslutningen till Customer Insights.

   [Power Platform-administratörer kan styra vem som kan skapa en ny Dataverse miljö](/power-platform/admin/control-environment-creation). Om du försöker konfigurera en ny Customer Insights-miljö och inte kan, kan administratören ha inaktiverat skapandet av Dataverse-miljöer för alla utom administratörer kanske du inte kan skapa en ny miljö.

1. Om du använder ditt eget Data Lake Storage-konto:
   1. Välj **Aktivera datadelning** med Dataverse.
   1. Ange **Behörighetsidentifierare**. För att få behörighetsidentifieraren [aktivera datadelning med Dataverse från din egen Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivera datadelning med Dataverse från din egen Azure Data Lake Storage (förhandsversion)

I [ditt eget Azure Data Lake Storage konto](own-data-lake-storage.md), verifiera att användaren som ställer in Customer Insights-miljön åtminstone har åtminstone behörighet för **Storage Blob-dataläsare** för behållaren `customerinsights` i lagringskontot.

> [!NOTE]
> Datadelning gäller endast om du använder ditt eget Azure Data Lake Storage konto. Den här inställningen är inte tillgänglig om Dataverse standardlagring används i Customer Insights.

### <a name="limitations"></a>Begränsningar

- Endast en till en-mappning mellan en Dataverse-organisation och ett Azure Data Lake Storage-konto. När en Dataverse-organisation väl är ansluten till ett lagringskonto går det inte att ansluta den till ett annat lagringskonto. Dess begränsning förhindrar att Dataverse fyller i flera olika lagringskonton.
- Datadelning fungerar inte om en Azure Private Link krävs för att få åtkomst till ditt Azure Data Lake Storage-lagringskonto eftersom detta finns bakom en brandvägg. Dataverse stöder för närvarande inte anslutningen till privata slutpunkter via Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Konfigurera säkerhetsgrupper på din egen Azure Data Lake Storage

1. Skapa två säkerhetsgrupper i din Azure-prenumeration – en **Läsare**-säkerhetsgrupp och en **Deltagare**-säkerhetsgrupp – och ange Microsoft Dataverse-tjänsten som ägare för båda säkerhetsgrupper.

1. Hantera åtkomstkontrolllistan (ACL) för `customerinsights`-behållare i ditt lagringskonto via dessa säkerhetsgrupper.
   1. Lägg till Microsoft Dataverse-tjänsten och eventuella Dataverse-baserade affärsprogram som Dynamics 365 Marketing i säkerhetsgruppen **Läsare** med **skrivskyddade** behörigheter.
   1. Lägg *endast* till programmet Customer Insights i säkerhetsgruppen **Deltagare** för att bevilja både **läs- och skrivbehörighet** för att skriva profiler och insikter.

### <a name="set-up-powershell"></a>Konfigurera PowerShell

Konfigurera PowerShell för att köra PowerShell-skript.

1. Installera den senaste versionen av [Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).
   1. På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och väljer **Kör som administratör**.
   1. I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.

1. Importera tre moduler.
   1. I PowerShell-fönstret anger du `Install-Module -Name Az.Accounts` och följer stegen.
   1. Upprepa för `Install-Module -Name Az.Resources` och `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Kör PowerShell-skript och hämta behörighetsidentifieraren

1. Hämta de två PowerShell-skripten du behöver för körning från vår teknikers [GitHub-lagringsplats](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Kräver behörigheter som administratör för klientorganisation.
   - `ByolSetup.ps1`: Kräver behörigheter för blobbdataägare för lagring på lagringskonto-/behållarnivå. Med det här skriptet skapas behörigheten för dig. Din rolltilldelning kan tas bort manuellt när skriptet har körts.

1. Kör det här `CreateSecurityGroups.ps1`-skriptet i Windows PowerShell genom att tillhandahålla Azure-prenumerations-ID:t som innehåller din Azure Data Lake Storage. Öppna PowerShell-skriptet i en redigerare om du vill granska ytterligare information och logiken som implementerats.

   Det här skriptet skapar två säkerhetsgrupper på din Azure-prenumeration: en för Läsare gruppen och en annan för Deltagare gruppen. Microsoft Dataverse-tjänsten är ägare till båda säkerhetsgrupperna.

1. Spara båda värdena för säkerhetsgruppens ID som genereras av detta skript att använda i `ByolSetup.ps1`-skriptet.

   > [!NOTE]
   > Skapandet av säkerhetsgrupper kan inaktiveras i klientorganisationen. I så fall behövs en manuell konfiguration, och din Azure AD-administratör måste även [ aktivera skapande av säkerhetsgrupper](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Kör detta `ByolSetup.ps1` i Windows PowerShell genom att tillhandahålla det ID för Azure-prenumeration som innehåller ditt Azure Data Lake Storage, namnet på ditt lagringskonto, resursgruppens namn samt ID-värdena för säkerhetsgrupperna Läsare och Deltagare. Öppna PowerShell-skriptet i en redigerare om du vill granska ytterligare information och logiken som implementerats.

   Detta skript lägger till den rollbaserade åtkomstkontrollen för Microsoft Dataverse-tjänsten och alla Dataverse-baserade affärsprogram. Dessutom uppdateras åtkomstkontrollistan (ACL) i `customerinsights`-behållaren för de säkerhetsgrupper som skapats med `CreateSecurityGroups.ps1`-skriptet. Gruppen Deltagare får behörigheten *rwx* och gruppen Läsare får endast behörigheten *r-x*.

1. Kopiera utdatasträngen som ser ut: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Ange den kopierade utdatasträngen i fältet **ID för behörigheter** i konfigurationssteget för miljön för Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsalternativ för att aktivera datadelning från din egna Azure Data Lake Storage med Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Ta bort en befintlig anslutning till en Dataverse-miljö

När du ansluter till en Dataverse-miljö betyder felmeddelandet **Denna CDS-organisation är redan ansluten till en annan instans av Customer Insights** att Dataverse-miljön redan används i en Customer Insights-miljö. Du kan ta bort den befintliga anslutningen som global administratör i Dataverse-miljön. Det kan ta några timmar innan ändringarna fylls i.

1. Gå till [Power Apps](https://make.powerapps.com).
1. Välj miljö i miljöväljaren.
1. Gå till **Lösningar**.
1. Avinstallera eller ta bort lösningen med namnet **Kundkortstillägg för Dynamics 365 Customer Insights (förhandsgranskning)**.

ELLER

1. Öppna din Dataverse-miljö.
1. Gå till **Avancerade inställningar** > **Lösningar**.
1. Avinstallera lösningen **CustomerInsightsCustomerCard**.

Om borttagningen av anslutningen misslyckas på grund av beroenden måste du även ta bort beroendena. Mer information finns i [Ta bort beroenden](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Utdataentiteter

Vissa utdataentiteter från Customer Insights är tillgängliga som tabeller i Dataverse. Avsnitten nedan beskriver det förväntade schemat för dessa tabeller.

- [CustomerProfile](#customerprofile)
- [Kontaktprofil](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Berikning](#enrichment)
- [Prediktion](#prediction)
- [Segmentmedlemskap](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Den här tabellen innehåller den enhetliga kundprofilen från Customer Insights. Schemat för Unified customer profile beror på entiteterna och attributen som används i föreningsprocessen för data. Ett kundprofilschema innehåller vanligtvis en delmängd av attributen från [definitionen av Common Data Model för CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Kundprofilen för scenariot B till B innehåller enhetliga konton och schemat innehåller vanligtvis en deluppsättning av attributen från [definitionen i Common Data Model för Konto](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>Kontaktprofil

En ContactProfile innehåller enhetlig information om en kontakt. Kontaktpersoner är [individer som är mappade till ett konto](data-unification-contacts.md) i ett B till B-scenario.

| Column                       | Type                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | Datum/tid       |  Kontaktens födelsedatum               |
|  City                 | Text |  Orten i kontaktens adress               |
|  ContactId            | Text |  ID för kontaktprofilen               |
|  ContactProfileId     | Unik identifierare   |  GUID för kontakten               |
|  CountryOrRegion      | Text |  Kontaktens land/region               |
|  CustomerId           | Text |  ID för kontaktpersonens konto mappas till               |
|  EntityName           | Text |  Entitet som data kommer från                |
|  FirstName            | Text |  Kontaktens förnamn               |
|  Kön               | Text |  Kontaktens kön               |
|  Id                   | Text |  Deterministiskt GUID baserat på `Identifier`               |
|  Identifierare           | Text |  Internt ID för kontaktprofilen: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Text |  Kontaktens jobbtitel               |
|  LastName             | Text |  Kontaktens efternamn               |
|  PostalCode           | Text |  Kontaktens postnummer               |
|  PrimaryEmail         | Text |  Kontaktens e-postadress               |
|  PrimaryPhone         | Text |  Kontaktens telefonnummer               |
|  Region      | Text |  Kontaktens delstat eller provins               |
|  StreetAddress        | Text |  Kontaktens gatuadress               |

### <a name="alternatekey"></a>AlternateKey

Tabellen AlternateKey innehåller nycklar för entiteterna, som deltog i sammanslagningsprocessen.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |Text         | Datakällans namn. Till exempel: `datasource5`        |
|EntityName        | Text        | Namnet på entiteten i Customer Insights. Till exempel: `contact1`        |
|AlternateValue    |Text         |Alternativt ID som mappas till kund-ID. Exempel: `cntid_1078`         |
|KeyRing           | Text        | JSON-värde  </br> Exempel: [{"dataSourceName":" datasource5 ",</br>"entityName":" kontakt1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Text        | ID för den enhetliga kundprofilen.         |
|AlternateKeyId     | Unik identifierare        |  AlternateKey deterministiskt GUID baserat på `Identifier`      |
|Identifierare |   Text      |   `DataSourceName|EntityName|AlternateValue`  </br> Exempel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Den här tabellen innehåller aktiviteter som görs av användare som är tillgängliga i Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Text      | Kundprofil-ID                                                                      |
| ActivityId        | Text      | Internt ID för kundaktiviteten (primärnyckel)                                       |
| SourceEntityName  | Text      | Källentitetens namn                                                                |
| SourceActivityId  | Text      | Primärnyckel från källentiteten                                                       |
| ActivityType      | Text      | Semantisk aktivitetstyp eller namn på anpassad aktivitet                                        |
| ActivityTimeStamp | Datum/tid    | Tidsstämpel för aktivitet                                                                      |
| Title             | Text      | Rubrik eller namn för aktiviteten                                                               |
| Description       | Text      | Aktivitetsbeskrivning                                                                     |
| webbadress               | Text      | Länk till en extern URL som är specifik för aktiviteten                                         |
| SemanticData      | Text | Innehåller en lista över nyckelvärdespar för semantiska mappningsfält som är specifika för typen av aktivitet |
| RangeIndex        | Text      | Unix tidsstämpel som används för sortering av aktivitetstidslinje och effektiva intervallfrågor |
| UnifiedActivityId   | Unik identifierare | Internt ID för kundaktiviteten (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Den här tabellen innehåller utdata för kundattributbaserade mått.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Text           | Kundprofil-ID        |
| Mått           | Text      | Innehåller en lista över nyckelvärdespar för måttnamn och värden för den angivna kunden |
| Identifierare | Text           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Unik identifierare     | Kundprofil-ID |

### <a name="enrichment"></a>Berikning

Den här tabellen innehåller utdata från anrikningsprocessen.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Text           | Kundprofil-ID                                 |
| EnrichmentProvider   | Text           | Namn för leverantören av anrikningen                                  |
| EnrichmentType       | Text           | Typ av anrikning                                      |
| Värden               | Text      | Lista över attribut som produceras av anrikningsprocessen |
| EnrichmentId | Unik identifierare            | Deterministiskt GUID genererat från `Identifier` |
| Identifierare   | Text           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Förutsägelse

Den här tabellen innehåller utdata från modellförutsägelser.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Text      | Kundprofil-ID                                  |
| ModelProvider        | Text      | Namn för leverantören av modellen                                      |
| Modell                | Text      | Modellnamn                                                |
| Värden               | Text | Lista över attribut som produceras av modellen |
| PredictionId | Unik identifierare       | Deterministiskt GUID genererat från `Identifier` |
| Identifierare   | Text      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentmedlemskap

Den här tabellen innehåller kundprofilernas information om segmentmedlemskap.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Text       | Kundprofil-ID        |
| SegmentProvider      | Text       | App som publicerar segmenten.      |
| SegmentMembershipType | Text       | Kundtyp som det här segmentmedlemskapet registrerar. Stöder flera typer, såsom kund, kontakt eller konto. Standard: kund  |
| Segment       | Text  | Lista med unika segment där kundprofilen är medlem      |
| Identifierare  | Text   | Unik identifierare för det här segmentmedlemskapets post. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Unik identifierare      | Deterministiskt GUID genererat från `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
