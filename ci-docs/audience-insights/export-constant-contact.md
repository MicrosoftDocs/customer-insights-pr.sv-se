---
title: Exportera Customer Insights-data till Constant Contact
description: Lär dig hur du konfigurerar anslutningen och exporterar till Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124295"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportera segment till Constant Contact (förhandsversion)

Exportera segment med enhetliga kundprofiler till Constant Contact och använd dem för marknadsföringsaktiviteter. 

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

-   Du har ett [Constant Contact-konto](https://www.constantcontact.com/account-home) och motsvarande autentiseringsuppgifter för administratör.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till en miljoner profiler per export till Constant Contact.
- Export till Constant Contact är begränsad till segment.
- Det kan ta upp till 1 timme att exportera upp till 1 miljon profiler till Constant Contact. 
- Hur många profiler du kan exportera till Constant Contact beror på och begränsas av ditt kontrakt med Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Konfigurera anslutning till Constant Contact

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Constant Contact** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Constant Contact.

1. Välj **Autentisera med AdRoll** och ange dina administratörsuppgifter för Constant Contact. 

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Constant Contact. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange din [**Constant Contact list-ID**](https://app.constantcontact.com/pages/contacts/ui#lists). Öppna en lista i Constant Contact för att hitta list-ID:t i URL:en.

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Det krävs att exportera segment till Constant Contact.

1. Alternativt kan du exportera Förnamn och Efternamn som ytterligare fält för att skapa mer personligt anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Constant Contact, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Constant Contact uppfyller alla eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
