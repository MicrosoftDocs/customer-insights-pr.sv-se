---
title: Exportera Customer Insights-data till Azure Synapse Analytics
description: Lär dig hur du konfigurerar anslutningen och exporterar till Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977399"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="0ec1f-103">Exportera data till Azure Synapse Analytics (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0ec1f-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="0ec1f-104">Azure Synapse är en analystjänst som snabbare kan få överblick över datalager och stora datasystem.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="0ec1f-105">Du kan skapa och använda dina Customer Insights-data i [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0ec1f-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="0ec1f-106">Prerequisites</span></span>

<span data-ttu-id="0ec1f-107">Följande krav måste uppfyllas för att konfigurera anslutningen från Customer Insights till Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec1f-108">Se till att ange alla **rolltilldelningar** enligt beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="0ec1f-109">Förkrav i Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0ec1f-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="0ec1f-110">Du har rollen **Administratör** i målgruppinsikter.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="0ec1f-111">Läs mer om hur du anger [användarbehörigheter i målinsikter](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="0ec1f-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="0ec1f-112">i Azure:</span><span class="sxs-lookup"><span data-stu-id="0ec1f-112">In Azure:</span></span> 

- <span data-ttu-id="0ec1f-113">En aktiv Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-113">An active Azure subscription.</span></span>

- <span data-ttu-id="0ec1f-114">Om du använder ett nytt Azure Data Lake Storage Gen2-konto behöver *huvudkonto för tjänsten för målgruppinsikter* behöver behörigheter **Storage Blob-datadeltagare**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="0ec1f-115">Läs mer om att [ansluta till ett Azure Data Lake Storage Gen2-konto med Azure-huvudkonto för tjänsten för målinsikter](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="0ec1f-116">Data Lake Storage Gen2 **måste ha** [hierarkiskt namnutrymme](/azure/storage/blobs/data-lake-storage-namespace) aktiverat.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="0ec1f-117">I resursgruppen som Azure Synapse arbetsytan finns, måste *huvudkonto för tjänsten* och *användare för målinsikter* måste tilldelas minst behörigheten **Läsare**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="0ec1f-118">Mer information finns i [Tilldela Azure-roller med Azure-portalen](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="0ec1f-119">*Användaren* behöver **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns kopplade till Azure Synapse arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="0ec1f-120">Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="0ec1f-121">*[Azure Synapse arbetsytan hanterad identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* behöver behörigheten **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns och kopplas till Azure Synapse arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="0ec1f-122">Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="0ec1f-123">På Azure Synapse arbetsytan behöver *huvudkonto för tjänsten för målinsikter* rollen **Administratör för Synapse** tilldelas.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="0ec1f-124">Mer information finns i [Konfigurera åtkomstkontroll för din Synapse-arbetsyta](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="0ec1f-125">Upprätta anslutningen och exportera till Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="0ec1f-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="0ec1f-126">Konfigurera en anslutning</span><span class="sxs-lookup"><span data-stu-id="0ec1f-126">Configure a connection</span></span>

1. <span data-ttu-id="0ec1f-127">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0ec1f-128">Välj **Lägg till anslutning** och välj **Azure Synapse Analytics** eller välj **Konfigurera** på panelen **Azure Synapse Analytics** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="0ec1f-129">Ge anslutningen ett beskrivande namn i fältet visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="0ec1f-130">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="0ec1f-131">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0ec1f-132">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-132">Choose who can use this connection.</span></span> <span data-ttu-id="0ec1f-133">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0ec1f-134">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0ec1f-135">Välj eller sök efter prenumerationen som du vill använda Customer Insights data i.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="0ec1f-136">Så fort en prenumeration har valts kan du också välja **Arbetsyta**, **Lagringskonto** och **Behållare**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="0ec1f-137">Välj **Spara** för att spara anslutningen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="0ec1f-138">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="0ec1f-138">Configure an export</span></span>

<span data-ttu-id="0ec1f-139">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0ec1f-140">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0ec1f-141">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0ec1f-142">Välj för att skapa en ny export **Lägg till export**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="0ec1f-143">I fältet **Anslutning för export** välj en anslutning från avsnittet **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="0ec1f-144">Om avsnittets namn inte visas finns det inga tillgängliga [anslutningar](connections.md) av den här typen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="0ec1f-145">Ange ett igenkännande **Visningsnamn** för exporten och ett **Databasnamn** .</span><span class="sxs-lookup"><span data-stu-id="0ec1f-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="0ec1f-146">Välj vilka entiteter du vill exportera till Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="0ec1f-147">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-147">Select **Save**.</span></span>

<span data-ttu-id="0ec1f-148">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0ec1f-149">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0ec1f-150">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0ec1f-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="0ec1f-151">Uppdatera en export</span><span class="sxs-lookup"><span data-stu-id="0ec1f-151">Update an export</span></span>

1. <span data-ttu-id="0ec1f-152">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0ec1f-153">Välj **Redigera** för exporten du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="0ec1f-154">**Lägga till** eller **Ta bort** entiteter från urvalet.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="0ec1f-155">Om entiteter tas bort från urvalet tas de inte bort från Synapse Analytics-databasen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="0ec1f-156">Framtida datauppdateringar uppdaterar emellertid inte de borttagna entiteterna i databasen.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="0ec1f-157">**Om du ändrar databasnamnet** skapas en ny Synapse Analytics-databas.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="0ec1f-158">Databasen med namnet som konfigurerats tidigare får inga uppdateringar i framtida uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="0ec1f-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
