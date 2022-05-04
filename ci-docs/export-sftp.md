---
title: Exportera Customer Insights-data till SFTP-värd (innehåller video)
description: Lär dig hur du konfigurerar anslutningen och exporterar till SFTP-plats.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5170ec4ca35ad2a94f02e9d696c44a32da888120
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647637"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Exportera segment och annan data till SFTP (förhandsversion)

Använd kunddata i program från tredje part genom att exportera dem till en SFTP-plats (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Krav för anslutning

- Tillgänglighet för en STP-värd och motsvarande autentiseringsuppgifter.

## <a name="known-limitations"></a>Kända begränsningar

- SFTP-destinationer bakom brandväggar stöds för närvarande inte. 
- Hur länge en export körs beror på systemprestanda. Vi rekommenderar två processorkärnor och 1 Gb minne som minimal konfiguration av servern. 
- Det kan ta 90 minuter att exportera entiteter med upp till 100 miljoner kundprofiler om du använder den rekommenderade minimikonfigurationen på två processorkärnor och 1 Gb minne. 

## <a name="set-up-connection-to-sftp"></a>Konfigurera anslutningar till SFTP

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **SFTP** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Tillhandahåll **Användarnamn**, **Lösenord**, **Värdnamn** och **Exportmapp** för ditt SFTP-konto.

1. Välj **Verifiera** för att testa anslutningen.

1. Välj om du vill exportera dina data **Komprimerad** eller **Uppackad** och **fältavgränsaren** för de exporterade filerna.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet SFTP. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. Markera de entiteter, till exempel segment, som du vill exportera.

   > [!NOTE]
   > Varje vald entitet delas upp i upp till fem utdatafiler när de exporteras. 

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
