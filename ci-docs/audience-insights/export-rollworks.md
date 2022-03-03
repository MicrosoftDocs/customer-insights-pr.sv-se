---
title: Exportera Customer Insights-data till RollWorks
description: Lär dig hur du konfigurerar anslutningen och exporterar till RollWorks.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 392084105628ba4e6008a1386a5ac80c809a004e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225621"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportera segment till RollWorks (förhandsversion)

Exportera segment med enhetliga kundprofiler till RollWorks och använd dem för annonser. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [RollWorks-konto](https://www.rollworks.com/) och motsvarande autentiseringsuppgifter för administratör.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till 250 000 kundprofiler per export till RollWorks.
- Du kan inte exportera segment med färre än 100 kundprofiler till RollWorks. 
- Export till RollWorks är begränsad till segment.
- Det kan ta upp till 10 minuter innan du exporterar upp till 250 000 kundprofiler till RollWorks. 
- Hur många kundprofiler du kan exportera till RollWorks är beroende av och begränsas av ditt kontrakt med RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Konfigurera anslutningen RollWorks

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **RollWorks** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till RollWorks.

1. Välj **Autentisera med RollWorks** och ange dina administratörsuppgifter för RollWorks.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet RollWorks. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange din **RollWorks annonsörs-ID** [RollWorks-annonserbar](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Det krävs att exportera segment till RollWorks.

1. Välj de segment som du vill exportera. Välj ett segment med minst 100 medlemmar. Det går inte att exportera mindre segment. Dessutom är det maximala värdet för ett segment som ska exporteras 250 000 medlemmar per export. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till RollWorks, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att RollWorks uppfyller alla eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
