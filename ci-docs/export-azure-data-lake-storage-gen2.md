---
title: Exportera data till Azure Data Lake Storage Gen2 (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen till Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196462"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportera data till Azure Data Lake Storage Gen2 (förhandsversion)

Lagra Customer Insights-data i Data Lake Storage Gen2-konto eller använd det för att överföra data till andra appar.

## <a name="prerequisites"></a>Förutsättningar

- Ett [lagringskonto som ska användas med Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). För att hitta namnet och nyckeln för lagringskontot, se [Hantera inställningar för lagringskonto i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Kända begränsningar

- För Azure Data Lake Storage Gen2, välj mellan [nivåerna standardprestanda och premium-prestanda](/azure/storage/blobs/create-data-lake-storage-account). Om du väljer prestandanivån Premium väljer du [premium blockblobb som kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Upprätta anslutningen till Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Azure Data Lake Gen 2**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för Azure Data Lake Storage Gen2.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Data Lake. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Ange mappnamnet för lagringen Azure Data Lake Storage Gen2.

1. Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exporterade data lagras i den Azure Data Lake Gen 2-behållare som du konfigurerade.

> [!TIP]
> Export av entiteter som innehåller en stor mängd data kan leda till flera CSV-filer i samma mapp för varje export. Att dela upp exporter sker av effektivitets skäl för att minimera den tid det tar för en export att slutföras.

[!INCLUDE [footer-include](includes/footer-banner.md)]
