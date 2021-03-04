---
title: Exportera Customer Insights-data till Azure Data Lake Storage Gen2
description: Lär dig hur du konfigurerar anslutningen till Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477201"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="0923e-103">Anslutningsprogram för Azure Data Lake Storage Gen2 (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0923e-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="0923e-104">Lagra dina Customer Insights-data i Azure Data Lake Storage Gen2 eller använd det för att överföra dina data till andra program.</span><span class="sxs-lookup"><span data-stu-id="0923e-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="0923e-105">Konfigurera anslutningsprogrammet för Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="0923e-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="0923e-106">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="0923e-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0923e-107">Under **Azure Data Lake Storage Gen2** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="0923e-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="0923e-108">Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="0923e-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0923e-109">Ange **Kontonamn**, **Kontonyckel** och **Behållare** för Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="0923e-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="0923e-110">Mer information om hur du skapar ett lagringskonto att använda med Azure Data Lake Storage Gen2 finns i [Skapa lagringskonto](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="0923e-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="0923e-111">Mer information om hur du hittar namnet och kontonyckeln till Azure Data Lake Gen2-lagringskontot finns i [Hantera inställningar för lagringskonto i Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="0923e-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="0923e-112">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0923e-112">Select **Next**.</span></span>

1. <span data-ttu-id="0923e-113">Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.</span><span class="sxs-lookup"><span data-stu-id="0923e-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="0923e-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0923e-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0923e-115">Exportera data</span><span class="sxs-lookup"><span data-stu-id="0923e-115">Export the data</span></span>

<span data-ttu-id="0923e-116">Du kan [Exportera data på begäran](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0923e-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="0923e-117">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0923e-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
