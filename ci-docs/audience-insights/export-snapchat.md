---
title: Exportera Customer Insights-data till Snapchat
description: Lär dig hur du konfigurerar anslutningen och exporterar till Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760645"
---
# <a name="export-segment-lists-to-snapchat-preview"></a>Exportera segmentlistor till Snapchat (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Snapchat och använd dem för annonser. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [Snapchat företagskonto](https://business.snapchat.com/), en [Snapchat-annonskonto](https://ads.snapchat.com/) och motsvarande administratörsuppgifter.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Export till Snapchat är begränsad till segment.
- Det kan ta upp till 15 minuter att exportera upp till 1 miljon profiler till Snapchat. 

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

1. Ange [**Snapchat målgrupps-ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Det krävs att exportera segment till Snapchat.

1. Välj de segment som du vill exportera. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Snapchat, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Snapchat uppfyller alla eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
