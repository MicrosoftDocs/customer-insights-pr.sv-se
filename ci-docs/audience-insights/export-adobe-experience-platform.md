---
title: Exportera Customer Insights-data till Adobe Experience Platform
description: Lär dig använda målgruppsinsikter i Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596291"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="72258-103">Använd Customer Insights-segment i Adobe Experience Platform (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="72258-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="72258-104">Som användare av målgruppsinsikter för Dynamics 365 Customer Insights kan du ha skapat segment som gör dina marknadsföringskampanjer effektivare genom att rikta sig mot relevanta målgrupper.</span><span class="sxs-lookup"><span data-stu-id="72258-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="72258-105">Om du vill använda ett segment från målgruppsinsikter i Adobe Experience Platform och program som Adobe Campaign Standard måste du följa stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="72258-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a><span data-ttu-id="72258-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="72258-107">Prerequisites</span></span>

-   <span data-ttu-id="72258-108">Dynamics 365 Customer Insights-licens</span><span class="sxs-lookup"><span data-stu-id="72258-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="72258-109">Adobe Experience Platform-licens</span><span class="sxs-lookup"><span data-stu-id="72258-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="72258-110">Licens för Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72258-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="72258-111">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="72258-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="72258-112">Översikt över kampanj</span><span class="sxs-lookup"><span data-stu-id="72258-112">Campaign Overview</span></span>

<span data-ttu-id="72258-113">För att få en bättre förståelse av hur du kan använda segment från målgruppsinsikter i Adobe Experience Platform, ska vi titta på en fiktiv exempelkampanj.</span><span class="sxs-lookup"><span data-stu-id="72258-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="72258-114">Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA.</span><span class="sxs-lookup"><span data-stu-id="72258-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="72258-115">Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration.</span><span class="sxs-lookup"><span data-stu-id="72258-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="72258-116">Om du vill behålla kunderna måste du skicka ett kampanjerbjudande via e-post med Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="72258-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="72258-117">I det här exemplet vill vi köra kampanjen via e-post en gång.</span><span class="sxs-lookup"><span data-stu-id="72258-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="72258-118">Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="72258-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="72258-119">Identifiera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="72258-119">Identify your target audience</span></span>

<span data-ttu-id="72258-120">I vårt scenario antar vi att e-postadresserna till kunderna finns tillgängliga målgruppsinsikter och deras kampanjinställningar har analyserats för att identifiera medlemmar i segmenten.</span><span class="sxs-lookup"><span data-stu-id="72258-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="72258-121">Det [segment du definierar i målgruppsinsikter](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.</span><span class="sxs-lookup"><span data-stu-id="72258-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

<span data-ttu-id="72258-123">E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="72258-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="72258-124">Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.</span><span class="sxs-lookup"><span data-stu-id="72258-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="72258-125">Exportera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="72258-125">Export your target audience</span></span>

<span data-ttu-id="72258-126">Med målgruppen identifierad kan vi konfigurera exporten från målgruppsinsikter till ett Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="72258-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="72258-127">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="72258-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="72258-128">I panelen **Azure Blob Storage** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="72258-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationspanel för Azure Blob Storage.":::

1. <span data-ttu-id="72258-130">Tillhandahåll ett **visningsnamn** för denna nya exportdestination och ange sedan **kontonamn**, **kontonyckel** och **behållare** för Azure Blob Storage-kontot som du vill exportera segmentet till.</span><span class="sxs-lookup"><span data-stu-id="72258-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 

   - <span data-ttu-id="72258-132">Om du vill veta mer om hur du hittar Azure Blob Storage-kontots namn och kontonyckel, se [Hantera lagringsinställningar i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="72258-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="72258-133">Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="72258-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="72258-134">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="72258-134">Select **Next**.</span></span>

1. <span data-ttu-id="72258-135">Välj det segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="72258-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="72258-136">I det här exemplet är det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="72258-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. <span data-ttu-id="72258-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="72258-138">Select **Save**.</span></span>

<span data-ttu-id="72258-139">När du har sparat exportmålet hittar du det under **Admin** > **Exporter** > **Mina exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="72258-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Skärmbild av lista över exporter och exempelsegment markerade.":::

<span data-ttu-id="72258-141">Nu kan du [exportera segmentet på begäran](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="72258-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="72258-142">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).</span><span class="sxs-lookup"><span data-stu-id="72258-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="72258-143">Kontrollera att antalet poster i det exporterade segmentet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="72258-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="72258-144">Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan.</span><span class="sxs-lookup"><span data-stu-id="72258-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="72258-145">Följande mappsökväg skapas automatiskt i behållaren:</span><span class="sxs-lookup"><span data-stu-id="72258-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="72258-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="72258-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="72258-147">Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="72258-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="72258-148">*model.json* för de exporterade entiteterna finns på nivån *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="72258-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="72258-149">Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="72258-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="72258-150">Definiera Experience Data Model (XDM) i Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="72258-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="72258-151">Innan exporterade data från målgruppsinsikter kan användas inom Adobe Experience Platform måste vi definiera Experience Data Model-schemat och [konfigurera data för kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="72258-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="72258-152">Lär dig [vad XDM är](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) och lär dig grunderna i [schemasammansättning](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="72258-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="72258-153">Importera data till Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="72258-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="72258-154">Nu när allt är på plats måste vi importera förberedda målgruppsdata från målgruppsinsikter till Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="72258-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="72258-155">Börja med att [skapa en Azure Blob Storage-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="72258-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="72258-156">När du har definierat källanslutningen [konfigurerar du ett dataflöde](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) för en anslutning för en molnagringsbatch för att importera segmentutdata från målgruppsinsikter till Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="72258-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="72258-157">Skapa en målgrupp i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72258-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="72258-158">För att skicka e-postmeddelandet för den här kampanjen använder vi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="72258-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="72258-159">När vi har importerat data till Adobe Experience Platform måste vi [skapa en målgrupp](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard med hjälp av data i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="72258-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="72258-160">Lär dig hur du [använder segmentverktyget](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) i Adobe Campaign Standard för att definiera en målgrupp baserad på data i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="72258-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="72258-161">Skapa och skicka e-postmeddelandet med Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72258-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="72258-162">Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="72258-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-postmeddelande med förnyelseerbjudande från Adobe Campaign Standard.":::