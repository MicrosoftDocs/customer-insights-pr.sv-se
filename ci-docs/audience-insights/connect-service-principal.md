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
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="47a02-103">Anslut till ett Azure Data Lake Storage Gen2-konto med ett huvudkonto för Azure-tjänsten för målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="47a02-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="47a02-104">Automatiserade verktyg som använder Azure-tjänster bör alltid ha begränsade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="47a02-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="47a02-105">I stället för att låta program logga in som en fullt privilegierad användare erbjuder Azure huvudkonton för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="47a02-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="47a02-106">Läs mer om hur du kan ansluta målgruppsinsikter med ett Azure Data Lake Storage Gen2-konto med hjälp av ett huvudkonto för Azure-tjänsten i stället för lagringskontonycklar.</span><span class="sxs-lookup"><span data-stu-id="47a02-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="47a02-107">Du kan använda tjänstens huvudkonto för att säkert [lägga till eller redigera en Common Data Model-mapp som en datakälla](connect-common-data-model.md) eller [skapa en ny eller uppdatera en befintlig miljö](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="47a02-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="47a02-108">Lagringskontot Azure Data Lake Gen2 som ska använda huvudkontot för tjänsten måste ha [Hierarkiskt namnområde (HNS) aktiverat](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="47a02-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="47a02-109">Du måste ha administratörsbehörighet för din Azure-prenumeration för att skapa huvudkontot för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="47a02-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="47a02-110">Skapa Azure-tjänstens huvudkonto för målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="47a02-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="47a02-111">Innan du skapar ett nytt huvudkonto för tjänsten för målgruppsinsikter bör du kontroller om det redan finns ett inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="47a02-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="47a02-112">Leta efter ett befintligt huvudkonto för tjänsten</span><span class="sxs-lookup"><span data-stu-id="47a02-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="47a02-113">Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.</span><span class="sxs-lookup"><span data-stu-id="47a02-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="47a02-114">Välj **Azure Active Directory** från Azure-tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="47a02-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="47a02-115">Under **Hantera** väljer du **Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="47a02-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="47a02-116">Sök efter första parts program-ID för målgruppsinsikter `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller namnet `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="47a02-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="47a02-117">Om du hittar en matchande post innebär det att huvudkontot för tjänsten för målgruppsinsikter existerar.</span><span class="sxs-lookup"><span data-stu-id="47a02-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="47a02-118">Du behöver inte skapa det igen.</span><span class="sxs-lookup"><span data-stu-id="47a02-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skärmbild som visar det befintliga huvudkontot för tjänsten.":::
   
6. <span data-ttu-id="47a02-120">Om inga resultat returneras skapar du ett nytt huvudkonto för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="47a02-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="47a02-121">Skapa ett nytt huvudkonto för tjänsten</span><span class="sxs-lookup"><span data-stu-id="47a02-121">Create a new service principal</span></span>

1. <span data-ttu-id="47a02-122">Installera den senaste versionen av **Azure Active Directory PowerShell för Graph**.</span><span class="sxs-lookup"><span data-stu-id="47a02-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="47a02-123">Mer information finns i [Installera Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="47a02-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="47a02-124">På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="47a02-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="47a02-125">I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="47a02-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="47a02-126">Skapa huvudkontot för tjänsten för målgruppsinsikter med Azure AD PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="47a02-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="47a02-127">I PowerShell-fönstret anger du `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="47a02-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="47a02-128">Ersätt "klientorganisationens ID" med klientorganisationens faktiska ID där du vill skapa huvudkontot för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="47a02-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="47a02-129">Parametern för miljönamn `AzureEnvironmentName` är valfri.</span><span class="sxs-lookup"><span data-stu-id="47a02-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="47a02-130">Ange `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="47a02-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="47a02-131">Det här kommandot skapar huvudkontot för tjänsten för målgruppsinsikter på den valda klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="47a02-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="47a02-132">Bevilja behörighet till huvudkontot för tjänsten för åtkomst till lagringskontot</span><span class="sxs-lookup"><span data-stu-id="47a02-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="47a02-133">Gå till Azure Portal och bevilja behörighet till huvudkontot för tjänsten för det lagringskonto du vill använda för målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="47a02-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="47a02-134">Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.</span><span class="sxs-lookup"><span data-stu-id="47a02-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="47a02-135">Öppna det lagringskonto du vill att tjänstens huvudkonto för målgruppsinsikter ska ha tillgång till.</span><span class="sxs-lookup"><span data-stu-id="47a02-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="47a02-136">Välj **Åtkomstkontroll (IAM)** från navigeringsfönstret och välj **Lägg till** > **Lägg till rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="47a02-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skärmbild som visar Azure Portal när du lägger till en rolltilldelning.":::
   
1. <span data-ttu-id="47a02-138">I fönstret **Lägg till rolltilldelning** anger du följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="47a02-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="47a02-139">Roll: *Storage Blob-datadeltagare*</span><span class="sxs-lookup"><span data-stu-id="47a02-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="47a02-140">Tilldela åtkomst till: *användare, grupp eller huvudkonto för tjänsten*</span><span class="sxs-lookup"><span data-stu-id="47a02-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="47a02-141">Välj: *Dynamics 365 AI för Customer Insights* (det [huvudkonto för tjänsten du skapade](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="47a02-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="47a02-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="47a02-142">Select **Save**.</span></span>

<span data-ttu-id="47a02-143">Det kan ta upp till 15 minuter att distribuera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="47a02-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="47a02-144">Ange Azure-resurs-ID eller Azure-prenumerationens information i lagringskontot som är bifogat målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="47a02-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="47a02-145">Bifoga ett Azure Data Lake-lagringskonto i målgruppsinsikter för att [lagra utdata](manage-environments.md) eller [använda det som en datakälla](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="47a02-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="47a02-146">Om du väljer alternativet Azure Data Lake kan du välja mellan en resurs- eller en prenumerationsbaserad metod.</span><span class="sxs-lookup"><span data-stu-id="47a02-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="47a02-147">Följ stegen nedan för att ange den information som krävs för den valda metoden.</span><span class="sxs-lookup"><span data-stu-id="47a02-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="47a02-148">Resursbaserad anslutning till lagringskonto</span><span class="sxs-lookup"><span data-stu-id="47a02-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="47a02-149">Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="47a02-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="47a02-150">Gå till **Inställningar** > **Egenskaper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="47a02-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="47a02-151">Kopiera resurs-ID för lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="47a02-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiera resurs-ID för lagringskonto.":::

1. <span data-ttu-id="47a02-153">I målgruppsinsikter infogar du resurs-ID i resursfältet som visas i fönstret för anslutning till lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="47a02-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Ange resurs-ID för lagringskonto.":::   
   
1. <span data-ttu-id="47a02-155">Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="47a02-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="47a02-156">Prenumerationsbaserad anslutning till lagringskonto</span><span class="sxs-lookup"><span data-stu-id="47a02-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="47a02-157">Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="47a02-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="47a02-158">Gå till **Inställningar** > **Egenskaper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="47a02-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="47a02-159">Granska **Prenumeration**, **Resursgrupp** och **Namn** på lagringskontot för att se till att du väljer rätt värden i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="47a02-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="47a02-160">I målgruppsinsikter väljer du värdena eller för motsvarande fält när du ansluter lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="47a02-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="47a02-161">Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="47a02-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]