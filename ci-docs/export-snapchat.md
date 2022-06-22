---
title: Exportera Customer Insights-data till Snapchat
description: Lär dig hur du konfigurerar anslutningen och exporterar till Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947298"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportera segment till Snapchat (förhandsversion)

Exportera segment med enhetliga kundprofiler till Snapchat och använd dem för annonser. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [Snapchat företagskonto](https://business.snapchat.com/), en [Snapchat-annonskonto](https://ads.snapchat.com/) och motsvarande administratörsuppgifter. Du måste minst vara medlem i ett organisationskonto och en datahanterare för ett specifikt annonskonto. 
-   Du har minst en målgrupp i Snapchat Audience Manager av typen SAM (Snap Audience Match). 
-   Du har [konfigurerade segments](segments.md) i Customer Insights.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Export till Snapchat är begränsad till segment.
- Det kan ta upp till 15 minuter innan du exporterar upp till 1 miljon kundprofiler till Snapchat. 

## <a name="set-up-connection-to-snapchat"></a>Konfigurera anslutningen Snapchat

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Snapchat** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Snapchat.

1. Välj **Autentisera med Snapchat** och ange dina administratörsuppgifter för Snapchat. 

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Snapchat. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange [**Snapchat segment/målgrupps-ID**](https://businesshelp.snapchat.com/s/article/custom-audiences). ID:t för publik finns i URL:en när du har valt publik i Snapchat Audience Manager. 

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Det krävs att exportera segment till Snapchat.

1. Välj de segment som du vill exportera. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Snapchat, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Snapchat uppfyller alla eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
