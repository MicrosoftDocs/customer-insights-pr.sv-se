---
title: Exportera Customer Insights-data till Google Ads
description: Lär dig hur du konfigurerar anslutningen och exporterar till Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976340"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportera segment till Google Ads (förhandsgranskning)

Exportera segment av enhetliga kundprofiler till Google Ads målgruppslista och använd dem för att annonsera i Google Sök, Gmail, YouTube och Googles Display-nätverk. 

## <a name="prerequisites-for-connection"></a>Krav för anslutning

-   Du har ett [Google Ads-konto](https://ads.google.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Du har en [godkänd token för Google Ads-utvecklare](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Du uppfyller kraven i [policyn för kundmatchning](https://support.google.com/adspolicy/answer/6299717)
-   Du uppfyller kraven i [storlekarna för återmarknadsföringslista](https://support.google.com/google-ads/answer/7558048) 

-   Det finns befintliga målgrupper i Google Ads och motsvarande ID. Mer information finns i [Målgrupper för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Du har [konfigurerat segment](segments.md)
-   Enhetliga kundprofiler i de exporterade segmenten innehåller fält som representerar en e-postadress, ett förnamn och ett efternamn

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 000 000 profiler per export till Google Ads.
- Export till Google Ads är begränsad till segment.
- Export av segment med totalt 1 000 000 profiler kan ta upp till 5 minuter på grund av begränsningar på leverantörens sida. 
- Matchningen i Google Ads kan ta upp till 48 timmar.

## <a name="set-up-connection-to-google-ads"></a>Konfigurera anslutningen Google Ads

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Google Ads** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt **[kund-ID för Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Ange ditt **[Google Ads-godkända utvecklartoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Autentisera med Google Ads** och ange dina Google Ads-autentiseringsuppgifter.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Google Ads. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange ditt **[målgrupps-ID för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** och välj **Anslut** för att initiera anslutningen till Google Ads.

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Upprepa samma steg för fälten **Förnamn** och **Efternamn**.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till Google Ads.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Google Ads tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Google Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
