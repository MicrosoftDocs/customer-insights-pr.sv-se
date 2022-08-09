---
title: Exportera SFTP-värd (förhandsversion) (innehåller video)
description: Lär dig hur du konfigurerar anslutningen och exporterar till SFTP-plats.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207251"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exportera till SFTP-värdar (förhandsversion)

Använd kunddata i program från tredje part genom att exportera dem till en SFTP-plats (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Förutsättningar

- Tillgänglighet för en STP-värd och motsvarande autentiseringsuppgifter.

## <a name="known-limitations"></a>Kända begränsningar

- SFTP-destinationer bakom brandväggar stöds för närvarande inte.
- Hur länge en export körs beror på systemprestanda. Vi rekommenderar två processorkärnor och 1 Gb minne som minimal konfiguration av servern.
- Upp till 100 miljoner kundprofiler, vilket kan ta 90 minuter om du använder den rekommenderade minimikonfigurationen på två processorkärnor och 1 Gb minne.
- Om du använder en SSH-nyckel för autentisering ska du se till att du [skapar din privata nyckel](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) som PEM eller SSH.COM format. Om du använder Putty konverterar du din privata nyckel genom att exportera is as Open SSH. Följande privata nyckelformat stöds:
  - RSA i OpenSSL PEM och ssh.com format
  - DSA i OpenSSL PEM och ssh.com format
  - ECDSA 256/384/521 i OpenSSL PEM-format
  - ED25519 och RSA i OpenSSH-nyckelformat

## <a name="set-up-connection-to-sftp"></a>Konfigurera anslutningar till SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **SFTP**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj om du vill autentisera via SSH eller användarnamn/lösenord för anslutningen och ange nödvändig information. Om du använder en SSH-nyckel för autentisering ska du se till att du [skapar din privata nyckel](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) som PEM eller SSH.COM format. Om du använder Putty konverterar du din privata nyckel genom att exportera is as Open SSH. Följande privata nyckelformat stöds:
   - RSA i OpenSSL PEM och ssh.com format
   - DSA i OpenSSL PEM och ssh.com format
   - ECDSA 256/384/521 i OpenSSL PEM-format
   - ED25519 och RSA i OpenSSH-nyckelformat

1. Välj **Verifiera** för att testa anslutningen.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet SFTP. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj om du vill exportera dina data **Komprimerad** eller **Uppackad** och **fältavgränsaren** för de exporterade filerna.

1. Markera de entiteter, till exempel segment, som du vill exportera.

   > [!NOTE]
   > Varje vald entitet delas upp i upp till fem utdatafiler när de exporteras.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Export av entiteter som innehåller en stor mängd data kan leda till flera CSV-filer i samma mapp för varje export. Att dela upp exporter sker av effektivitets skäl för att minimera den tid det tar för en export att slutföras.

[!INCLUDE [footer-include](includes/footer-banner.md)]
