---
title: Exportera segment till Facebook Ads Manager (förhandsgranskning) (innehåller videoklipp)
description: Lär dig hur du konfigurerar anslutningen och exporterar till Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195036"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportera segment till Facebook Ads Manager (förhandsgranskning)

Exportera segment med enhetliga kundprofiler till Facebook Ads Manager för att skapa kampanjer på Facebook och Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Förutsättningar

- En [Facebook Ads-konto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som omfattar ett [Facebook Business-konto](https://business.facebook.com/).
- Administratör privilegier på [Facebook Ads-konto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 10 miljoner kundprofiler per export till Facebook Ads Manager, vilket kan ta upp till 90 minuter.
- Endast segment.
- Facebook *kundlistan* typ i endast [målgrupp](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > I vissa fall visas anpassade målgrupper av olika typer i listrutan. Om du väljer en annan typ än *kundlistan*, misslyckas exporten.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfigurera anslutning till Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Facebook Ads Manager**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. [Tillåt deltagare använda en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentisera med Facebook Ads:

   1. Välj **Fortsätt med Facebook** för att logga in på ditt Facebook Ads-konto.

   1. Bevilja **ads_management**-behörighet efter autentisering med Facebook.

   1. Välj det **Facebook Ads-konto** som du vill arbeta med.

   1. Välj en **befintlig anpassad målgrupp** i listrutan eller skapa en **Ny anpassad målgrupp**.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** välj en anslutning från avsnittet Facebook Ads Manager. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. I fältet **Anslut data**, välj **E-post**, **Namn och adress** eller **Telefon** som ska skickas till Facebook Ads Manager.

1. Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.
   > [!TIP]
   > De bästa chanserna för en matchning uppstår om du väljer **E-postmeddelande** som nyckelidentifierare. Om du lägger till ytterligare identifierare kan matchningen förbättras.

1. Välj **Lägg till attribut** för att mappa fler attribut som ska skickas till Facebook Ads Manager. Attribut från Facebook Ads Manager mappar till följande användarvänliga namn: **FN** = **Förnamn**, **LN** = **Efternamn**, **FI** = **Första initial**, **PHONE** = **Telefon**, **GEN** = **Kön**, **DOB** = **Födelsedatum**, **ST** = **Delstat**, **CT** = **Stat**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/region**

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
