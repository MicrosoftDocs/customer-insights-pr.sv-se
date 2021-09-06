---
title: Exportera Customer Insights-data till Sendinblue
description: Lär dig hur du konfigurerar anslutningen och exporterar till Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036077"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportera segment till Sendinblue (förhandsversion)

Exportera segment från enhetliga kundprofiler i syfte att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Sendinblue.

## <a name="prerequisites-for-connection"></a>Krav för anslutning

-   Du har ett [Sendinblue-konto](https://www.sendinblue.com/) och motsvarande autentiseringsuppgifter för administratör.
-   Det finns befintliga listor i Sendinblue och motsvarande ID.
-   Du har [konfigurerat segment](segments.md).
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 miljoner profiler per export till Sendinblue.
- Exporten till Sendinblue är begränsad till segment.
- Det kan ta upp till 90 minuter att exportera segment med totalt 1 miljoner profiler. 
- Antalet profiler du kan exportera till Sendinblue beror på och begränsas efter ditt kontrakt med Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Konfigurera anslutning till Sendinblue

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Sendinblue** om du vill konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange din **[SendinBlue API-nyckel](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Välj **Jag godkänner** för att bekräfta **Datasekretess och efterlevnad** och välj **Anslut** för att initiera anslutningen till Sendinblue.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet Sendinblue. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Ange ditt **List-ID för Sendinblue** 

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. 

1. Alternativt kan du exportera **Förnamn**, **Efternamn** och **Telefonnummer** om du vill skapa mer anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till Sendinblue tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Sendinblue uppfyller dina eventuella sekretess- och säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
