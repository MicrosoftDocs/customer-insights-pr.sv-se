---
title: Exportera Customer Insights-data till Azure Data Lake Storage Gen2
description: Lär dig hur du konfigurerar anslutningen till Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760073"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Upprätta anslutningen till Azure Data Lake Storage Gen2 (förhandsversion)

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Azure Data Lake Gen 2** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för Azure Data Lake Storage Gen2.
    - Mer information om hur du skapar ett lagringskonto att använda med Azure Data Lake Storage Gen2 finns i [Skapa lagringskonto](/azure/storage/blobs/create-data-lake-storage-account). 
    - Mer information om hur du hittar Azure Data Lake Gen 2-kontonamn och kontonyckel finns i [Hantera inställningar för lagringskonto på Azure-portalen](/azure/storage/common/storage-account-manage).

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet **Azure Data Lake**. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Markera rutan bredvid var och en av de entiteter som du vill exportera till det här målet.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

Exporterade data lagras i den Azure Data Lake Gen 2-behållare som du konfigurerade. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]