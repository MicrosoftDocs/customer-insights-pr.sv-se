---
title: Exportera segment till Braze (förhandsgranskning)
description: Lär dig att konfigurera anslutningen och exporten till Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081883"
---
# <a name="export-segments-to-braze-preview"></a>Exportera segment till Braze (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Braze och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

- Ett [Braze-konto](https://www.braze.com/) och motsvarande administratörsbehörigheter.
- Befintliga [segment i Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurerade segments](segments.md) i Customer Insights.
- Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress och ett Braze-kund-ID.

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

1. I fältet **Anslutning för export** väljer du en anslutning från Braze-avsnittet. Om du inte ser det här avsnittet finns det inga tillgängliga anslutningar av den här typen.  

1. Lägg till **visningsnamn** för din export.

1. Lägg till API-identifieraren för braze-segmentet som du vill exportera till i fältet **API-ID för Braze-segment**. Du hittar identifieraren i segmentinformationen på Braze-plattformen.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. I fältet **Kund-ID**, välj fältet som representerar kundens Braze ID. Detta krävs för att exportera segment till Braze. Du kan välja fler fält om du vill.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Braze tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att Braze uppfyller eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
