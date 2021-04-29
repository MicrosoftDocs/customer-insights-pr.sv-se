---
title: Exportera Customer Insights-data till Adobe Experience Platform
description: Lär dig använda målgruppsinsikter i Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760123"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="1ef19-103">Använd Customer Insights-segment i Adobe Experience Platform (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="1ef19-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="1ef19-104">Som användare av målgruppsinsikter för Dynamics 365 Customer Insights kan du ha skapat segment som gör dina marknadsföringskampanjer effektivare genom att rikta sig mot relevanta målgrupper.</span><span class="sxs-lookup"><span data-stu-id="1ef19-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1ef19-105">Om du vill använda ett segment från målgruppsinsikter i Adobe Experience Platform och program som Adobe Campaign Standard måste du följa stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="1ef19-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a><span data-ttu-id="1ef19-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="1ef19-107">Prerequisites</span></span>

-   <span data-ttu-id="1ef19-108">Dynamics 365 Customer Insights-licens</span><span class="sxs-lookup"><span data-stu-id="1ef19-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1ef19-109">Adobe Experience Platform-licens</span><span class="sxs-lookup"><span data-stu-id="1ef19-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="1ef19-110">Licens för Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1ef19-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1ef19-111">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="1ef19-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1ef19-112">Översikt över kampanj</span><span class="sxs-lookup"><span data-stu-id="1ef19-112">Campaign Overview</span></span>

<span data-ttu-id="1ef19-113">För att få en bättre förståelse av hur du kan använda segment från målgruppsinsikter i Adobe Experience Platform, ska vi titta på en fiktiv exempelkampanj.</span><span class="sxs-lookup"><span data-stu-id="1ef19-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1ef19-114">Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA.</span><span class="sxs-lookup"><span data-stu-id="1ef19-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1ef19-115">Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration.</span><span class="sxs-lookup"><span data-stu-id="1ef19-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1ef19-116">Om du vill behålla kunderna måste du skicka ett kampanjerbjudande via e-post med Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ef19-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="1ef19-117">I det här exemplet vill vi köra kampanjen via e-post en gång.</span><span class="sxs-lookup"><span data-stu-id="1ef19-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1ef19-118">Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="1ef19-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1ef19-119">Identifiera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="1ef19-119">Identify your target audience</span></span>

<span data-ttu-id="1ef19-120">I vårt scenario antar vi att e-postadresserna till kunderna finns tillgängliga målgruppsinsikter och deras kampanjinställningar har analyserats för att identifiera medlemmar i segmenten.</span><span class="sxs-lookup"><span data-stu-id="1ef19-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1ef19-121">Det [segment du definierar i målgruppsinsikter](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.</span><span class="sxs-lookup"><span data-stu-id="1ef19-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

<span data-ttu-id="1ef19-123">E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="1ef19-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1ef19-124">Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.</span><span class="sxs-lookup"><span data-stu-id="1ef19-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1ef19-125">Exportera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="1ef19-125">Export your target audience</span></span>

<span data-ttu-id="1ef19-126">Med målgruppen identifierad kan vi konfigurera exporten från målgruppsinsikter till ett Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="1ef19-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="1ef19-127">Konfigurera en anslutning</span><span class="sxs-lookup"><span data-stu-id="1ef19-127">Configure a connection</span></span>

1. <span data-ttu-id="1ef19-128">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="1ef19-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1ef19-129">Välj **Lägg till anslutning** och välj **Azure Blob Storage** eller välj **Konfigurera** i panelen **Azure Blob Storage**:</span><span class="sxs-lookup"><span data-stu-id="1ef19-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationspanel för Azure Blob Storage."::: <span data-ttu-id="1ef19-131">för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1ef19-131">to configure the connection.</span></span>

1. <span data-ttu-id="1ef19-132">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="1ef19-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1ef19-133">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="1ef19-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1ef19-134">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1ef19-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1ef19-135">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1ef19-135">Choose who can use this connection.</span></span> <span data-ttu-id="1ef19-136">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="1ef19-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1ef19-137">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1ef19-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1ef19-138">Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto som du vill exportera segmentet till.</span><span class="sxs-lookup"><span data-stu-id="1ef19-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 
   
    - <span data-ttu-id="1ef19-140">Mer information om hur du hittar Blob Storage-kontonamn och kontonyckel finns i [Hantera inställningar för lagringskonto på Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1ef19-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="1ef19-141">Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1ef19-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1ef19-142">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1ef19-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="1ef19-143">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="1ef19-143">Configure an export</span></span>

<span data-ttu-id="1ef19-144">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="1ef19-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1ef19-145">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1ef19-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1ef19-146">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="1ef19-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1ef19-147">Välj för att skapa en ny export **Lägg till export**.</span><span class="sxs-lookup"><span data-stu-id="1ef19-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1ef19-148">I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="1ef19-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="1ef19-149">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="1ef19-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1ef19-150">Välj det segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="1ef19-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="1ef19-151">I det här exemplet är det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1ef19-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. <span data-ttu-id="1ef19-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1ef19-153">Select **Save**.</span></span>

<span data-ttu-id="1ef19-154">När du har sparat exportmålet visas det i **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="1ef19-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="1ef19-155">Nu kan du [exportera segmentet på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1ef19-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1ef19-156">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).</span><span class="sxs-lookup"><span data-stu-id="1ef19-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1ef19-157">Kontrollera att antalet poster i det exporterade segmentet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="1ef19-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1ef19-158">Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan.</span><span class="sxs-lookup"><span data-stu-id="1ef19-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="1ef19-159">Följande mappsökväg skapas automatiskt i behållaren:</span><span class="sxs-lookup"><span data-stu-id="1ef19-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1ef19-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="1ef19-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="1ef19-161">Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="1ef19-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="1ef19-162">*model.json* för de exporterade entiteterna finns på nivån *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="1ef19-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="1ef19-163">Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="1ef19-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="1ef19-164">Definiera Experience Data Model (XDM) i Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1ef19-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="1ef19-165">Innan exporterade data från målgruppsinsikter kan användas inom Adobe Experience Platform måste vi definiera Experience Data Model-schemat och [konfigurera data för kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="1ef19-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="1ef19-166">Lär dig [vad XDM är](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) och lär dig grunderna i [schemasammansättning](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="1ef19-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="1ef19-167">Importera data till Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1ef19-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="1ef19-168">Nu när allt är på plats måste vi importera förberedda målgruppsdata från målgruppsinsikter till Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ef19-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="1ef19-169">Börja med att [skapa en Azure Blob Storage-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="1ef19-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="1ef19-170">När du har definierat källanslutningen [konfigurerar du ett dataflöde](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) för en anslutning för en molnagringsbatch för att importera segmentutdata från målgruppsinsikter till Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ef19-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1ef19-171">Skapa en målgrupp i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1ef19-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1ef19-172">För att skicka e-postmeddelandet för den här kampanjen använder vi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1ef19-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="1ef19-173">När vi har importerat data till Adobe Experience Platform måste vi [skapa en målgrupp](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard med hjälp av data i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ef19-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="1ef19-174">Lär dig hur du [använder segmentverktyget](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) i Adobe Campaign Standard för att definiera en målgrupp baserad på data i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ef19-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1ef19-175">Skapa och skicka e-postmeddelandet med Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1ef19-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1ef19-176">Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="1ef19-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-postmeddelande med förnyelseerbjudande från Adobe Campaign Standard.":::
