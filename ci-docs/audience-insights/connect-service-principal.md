---
title: Ansluta till ett Azure Data Lake Storage Gen 2-konto med ett huvudkonto för tjänsten
description: använd ett huvudkonto för Azure-tjänsten för målgruppsinsikter för att ansluta till din egen datasjö när de bifogas till målgruppsinsikter.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644110"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="10ab1-103">Anslut till ett Azure Data Lake Storage Gen2-konto med ett huvudkonto för Azure-tjänsten för målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="10ab1-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="10ab1-104">Automatiserade verktyg som använder Azure-tjänster bör alltid ha begränsade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="10ab1-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="10ab1-105">I stället för att låta program logga in som en fullt privilegierad användare erbjuder Azure huvudkonton för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="10ab1-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="10ab1-106">Läs mer om hur du kan ansluta målgruppsinsikter med ett Azure Data Lake Storage Gen2-konto med hjälp av ett huvudkonto för Azure-tjänsten i stället för lagringskontonycklar.</span><span class="sxs-lookup"><span data-stu-id="10ab1-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="10ab1-107">Du kan använda tjänstens huvudkonto för att säkert [lägga till eller redigera en Common Data Model-mapp som en datakälla](connect-common-data-model.md) eller [skapa en ny eller uppdatera en befintlig miljö](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="10ab1-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="10ab1-108">Du måste ha administratörsbehörighet för din Azure-prenumeration för att skapa huvudkontot för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="10ab1-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="10ab1-109">Skapa Azure-tjänstens huvudkonto för målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="10ab1-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="10ab1-110">Innan du skapar ett nytt huvudkonto för tjänsten för målgruppsinsikter bör du kontroller om det redan finns ett inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="10ab1-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="10ab1-111">Leta efter ett befintligt huvudkonto för tjänsten</span><span class="sxs-lookup"><span data-stu-id="10ab1-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="10ab1-112">Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.</span><span class="sxs-lookup"><span data-stu-id="10ab1-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="10ab1-113">Välj **Azure Active Directory** från Azure-tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="10ab1-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="10ab1-114">Under **Hantera** väljer du **Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="10ab1-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="10ab1-115">Sök efter första parts program-ID för målgruppsinsikter `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller namnet `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="10ab1-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="10ab1-116">Om du hittar en matchande post innebär det att huvudkontot för tjänsten för målgruppsinsikter existerar.</span><span class="sxs-lookup"><span data-stu-id="10ab1-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="10ab1-117">Du behöver inte skapa det igen.</span><span class="sxs-lookup"><span data-stu-id="10ab1-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skärmbild som visar det befintliga huvudkontot för tjänsten.":::
   
6. <span data-ttu-id="10ab1-119">Om inga resultat returneras skapar du ett nytt huvudkonto för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="10ab1-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="10ab1-120">Skapa ett nytt huvudkonto för tjänsten</span><span class="sxs-lookup"><span data-stu-id="10ab1-120">Create a new service principal</span></span>

1. <span data-ttu-id="10ab1-121">Installera den senaste versionen av **Azure Active Directory PowerShell för Graph**.</span><span class="sxs-lookup"><span data-stu-id="10ab1-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="10ab1-122">Mer information finns i [Installera Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="10ab1-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="10ab1-123">På datorn väljer du Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="10ab1-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="10ab1-124">I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="10ab1-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="10ab1-125">Skapa huvudkontot för tjänsten för målgruppsinsikter med Azure AD PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="10ab1-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="10ab1-126">I PowerShell-fönstret anger du `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="10ab1-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="10ab1-127">Ersätt "klientorganisationens ID" med klientorganisationens faktiska ID där du vill skapa huvudkontot för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="10ab1-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="10ab1-128">Parametern för miljönamn `AzureEnvironmentName` är valfri.</span><span class="sxs-lookup"><span data-stu-id="10ab1-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="10ab1-129">Ange `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="10ab1-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="10ab1-130">Det här kommandot skapar huvudkontot för tjänsten för målgruppsinsikter på den valda klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="10ab1-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="10ab1-131">Bevilja behörighet till huvudkontot för tjänsten för åtkomst till lagringskontot</span><span class="sxs-lookup"><span data-stu-id="10ab1-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="10ab1-132">Gå till Azure Portal och bevilja behörighet till huvudkontot för tjänsten för det lagringskonto du vill använda för målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="10ab1-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="10ab1-133">Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.</span><span class="sxs-lookup"><span data-stu-id="10ab1-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="10ab1-134">Öppna det lagringskonto du vill att tjänstens huvudkonto för målgruppsinsikter ska ha tillgång till.</span><span class="sxs-lookup"><span data-stu-id="10ab1-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="10ab1-135">Välj **Åtkomstkontroll (IAM)** från navigeringsfönstret och välj **Lägg till** > **Lägg till rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="10ab1-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skärmbild som visar Azure Portal när du lägger till en rolltilldelning.":::
   
1. <span data-ttu-id="10ab1-137">I fönstret **Lägg till rolltilldelning** anger du följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="10ab1-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="10ab1-138">Roll: *Storage Blob-datadeltagare*</span><span class="sxs-lookup"><span data-stu-id="10ab1-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="10ab1-139">Tilldela åtkomst till: *användare, grupp eller huvudkonto för tjänsten*</span><span class="sxs-lookup"><span data-stu-id="10ab1-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="10ab1-140">Välj: *Dynamics 365 AI för Customer Insights* (det [huvudkonto för tjänsten du skapade](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="10ab1-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="10ab1-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="10ab1-141">Select **Save**.</span></span>

<span data-ttu-id="10ab1-142">Det kan ta upp till 15 minuter att distribuera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="10ab1-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="10ab1-143">Ange Azure-resurs-ID eller Azure-prenumerationens information i lagringskontot som är bifogat målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="10ab1-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="10ab1-144">Bifoga ett Azure Data Lake-lagringskonto i målgruppsinsikter för att [lagra utdata](manage-environments.md) eller [använda det som en datakälla](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="10ab1-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="10ab1-145">Om du väljer alternativet Azure Data Lake kan du välja mellan en resurs- eller en prenumerationsbaserad metod.</span><span class="sxs-lookup"><span data-stu-id="10ab1-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="10ab1-146">Följ stegen nedan för att ange den information som krävs för den valda metoden.</span><span class="sxs-lookup"><span data-stu-id="10ab1-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="10ab1-147">Resursbaserad anslutning till lagringskonto</span><span class="sxs-lookup"><span data-stu-id="10ab1-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="10ab1-148">Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="10ab1-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="10ab1-149">Gå till **Inställningar** > **Egenskaper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="10ab1-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="10ab1-150">Kopiera resurs-ID för lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="10ab1-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiera resurs-ID för lagringskonto.":::

1. <span data-ttu-id="10ab1-152">I målgruppsinsikter infogar du resurs-ID i resursfältet som visas i fönstret för anslutning till lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="10ab1-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Ange resurs-ID för lagringskonto.":::   
   
1. <span data-ttu-id="10ab1-154">Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="10ab1-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="10ab1-155">Prenumerationsbaserad anslutning till lagringskonto</span><span class="sxs-lookup"><span data-stu-id="10ab1-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="10ab1-156">Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="10ab1-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="10ab1-157">Gå till **Inställningar** > **Egenskaper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="10ab1-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="10ab1-158">Granska **Prenumeration**, **Resursgrupp** och **Namn** på lagringskontot för att se till att du väljer rätt värden i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="10ab1-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="10ab1-159">I målgruppsinsikter väljer du värdena eller för motsvarande fält när du ansluter lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="10ab1-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Ange resurs-ID för lagringskonto.":::
   
1. <span data-ttu-id="10ab1-161">Fortsätt med de återstående stegen i målgruppsinsikter för att bifoga lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="10ab1-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
