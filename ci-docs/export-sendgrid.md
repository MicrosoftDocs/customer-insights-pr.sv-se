---
title: Exportera Customer Insights-data till SendGrid
description: Lär dig hur du konfigurerar anslutningen och exporterar till SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647877"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportera segment till SendGrid (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till SendGrid-kontaktlistor och använd dem för kampanjer och e-postmarknadsföring i SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [SendGrid-konto](https://sendgrid.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga kontaktlistor i SendGrid och motsvarande ID. Mer information finns i [SendGrid – Hantera kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Du har [konfigurerade segments](segments.md) i Customer Insights.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 100 000 kundprofiler totalt till SendGrid.
- Export till SendGrid är begränsad till segment.
- Det kan ta upp till några timmar innan du exporterar upp till 100 000 kundprofiler till SendGrid. 
- Hur många kundprofiler du kan exportera till SendGrid är beroende av och begränsas av ditt kontrakt med SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Konfigurera anslutningen SendGrid

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **SendGrid** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **SendGrids API-nyckel** [SendGrids API-nyckel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till SendGrid.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet SendGrid. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange ditt **[ID för SendGrid-lista](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Land/region**, **Delstat**, **Stad** och **Postnummer**.

1. Välj de segment som du vill exportera. Vi **rekommenderar starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till SendGrid. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till SendGrid tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att SendGrid uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
