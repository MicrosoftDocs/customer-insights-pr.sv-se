---
title: Exportera segment till Microsoft Advertising (förhandsversion)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca37159ec6473ad5c331a0ce1aa8424d277529ff
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081913"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportera segment till Microsoft Advertising (förhandsversion)

Exportera Customer Insights-segment till Microsoft Advertising för att skapa Customer Match-målgrupper. Använd dessa målgrupper för dina annonskampanjer.

## <a name="prerequisites"></a>Förutsättningar

-   Ett [Microsoft Advertising-konto](https://ads.microsoft.com/) och motsvarande autentiseringsuppgifter för administratör.
-   Du har accepterat användarvillkoren för Customer Match. 
-   [Konfigurerade segments](segments.md) i Customer Insights.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält med en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till 500 000 kundprofiler per export till Microsoft Advertising.
- Export till Microsoft Advertising är begränsad till segment.
- Det kan ta upp till 10 minuter innan du exporterar upp till 500 000 kundprofiler till Microsoft Advertising. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Upprätta anslutningen till Microsoft Advertising

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Microsoft Advertising** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Standardinställningen är administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Microsoft Advertising.

1. Välj **Autentisera med Microsoft Advertising** och ange dina administratörsuppgifter för Microsoft Advertising.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Microsoft Advertising. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Välj de segment som ska exporteras. Customer Match-målgrupperna i Microsoft Advertising skapas automatiskt med namnet på de segment som valts för export. Varje segment resulterar i en separat Customer Match-målgrupp. 

1. Ange ditt **kund-ID och konto-ID för Microsoft Advertising**. Du hittar kund-ID (`cid`) och konto-ID (`aid`) i parametrarna för webbadressen när du är inloggad på Microsoft Advertising.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet med en kunds e-postadress. Det krävs för att exportera segment till Microsoft Advertising.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Microsoft Advertising tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Microsoft Advertising uppfyller alla eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort det här exportmålet för att stoppa användningen av den här funktionen.