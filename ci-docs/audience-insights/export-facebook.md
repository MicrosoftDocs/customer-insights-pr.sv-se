---
title: Exportera Customer Insights-data till Facebook Ads Manager
description: Lär dig hur du konfigurerar anslutningen och exporterar till Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976064"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Exportera segmentlistan till Facebook Ads Manager (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Facebook Ads Manager för att skapa kampanjer på Facebook och Instagram.

## <a name="prerequisites-for-connection"></a>Krav för anslutning

- Du måste ha ett [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som inkluderar ett [**Facebook företagskonto**](https://business.facebook.com/).
- Du måste vara en administratör på [**Facebook Ad-kontot**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 10 miljoner kundprofiler per export till annonshanteraren för Facebook.
- Export till annonshanteraren för Facebook är begränsad till segment.
- Skapa eller uppdatera anpassade målgrupper endast i Facebook av typen *kundlista*.
- Det kan ta upp till 90 minuter att exportera segment med totalt 10 miljoner profiler.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfigurera anslutning till Facebook Ads Manager

Innan användarna kan skapa en export måste en administratör konfigurera anslutningen till tjänsten och tillåta deltagare att använda anslutningen.

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Facebook Ads Manager** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet **Administratörer**. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentisera med Facebook Ads: 

   1. Välj **Fortsätt med Facebook** för att logga in på ditt Facebook annonskonto.

   1. Bevilja **ads_management**-behörighet efter autentisering med Facebook.

   1. Välj det **Facebook Ads-konto** som du vill arbeta med.

   1. Välj en **befintlig anpassad publik** i listrutan eller skapa en **ny anpassad publik**. Mer information finns i [**målgrupper i Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Du kan bara skapa eller uppdatera anpassade målgrupper på Facebook av typen *kundlista* med den här exporten. I vissa fall visas anpassade målgrupper av olika typer i listrutan. Om du väljer en annan typ än *kundlistan* misslyckas exporten. 

1. Granska **Datasekretess och överensstämmelse** och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**. 

1. I **Anslutning för export**, välj en anslutning från avsnittet **Facebook Ads Manager**. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. I fältet **Välj din nyckelidentifierare**, välj **E-post**, **Namn och adress** eller **Telefon** som ska skickas till Facebook Ads Manager. 

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.

1. Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.
   > [TIPS] De bästa chanserna för en matchning uppstår om du väljer **E-post** som nyckelidentifierare. Om du lägger till ytterligare identifierare kan matchningen förbättras.

1. Välj **Lägg till attribut** för att mappa fler attribut som ska skickas till Facebook Ads Manager. Attribut från Facebook Ads Manager mappar till följande användarvänliga namn: **FN** = **förnamn**, **LN** = **efternamn**, **FI** = **första initial**, **PHONE** = **telefon**, **GEN** = **kön**, **DOB** = **födelsedatum**, **ST** = **ort**, **CT** = **City**, **ZIP** = **postnummer**, **COUNTRY** = **land/region**

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Facebook Ads Manager tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Facebook Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
