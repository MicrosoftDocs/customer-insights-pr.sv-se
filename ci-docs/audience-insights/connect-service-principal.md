---
title: Ansluta till ett Azure Data Lake Storage Gen 2-konto med ett huvudkonto för tjänsten
description: Använd ett huvudkonto för Azure-tjänsten för målgruppsinsikter för att ansluta till din egen datasjö när de bifogas till målgruppsinsikter.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267744"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Anslut till ett Azure Data Lake Storage Gen2-konto med ett huvudkonto för Azure-tjänsten för målgruppsinsikter

Automatiserade verktyg som använder Azure-tjänster bör alltid ha begränsade behörigheter. I stället för att låta program logga in som en fullt privilegierad användare erbjuder Azure huvudkonton för tjänsten. Läs mer om hur du kan ansluta målgruppsinsikter med ett Azure Data Lake Storage Gen2-konto med hjälp av ett huvudkonto för Azure-tjänsten i stället för lagringskontonycklar. 

Du kan använda tjänstens huvudkonto för att säkert [lägga till eller redigera en Common Data Model-mapp som en datakälla](connect-common-data-model.md) eller [skapa en ny eller uppdatera en befintlig miljö](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Lagringskontot Azure Data Lake Gen2 som ska använda huvudkontot för tjänsten måste ha [Hierarkiskt namnområde (HNS) aktiverat](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - Du måste ha administratörsbehörighet för din Azure-prenumeration för att skapa huvudkontot för tjänsten.

## <a name="create-azure-service-principal-for-audience-insights"></a>Skapa Azure-tjänstens huvudkonto för målgruppsinsikter

Innan du skapar ett nytt huvudkonto för tjänsten för målgruppsinsikter bör du kontroller om det redan finns ett inom organisationen.

### <a name="look-for-an-existing-service-principal"></a>Leta efter ett befintligt huvudkonto för tjänsten

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

2. Välj **Azure Active Directory** från Azure-tjänsterna.

3. Under **Hantera** väljer du **Företagsprogram**.

4. Sök efter första parts program-ID för målgruppsinsikter `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller namnet `Dynamics 365 AI for Customer Insights`.

5. Om du hittar en matchande post innebär det att huvudkontot för tjänsten för målgruppsinsikter existerar. Du behöver inte skapa det igen.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skärmbild som visar det befintliga huvudkontot för tjänsten.":::
   
6. Om inga resultat returneras skapar du ett nytt huvudkonto för tjänsten.

### <a name="create-a-new-service-principal"></a>Skapa ett nytt huvudkonto för tjänsten

1. Installera den senaste versionen av **Azure Active Directory PowerShell för Graph**. Mer information finns i [Installera Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och **Kör som administratör**.
   
   - I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.

2. Skapa huvudkontot för tjänsten för målgruppsinsikter med Azure AD PowerShell-modulen.
   - I PowerShell-fönstret anger du `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Ersätt "klientorganisationens ID" med klientorganisationens faktiska ID där du vill skapa huvudkontot för tjänsten. Parametern för miljönamn `AzureEnvironmentName` är valfri.
  
   - Ange `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Det här kommandot skapar huvudkontot för tjänsten för målgruppsinsikter på den valda klientorganisationen.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Bevilja behörighet till huvudkontot för tjänsten för åtkomst till lagringskontot

Gå till Azure Portal och bevilja behörighet till huvudkontot för tjänsten för det lagringskonto du vill använda för målgruppsinsikter.

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

1. Öppna det lagringskonto du vill att tjänstens huvudkonto för målgruppsinsikter ska ha tillgång till.

1. Välj **Åtkomstkontroll (IAM)** från navigeringsfönstret och välj **Lägg till** > **Lägg till rolltilldelning**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skärmbild som visar Azure Portal när du lägger till en rolltilldelning.":::
   
1. I fönstret **Lägg till rolltilldelning** anger du följande egenskaper:
   - Roll: *Storage Blob-datadeltagare*
   - Tilldela åtkomst till: *användare, grupp eller huvudkonto för tjänsten*
   - Välj: *Dynamics 365 AI för Customer Insights* (det [huvudkonto för tjänsten du skapade](#create-a-new-service-principal))

1.  Välj **Spara**.

Det kan ta upp till 15 minuter att distribuera ändringarna.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Ange Azure-resurs-ID eller Azure-prenumerationens information i lagringskontot som är bifogat målgruppsinsikter.

Bifoga ett Azure Data Lake-lagringskonto i målgruppsinsikter för att [lagra utdata](manage-environments.md) eller [använda det som en datakälla](connect-common-data-service-lake.md). Om du väljer alternativet Azure Data Lake kan du välja mellan en resurs- eller en prenumerationsbaserad metod.

Följ stegen nedan för att ange den information som krävs för den valda metoden.

### <a name="resource-based-storage-account-connection"></a>Resursbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. Gå till **Inställningar** > **Egenskaper** i navigeringsfönstret.

1. Kopiera resurs-ID för lagringskonto.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiera resurs-ID för lagringskonto.":::

1. I målgruppsinsikter infogar du resurs-ID i resursfältet som visas i fönstret för anslutning till lagringskonto.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Ange resurs-ID för lagringskonto.":::   
   
1. Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.

### <a name="subscription-based-storage-account-connection"></a>Prenumerationsbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. Gå till **Inställningar** > **Egenskaper** i navigeringsfönstret.

1. Granska **Prenumeration**, **Resursgrupp** och **Namn** på lagringskontot för att se till att du väljer rätt värden i målgruppsinsikter.

1. I målgruppsinsikter väljer du värdena eller för motsvarande fält när du ansluter lagringskontot.
   
1. Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.


[!INCLUDE[footer-include](../includes/footer-banner.md)]