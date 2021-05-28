---
title: Exportera Customer Insights-data till Azure Blob Storage
description: Lär dig hur du konfigurerar anslutningen och exporterar till Blob Storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976203"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="33e65-103">Exportera segmentlista och andra data till Azure Blob Storage (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="33e65-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="33e65-104">Lagra Customer Insights-data i Blob Storage eller använd det för att överföra data till andra appar.</span><span class="sxs-lookup"><span data-stu-id="33e65-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="33e65-105">Upprätta anslutningen till Blob Storage</span><span class="sxs-lookup"><span data-stu-id="33e65-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="33e65-106">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="33e65-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="33e65-107">Välj **Lägg till anslutning** och välj **Azure Blob Storage** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="33e65-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="33e65-108">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="33e65-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="33e65-109">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="33e65-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="33e65-110">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="33e65-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="33e65-111">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="33e65-111">Choose who can use this connection.</span></span> <span data-ttu-id="33e65-112">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="33e65-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="33e65-113">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="33e65-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="33e65-114">Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="33e65-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="33e65-115">Mer information om hur du hittar Blob Storage-kontonamn och kontonyckel finns i [Hantera inställningar för lagringskonto på Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="33e65-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="33e65-116">Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="33e65-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="33e65-117">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="33e65-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="33e65-118">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="33e65-118">Configure an export</span></span>

<span data-ttu-id="33e65-119">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="33e65-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="33e65-120">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="33e65-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="33e65-121">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="33e65-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="33e65-122">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="33e65-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="33e65-123">I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="33e65-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="33e65-124">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="33e65-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="33e65-125">Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.</span><span class="sxs-lookup"><span data-stu-id="33e65-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="33e65-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="33e65-126">Select **Save**.</span></span>

<span data-ttu-id="33e65-127">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="33e65-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="33e65-128">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="33e65-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="33e65-129">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="33e65-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="33e65-130">Exporterade data lagras i den Blob Storage-behållare som du konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="33e65-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="33e65-131">Följande mappsökvägar skapas automatiskt i behållaren:</span><span class="sxs-lookup"><span data-stu-id="33e65-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="33e65-132">För källentiteter och entiteter som genererats av systemet: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="33e65-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="33e65-133">Exempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="33e65-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="33e65-134">Model.json för de exporterade entiteterna finns på %ExportDestinationName% nivån</span><span class="sxs-lookup"><span data-stu-id="33e65-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="33e65-135">Exempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="33e65-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
