---
title: Exportera Customer Insights-data till Azure Data Lake Storage Gen2
description: Lär dig hur du konfigurerar anslutningen till Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760073"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="7a746-103">Upprätta anslutningen till Azure Data Lake Storage Gen2 (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="7a746-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="7a746-104">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="7a746-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7a746-105">Välj **Lägg till anslutning** och välj **Azure Data Lake Gen 2** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="7a746-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="7a746-106">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="7a746-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7a746-107">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="7a746-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7a746-108">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="7a746-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7a746-109">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="7a746-109">Choose who can use this connection.</span></span> <span data-ttu-id="7a746-110">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="7a746-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7a746-111">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7a746-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7a746-112">Ange **Kontonamn**, **Kontonyckel** och **Behållare** för Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="7a746-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="7a746-113">Mer information om hur du skapar ett lagringskonto att använda med Azure Data Lake Storage Gen2 finns i [Skapa lagringskonto](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="7a746-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="7a746-114">Mer information om hur du hittar Azure Data Lake Gen 2-kontonamn och kontonyckel finns i [Hantera inställningar för lagringskonto på Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="7a746-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="7a746-115">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="7a746-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="7a746-116">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="7a746-116">Configure an export</span></span>

<span data-ttu-id="7a746-117">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="7a746-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7a746-118">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7a746-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7a746-119">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="7a746-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7a746-120">Välj för att skapa en ny export **Lägg till export**.</span><span class="sxs-lookup"><span data-stu-id="7a746-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="7a746-121">I fältet **Anslutning för export**, välj en anslutning från avsnittet **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="7a746-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="7a746-122">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="7a746-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7a746-123">Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.</span><span class="sxs-lookup"><span data-stu-id="7a746-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="7a746-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7a746-124">Select **Save**.</span></span>

<span data-ttu-id="7a746-125">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="7a746-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7a746-126">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7a746-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7a746-127">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7a746-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="7a746-128">Exporterade data lagras i den Azure Data Lake Gen 2-behållare som du konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="7a746-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
