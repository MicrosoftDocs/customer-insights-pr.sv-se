---
title: Arbeta med Customer Insights-data i Microsoft Dataverse
description: Lär dig hur du ansluter Customer Insights och Microsoft Dataverse och förstå utdataentiteterna som exporteras till Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011576"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeta med Customer Insights-data i Microsoft Dataverse

Med Customer Insights kan du göra utdataentiteter tillgängliga som [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denna integration möjliggör enkel datadelning och anpassad utveckling genom en metod med lite kod/ingen kod. [Utdataentiteterna](#output-entities) är tillgängliga som tabeller i en Dataverse-miljö. Du kan använda data för val annat program baserat på Dataverse-tabeller. Dessa tabeller möjliggör scenarier som automatiserade arbetsflöden genom Power Automate eller att skapa appar med Power Apps.

Om du ansluter till din Dataverse-miljö kan du [även hämta data från lokala datakällor med Power Platform-dataflöden och gateways](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Förutsättningar

- Customer Insights och Dataverse-miljöer måste finnas i samma region.
- Du måste ha en global administratörsroll i Dataverse-miljön. Kontrollera att denna [Dataverse-miljö är associerad](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) med vissa säkerhetsgrupper, samt kontrollera att du har lagts till i dessa säkerhetsgrupper.
- Ingen annan Customer Insights-miljö har redan associerats med den Dataverse-miljö du vill ansluta. Lär dig hur du [tar bort en befintlig anslutning till en Dataverse-miljö](#remove-an-existing-connection-to-a-dataverse-environment).
- En Microsoft Dataverse-miljö kan bara ansluta till ett enda lagringskonto. Detta gäller endast om du konfigurerar miljön för att [använda ditt Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Ansluta en Dataverse-miljö till Customer Insights

I steget **Microsoft Dataverse** kan du koppla Customer Insights till din Dataverse-miljö när du [skapar en Customer Insights-miljö](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="-datadelning med Microsoft Dataverse automatiskt aktiverat för nya miljöer.":::

Administratörer kan konfigurera Customer Insights för att ansluta till en befintlig Dataverse-miljö. Genom att tillhandahålla webbadressen till Dataverse miljön, det kopplar till deras nya Customer Insights-miljö.

Om du inte vill använda en befintlig Dataverse-miljö skapar systemet en ny miljö för Customer Insights data i din klientorganisation. [Power Platform-administratörer kan styra vem som kan skapa miljöer](/power-platform/admin/control-environment-creation). När du konfigurerar en ny Customer Insights-miljö och administratören har inaktiverat skapandet av Dataverse-miljöer för alla utom administratörer kanske du inte kan skapa en ny miljö.

**Aktivera datadelning** med Dataverse genom att markera kryssrutan för datadelning.

Om du använder ditt eget Data Lake Storage-konto behöver du också **behörighetsidentifieraren**. Mer information om hur du hämtar behörighetsidentifieraren finns i följande avsnitt.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivera datadelning med Dataverse från din egen ( Azure Data Lake Storage-förhandsversion)

Att aktivera datadelning med Microsoft Dataverse när din miljö [använder ditt eget Azure Data Lake Storage-konto](own-data-lake-storage.md) kräver lite extra konfiguration. Användaren som konfigurerar Customer Insights-miljön måste minst ha behörighet för **Storage Blob Data-läsare** för behållaren *CustomerInsights* på Azure Data Lake Storage-kontot.

1. Skapa två säkerhetsgrupper i din Azure-prenumeration – en **Läsare**-säkerhetsgrupp och en **Deltagare**-säkerhetsgrupp – och ange Microsoft Dataverse-tjänsten som ägare för båda säkerhetsgrupper.
2. Hantera åtkomstkontrolllistan (ACL) för CustomerInsights-behållare i ditt lagringskonto via dessa säkerhetsgrupper. Lägg till Microsoft Dataverse-tjänsten och eventuella Dataverse-baserade affärsprogram som Dynamics 365 Marketing i säkerhetsgruppen **Läsare** med **skrivskyddade** behörigheter. Lägg *endast* till programmet Customer Insights i säkerhetsgruppen **Deltagare** för att bevilja både **läs- och skrivbehörighet** för att skriva profiler och insikter.

### <a name="limitations"></a>Begränsningar

Det finns två begränsningar för hur du använder Dataverse med ditt eget Azure Data Lake Storage-konto:

- Det finns en till en-mappning mellan en Dataverse-organisation och ett Azure Data Lake Storage-konto. När en Dataverse-organisation väl är ansluten till ett lagringskonto går det inte att ansluta den till ett annat lagringskonto. Denns begränsning förhindrar att Dataverse fyller i flera olika lagringskonton.
- Datadelning fungerar inte om en Azure Private Link krävs för att få åtkomst till ditt Azure Data Lake Storage-lagringskonto eftersom detta finns bakom en brandvägg. Dataverse stöder för närvarande inte anslutningen till privata slutpunkter via Private Link.

### <a name="set-up-powershell"></a>Konfigurera PowerShell

För att kunna köra PowerShell-skripten måste du först konfigurera PowerShell därefter.

1. Installera den senaste versionen av [Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).
   1. På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och väljer **Kör som administratör**.
   1. I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.
2. Importera tre moduler.
    1. I PowerShell-fönstret anger du `Install-Module -Name Az.Accounts` och följer stegen.
    1. Upprepa för `Install-Module -Name Az.Resources` och `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigurationssteg

1. Hämta de två PowerShell-skripten du behöver för körning från vår teknikers [GitHub-lagringsplats](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Du måste ha behörighet för *administratör för klientorganisation* för att kunna köra detta PowerShell-skript.
       - Detta PowerShell-skriptet skapar två säkerhetsgrupper i din Azure-prenumeration. En för gruppen Läsare och en annan för gruppen Deltagare, och gör dessutom tjänsten Microsoft Dataverse till ägare för båda säkerhetsgrupper.
       - Kör det här PowerShell-skriptet i Windows PowerShell genom att tillhandahålla Azure-prenumerations-ID:t som innehåller din Azure Data Lake Storage. Öppna PowerShell-skriptet i en redigerare om du vill granska ytterligare information och logiken som implementerats.
       - Spara båda värdena för säkerhetsgruppens ID som genereras av detta skript, detta eftersom vi ska använda dem i `ByolSetup.ps1`-skriptet.

        > [!NOTE]
        > Skapandet av säkerhetsgrupper kan inaktiveras i klientorganisationen. I så fall behövs en manuell konfiguration, och din Azure AD-administratör måste även [ aktivera skapande av säkerhetsgrupper](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Du behöver behörigheter för *Storage Blob Data-ägare* på nivån för lagringskonto/behållare för att köra det här skriptet, eller också skapar det här skriptet ett åt dig. Din rolltilldelning kan tas bort manuellt när skriptet har körts.
        - Detta PowerShell-skript lägger till den tole-baserade åtkomstkontrollen (RBAC) för Microsoft Dataverse-tjänsten och alla Dataverse-baserade affärsprogram. Dessutom uppdateras åtkomstkontrollistan (ACL) i CustomerInsights-behållaren för de säkerhetsgrupper som skapats med `CreateSecurityGroups.ps1`-skriptet. Gruppen Deltagare har behörigheten *rwx* och gruppen Läsare har endast behörigheten *r-x*.
        - Kör detta PowerShell-skript i Windows PowerShell genom att tillhandahålla det ID för Azure-prenumeration som innehåller ditt Azure Data Lake Storage, namnet på ditt lagringskonto, resursgruppens namn samt ID-värdena för säkerhetsgrupperna Läsare och Deltagare. Öppna PowerShell-skriptet i en redigerare om du vill granska ytterligare information och logiken som implementerats.
        - Kopiera utdatasträngen när skriptet har körts. Utdatasträngen ser ut så här: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Ange utdatasträngen som kopierats ovan i fältet **ID för behörigheter** i konfigurationssteget för miljön för Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsalternativ för att aktivera datadelning från din egna Azure Data Lake Storage med Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Ta bort en befintlig anslutning till en Dataverse-miljö

När du ansluter till en Dataverse-miljö betyder felmeddelandet **Denna CDS-organisation är redan ansluten till en annan instans av Customer Insights** att Dataverse-miljön redan används i en Customer Insights-miljö. Du kan ta bort den befintliga anslutningen som global administratör i Dataverse-miljön. Det kan ta några timmar innan ändringarna fylls i.

1. Gå till [Power Apps](https://make.powerapps.com).
1. Välj miljö i miljöväljaren.
1. Gå till **Lösningar**
1. Avinstallera eller ta bort lösningen med namnet **Kundkortstillägg för Dynamics 365 Customer Insights (förhandsgranskning)**.

ELLER

1. Öppna din Dataverse-miljö.
1. Gå till **Avancerade inställningar** > **Lösningar**.
1. Avinstallera lösningen **CustomerInsightsCustomerCard**.

Om borttagningen av anslutningen misslyckas på grund av beroenden måste du även ta bort beroendena. Mer information finns i [Ta bort beroenden](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Utdataentiteter

Vissa utdataentiteter från Customer Insights är tillgängliga som tabeller i Dataverse. Avsnitten nedan beskriver det förväntade schemat för dessa tabeller.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Berikning](#enrichment)
- [Prediktion](#prediction)
- [Segmentmedlemskap](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Den här tabellen innehåller den enhetliga kundprofilen från Customer Insights. Schemat för Unified customer profile beror på entiteterna och attributen som används i föreningsprocessen för data. Ett kundprofilschema innehåller vanligtvis en delmängd av attributen från [definitionen av Common Data Model för CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabellen AlternateKey innehåller nycklar för entiteterna, som deltog i sammanslagningsprocessen.

|Column  |Type  |Beskrivning  |
|---------|---------|---------|
|DataSourceName    |String         | Datakällans namn. Till exempel: `datasource5`        |
|EntityName        | String        | Namnet på entiteten i Customer Insights. Till exempel: `contact1`        |
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

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kundprofil-ID        |
| SegmentProvider      | String       | App som publicerar segmenten.      |
| SegmentMembershipType | String       | Kundtyp som det här segmentmedlemskapet registrerar. Stöder flera typer, såsom kund, kontakt eller konto. Standard: kund  |
| Segment       | JSON-sträng  | Lista med unika segment där kundprofilen är medlem      |
| msdynci_identifier  | String   | Unik identifierare för det här segmentmedlemskapets post. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministiskt GUID genererat från `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
