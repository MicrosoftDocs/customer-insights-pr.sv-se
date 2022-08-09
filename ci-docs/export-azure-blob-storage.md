---
title: Exportera data till en Azure Blob Storage (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Blob Storage.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195726"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportera data till en Azure Blob Storage (förhandsgranskning)

Lagra Customer Insights-data i Blob Storage eller använd det för att överföra data till andra appar.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Azure Blob Storage-konto](/azure/storage/blobs/create-data-lake-storage-account) namn och kontonyckel. För att hitta namnet och nyckeln, se [Hantera inställningar för lagringskonto i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Kända begränsningar

- För Azure Blob Storage kan du välja mellan [Nivåerna standardprestanda och premium-prestanda](/azure/storage/blobs/storage-blob-performance-tiers). Om du väljer prestandanivån Premium väljer du [premium blockblobb som kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Upprätta anslutningen till Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Azure Blob Storage**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Om du vill konfigurera den här exporten måste du ha [behörighet](export-destinations.md#set-up-a-new-export) för den här anslutningstypen.

> [!IMPORTANT]
> Om du har aktiverat [inställningen för mjuk borttagning](/azure/storage/blobs/soft-delete-blob-enable) för Azure Blob Storage-kontot misslyckas exporten. Inaktivera mjuk borttagning för att exportera data till blobbar.

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Blob Storage. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange mappnamnet för Blob Storage.

1. Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exporterade data lagras i den Blob Storage-behållare som du konfigurerat. Följande mappsökvägar skapas automatiskt i behållaren:

- För källentiteter och entiteter som genererats av systemet:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Export av entiteter som innehåller en stor mängd data kan leda till flera CSV-filer i samma mapp för varje export. Att dela upp exporter sker av effektivitets skäl för att minimera den tid det tar för en export att slutföras.

- model.json för de exporterade entiteterna finns på nivån *%ExportDestinationName%*.  
  
  Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
