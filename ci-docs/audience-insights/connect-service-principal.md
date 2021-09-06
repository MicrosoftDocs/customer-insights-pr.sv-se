---
title: Ansluta till ett Azure Data Lake Storage konto med hjälp av ett tjänstobjekt
description: Använd en Azure-huvudkonto för tjänsten och anslut till din egen datasjö.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461170"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ansluta till ett Azure Data Lake Storage konto med hjälp av ett Azure-tjänstobjekt
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Automatiserade verktyg som använder Azure-tjänster bör alltid ha begränsade behörigheter. I stället för att låta program logga in som en fullt privilegierad användare erbjuder Azure huvudkonton för tjänsten. Läs vidare för att lära dig hur du ansluter Dynamics 365 Customer Insights med ett Azure Data Lake Storage konto med hjälp av en Azure huvudkonto för tjänsten i stället för lagringskontonycklar. 

Du kan använda huvudkonto för tjänsten för att på ett säkert sätt [lägga till eller redigera mappen Common Data Model datakälla](connect-common-data-model.md), eller [skapa eller uppdatera en miljö](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Det Data Lake Storage-konto som ska användas<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> huvudkonto för tjänsten måste ha [hierarkiskt namnutrymme aktiverat](/azure/storage/blobs/data-lake-storage-namespace).
> - Du måste ha administratörsbehörighet för din Azure-prenumeration för att skapa huvudkontot för tjänsten.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Skapa ett Azure-huvudkonto för tjänsten för Customer Insights

Innan du skapar ett nytt huvudkonto för tjänsten för målgruppsinsikter eller engagemangsinsikter bör du kontrollera om den redan finns i organisationen.

### <a name="look-for-an-existing-service-principal"></a>Leta efter ett befintligt huvudkonto för tjänsten

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

2. Från **Azure-tjänster**, välj **Azure Active Directory**.

3. Under **Hantera** väljer du **Företagsprogram**.

4. Sök efter Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> program-ID:
   - Målgruppsinsikter: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med namnet`Dynamics 365 AI for Customer Insights`
   - Engagemangsinsikter: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` med namnet `Dynamics 365 AI for Customer Insights engagement insights`

5. Om du hittar en matchande post betyder det att huvudkonto för tjänsten redan finns. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skärmbild med ett befintligt huvudkonto för tjänsten.":::
   
6. Om inga resultat returneras skapar du ett nytt huvudkonto för tjänsten.

>[!NOTE]
>För att utnyttja den kompletta kraften Dynamics 365 Customer Insights föreslår vi att du lägger till båda apparna i huvudkonto för tjänsten.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Skapa ett nytt huvudkonto för tjänsten
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Installera den senaste versionen av Azure Active Directory PowerShell for Graph. Mer information finns i [Installera Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och väljer **Kör som administratör**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.

2. Skapa huvudkonto för tjänsten för Customer Insights med Azure AD PowerShell-modulen.

   1. I PowerShell-fönstret anger du `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Ersätt *"[ditt klient-ID]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> med det faktiska ID:t för din klientorganisation där du vill skapa huvudkonto för tjänsten. Parametern för miljönamn `AzureEnvironmentName` är valfri.
  
   1. Ange `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Det här kommandot skapar huvudkontot för tjänsten för målgruppsinsikter på den valda klientorganisationen. 

   1. Ange `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Det här kommandot skapar huvudkonto för tjänsten för engagemangsinsikter<!--note from editor: Edit okay?--> i den valda klientorganisationen.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Bevilja behörighet till huvudkontot för tjänsten för åtkomst till lagringskontot

Gå till Azure Portal och bevilja behörighet till huvudkontot för tjänsten för det lagringskonto du vill använda för målgruppsinsikter.

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

1. Öppna det lagringskonto du vill att tjänstens huvudkonto för målgruppsinsikter ska ha tillgång till.

1. I den vänstra ruta, välj **Åtkomstkontroll (IAM)** och välj sedan **Lägg till** > **Lägg till rolltilldelning**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skärmbild som visar Azure-portalen och lägger till en rolltilldelning.":::

1. I fönstret **Lägg till rolltilldelning** ange följande egenskaper:
   - Roll: **Storage Blob-datadeltagare**
   - Tilldela åtkomst till: **användare, grupp eller huvudkonto för tjänsten**
   - Välj: **Dynamics 365 AI for Customer Insights** och **Dynamics 365 AI for Customer Insights engagemangsinsikter** (de två [huvudkonto](#create-a-new-service-principal) du skapade tidigare i den här proceduren)

1.  Välj **Spara**.

Det kan ta upp till 15 minuter att distribuera ändringarna.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Ange Azure-resurs-ID eller Azure-prenumerationens information i lagringskontot som är bifogat målgruppsinsikter

Du kan<!--note from editor: Edit suggested only if this section is optional.--> bifoga ett Data Lake Storage-konto i målgruppsiniskter för att [lagra utdata ](manage-environments.md) eller [använda dem som datakälla](connect-common-data-service-lake.md). Med det här alternativet kan du välja mellan en resursbaserad metod eller en prenumerationsbaserad metod. Beroende på vilken metod du väljer följer du proceduren i något av följande avsnitt.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Resursbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. I den vänstra rutan, gå till **Inställningar** > **Egenskaper**.

1. Kopiera resurs-ID för lagringskonto.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiera resurs-ID för lagringskonto.":::

1. I målgruppsinsikter infogar du resurs-ID:t i resursfältet som visas på skärmen för anslutning till lagringskonto.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Ange resurs-ID för lagringskonto.":::   

1. Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.

### <a name="subscription-based-storage-account-connection"></a>Prenumerationsbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. I den vänstra rutan, gå till **Inställningar** > **Egenskaper**.

1. Granska **Prenumeration**, **Resursgrupp** och **Namn** på lagringskontot för att se till att du väljer rätt värden i målgruppsinsikter.

1. I målgruppsinsikter väljer du värden för motsvarande fält när du bifogar ett lagringskonto.

1. Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.


[!INCLUDE[footer-include](../includes/footer-banner.md)]