---
title: Exportera Customer Insights-data till Braze
description: Lär dig att konfigurera anslutningen och exporten till Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524173"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exportera segmentlistor till Braze (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Braze och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Braze-konto](https://www.braze.com/) och motsvarande administratörsbehörigheter.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress och ett Braze-kund-ID. 

## <a name="known-limitations"></a>Kända begränsningar

- Export till Braze är begränsat till segment.
- Det kan ta upp till 40 minuter att exportera upp till 1 miljon kundprofiler till Braze. 
- Antalet kundprofiler du kan exportera till Braze är beroende av och begränsas av ditt avtal med Braze.

## <a name="set-up-connection-to-braze"></a>Upprätta anslutningen till Braze

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Braze** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll din [Braze API-nyckel](https://www.braze.com/docs/api/basics/) för att fortsätta logga in. 

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Braze.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export** väljer du en anslutning från Braze-avsnittet. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.  

3. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält som representerar en kunds e-postadress, och i fältet "Kund-ID" väljer du det fält som representerar kundens Braze-ID. Detta krävs för att exportera segment till Braze. Segmenten i Braze skapas med samma namn på segmenten som i Dynamics 365 Customer Insights. Du kan välja ytterligare valfria fält för matchande data. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Braze tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att Braze uppfyller eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
