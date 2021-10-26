---
title: Exportera Customer Insights-data till Mailchimp
description: Lär dig hur du konfigurerar anslutningen och exporterar till Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 94a9fead56ce8c40b35d4eb41ebdc0d672798dce
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618636"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportera segment till Mailchimp (förhandsversion)

Exportera segment av enhetliga kundprofiler till Mailchimp för att skapa nyhetsbrev och e-postkampanjer.

## <a name="prerequisites-for-connection"></a>Krav för anslutning

-   Du har ett [Mailchimp-konto](https://mailchimp.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga målgrupper i Mailchimp och motsvarande ID. Mer information finns i [Målgrupper för Mailchimp](https://mailchimp.com/help/create-audience/).
-   Du har [konfigurerat segment](segments.md)
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljoner kundprofiler per export till Mailchimp.
- Export till Mailchimp är begränsad till segment.
- Det kan ta upp till tre timmar att exportera segment med en miljoner kundprofiler. 
- Hur många kundprofiler du kan exportera till Mailchimp är beroende av och begränsas av ditt kontrakt med Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Konfigurera anslutningen Mailchimp

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Mailchimp** om du vill konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Mailchimp.

1. Välj **Autentisera med Mailchimp** och ange dina Mailchimp-autentiseringsuppgifter.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen. 

## <a name="configure-the-connector"></a>Konfigurera kopplingen

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data**> **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Mailchimp. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange din **[Målgrupps-ID för Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. I avsnittet **Datamatchning** går du till fältet **E-post** och markerar fältet som representerar en kunds e-postadress. 

1. Alternativt kan du exportera **Förnamn** och **Efternamn** för att skapa mer anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till Mailchimp.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Mailchimp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Mailchimp uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
