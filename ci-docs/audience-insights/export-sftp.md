---
title: Exportera Customer Insights-data till SFTP-värdar
description: Lär dig hur du konfigurerar anslutningen till en SFTP-värd.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598407"
---
# <a name="connector-for-sftp-preview"></a>Koppling för SFTP (förhandsversion)

Du kan använda dina kunddata i program från tredje part genom att exportera dem till en SFTP-värd (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Förutsättningar

- Tillgänglighet för en STP-värd och motsvarande autentiseringsuppgifter.

## <a name="connect-to-sftp"></a>Anslut till SFTP

1. Gå till **Administratör** > **Exportera mål**.

1. Under **SFTP**, välj **Inställning**.

1. Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.

1. Tillhandahåll **Användarnamn**, **Lösenord**, **Värdnamn** och **Exportmapp** för ditt SFTP-konto.

1. Välj **Verifiera** för att testa anslutningen.

1. Efter verifieringen väljer du om du vill exportera dina data **g-zippade** eller **uppackade** och väljer **fältavgränsare** för de exporterade filerna.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Nästa** du vill börja konfigurera exporten.

## <a name="configure-the-export"></a>Konfigurera exporten

1. Markera de entiteter, till exempel segment, som du vill exportera.

   > [!NOTE]
   > Varje vald entitet kommer att vara upp till fem utdatafiler när de exporteras. 

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).

## <a name="known-limitations"></a>Kända begränsningar

- Hur länge en export körs beror på systemprestanda. Vi rekommenderar två processorkärnor och 1 Gb minne som minimal konfiguration av servern. 
- Det kan ta 90 minuter att exportera entiteter med upp till 100 miljoner kundprofiler om du använder den rekommenderade minimikonfigurationen på två processorkärnor och 1 Gb minne. 

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]