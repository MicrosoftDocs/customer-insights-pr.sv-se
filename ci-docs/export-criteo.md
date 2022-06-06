---
title: Exportera Customer Insights-data till Criteo
description: Lär dig att konfigurera anslutningen och exporten till Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808778"
---
# <a name="export-segments-to-criteo-preview"></a>Exportera segment till Criteo (förhandsgranskning)

Exportera segment för enhetliga kundprofiler för att generera kampanjer, tillhandahålla e-postmarknadsföring och utnyttja specifika kundgrupper med Criteo.

## <a name="prerequisites-for-connection"></a>Krav för anslutning

-   Du har ett [Criteo Dynamics Retargeting-konto](https://www.criteo.com/login/) och motsvarande administratörsbehörigheter.
-   Du har [konfigurerat segment](segments.md).
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljoner kundprofiler per export till Criteo.
- Export till Criteo är begränsat till segment.
- Det kan ta upp till 30 minuter att exportera segment med 1 miljon kundprofiler. 
- Antalet kundprofiler som du kan exportera till Criteo är beroende av och begränsas av ditt avtal med Criteo.

## <a name="set-up-connection-to-criteo"></a>Upprätta anslutningen till Criteo

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Criteo** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag godkänner** att bekräfta **sekretess och regelefterlevnad** och välj **Anslut** för att initiera anslutningen till Criteo.

1. Välj **Autentisera med Criteo** och ange ditt administratörsanvändarnamn och dina autentiseringsuppgifter för Criteo. 

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export** väljer du en anslutning från Criteo-avsnittet. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen. 

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. 

1. Alternativt kan du exportera **Annonsörs-ID** och **Namn**

1. Välj de segment som du vill exportera. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Criteo tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att Criteo uppfyller eventuella sekretess- eller säkerhetskrav som kan finnas. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](includes/footer-banner.md)]
