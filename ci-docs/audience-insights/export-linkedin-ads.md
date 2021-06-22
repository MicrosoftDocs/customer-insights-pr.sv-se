---
title: Exportera Customer Insights-data till LinkedIn Ads
description: Lär dig hur du konfigurerar anslutningen och exporterar till LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124560"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportera segment till LinkedIn Ads (förhandsversion)

Exportera segment med enhetliga kundprofiler till LinkedIn Ads för att skapa matchade målgrupper. Använd de matchade målgrupperna för företagsinriktning och kontaktinriktning.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) och motsvarande administratörsautentiseringsuppgifter.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Kundprofiler i de exporterade segmenten innehåller ett fält med en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till 100 000 profiler per export till LinkedIn Ads.
- Export till LinkedIn Ads är begränsad till segment.
- Det kan ta upp till 10 minuter att exportera upp till 100 000 profiler till LinkedIn Ads. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Upprätta anslutningen till LinkedIn Ads

1. I målgruppsinsikter, gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **LinkedIn Ads** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt [LinkedIn Campaign Manager-konto-ID](https://www.linkedin.com/help/lms/answer/a424270).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Campaign Monitor.

1. Välj **Autentisera med LinkedIn** och tillhandahåll dina administratörsautentiseringsuppgifter för LinkedIn Campaign Manager.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera en export om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet LinkedIn Ads. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Välj om du vill exportera data för att göra [kontaktinriktning](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [företagsinriktning](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn. 

1. I avsnittet **Datamatchning** väljer du fältet i den enhetliga kundprofilen som representerar en kunds e-postadress. Det krävs för att exportera segment till LinkedIn Ads.

1. Välj de segment som du vill exportera. De matchade målgrupperna i LinkedIn Campaign Manager skapas automatiskt med namnet på de segment som du har valt att exportera. Varje segment resulterar i en separat matchad målgrupp. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till LinkedIn Ads tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att LinkedIn Ads uppfyller alla eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort det här exportmålet för att stoppa användningen av den här funktionen.
