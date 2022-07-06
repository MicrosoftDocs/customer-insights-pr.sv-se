---
title: Exportera segment till LiveRamp (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3e30a16dcb276fa6c951ad0b42ed0a4792f87ce3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050785"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportera segment till LiveRamp&reg; (förhandsgranskning)

Aktivera dina data i LiveRamp för att ansluta till över 500 plattformar på digitala, sociala och TV. Arbeta med dina data i LiveRamp om du vill rikta, undertrycka och anpassa AD-kampanjer.

## <a name="prerequisites-for-a-connection"></a>Krav för anslutning

- Du måste ha en LiveRamp-prenumeration om du vill använda den här anslutningen.
- Om du vill få en prenumeration [kontaktar du LiveRamp](https://liveramp.com/contact/) direkt. [Läs mer om LiveRamp-registrering](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Konfigurera anslutningen LiveRamp

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **LiveRamp** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange ett **användarnamn** och **lösenord** för ditt LiveRamp-skyddade FTP-konto (SFTP).
Autentiseringsuppgifterna kan skilja sig från dina autentiseringsuppgifter för LiveRamp.

1. Välj **kontrollera** för att testa anslutningen till LiveRamp.

1. När du har verifierat klart anger du ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till destination**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet LiveRamp. Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.

1. I fältet **Välj din nyckelidentifierare** välj **E-post**,  **Namn och adress** eller **Telefon** att skicka till LiveRamp för identitetsmatchning.
   > [!div class="mx-imgBorder"]
   > ![LiveRamp-anslutningsprogram med attributmappning.](media/export-liveramp-segments.png "LiveRamp-koppling med attributmappning")

1. Mappa motsvarande attribut från entiteten *Kund* för den valda nyckel-ID:t.

1. Välj **Lägg till attribut** för att mappa fler attribut som ska skickas till LiveRamp.

   > [!TIP]
   > Om du skickar fler attribut för nyckelidentifierare till LiveRamp får du troligen en högre matchningsfrekvens.

1. Markera de segment du vill exportera till LiveRamp.

1. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Liveramp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Liveramp uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.

[!INCLUDE [footer-include](includes/footer-banner.md)]