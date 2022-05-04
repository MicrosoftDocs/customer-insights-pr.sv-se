---
title: Exportera Customer Insights-data till ActiveCampaign
description: Lär dig hur du konfigurerar anslutningen och exporterar till ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647737"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportera segment till ActiveCampaign (förhandsversion)

Exportera segment med enhetliga kundprofiler till ActiveCampaign och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [ActiveCampaign-konto](https://www.activecampaign.com/) och motsvarande autentiseringsuppgifter för administratör.
-   Du har [konfigurerade segments](segments.md) i Customer Insights.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält med en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera ta upp till 1 miljon kundprofiler per export till ActiveCampaign och det kan ta 90 minuter att genomföra.
- Exporten till ActiveCampaign är begränsad till segment.
- Hur många kundprofiler du kan exportera till ActiveCampaign är beroende av ditt kontrakt med ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Upprätta anslutning till ActiveCampaign

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och völj **ActiveCampaign** om du vill konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange din [API-nyckel för ActiveCampaign och ditt värdnamn för REST-slutpunkt](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Endast slutpunktsvärdnamn för REST utan https://. 

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** för att initiera anslutningen till ActiveCampaign.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera en export om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet ActiveCampaign. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange ditt [**List-ID för ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Detta krävs för att kunna exporter segment till ActiveCampaign. Alternativt kan du exportera förnamn, efternamn och telefonnummer om du vill skapa mer anpassade e-postmeddelanden. Välj Lägg till attribut för att mappa dessa fält.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till ActiveCampaign tillåter du överföringen av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att ActiveCampaign uppfyller eventuella sekretess- och säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
