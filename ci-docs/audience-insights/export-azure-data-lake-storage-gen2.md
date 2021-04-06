---
title: Exportera Customer Insights-data till Azure Data Lake Storage Gen2
description: Lär dig hur du konfigurerar anslutningen till Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596663"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="568ec-103">Anslutningsprogram för Azure Data Lake Storage Gen2 (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="568ec-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="568ec-104">Lagra dina Customer Insights-data i Azure Data Lake Storage Gen2 eller använd det för att överföra dina data till andra program.</span><span class="sxs-lookup"><span data-stu-id="568ec-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="568ec-105">Konfigurera anslutningsprogrammet för Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="568ec-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="568ec-106">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="568ec-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="568ec-107">Under **Azure Data Lake Storage Gen2** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="568ec-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="568ec-108">Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="568ec-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="568ec-109">Ange **Kontonamn**, **Kontonyckel** och **Behållare** för Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="568ec-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="568ec-110">Mer information om hur du skapar ett lagringskonto att använda med Azure Data Lake Storage Gen2 finns i [Skapa lagringskonto](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="568ec-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="568ec-111">Mer information om hur du hittar namnet och kontonyckeln till Azure Data Lake Gen2-lagringskontot finns i [Hantera inställningar för lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="568ec-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="568ec-112">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="568ec-112">Select **Next**.</span></span>

1. <span data-ttu-id="568ec-113">Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.</span><span class="sxs-lookup"><span data-stu-id="568ec-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="568ec-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="568ec-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="568ec-115">Exportera data</span><span class="sxs-lookup"><span data-stu-id="568ec-115">Export the data</span></span>

<span data-ttu-id="568ec-116">Du kan [Exportera data på begäran](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="568ec-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="568ec-117">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="568ec-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>