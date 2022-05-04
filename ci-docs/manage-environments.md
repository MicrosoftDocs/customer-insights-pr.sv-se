---
title: Skapa och hantera miljöer
description: Läs om hur du registrerar dig för tjänsten och hur du hanterar miljöer.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647840"
---
# <a name="manage-environments"></a>Hantera miljöer

## <a name="switch-environments"></a>Växla miljö

Välj kontrollen **miljö** i det övre högra hörnet av sidan om du vill ändra miljöer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skärmbild av kontrollen för att växla miljöer.":::

Administratörer kan [skapa](create-environment.md) och hantera miljöer.

## <a name="edit-an-existing-environment"></a>Redigera en befintlig miljö

Du kan redigera vissa av detaljerna i befintliga miljöer.

1.  Välj **Miljö**-väljaren i apphuvudet.

2.  Välj ikonen **Redigera**.

3. I rutan **Redigera miljö** kan du uppdatera miljöinställningarna.

Mer information om miljöinställningar finns i [Skapa en ny miljö](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Anslut till Microsoft Dataverse
   
I **Microsoft Dataverse** steget kan du koppla Customer Insights till din Dataverse miljö. 

Tillhandahåll din egen Microsoft Dataverse-miljö för att dela data (profiler och insikter) med företagsprogram baserade på Dataverse, som Dynamics 365 Marketing eller modellbaserade program i Power Apps.

Om du vill använda [färdiga prediktionsmodeller](predictions-overview.md#out-of-box-models), konfigurera datadelning med Dataverse. Du kan också aktivera datainmatning från lokala datakällor, med den Microsoft Dataverse miljö-URL som organisationen administrerar.

Om du aktiverar datadelning med Microsoft Dataverse genom att markera kryssrutan för datadelning utlöses en fullständig engångsuppdatering av dina datakällor och alla andra processer.

> [!IMPORTANT]
> 1. Customer Insights och Dataverse måste finnas i samma region för att kunna dela data.
> 1. Du måste ha en global administratörsroll i Dataverse-miljön. Kontrollera att denna [Dataverse-miljö är associerad](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) med vissa säkerhetsgrupper, samt kontrollera att du har lagts till i dessa säkerhetsgrupper.
> 1. Ingen befintlig Customer Insights-miljö har redan associerats med den Dataverse-miljön. Lär dig hur du [tar bort en befintlig anslutning till en Dataverse-miljö](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivera datadelning med Dataverse från din egen ( Azure Data Lake Storage-förhandsversion)

Om din miljö är konfigurerad att använda din egen Azure Data Lake Storage för att lagra Customer Insights-data, kommer möjliggörande av datadelning med Microsoft Dataverse att kräva viss extra konfiguration.

1. Skapa två säkerhetsgrupper i din Azure-prenumeration – en **Läsare**-säkerhetsgrupp och en **Deltagare**-säkerhetsgrupp – och ange Microsoft Dataverse-tjänsten som ägare för båda säkerhetsgrupper.
2. Hantera åtkomstkontrolllistan (ACL) för CustomerInsights-behållare i ditt lagringskonto via dessa säkerhetsgrupper. Lägg till Microsoft Dataverse-tjänsten och eventuella Dataverse-baserade affärsprogram som Dynamics 365 Marketing i säkerhetsgruppen **Läsare** med **skrivskyddade** behörigheter. Lägg *endast* till programmet Customer Insights i säkerhetsgruppen **Deltagare** för att bevilja både **läs- och skrivbehörighet** för att skriva profiler och insikter.
   
#### <a name="prerequisites"></a>Förutsättningar

För att kunna köra PowerShell-skripten måste följande tre moduler importeras. 

1. Installera den senaste versionen av [Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).
   1. På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och väljer **Kör som administratör**.
   1. I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.
2. Importera tre moduler.
    1. I PowerShell-fönstret anger du `Install-Module -Name Az.Accounts` och följer stegen. 
    1. Upprepa för `Install-Module -Name Az.Resources` och `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Konfigurationssteg

1. Hämta de två PowerShell-skripten du behöver för körning från vår teknikers [GitHub-lagringsplats](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Du måste ha behörighet för *administratör för klientorganisation* för att kunna köra detta PowerShell-skript. 
       - Detta PowerShell-skriptet skapar två säkerhetsgrupper i din Azure-prenumeration. En för gruppen Läsare och en annan för gruppen Deltagare, och gör dessutom tjänsten Microsoft Dataverse till ägare för båda säkerhetsgrupper.
       - Kör det här PowerShell-skriptet i Windows PowerShell genom att tillhandahålla Azure-prenumerations-ID:t som innehåller din Azure Data Lake Storage. Öppna PowerShell-skriptet i en redigerare om du vill granska ytterligare information och logiken som implementerats.
       - Spara båda värdena för säkerhetsgruppens ID som genereras av detta skript, detta eftersom vi ska använda dem i `ByolSetup.ps1`-skriptet.
       
        > [!NOTE]
        > Skapandet av säkerhetsgrupper kan inaktiveras i klientorganisationen. I så fall behövs en manuell konfiguration, och din Azure AD-administratör måste även [ aktivera skapande av säkerhetsgrupper](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Du behöver behörigheter för *Lagringsägare för blogdata* på nivån för lagringskonto/behållare för att köra det här skriptet, eller också skapar det här skriptet ett åt dig. Din rolltilldelning kan tas bort manuellt när skriptet har körts.
        - Detta PowerShell-skript lägger till den tole-baserade åtkomstkontrollen (RBAC) för Microsoft Dataverse-tjänsten och alla Dataverse-baserade affärsprogram. Dessutom uppdateras åtkomstkontrollistan (ACL) i CustomerInsights-behållaren för de säkerhetsgrupper som skapats med `CreateSecurityGroups.ps1`-skriptet. Gruppen Deltagare har behörigheten *rwx* och gruppen Läsare har endast behörigheten *r-x*.
        - Kör detta PowerShell-skript i Windows PowerShell genom att tillhandahålla det ID för Azure-prenumeration som innehåller ditt Azure Data Lake Storage, namnet på ditt lagringskonto, resursgruppens namn samt ID-värdena för säkerhetsgrupperna Läsare och Deltagare. Öppna PowerShell-skriptet i en redigerare om du vill granska ytterligare information och logiken som implementerats.
        - Kopiera utdatasträngen när skriptet har körts. Utdatasträngen ser ut så här: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Ange utdatasträngen som kopierats ovan i fältet **ID för behörigheter** i konfigurationssteget för miljön för Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsalternativ för att aktivera datadelning från din egna Azure Data Lake Storage med Microsoft Dataverse.":::

Customer Insights stöder inte följande datadelningsscenarier:
- Om du aktiverar datadelning med Dataverse kommer du inte kunna [skapa förutsagda eller saknade värden i en entitet](predictions.md).
- Om du aktiverar datadelning med Dataverse kommer du inte att kunna visa några valfria PowerBI Embedded-rapporter i din Customer Insights-miljö.

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

## <a name="copy-the-environment-configuration"></a>Kopiera miljökonfigurationen

Som administratör kan du välja att kopiera konfigurationen från en befintlig miljö när du skapar en ny. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skärmbild av inställningsalternativen i miljöinställningarna.":::

Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.

Följande konfigurationsinställningar kan kopieras:

- Inmatade/importerade datakällor
- Dataföreningskonfiguration (mappning, matchning, sammanslagning)
- Segments
- Mått
- Relationer
- Aktiviteter
- Sök och filtrera index
- Exportmål
- Schemalagd uppdatering
- Berikningar
- Modellhantering
- Rolltilldelningar

## <a name="set-up-a-copied-environment"></a>Konfigurera en kopierad miljö

När du kopierar miljökonfigurationen kopieras *inte* följande data:

- Kundprofiler.
- Autentiseringsuppgifter för datakälla. Du måste ange autentiseringsuppgifterna för varje datakälla och uppdatera datakällorna manuellt.
- Datakällor från mappen Common Data Model och Dataverse-hanterad data lake. Du måste skapa dessa datakällor manuellt med samma namn som i källmiljön.
- Anslutningshemligheter som används för export och berikanden. Du måste återautentisera anslutningarna och sedan återaktivera berikanden och exporter. 

När du kopierar en miljö visas ett bekräftelsemeddelande om att den nya miljön har skapats. Välj **gå till datakällor** om du vill visa listan över datakällor.

I alla data källor visas statusen **Autentiseringsuppgifter krävs**. Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista över datakällor som kopierats och som behöver autentisering.":::

När datakällorna har uppdaterats går du till **Data** > **Förena**. Här hittar du inställningar från källmiljön. Redigera dem efter behov eller välj **kör** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.

När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.

Innan du återaktiverar exporter och berikanden går du till **Administratör** > **Anslutningar** för att återautentisera anslutningarna i din nya miljö.

## <a name="change-the-owner-of-an-environment"></a>Byt ägare till miljön

Flera användare kan ha administratörsbehörigheter i Customer Insights, men bara en användare är ägare till en miljö. Som standard är det administratören som ursprungligen skapar en miljö. Som administratör för en miljö kan du tilldela ägarskap till en annan användare med administratörsbehörighet.

1. Välj **Miljö**-väljaren i apphuvudet.

1. Välj ikonen **Redigera**.

1. I rutan **Redigera miljö**, gå till steget **Grundläggande information**.

1. I fältet **Ändra miljöns ägare**, välj ny ägare för miljön.  

1. Välj **Granska och slutför**, sedan **Uppdatera** för att tillämpa ändringarna. 

## <a name="claim-ownership-of-an-environment"></a>Begära ägarskap för en miljö

Om ägaren till en miljö lämnar organisationen eller om användarkontot tas bort, har miljön ingen ägare. En användare med administratörsbehörighet kan begära ägarskapet och bli den nya ägaren. De kan fortsätta äga miljön eller [ändra ägarskapet till en annan administratör](#change-the-owner-of-an-environment). 

Om du vill begära ägarskap väljer du knappen **Ta ägarskap** som visas överst på varje sida i Customer Insights när den ursprungliga ägaren lämnar organisationen.

## <a name="reset-an-existing-environment"></a>Återställa en befintlig miljö

Som ägare av en miljö kan du återställa en miljö till ett tomt tillstånd om du vill ta bort alla konfigurationer och ta bort inrättade data.

1.  Välj **Miljö**-väljaren i apphuvudet. 

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Återställ**. 

4.  Bekräfta borttagningen genom att ange miljönamnet och välj **Återställ**.

## <a name="delete-an-existing-environment"></a>Ta bort en befintlig miljö

Som ägare av en miljö kan du ta bort en miljö som du administrerar.

1.  Välj **Miljö**-väljaren i apphuvudet.

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Ta bort**. 

4.  Bekräfta borttagningen genom att ange miljö namnet och välja **ta bort**.

> [!NOTE]
> Om du tar bort en miljö tas inte anslutningen till en Dataverse-miljö bort. Lär dig hur du [tar bort en befintlig anslutning till en Dataverse-miljö](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
