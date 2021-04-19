---
title: Exportera Customer Insights-data till Azure Data Lake Storage Gen2
description: Lär dig hur du konfigurerar anslutningen till Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596663"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Anslutningsprogram för Azure Data Lake Storage Gen2 (förhandsversion)

Lagra dina Customer Insights-data i Azure Data Lake Storage Gen2 eller använd det för att överföra dina data till andra program.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfigurera anslutningsprogrammet för Azure Data Lake Storage Gen2

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. Under **Azure Data Lake Storage Gen2** väljer du **Konfigurera**.

1. Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för Azure Data Lake Storage Gen2.
    - Mer information om hur du skapar ett lagringskonto att använda med Azure Data Lake Storage Gen2 finns i [Skapa lagringskonto](/azure/storage/blobs/create-data-lake-storage-account). 
    - Mer information om hur du hittar namnet och kontonyckeln till Azure Data Lake Gen2-lagringskontot finns i [Hantera inställningar för lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).

1. Välj **Nästa**.

1. Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md#export-data-on-demand). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).