---
title: Ansluta till ett Azure Data Lake Storage konto med hjälp av ett tjänstobjekt
description: Använd en Azure-huvudkonto för tjänsten och anslut till din egen datasjö.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647700"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ansluta till ett Azure Data Lake Storage konto med hjälp av ett Azure-tjänstobjekt

Denna artikel diskuterar hur du ansluter Dynamics 365 Customer Insights med ett Azure Data Lake Storage konto med ett Azure huvudkonto för tjänsten istället för lagringskontonycklar. 

Automatiserade verktyg som använder Azure-tjänster bör alltid ha begränsade behörigheter. I stället för att låta program logga in som en fullt privilegierad användare erbjuder Azure huvudkonton för tjänsten. Du kan använda tjänstens huvudkonto för att säkert [lägga till eller redigera en mapp för Common Data Model som datakälla](connect-common-data-model.md) eller [skapa eller uppdatera en miljö](create-environment.md).

> [!IMPORTANT]
> - Data Lake-lagringskontot som använder tjänstens huvudkonto måste vara Gen2 och ha [hierarkiskt namnområde aktiverat](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1-lagringskonton stöds inte.
> - Du behöver administratörsbehörighet för din Azure-prenumeration för att skapa ett huvudkonto för tjänsten.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Skapa ett Azure-huvudkonto för tjänsten för Customer Insights

Innan du skapar ett nytt tjänstens huvudkonto för Customer Insights bör du kontrollera om det redan finns i organisationen.

### <a name="look-for-an-existing-service-principal"></a>Leta efter ett befintligt huvudkonto för tjänsten

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

2. Från **Azure-tjänster**, välj **Azure Active Directory**.

3. Under **Hantera** väljer du **Företagsprogram**.

4. Sök efter Microsoft-program-ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med namnet `Dynamics 365 AI for Customer Insights`.

5. Om du hittar en matchande post betyder det att huvudkonto för tjänsten redan finns. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skärmbild med ett befintligt huvudkonto för tjänsten.":::
   
6. Om inga resultat returneras skapar du ett nytt huvudkonto för tjänsten.

### <a name="create-a-new-service-principal"></a>Skapa ett nytt huvudkonto för tjänsten

1. Installera den senaste versionen av Azure Active Directory PowerShell for Graph. Mer information finns i [Installera Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och väljer **Kör som administratör**.
   
   1. I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.

2. Skapa huvudkonto för tjänsten för Customer Insights med Azure AD PowerShell-modulen.

   1. I PowerShell-fönstret anger du `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Ersätt *[ditt katalog-ID]* med det faktiska Katalog-ID för din Azure-prenumeration där du vill skapa tjänstens huvudnamn. Parametern för miljönamn `AzureEnvironmentName` är valfri.
  
   1. Ange `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Det här kommandot skapar tjänsthuvudman för Customer Insights på den valda Azure-prenumerationen. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Bevilja behörighet till huvudkontot för tjänsten för åtkomst till lagringskontot

Gå till Azure-portalen och ge behörigheter till tjänstehuvudmannen för det lagringskonto du vill använda i Customer Insights.

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

1. Öppna det lagringskonto som du vill att tjänstansvarig för Customer Insights ska ha åtkomst till.

1. I den vänstra ruta, välj **Åtkomstkontroll (IAM)** och välj sedan **Lägg till** > **Lägg till rolltilldelning**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skärmbild som visar Azure-portalen och lägger till en rolltilldelning.":::

1. I fönstret **Lägg till rolltilldelning** ange följande egenskaper:
   - Roll: **Storage Blob-datadeltagare**
   - Tilldela åtkomst till: **användare, grupp eller huvudkonto för tjänsten**
   - Välj medlemmar: **Dynamics 365 AI for Customer Insights** ([huvudkonto för tjänsten](#create-a-new-service-principal) du skapade tidigare i den här proceduren)

1.  Välj **Granska + tilldela**.

Det kan ta upp till 15 minuter att distribuera ändringarna.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Ange Azure-resurs-ID eller Azure-prenumerationsinformationen i bilagan för lagringskontot i Customer Insights

Du kan bifoga ett Data Lake Storage-konton i Customer Insights för att [lagra utdata](manage-environments.md) eller [använda dem som datakälla](connect-dataverse-managed-lake.md). Med det här alternativet kan du välja mellan en resursbaserad metod eller en prenumerationsbaserad metod. Beroende på vilken metod du väljer följer du proceduren i något av följande avsnitt.

### <a name="resource-based-storage-account-connection"></a>Resursbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. I den vänstra rutan, gå till **Inställningar** > **Egenskaper**.

1. Kopiera resurs-ID för lagringskonto.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiera resurs-ID för lagringskonto.":::

1. I Customer Insights infogar du resurs-ID:t i resursfältet som visas på skärmen för lagringskontoanslutning.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Ange resurs-ID för lagringskonto.":::   

1. Fortsätt med de återstående stegen i Customer Insights för att bifoga lagringskontot.

### <a name="subscription-based-storage-account-connection"></a>Prenumerationsbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. I den vänstra rutan, gå till **Inställningar** > **Egenskaper**.

1. Granska **Prenumeration**, **Resursgrupp** och **Namn** för lagringskontot för att se till att du väljer rätt värden i Customer Insights.

1. I Customer Insights väljer du värden för motsvarande fält när du bifogar ett lagringskonto.

1. Fortsätt med de återstående stegen i Customer Insights för att bifoga lagringskontot.


[!INCLUDE [footer-include](includes/footer-banner.md)]