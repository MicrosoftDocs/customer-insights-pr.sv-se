---
title: Exportera segment till Marketo (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8cd24cf436bd5fdfd4ec3834d35baa1495e37ca4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053227"
---
# <a name="export-segments-to-marketo-preview"></a>Exportera segment till Marketo (förhandsgranskning)

Exportera segment av enhetliga kundprofiler för att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Marketo.

## <a name="prerequisites-for-connection"></a>Krav för anslutning

-   Du har ett [Marketo-konto](https://login.marketo.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga listor i Marketo och motsvarande ID. Mer information finns på [Marketo-listor](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Du har [konfigurerat segment](segments.md).
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljoner kundprofiler per export till Marketo.
- Export till Marketo är begränsad till segment.
- Det kan ta upp till tre timmar att exportera segment med totalt 1 miljon kundprofiler. 
- Hur många kundprofiler du kan exportera till Marketo är beroende av och begränsas av ditt kontrakt med Marketo.

## <a name="set-up-connection-to-marketo"></a>Upprätta anslutningen till Marketo

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Marketo** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ditt **[klient-ID för Marketo, din klienthemlighet och slutpunktsvärdnamnet för REST](https://developers.marketo.com/rest-api/authentication/)**. Endast slutpunktsvärdnamn för REST utan `https://`. Exempel: `xyz-abc-123.mktorest.com`. 

1. Välj **Jag godkänner** för att bekräfta **datasekretess och regelefterlevnad** och välj **Anslut** för att initiera anslutningen till Marketo.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Marketo. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange ditt **[ID för Marketo-lista](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. List-ID:t är ett endast numeriskt värde. Om ditt Marketo-list-ID är ST12345A7 tar du bort tecknet före och efter numeriska tecken och anger `12345`. 

1. I avsnittet **Datamatchning** väljer du minst ett fält som representerar en kunds e-postadress eller en kunds Marketo-ID. 

1. Alternativt kan du exportera **Förnamn**, **Efternamn**, **Ort**, **Delstat** och **Land/Region** för att skapa mer anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till Marketo.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). I Marketo kan du nu hitta dina segment under [Marketo-listor](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Marketo tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Marketo uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
