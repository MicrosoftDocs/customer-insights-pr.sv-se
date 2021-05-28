---
title: Exportera Customer Insights-data till DotDigital
description: Lär dig hur du konfigurerar anslutningen och exporterar till DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976868"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a>Exportera segmentlistor till DotDigital (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till DotDigital-adressböcker och använd dem för kampanjer, skicka marknadsföring via e-post och skapa kundsegment med DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [DotDigital-konto](https://dotdigital.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga adressböcker i DotDigital och motsvarande ID. ID hittar du i URL-adressen när du väljer och öppnar en adressbok. Mer information finns i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 000 000 profiler per export till DotDigital.
- Export till DotDigital är begränsad till segment.
- Export av segment med totalt 1 000 000 profiler kan ta upp till 3 timmar på grund av begränsningar på leverantörens sida. 
- Antalet profiler som du kan exportera till DotDigital är beroende av och begränsat enligt ditt kontrakt med DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurera anslutningen DotDigital

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **DotDigital** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt **användarnamn och lösenord för DotDigital**.

1. Ange ditt **[ID till DotDigital-adressboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till DotDigital.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet DotDigital. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.


1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Fullständigt namn**, **Kön** och **Postnummer**.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till DotDigital.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 
 
I DotDigital kan du nu hitta segment i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till DotDigital tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att DotDigital uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]