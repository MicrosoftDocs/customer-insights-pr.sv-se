---
title: Exportera Customer Insights-data till SFTP-värdar
description: Lär dig hur du konfigurerar anslutningen till en SFTP-värd.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643525"
---
# <a name="connector-for-sftp-preview"></a>Koppling för SFTP (förhandsversion)

Du kan använda dina kunddata i program från tredje part genom att exportera dem till en SFTP-värd (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Förutsättningar

- En SFTP-värd och motsvarande autentiseringsuppgifter är tillgängliga.

## <a name="connect-to-sftp"></a>Anslut till SFTP

1. Gå till **Administratör** > **Exportera mål**.

1. Under **SFTP**, välj **Inställning**.

1. Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.

1. Ange **Användarnamn**, **Lösenord** och **Värdnamn** för ditt SFTP-konto. Exempel: Om din SFTP-servers rotmapp är /root/folder och du vill att data ska exporteras till /root/folder/ci_export_destination_folder bör värden vara sftp://<server_address>/ci_export_destination_folder".

1. Välj **Verifiera** för att testa anslutningen.

1. När du har verifierat den kan du välja om du vill exportera dina data som **komprimerad** eller **uppackad** och välja **fältavgränsare** för de exporterade filerna.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Nästa** du vill börja konfigurera exporten.

## <a name="configure-the-connection"></a>Konfigurera anslutningen

1. Välj **kundattributen** som ska exporteras. Du kan exportera ett eller flera attribut.

1. Välj **Nästa**.

1. Välj de segment som du vill exportera.

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
