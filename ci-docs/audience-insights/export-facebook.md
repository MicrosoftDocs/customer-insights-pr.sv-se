---
title: Exportera Customer Insights-data till Facebook Ads Manager
description: Lär dig hur du konfigurerar anslutningen till Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596705"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Koppling för Facebook Ads Manager (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Facebook Ads Manager för att skapa kampanjer på Facebook och Instagram.

## <a name="prerequisites"></a>Förutsättningar

- Du måste ha ett [**Facebook Ad-konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) med ett [**Facebook Business-konto**](https://business.facebook.com/).
- Du måste vara en administratör på [**Facebook Ad-kontot**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Ansluta till Facebook Ads Manager

1. Gå till **Administratör** > **Exportera mål**.

1. Under **Facebook Ads Manager**, välj **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

1. Välj **Fortsätt med Facebook** för att logga in på ditt Facebook annonskonto.

1. Bevilja **ads_management**-behörighet efter autentisering med Facebook.

1. Välj det **Facebook Ads-konto** som du vill arbeta med.

1. Välj en **befintlig anpassad publik** i listrutan eller skapa en **ny anpassad publik**. Mer information finns i [**målgrupper i Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I fältet **Välj din nyckelidentifierare**, välj **E-post**, **Namn och adress** eller **Telefon** som ska skickas till Facebook Ads Manager.

1. Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.
   > [TIPS] De bästa chanserna för en matchning uppstår om du väljer **E-post** som nyckelidentifierare. Om du lägger till ytterligare identifierare kan matchningen förbättras.

1. Välj **Lägg till** om du vill mappa ytterligare attribut att skicka till Facebook Ads Manager. Attribut från Facebook Ads Manager mappar till följande användarvänliga namn: **FN** = **förnamn**, **LN** = **efternamn**, **FI** = **första initial**, **PHONE** = **telefon**, **GEN** = **kön**, **DOB** = **födelsedatum**, **ST** = **ort**, **CT** = **City**, **ZIP** = **postnummer**, **COUNTRY** = **land/region**

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 10 miljoner kundprofiler per export till annonshanteraren för Facebook 
- Export till annonshanteraren för Facebook är begränsad till segment
- Det kan ta upp till 90 minuter att exportera segment med totalt 10 miljoner profiler

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Facebook Ads Manager tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Facebook Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]