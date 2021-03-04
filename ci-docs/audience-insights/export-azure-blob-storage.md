---
title: Exportera Customer Insights-data till Azure Blob Storage
description: Lär dig hur du konfigurerar anslutningen till Azure Blob Storage.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269214"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Connector för Azure Blob Storage (förhandsversion)

Lagra Customer Insights-data i Azure Blob Storage eller använd det för att överföra data till andra program.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurera anslutningsprogram för Azure Blob Storage

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. Under **Azure Blob Storage**, välj **Ställ in**.

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Azure Blob Storage-kontot.
    - Om du vill veta mer om hur du hittar Azure Blob Storage-kontots namn och kontonyckel, se [Hantera lagringsinställningar i Azure-portalen](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Mer information om hur du skapar en behållare finns i [skapa en behållare](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.

1. Välj **Nästa**.

1. Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.

1. Välj **Spara**.

Exporterade data lagras i Azure Blob Storage-behållaren som du konfigurerade. Följande mappsökvägar skapas automatiskt i behållaren:

- För källentiteter och entiteter som genererats av systemet: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json för de exporterade entiteterna lagras på nivån %ExportDestinationName%
  - Exempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md#export-data-on-demand). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]