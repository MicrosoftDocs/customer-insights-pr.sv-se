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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Använd Customer Insights-segment i Adobe Experience Platform (förhandsversion)

Som användare av målgruppsinsikter för Dynamics 365 Customer Insights kan du ha skapat segment som gör dina marknadsföringskampanjer effektivare genom att rikta sig mot relevanta målgrupper. Om du vill använda ett segment från målgruppsinsikter i Adobe Experience Platform och program som Adobe Campaign Standard måste du följa stegen i den här artikeln.

:::image type="content" source="media/AEP-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a>Förutsättningar

-   Dynamics 365 Customer Insights-licens
-   Adobe Experience Platform-licens
-   Licens för Adobe Campaign Standard
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Översikt över kampanj

För att få en bättre förståelse av hur du kan använda segment från målgruppsinsikter i Adobe Experience Platform, ska vi titta på en fiktiv exempelkampanj.

Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA. Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration. Om du vill behålla kunderna måste du skicka ett kampanjerbjudande via e-post med Adobe Experience Platform.

I det här exemplet vill vi köra kampanjen via e-post en gång. Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång.

## <a name="identify-your-target-audience"></a>Identifiera din målgrupp

I vårt scenario antar vi att e-postadresserna till kunderna finns tillgängliga målgruppsinsikter och deras kampanjinställningar har analyserats för att identifiera medlemmar i segmenten.

Det [segment du definierar i målgruppsinsikter](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen. Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.

## <a name="export-your-target-audience"></a>Exportera din målgrupp

Med målgruppen identifierad kan vi konfigurera exporten från målgruppsinsikter till ett Azure Blob Storage-konto.

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. I panelen **Azure Blob Storage** väljer du **Konfigurera**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationspanel för Azure Blob Storage.":::

1. Tillhandahåll ett **visningsnamn** för denna nya exportdestination och ange sedan **kontonamn**, **kontonyckel** och **behållare** för Azure Blob Storage-kontot som du vill exportera segmentet till.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 

   - Om du vill veta mer om hur du hittar Azure Blob Storage-kontots namn och kontonyckel, se [Hantera lagringsinställningar i Azure-portalen](/azure/storage/common/storage-account-manage).

   - Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Välj **Nästa**.

1. Välj det segment som du vill exportera. I det här exemplet är det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. Välj **Spara**.

När du har sparat exportmålet hittar du det under **Admin** > **Exporter** > **Mina exportdestinationer**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Skärmbild av lista över exporter och exempelsegment markerade.":::

Nu kan du [exportera segmentet på begäran](export-destinations.md#export-data-on-demand). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).

> [!NOTE]
> Kontrollera att antalet poster i det exporterade segmentet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.

Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan. Följande mappsökväg skapas automatiskt i behållaren:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* för de exporterade entiteterna finns på nivån *%ExportDestinationName%*.

Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiera Experience Data Model (XDM) i Adobe Experience Platform

Innan exporterade data från målgruppsinsikter kan användas inom Adobe Experience Platform måste vi definiera Experience Data Model-schemat och [konfigurera data för kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lär dig [vad XDM är](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) och lär dig grunderna i [schemasammansättning](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importera data till Adobe Experience Platform

Nu när allt är på plats måste vi importera förberedda målgruppsdata från målgruppsinsikter till Adobe Experience Platform.

Börja med att [skapa en Azure Blob Storage-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

När du har definierat källanslutningen [konfigurerar du ett dataflöde](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) för en anslutning för en molnagringsbatch för att importera segmentutdata från målgruppsinsikter till Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Skapa en målgrupp i Adobe Campaign Standard

För att skicka e-postmeddelandet för den här kampanjen använder vi Adobe Campaign Standard. När vi har importerat data till Adobe Experience Platform måste vi [skapa en målgrupp](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard med hjälp av data i Adobe Experience Platform.

Lär dig hur du [använder segmentverktyget](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) i Adobe Campaign Standard för att definiera en målgrupp baserad på data i Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Skapa och skicka e-postmeddelandet med Adobe Campaign Standard

Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-postmeddelande med förnyelseerbjudande från Adobe Campaign Standard.":::