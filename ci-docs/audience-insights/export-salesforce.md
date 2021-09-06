---
title: Exportera Customer Insights-data till Salesforce Marketing Cloud
description: Lär dig hur du konfigurerar anslutningen och exporterar till Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b50539d6478a8fe196048f0fb421e5856f713a3ddc6577a637e593f90857ae8b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035575"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Exportera segment och andra data till Salesforce Marketing Cloud (förhandsgranskning)

Använd dina kunddata i Salesforce Marketing Cloud genom att exportera dem via en plats för säkert filöverföringsprotokoll (SFTP).

## <a name="prerequisites-for-connection"></a>Krav för anslutning

- Tillgängligheten för en SFTP-värd och motsvarande administratörsuppgifter. [Så här konfigurerar su SFTP-platser för Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Konfigurera anslutningen till Salesforce Marketing Cloud

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Salesforce Marketing Cloud** om du vill konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll **Användarnamn**, **Lösenord**, **Värdnamn** och **Exportmapp** för ditt SFTP-konto.

1. Välj **Verifiera** för att testa anslutningen.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet SFTP. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Välj om du vill exportera dina data **Komprimerad** eller **Uppackad** och **fältavgränsaren** för de exporterade filerna.

1. Markera de entiteter, till exempel segment, som du vill exportera.

   > [!NOTE]
   > Varje vald entitet delas upp i upp till fem utdatafiler när de exporteras. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importera Customer Insights-data från SFTP-plats till Salesforce Marketing Cloud

1. Skapa [datatillägg i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) för att importera datafilen för Customer Insights från SFTP-platsen.

2. [Importera data från SFTP-platsen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) till datatillägget för Salesforce Marketing Cloud. 

3. Konfigurera automatiseringen för att importera data till datatilläggen. Läs mer om [automatisering via filsläpp och schemalagda automatiseringar](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definiera ett [automatisering via filsläpp](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [schemalagd automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Här följer ett exempel på [en automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
