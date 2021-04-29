---
title: Exportera Customer Insights-data till AdRoll
description: Lär dig hur du konfigurerar anslutningen och exporterar till AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895981"
---
# <a name="export-segment-lists-to-adroll-preview"></a>Exportera segmentlistor till AdRoll (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till AdRoll och använd dem för annonsering. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [AdRoll-konto](https://www.adroll.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till totalt 250 000 profiler per export till AdRoll.
- Du kan inte exportera segment med färre än 100 profiler till AdRoll. 
- Export till AdRoll är begränsad till segment.
- Det kan ta upp till 10 minuter att exportera upp till 250 000 profiler till AdRoll. 
- Antalet profiler som du kan exportera till AdRoll är beroende av och begränsat enligt ditt kontrakt med AdRoll.

## <a name="set-up-connection-to-adroll"></a>Upprätta anslutningen till AdRoll

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **AdRoll** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till AdRoll.

1. Välj **Autentisera med AdRoll** och ange dina autentiseringsuppgifter som administratör för AdRoll. 

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet AdRoll. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange ditt **AdRoll annonsörens ID** För mer information, se [Annonsörprofiler för AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Det krävs för att exportera segment till AdRoll.

1. Välj de segment som du vill exportera. Välj ett segment med minst 100 medlemmar. Det går inte att exportera mindre segment. Dessutom är det maximala värdet för ett segment som ska exporteras 250 000 medlemmar per export. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till AdRoll tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att AdRoll uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
