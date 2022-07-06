---
title: Exportera segment till Adobe Experience Platform (förhandsversion)
description: Lär dig hur du använder segmenten Customer Insights i Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052533"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportera segment till Adobe Experience Platform (förhandsversion)

Som användare av Dynamics 365 Customer Insights kan du ha skapat segment för att göra dina marknadsföringskampanjer effektivare genom att rikta dig till relevanta målgrupper. Om du vill använda ett segment från Customer Insights i Adobe Experience Platform och program som Adobe Campaign Standard måste du följa några steg som beskrivs i den här artikeln.

:::image type="content" source="media/AEP-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a>Förutsättningar

-   Dynamics 365 Customer Insights-licens
-   Adobe Experience Platform-licens
-   Adobe Campaign Standard licens
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Översikt över kampanj

För att bättre förstå hur du kan använda segment från Customer Insights i Adobe Experience Platform, låt oss titta på en fiktiv exempelkampanj.

Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA. Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration. För att behålla dessa kunder vill du skicka ett kampanjerbjudande via e-post med Adobe Experience Platform.

I det här exemplet vill vi köra kampanjen via e-post en gång. Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång.

## <a name="identify-your-target-audience"></a>Identifiera din målgrupp

I vårt scenario förutsätter vi att kundernas e-postadresser är tillgängliga i Customer Insights och att deras reklampreferenser har analyserats för att identifiera medlemmar i segmenten.

[Segmentet du definierar i Customer Insights](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen. Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.

## <a name="export-your-target-audience"></a>Exportera din målgrupp

Med vårt mål publik kan vi konfigurera exporten från Customer Insights till ett Azure Blob Storage-konto.

### <a name="configure-a-connection"></a>Konfigurera en anslutning

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj sedan **Azure Blob Storage** eller **Konfigurera** i panelen **Azure Blob Storage** för att konfigurera anslutningen.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationspanel för Azure Blob Storage."::: 

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto som du vill exportera segmentet till.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 
   
    - Mer information om hur du hittar kontonamn och kontonyckel för Blob Storage finns i [Hantera inställningar för lagringskonto på Azure-portalen](/azure/storage/common/storage-account-manage).
    - Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Välj **Spara** för att slutföra anslutningen. 

### <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Blob Storage. Om avsnittets namn inte visas är inga anslutningar av den här typen tillgängliga för dig.

1. Välj det segment som du vill exportera. I det här exemplet är det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. Välj **Spara**.

När du har sparat exportmålet visas det i **Data** > **Exporter**.

Nu kan du [exportera segmentet på begäran](export-destinations.md#run-exports-on-demand). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).

> [!NOTE]
> Kontrollera att antalet poster i det exporterade avsnittet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.

Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan. Följande mappsökväg skapas automatiskt i behållaren:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* för de exporterade entiteterna finns på nivån *%ExportDestinationName%*.

Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiera Experience Data Model (XDM) i Adobe Experience Platform

Innan de exporterade data från Customer Insights kan användas i Adobe Experience Platform, vi måste definiera Experience Data Model-schemat och [konfigurera data för kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lär dig [vad XDM är](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) och lär dig grunderna i [schemasammansättning](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importera data till Adobe Experience Platform

Nu när allt är på plats måste vi importera de förberedda publik från Customer Insights i Adobe Experience Platform.

Börja med att [skapa en Azure Blob Storage-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

När du har definierat källanslutningen [konfigurerar du ett dataflöde](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) för en batchanslutning för molnlagring så att segmenten från Customer Insights importeras till Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Skapa en målgrupp Adobe Campaign Standard

För att skicka e-postmeddelandet för den här kampanjen använder vi Adobe Campaign Standard. När vi har importerat dessa data till Adobe Experience Platform, måste vi [skapa en målgrupp](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard med data i Adobe Experience Platform.


Lär dig hur [du använder segmentverktyget](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) i Adobe Campaign Standard för att definiera en målgrupp baserad på data i Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Skapa och skicka e-postmeddelandet med Adobe Campaign Standard

Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-post med förnyelseerbjudande från Adobe Campaign Standard.":::
