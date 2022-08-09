---
title: Exportera data till Salesforce Marketing Cloud (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197060"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportera data till Salesforce Marketing Cloud (förhandsgranskning)

Använd dina kunddata i Salesforce Marketing Cloud genom att exportera dem via en plats för säkert filöverföringsprotokoll (SFTP).

## <a name="prerequisites"></a>Förutsättningar

- EN [SFTP-värd för Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) och motsvarande administratörsuppgifter.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Konfigurera anslutningen till Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Salesforce Marketing Cloud**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll **Användarnamn**, **Lösenord**, **Värdnamn** och **Exportmapp** för ditt SFTP-konto.

1. Välj **Verifiera** för att testa anslutningen.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet SFTP. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj om du vill exportera dina data **Komprimerad** eller **Uppackad** och **fältavgränsaren** för de exporterade filerna.

1. Markera de entiteter, till exempel segment, som du vill exportera.

   > [!NOTE]
   > Varje vald entitet delas upp i upp till fem utdatafiler när de exporteras.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importera Customer Insights-data från SFTP-plats till Salesforce Marketing Cloud

1. Skapa [datatillägg i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) för att importera datafilen för Customer Insights från SFTP-platsen.

2. [Importera data från SFTP-platsen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) till datatillägget för Salesforce Marketing Cloud.

3. Konfigurera automatiseringen för att importera data till datatilläggen. Läs mer om [automatisering via filsläpp och schemalagda automatiseringar](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definiera ett [automatisering via filsläpp](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [schemalagd automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Här följer ett exempel på [en automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
