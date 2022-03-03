---
title: Exportera Customer Insights-data till Klaviyo
description: Lär dig hur du konfigurerar anslutningen och exporterar till Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 027aee70d9fdab0a92d7fd99209a6ac2ca3cc361
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225490"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Exportera segmentlistor till Klaviyo (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Klaviyo och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Klaviyo-konto](https://www.klaviyo.com/) och motsvarande autentiseringsuppgifter för administratör.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till 100 000 kundprofiler per export till Klaviyo.
- Exporten till Klaviyo är begränsad till segment.
- Det kan ta upp till 20 minuter innan du exporterar upp till 1 miljon kundprofiler till Klaviyo. 
- Hur många kundprofiler du kan exportera till Klaviyo är beroende av och begränsas av ditt kontrakt med Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Upprätta anslutningen till Klaviyo

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Klaviyo** om du vill konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll din [Klaviyo API-nyckel](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) för att fortsätta logga in. 

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** för att initiera anslutningen till Klaviyo.

1. Välj **Autentisera med Klaviyo** och ange dina administratörsautentiseringsuppgifter för Klaviyo.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet Klaviyo. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange ditt [**List-ID för Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Detta krävs för att kunna exporter segment till Klaviyo.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till Klaviyo tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Klaviyo uppfyller dina eventuella sekretess- och säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
