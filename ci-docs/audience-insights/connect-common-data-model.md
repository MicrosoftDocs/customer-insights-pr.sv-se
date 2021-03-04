---
title: Anslut Common Data Model till ett Azure Data Lake-konto
description: Arbeta med Common Data Model-data med hjälp av Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267882"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="1187a-103">Anslut till en Common Data Model-mapp som använder Azure Data Lake-konto</span><span class="sxs-lookup"><span data-stu-id="1187a-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="1187a-104">Den här artikeln innehåller information om hur du matar in data från en Common Data Model-mapp med hjälp av ditt Azure Data Lake Storage Gen2-konto.</span><span class="sxs-lookup"><span data-stu-id="1187a-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="1187a-105">Viktigt!</span><span class="sxs-lookup"><span data-stu-id="1187a-105">Important considerations</span></span>

- <span data-ttu-id="1187a-106">Data i Azure Data Lake måste följa standarden Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="1187a-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="1187a-107">Andra format stöds inte för tillfället.</span><span class="sxs-lookup"><span data-stu-id="1187a-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="1187a-108">Datainmatning stöder Azure Data Lake *Gen2*-lagringskonton exklusivt.</span><span class="sxs-lookup"><span data-stu-id="1187a-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="1187a-109">Du kan inte använda Azure Data Lake Gen1-lagringskonton för att mata in data.</span><span class="sxs-lookup"><span data-stu-id="1187a-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="1187a-110">Om du vill autentisera med Azure-tjänstens huvudkonto, se till att det är konfigurerat i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="1187a-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="1187a-111">Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1187a-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="1187a-112">Den Azure Data Lake du vill ansluta och mata in data från måste vara i samma Azure-region som Dynamics 365 Customer Insights-miljön.</span><span class="sxs-lookup"><span data-stu-id="1187a-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="1187a-113">Anslutningar till en Common Data Model-mapp från en datasjö i en annan Azure-region stöds inte.</span><span class="sxs-lookup"><span data-stu-id="1187a-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="1187a-114">Om du vill veta Azure-regionen i miljön, gå till **Admin** > **System** > **Om** i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="1187a-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="1187a-115">Data som lagras i onlinetjänster kan lagras på en annan plats än där data behandlas eller lagras i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1187a-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="1187a-116">Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="1187a-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="1187a-117">Anslut till en Common Data Model-mapp</span><span class="sxs-lookup"><span data-stu-id="1187a-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="1187a-118">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="1187a-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="1187a-119">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="1187a-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="1187a-120">Välj **Anslut till en Common Data Model-mapp**, ange ett **Namn** på datakällan och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="1187a-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="1187a-121">Namnge riktlinjer:</span><span class="sxs-lookup"><span data-stu-id="1187a-121">Name guidelines:</span></span> 
   - <span data-ttu-id="1187a-122">Inled med en bokstav.</span><span class="sxs-lookup"><span data-stu-id="1187a-122">Start with a letter.</span></span>
   - <span data-ttu-id="1187a-123">Använd endast bokstäver och siffror.</span><span class="sxs-lookup"><span data-stu-id="1187a-123">Use letters and numbers only.</span></span> <span data-ttu-id="1187a-124">Specialtecken och blanksteg är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="1187a-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="1187a-125">Använd mellan 3 och 64 tecken.</span><span class="sxs-lookup"><span data-stu-id="1187a-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="1187a-126">Du kan välja mellan att använda ett resursbaserat alternativ och ett prenumerationsbaserat alternativ för autentisering.</span><span class="sxs-lookup"><span data-stu-id="1187a-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="1187a-127">Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1187a-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1187a-128">Ange informationen **Behållare** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="1187a-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1187a-129">![Dialogruta för att ange nya anslutningsdetaljer för Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="1187a-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="1187a-130">Du behöver en av följande roller antingen till den behållare eller det lagringskonto som nämns ovan för att kunna ansluta till och skapa en datakälla:</span><span class="sxs-lookup"><span data-stu-id="1187a-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="1187a-131">Storage Blob-dataläsare</span><span class="sxs-lookup"><span data-stu-id="1187a-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="1187a-132">Storage Blob-dataägare</span><span class="sxs-lookup"><span data-stu-id="1187a-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="1187a-133">Storage Blob-datadeltagare</span><span class="sxs-lookup"><span data-stu-id="1187a-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="1187a-134">I dialogrutan **Välj en Common Data Model-mapp** väljer du den model.json-fil eller manifest.json som data ska importeras från och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="1187a-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1187a-135">Inga model.json- eller manifest.json-filer som är associerade med en annan datakälla i miljön visas.</span><span class="sxs-lookup"><span data-stu-id="1187a-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="1187a-136">Du får en lista över tillgängliga entiteter i den valda model.json- eller manifest.json-filen.</span><span class="sxs-lookup"><span data-stu-id="1187a-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="1187a-137">Du kan granska och välja i listan bland tillgängliga entiteter och välja **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1187a-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="1187a-138">Alla de valda entiteterna matas in från den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="1187a-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1187a-139">![Dialogruta med en lista över entiteter från en modell.json-fil](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="1187a-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="1187a-140">Ange vilka dataentiteter du vill aktivera dataprofilering för och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1187a-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="1187a-141">Med dataprofilering kan du använda analyser och andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="1187a-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="1187a-142">Du kan välja hela entiteten, som väljer alla attribut från entiteten, eller välja vissa valfria attribut.</span><span class="sxs-lookup"><span data-stu-id="1187a-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="1187a-143">Som standard är ingen entitet aktiverad för dataprofilering.</span><span class="sxs-lookup"><span data-stu-id="1187a-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1187a-144">![Dialogruta som visar en dataprofilering](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="1187a-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="1187a-145">När du har sparat dina val öppnas sidan **datakällor**.</span><span class="sxs-lookup"><span data-stu-id="1187a-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="1187a-146">Nu bör du se anslutningen för Common Data Model-mappen som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="1187a-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="1187a-147">En model.json- eller manifest.json-fil kan bara associera med en datakälla i samma miljö.</span><span class="sxs-lookup"><span data-stu-id="1187a-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="1187a-148">Samma model.json- eller manifest.json-fil kan dock användas för datakällor i flera miljöer.</span><span class="sxs-lookup"><span data-stu-id="1187a-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="1187a-149">Redigera en datakälla för en Common Data Model-mapp</span><span class="sxs-lookup"><span data-stu-id="1187a-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="1187a-150">Du kan uppdatera åtkomstnyckeln för det lagringskonto som innehåller Common Data Model-mappen.</span><span class="sxs-lookup"><span data-stu-id="1187a-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="1187a-151">Du kan också ändra filen model.json eller manifest.json.</span><span class="sxs-lookup"><span data-stu-id="1187a-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="1187a-152">Om du vill ansluta till en annan behållare från lagringskontot eller ändra kontonamnet måste du [skapa en ny datakällaanslutning](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="1187a-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="1187a-153">I målgruppsinsikter går du till **Data** > **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="1187a-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1187a-154">Markera tre punkter bredvid datakälla som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="1187a-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="1187a-155">Välj alternativet **Redigera** från listan.</span><span class="sxs-lookup"><span data-stu-id="1187a-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="1187a-156">Om du vill kan du uppdatera **åtkomst nyckeln** och välja **nästa**.</span><span class="sxs-lookup"><span data-stu-id="1187a-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialogruta för att redigera och uppdatera en snabb tangent för en befintlig datakälla](media/edit-access-key.png)

5. <span data-ttu-id="1187a-158">Eventuellt kan du uppdatera från en kontonyckelanslutning till en resursbaserad eller en prenumerationsbaserad anslutning.</span><span class="sxs-lookup"><span data-stu-id="1187a-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="1187a-159">Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1187a-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1187a-160">Du kan inte ändra informationen **Behållare** när anslutningen uppdateras.</span><span class="sxs-lookup"><span data-stu-id="1187a-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialogruta för att ange anslutningsinformation för Azure Data Lake till ett befintligt lagringskonto](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="1187a-162">Du behöver en av följande roller antingen till den behållare eller det lagringskonto som nämns ovan för att kunna ansluta till och skapa en datakälla:</span><span class="sxs-lookup"><span data-stu-id="1187a-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="1187a-163">Storage Blob-dataläsare</span><span class="sxs-lookup"><span data-stu-id="1187a-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="1187a-164">Storage Blob-dataägare</span><span class="sxs-lookup"><span data-stu-id="1187a-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="1187a-165">Storage Blob-datadeltagare</span><span class="sxs-lookup"><span data-stu-id="1187a-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="1187a-166">Alternativt kan du välja en annan model.json- eller manifest.json-fil med en annan uppsättning entiteter från behållaren.</span><span class="sxs-lookup"><span data-stu-id="1187a-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="1187a-167">Eventuellt kan du välja ytterligare entiteter att mata in.</span><span class="sxs-lookup"><span data-stu-id="1187a-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="1187a-168">Du kan också ta bort alla entiteter som redan är markerade om det inte finns några beroenden.</span><span class="sxs-lookup"><span data-stu-id="1187a-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1187a-169">Om det finns beroenden på den befintliga filen model.json eller manifest.json och entitetsuppsättningen visas ett felmeddelande och det går inte att välja en annan model.json- eller manifest.json-fil.</span><span class="sxs-lookup"><span data-stu-id="1187a-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="1187a-170">Ta bort dessa beroenden innan du ändrar filen model.json eller manifest.json, eller skapa en ny datakälla med den model.json- eller manifest.json-fil som du vill använda för att undvika att ta bort beroendena.</span><span class="sxs-lookup"><span data-stu-id="1187a-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="1187a-171">Eventuellt kan du välja ytterligare attribut eller entiteter för att aktivera dataprofilering på eller inaktivera redan valda.</span><span class="sxs-lookup"><span data-stu-id="1187a-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]