---
title: Exportera Customer Insights-data till Adobe Campaign Standard
description: Lär dig använda målgruppsinsikter i Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760303"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="446d5-103">Använd Customer Insights-segment i Adobe Campaign Standard (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="446d5-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="446d5-104">Som användare av målgruppsinsikter för Dynamics 365 Customer Insights kan du ha skapat segment som gör dina marknadsföringskampanjer effektivare genom att rikta sig mot relevanta målgrupper.</span><span class="sxs-lookup"><span data-stu-id="446d5-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="446d5-105">Om du vill använda ett segment från målgruppsinsikter i Adobe Experience Platform och program som Adobe Campaign Standard måste du följa stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="446d5-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a><span data-ttu-id="446d5-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="446d5-107">Prerequisites</span></span>

-   <span data-ttu-id="446d5-108">Dynamics 365 Customer Insights-licens</span><span class="sxs-lookup"><span data-stu-id="446d5-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="446d5-109">Licens för Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="446d5-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="446d5-110">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="446d5-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="446d5-111">Översikt över kampanj</span><span class="sxs-lookup"><span data-stu-id="446d5-111">Campaign Overview</span></span>

<span data-ttu-id="446d5-112">För att få en bättre förståelse av hur du kan använda segment från målgruppsinsikter i Adobe Experience Platform, ska vi titta på en fiktiv exempelkampanj.</span><span class="sxs-lookup"><span data-stu-id="446d5-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="446d5-113">Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA.</span><span class="sxs-lookup"><span data-stu-id="446d5-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="446d5-114">Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration.</span><span class="sxs-lookup"><span data-stu-id="446d5-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="446d5-115">Om du vill behålla kunderna måste du skicka ett kampanjerbjudande via e-post med Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="446d5-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="446d5-116">I det här exemplet vill vi köra kampanjen via e-post en gång.</span><span class="sxs-lookup"><span data-stu-id="446d5-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="446d5-117">Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="446d5-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="446d5-118">Målgruppsinsikter och Adobe Campaign Standard konfigureras dock så att de också fungerar för ett återkommande kampanjscenario.</span><span class="sxs-lookup"><span data-stu-id="446d5-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="446d5-119">Identifiera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="446d5-119">Identify your target audience</span></span>

<span data-ttu-id="446d5-120">I vårt scenario antar vi att e-postadresserna till kunderna finns tillgängliga målgruppsinsikter och deras kampanjinställningar har analyserats för att identifiera medlemmar i segmenten.</span><span class="sxs-lookup"><span data-stu-id="446d5-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="446d5-121">Det [segment du definierar i målgruppsinsikter](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.</span><span class="sxs-lookup"><span data-stu-id="446d5-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

<span data-ttu-id="446d5-123">E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="446d5-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="446d5-124">Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.</span><span class="sxs-lookup"><span data-stu-id="446d5-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="446d5-125">Exportera din målgrupp</span><span class="sxs-lookup"><span data-stu-id="446d5-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="446d5-126">Konfigurera en anslutning</span><span class="sxs-lookup"><span data-stu-id="446d5-126">Configure a connection</span></span>

<span data-ttu-id="446d5-127">Med målgruppen identifierad kan vi konfigurera exporten från målgruppsinsikter till ett Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="446d5-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="446d5-128">I målgruppsinsikter, gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="446d5-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="446d5-129">Välj **Lägg till anslutning** och välj **Adobe Campaign** om du vill konfigurera anslutningen eller välj **Konfigurera** i panelen **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="446d5-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationspanel för Adobe Campaign Standard.":::

1. <span data-ttu-id="446d5-131">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="446d5-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="446d5-132">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="446d5-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="446d5-133">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="446d5-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="446d5-134">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="446d5-134">Choose who can use this connection.</span></span> <span data-ttu-id="446d5-135">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="446d5-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="446d5-136">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="446d5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="446d5-137">Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Azure Blob Storage-konto som du vill exportera segmentet till.</span><span class="sxs-lookup"><span data-stu-id="446d5-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 

   - <span data-ttu-id="446d5-139">Om du vill veta mer om hur du hittar Azure Blob Storage-kontots namn och kontonyckel, se [Hantera lagringsinställningar i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="446d5-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="446d5-140">Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="446d5-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="446d5-141">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="446d5-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="446d5-142">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="446d5-142">Configure an export</span></span>

<span data-ttu-id="446d5-143">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="446d5-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="446d5-144">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="446d5-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="446d5-145">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="446d5-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="446d5-146">Välj för att skapa en ny export **Lägg till export**.</span><span class="sxs-lookup"><span data-stu-id="446d5-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="446d5-147">I fältet **Anslutning för export**, välj en anslutning från avsnittet Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="446d5-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="446d5-148">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="446d5-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="446d5-149">Välj det segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="446d5-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="446d5-150">I det här exemplet är det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="446d5-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. <span data-ttu-id="446d5-152">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="446d5-152">Select **Next**.</span></span>

1. <span data-ttu-id="446d5-153">Nu mappar vi fälten **Källa** från målgruppsinsiktssegmentet till fälten **Mål** i Adobe Campaign Standard-profilschemat.</span><span class="sxs-lookup"><span data-stu-id="446d5-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Fältmappning för Adobe Campaign Standard-anslutningsprogrammet.":::

   <span data-ttu-id="446d5-155">Om du vill lägga till fler attribut väljer du **Lägg till attribut**.</span><span class="sxs-lookup"><span data-stu-id="446d5-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="446d5-156">Målnamnet kan vara ett annat än källfältets namn så du kan mappa segmentutdata från målgruppsinsikter till Adobe Campaign Standard om fälten inte har samma namn i de två systemen.</span><span class="sxs-lookup"><span data-stu-id="446d5-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="446d5-157">E-postadress används som ett identitetsfält, men du kan använda en annan identifierare från din kundprofil för målgruppsinsikter för att mappa data till Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="446d5-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="446d5-158">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="446d5-158">Select **Save**.</span></span>

<span data-ttu-id="446d5-159">När du har sparat exportmålet visas det i **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="446d5-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="446d5-160">Nu kan du [exportera segmentet på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="446d5-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="446d5-161">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).</span><span class="sxs-lookup"><span data-stu-id="446d5-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="446d5-162">Kontrollera att antalet poster i det exporterade segmentet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="446d5-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="446d5-163">Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan.</span><span class="sxs-lookup"><span data-stu-id="446d5-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="446d5-164">Följande mappsökväg skapas automatiskt i behållaren:</span><span class="sxs-lookup"><span data-stu-id="446d5-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="446d5-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="446d5-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="446d5-166">Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="446d5-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="446d5-167">Konfigurera Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="446d5-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="446d5-168">När ett segment från målgruppsinsikter exporteras innehåller det de kolumner du valde när du definierade exportmålet i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="446d5-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="446d5-169">Dessa data kan användas för att [skapa profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="446d5-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="446d5-170">För att kunna använda segmenten i Adobe Campaign Standard måste vi utöka profilschemat i Adobe Campaign Standard så att det omfattar ytterligare två fält.</span><span class="sxs-lookup"><span data-stu-id="446d5-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="446d5-171">Lär dig hur du [utökar profilresursen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nya fält i Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="446d5-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="446d5-172">I vårt exempel är dessa fält *Segmentnamn och Segmentdatum (valfritt).*</span><span class="sxs-lookup"><span data-stu-id="446d5-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="446d5-173">Vi använder fälten för att identifiera vilka profiler i Adobe Campaign Standard som ska användas för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="446d5-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="446d5-174">Om det inte finns några andra poster i Adobe Campaign Standard, förutom de du ska importera, kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="446d5-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="446d5-175">Importera data till Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="446d5-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="446d5-176">Nu när allt är på plats måste vi importera förberedda målgruppsdata från målgruppsinsikter till Adobe Campaign Standard för att skapa profiler.</span><span class="sxs-lookup"><span data-stu-id="446d5-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="446d5-177">Lär dig [hur du importerar profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) med hjälp av ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="446d5-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="446d5-178">Importarbetsflödet i bilden nedan har konfigurerats att köras var 8:e timme och söker efter exporterade målgruppsinsiktssegment (.csv-fil i Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="446d5-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="446d5-179">Arbetsflödet extraherar .csv-filens innehåll i en angiven kolumnordning.</span><span class="sxs-lookup"><span data-stu-id="446d5-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="446d5-180">Arbetsflödet har skapats för att utföra grundläggande felhantering och se till att varje post har en e-postadress innan data skickas i Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="446d5-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="446d5-181">Arbetsflödet extraherar också segmentnamnet från filnamnet innan det konfigureras i ACS-profildata.</span><span class="sxs-lookup"><span data-stu-id="446d5-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skärmbild av ett importarbetsflöde i användargränssnittet i Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="446d5-183">Hämta målgrupp i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="446d5-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="446d5-184">När data har importerats till Adobe Campaign Standard kan du [skapa ett arbetsflöde](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) och [fråga](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kunderna baserat på *Segmentnamn* och *Segmentdatum* för att välja profiler som identifierades för exempelkampanjen.</span><span class="sxs-lookup"><span data-stu-id="446d5-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="446d5-185">Skapa och skicka e-postmeddelandet med Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="446d5-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="446d5-186">Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="446d5-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-postmeddelande med förnyelseerbjudande från Adobe Campaign Standard.":::
