---
title: Exportera Customer Insights-data till Azure Blob Storage
description: Lär dig hur du konfigurerar anslutningen och exporterar till Blob Storage.
ms.date: 06/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e38fc06a948178fcbc62c08a4cf4816e1d030e79
ms.sourcegitcommit: 656b1a6cdff37ba4f808311fd0327ab38e02ed13
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "6318321"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportera segmentlista och andra data till Azure Blob Storage (förhandsgranskning)

Lagra Customer Insights-data i Blob Storage eller använd det för att överföra data till andra appar.

## <a name="set-up-the-connection-to-blob-storage"></a>Upprätta anslutningen till Blob Storage

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Azure Blob Storage** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto.
    - Mer information om hur du hittar kontonamn och kontonyckel för Blob Storage finns i [Hantera inställningar för lagringskonto på Azure-portalen](/azure/storage/common/storage-account-manage).
    - Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Om du har aktiverat inställningen för mjuk borttagning av Azure Blob Storage-kontot misslyckas exporten. Inaktivera mjuk borttagning för att exportera data till blobbar. Mer information finns i [Aktivera mjuk borttagning av blobb](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Blob Storage. Om avsnittets namn inte visas är inga anslutningar av den här typen tillgängliga för dig.

1. Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).     

Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

Exporterade data lagras i den Blob Storage-behållare som du konfigurerat. Följande mappsökvägar skapas automatiskt i behållaren:

- För källentiteter och entiteter som genererats av systemet:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Exempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- model.json för de exporterade entiteterna finns på %ExportDestinationName%-nivån  
  - Exempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
