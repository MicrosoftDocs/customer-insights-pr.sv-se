---
title: Exportera data till en Azure Blob Storage (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Blob Storage.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 059c8364ca0f3740bc0e4ffeeeba94246c9e5696
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055512"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportera data till en Azure Blob Storage (förhandsgranskning)

Lagra Customer Insights-data i Blob Storage eller använd det för att överföra data till andra appar.

## <a name="known-limitations"></a>Kända begränsningar

1. För Azure Blob Storage kan du välja mellan [Nivåerna standardprestanda och premium-prestanda](/azure/storage/blobs/storage-blob-performance-tiers). Om du väljer prestandanivån Premium väljer du [premium blockblobb som kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

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
> Om du har aktiverat inställningen för mjuk borttagning av Azure Blob Storage-kontot misslyckas exporten. Inaktivera mjuk borttagning för att exportera data till blobbar. Mer information finns i [Aktivera mjuk borttagning av blobb](/azure/storage/blobs/soft-delete-blob-enable)

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
  
  > [!TIP]
  > Export av entiteter som innehåller en stor mängd data kan leda till flera CSV-filer i samma mapp för varje export. Att dela upp exporter sker av effektivitets skäl för att minimera den tid det tar för en export att slutföras.

- model.json för de exporterade entiteterna finns på %ExportDestinationName%-nivån  
  - Exempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
