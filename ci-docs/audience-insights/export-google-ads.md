---
title: Exportera Customer Insights-data till Google Ads
description: Lär dig hur du konfigurerar anslutningen och exporterar till Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523827"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportera segment till Google Ads (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till en Google Ads-målgruppslista och använd dem för att annonsera på Google Search, Gmail, YouTube och Google Display Network. 


## <a name="prerequisites-for-connection"></a>Krav för anslutning

-   Du har ett [Google Ads-konto](https://ads.google.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Du uppfyller kraven i [policyn för kundmatchning](https://support.google.com/adspolicy/answer/6299717).
-   Du uppfyller kraven i [storlekar för återmarknadsföringslista](https://support.google.com/google-ads/answer/7558048).
-   Du har [konfigurerat segment](segments.md).
-   Enhetliga kundprofiler i de exporterade segmenten innehåller fält som representerar e-postadress, telefonnummer, ID för mobilannonsör, användar-ID för tredje part, samt adress.

## <a name="known-limitations"></a>Kända begränsningar

- Export till Google Ads är begränsad till segment.
- Det kan ta upp till 30 minuter att exportera segment med totalt 1 miljoner kundprofiler, detta på grund av begränsningar på leverantörssidan. 
- Matchningen i Google Ads kan ta upp till 48 timmar.

## <a name="set-up-connection-to-google-ads"></a>Konfigurera anslutningen Google Ads

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Google Ads** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt **[kund-ID för Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Autentisera med Google Ads** och ange dina Google Ads-autentiseringsuppgifter.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Google Ads. Om avsnittets namn inte visas är inga anslutningar av den här typen tillgängliga för dig.

1. Om du vill skapa en ny målgrupp låter du fältet ID för Google-målgrupp vara tomt. Vi skapar automatiskt en ny målgrupp på ditt Google Ads-konto och använder namnet på det exporterade segmentet. Om du vill uppdatera en befintlig Google Ads-målgrupp anger du ditt [målgrupps-ID för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. I avsnittet **Datamatchning** väljer du ett eller flera datafält som ska exporteras, och markerar sedan det fält som representerar motsvarande datafält i Customer Insights.

1. Välj de segment som du vill exportera. 

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). 

Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Google Ads tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Google Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
