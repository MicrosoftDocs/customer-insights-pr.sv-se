---
title: Exportera segment till Adobe Experience Platform (förhandsversion)
description: Lär dig hur du använder segmenten Customer Insights i Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195312"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportera segment till Adobe Experience Platform (förhandsversion)

Exportera segment som riktar sig till relevanta målgrupper till Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a>Förutsättningar

- En Adobe Experience Platform-licens.
- En Adobe Campaign Standard licens.
- Ett [Azure Blob Storage-konto](/azure/storage/blobs/create-data-lake-storage-account) namn och kontonyckel. För att hitta namnet och nyckeln, se [Hantera inställningar för lagringskonto i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Vi konfigurerar exporten från Customer Insights till ett Azure Blob Storage-konto.

### <a name="set-up-connection-to-azure-blob-storage"></a>Upprätta anslutningen till Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Azure Blob Storage**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto som du vill exportera segmentet till.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. ":::

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

### <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Blob Storage. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj det segment som du vill exportera. I det här exemplet är det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Kontrollera att antalet poster i det exporterade avsnittet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.

Exporterade data lagras i Azure Blob Storage-behållaren som du konfigurerade. Följande mappsökvägar skapas automatiskt i behållaren:

- För källentiteter och entiteter som genererats av systemet:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* för de exporterade entiteterna finns på nivån *%ExportDestinationName%*.

  Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiera Experience Data Model (XDM) i Adobe Experience Platform

Innan de exporterade data från Customer Insights kan användas i Adobe Experience Platform, vi måste definiera Experience Data Model-schemat och [konfigurera data för kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lär dig [vad XDM är](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) och lär dig grunderna i [schemasammansättning](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importera data till Adobe Experience Platform

Importera de förberedda måldata från Customer Insights till Adobe Experience Platform.

1. [Skapa en Azure Blob Storage källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigurerar du ett dataflöde](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) för en batchanslutning för molnlagring så att segmenten från Customer Insights importeras till Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Skapa en målgrupp Adobe Campaign Standard

För att skicka e-postmeddelandet för den här kampanjen använder vi Adobe Campaign Standard.

1. [Skapa en målgrupp](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard med hjälp av data i Adobe Experience Platform.

1. [Du använder segmentverktyget](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) i Adobe Campaign Standard för att definiera en målgrupp baserad på data i Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Skapa och skicka e-postmeddelandet med Adobe Campaign Standard

Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-post med förnyelseerbjudande från Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
