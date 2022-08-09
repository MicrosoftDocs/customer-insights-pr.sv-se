---
title: Exportera segment till LiveRamp (förhandsgranskning)
description: Lär dig hur du konfigurerar anslutningen och exporterar till LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196738"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportera segment till LiveRamp&reg; (förhandsgranskning)

Aktivera dina data i LiveRamp för att ansluta till över 500 plattformar på digitala, sociala och TV. Arbeta med dina data i LiveRamp om du vill rikta, undertrycka och anpassa AD-kampanjer.

## <a name="prerequisites"></a>Förutsättningar

- En LiveRamp-prenumeration om du vill använda den här anslutningen. Om du vill få en prenumeration [kontaktar du LiveRamp](https://liveramp.com/contact/) direkt. [Läs mer om LiveRamp-registrering](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Kända begränsningar

- Vid export av LiveRamp används SFTP-export. SFTP-destinationer bakom brandväggar stöds för närvarande inte.
- Om du använder en SSH-nyckel för autentisering ska du se till att du [skapar din privata nyckel](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) som PEM eller SSH.COM format. Om du använder Putty konverterar du din privata nyckel genom att exportera is as Open SSH. Följande privata nyckelformat stöds:
  - RSA i OpenSSL PEM och ssh.com format
  - DSA i OpenSSL PEM och ssh.com format
  - ECDSA 256/384/521 i OpenSSL PEM-format
  - ED25519 och RSA i OpenSSH-nyckelformat
- Hur länge en export körs beror på systemprestanda. Vi rekommenderar två processorkärnor och 1 Gb minne som minimal konfiguration av servern.
- Det kan ta 90 minuter att exportera entiteter med upp till 100 miljoner kundprofiler om du använder den rekommenderade minimikonfigurationen på två processorkärnor och 1 Gb minne.
- Det faktiska antalet profiler (eller data) du kan exportera till LiveRamp beror på ditt abonnemang med LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Konfigurera anslutningen LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **LiveRamp**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj om du vill autentisera via SSH eller användarnamn/lösenord för anslutningen och ange nödvändig information.

1. Välj **kontrollera** för att testa anslutningen till LiveRamp.

1. Efter en lyckad verifiering granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet LiveRamp. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. I fältet **Anslut data** välj **E-post**,  **Namn och adress** eller **Telefon** att skicka till LiveRamp för identitetsmatchning.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp-anslutningsprogram med attributmappning.":::

1. Mappa motsvarande attribut från entiteten *Kund* för den valda nyckel-ID:t.

1. Välj **Lägg till attribut** för att mappa fler attribut som ska skickas till LiveRamp.

   > [!TIP]
   > Om du skickar fler attribut för nyckelidentifierare till LiveRamp får du troligen en högre matchningsfrekvens.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
