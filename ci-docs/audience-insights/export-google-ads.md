---
title: Exportera Customer Insights-data till Google Ads
description: Lär dig hur du konfigurerar anslutningen till Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268984"
---
# <a name="connector-for-google-ads-preview"></a>Anslutningsprogram för Google Ads (förhandsversion)

Exportera segment av enhetliga kundprofiler till Google Ads målgruppslista och använd dem för att annonsera i Google Sök, Gmail, YouTube och Googles Display-nätverk. 

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Google Ads-konto](https://ads.google.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga målgrupper i Google Ads och motsvarande ID. Mer information finns i [Målgrupper för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Du har [konfigurerat segment](segments.md)
-   Enhetliga kundprofiler i de exporterade segmenten innehåller fält som representerar en e-postadress, ett förnamn och ett efternamn

## <a name="connect-to-google-ads"></a>Anslut till Google Ads

1. Gå till **Administratör** > **Exportera mål**.

1. Under **Google Ads** väljer du **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

1. Ange ditt **[kund-ID för Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Ange ditt **[Google Ads-godkända utvecklartoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Ange ditt **[målgrupps-ID för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** och välj **Anslut** för att initiera anslutningen till Google Ads.

1. Välj **Autentisera med Google Ads** och ange dina Google Ads-autentiseringsuppgifter.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportera skärmbild för Google Ads-anslutning":::

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Upprepa samma steg för fälten **Förnamn** och **Efternamn**.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till Google Ads.

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab). I Google Ads kan du nu hitta dina segment under [Google Ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 000 000 profiler per export till Google Ads.
- Export till Google Ads är begränsad till segment.
- Export av segment med totalt 1 000 000 profiler kan ta upp till 5 minuter på grund av begränsningar på leverantörens sida. 
- Matchningen i Google Ads kan ta upp till 48 timmar.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Google Ads tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Google Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]