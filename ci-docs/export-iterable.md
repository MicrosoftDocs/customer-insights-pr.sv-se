---
title: Exportera segment till Iterable (förhandsgranskning)
description: Lär dig att konfigurera anslutningen och exporten till Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 98d5aeab6b0e932d291213053d509ec72da82e47
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052257"
---
# <a name="export-segments-to-iterable-preview"></a>Exportera segment till Iterable (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Iterable och använd dem för marknadsföringsaktiviteter.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Iterable-konto](https://iterable.com/) och motsvarande administratörsbehörigheter.
-   Du har [konfigurerade segments](segments.md) i Customer Insights.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Export till Iterable är begränsat till segment.
- Det kan ta upp till 30 minuter att exportera upp till 1 miljon kundprofiler till Iterable. 
- Hur många kundprofiler du kan exportera till Iterable är beroende av och begränsas av ditt avtal med Iterable.

## <a name="set-up-connection-to-iterable"></a>Upprätta anslutningen till Iterable

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Iterable** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll din [Iterable API-nyckel](https://support.iterable.com/hc/en-us/articles/360043464871) för att fortsätta logga in. 

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Iterable.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export** väljer du en anslutning från Iterable-avsnittet. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

3. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Du måste exportera segment till Iterable. Listan som skapas i Iterable får exakt samma namn som segmentnamnet i Dynamics 365 Customer Insights.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Iterable tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att Iterable uppfyller eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
