---
title: Exportera Customer Insights-data till Adobe Experience Platform
description: Lär dig hur du använder segment för målgruppsinsikter i Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305546"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="c7a4b-103">Använd Customer Insights-segment i Adobe Experience Platform (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="c7a4b-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="c7a4b-104">Som användare av målgruppsikter i Dynamics 365 Customer Insights kan du ha skapat segment i avsikt att göra dina marknadsföringskampanjer mer effektiva genom att rikta dig till relevanta målgrupper.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c7a4b-105">Om du vill använda ett segment från målgruppsinsikter i Adobe Experience Platform och program som Adobe Campaign Standard måste du följa stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a><span data-ttu-id="c7a4b-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c7a4b-107">Prerequisites</span></span>

-   <span data-ttu-id="c7a4b-108">Dynamics 365 Customer Insights-licens</span><span class="sxs-lookup"><span data-stu-id="c7a4b-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c7a4b-109">Adobe Experience Platform-licens</span><span class="sxs-lookup"><span data-stu-id="c7a4b-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="c7a4b-110">Licens för Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c7a4b-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c7a4b-111">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="c7a4b-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c7a4b-112">Översikt över kampanj</span><span class="sxs-lookup"><span data-stu-id="c7a4b-112">Campaign Overview</span></span>

<span data-ttu-id="c7a4b-113">För att få en bättre förståelse av hur du kan använda segment från målgruppsinsikter i Adobe Experience Platform, ska vi titta på en fiktiv exempelkampanj.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c7a4b-114">Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c7a4b-115">Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c7a4b-116">Om du vill behålla kunderna måste du skicka ett kampanjerbjudande via e-post med Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="c7a4b-117">I det här exemplet vill vi köra kampanjen via e-post en gång.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c7a4b-118">Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c7a4b-119">Identifiera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="c7a4b-119">Identify your target audience</span></span>

<span data-ttu-id="c7a4b-120">I vårt scenario antar vi att e-postadresserna till kunderna finns tillgängliga målgruppsinsikter och deras kampanjinställningar har analyserats för att identifiera medlemmar i segmenten.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c7a4b-121">Det [segment du definierar i målgruppsinsikter](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

<span data-ttu-id="c7a4b-123">E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c7a4b-124">Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c7a4b-125">Exportera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="c7a4b-125">Export your target audience</span></span>

<span data-ttu-id="c7a4b-126">Med målgruppen identifierad kan vi konfigurera exporten från målgruppsinsikter till ett Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="c7a4b-127">Konfigurera en anslutning</span><span class="sxs-lookup"><span data-stu-id="c7a4b-127">Configure a connection</span></span>

1. <span data-ttu-id="c7a4b-128">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c7a4b-129">Välj **Lägg till anslutning** och välj sedan **Azure Blob Storage** eller **Konfigurera** i panelen **Azure Blob Storage** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationspanel för Azure Blob Storage."::: 

1. <span data-ttu-id="c7a4b-131">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c7a4b-132">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c7a4b-133">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c7a4b-134">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-134">Choose who can use this connection.</span></span> <span data-ttu-id="c7a4b-135">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c7a4b-136">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c7a4b-137">Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto som du vill exportera segmentet till.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 
   
    - <span data-ttu-id="c7a4b-139">Mer information om hur du hittar kontonamn och kontonyckel för Blob Storage finns i [Hantera inställningar för lagringskonto på Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="c7a4b-140">Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c7a4b-141">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="c7a4b-142">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="c7a4b-142">Configure an export</span></span>

<span data-ttu-id="c7a4b-143">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c7a4b-144">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c7a4b-145">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c7a4b-146">Välj för att skapa en ny export **Lägg till export**.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c7a4b-147">I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="c7a4b-148">Om avsnittets namn inte visas är inga anslutningar av den här typen tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="c7a4b-149">Välj det segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="c7a4b-150">I det här exemplet är det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. <span data-ttu-id="c7a4b-152">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-152">Select **Save**.</span></span>

<span data-ttu-id="c7a4b-153">När du har sparat exportmålet visas det i **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="c7a4b-154">Nu kan du [exportera segmentet på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="c7a4b-155">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7a4b-156">Kontrollera att antalet poster i det exporterade segmentet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c7a4b-157">Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="c7a4b-158">Följande mappsökväg skapas automatiskt i behållaren:</span><span class="sxs-lookup"><span data-stu-id="c7a4b-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c7a4b-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="c7a4b-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="c7a4b-160">Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="c7a4b-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="c7a4b-161">*model.json* för de exporterade entiteterna finns på nivån *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="c7a4b-162">Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="c7a4b-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="c7a4b-163">Definiera Experience Data Model (XDM) i Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c7a4b-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="c7a4b-164">Innan exporterade data från målgruppsinsikter kan användas inom Adobe Experience Platform måste vi definiera Experience Data Model-schemat och [konfigurera data för kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="c7a4b-165">Lär dig [vad XDM är](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) och lär dig grunderna i [schemasammansättning](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="c7a4b-166">Importera data till Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c7a4b-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="c7a4b-167">Nu när allt är på plats måste vi importera förberedda målgruppsdata från målgruppsinsikter till Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="c7a4b-168">Börja med att [skapa en Azure Blob Storage-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="c7a4b-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="c7a4b-169">När du har definierat källanslutningen [konfigurerar du ett dataflöde](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) för en anslutning för en molnagringsbatch för att importera segmentutdata från målgruppsinsikter till Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c7a4b-170">Skapa en målgrupp i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c7a4b-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c7a4b-171">För att skicka e-postmeddelandet för den här kampanjen använder vi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="c7a4b-172">När vi har importerat data till Adobe Experience Platform måste vi [skapa en målgrupp](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard med hjälp av data i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="c7a4b-173">Lär dig hur du [använder segmentverktyget](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) i Adobe Campaign Standard för att definiera en målgrupp baserad på data i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c7a4b-174">Skapa och skicka e-postmeddelandet med Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c7a4b-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c7a4b-175">Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="c7a4b-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-postmeddelande med förnyelseerbjudande från Adobe Campaign Standard.":::
