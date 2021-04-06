---
title: Exportera Customer Insights-data till Mailchimp
description: Lär dig hur du konfigurerar anslutningen till Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598223"
---
# <a name="connector-for-mailchimp-preview"></a>Anslutningsprogram för Mailchimp (förhandsversion)

Exportera segment av enhetliga kundprofiler till Mailchimp för att skapa nyhetsbrev och e-postkampanjer.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Mailchimp-konto](https://mailchimp.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga målgrupper i Mailchimp och motsvarande ID. Mer information finns i [Målgrupper för Mailchimp](https://mailchimp.com/help/create-audience/).
-   Du har [konfigurerat segment](segments.md)
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="connect-to-mailchimp"></a>Anslut till Mailchimp

1. Gå till **Administratör** > **Exportera mål**.

1. Under **Mailchimp** väljer du **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Ange ditt **[målgrupps-ID för Mailchimp](https://mailchimp.com/help/find-audience-id/)** och välj **Anslut** för att initiera anslutningen till Mailchimp.

1. Välj **Autentisera med Mailchimp** och ange dina Mailchimp-autentiseringsuppgifter.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportera skärmbild för Mailchimp-anslutning":::

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. 

1. Alternativt kan du exportera **Förnamn** och **Efternamn** som ytterligare fält för att skapa mer personligt anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Välj fält och segment som ska exporteras till Mailchimp":::

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab). I Mailchimp kan du nu hitta dina segment under [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 000 000 profiler per export till Mailchimp.
- Export till Mailchimp är begränsad till segment.
- Export av segment med totalt 1 000 000 profiler kan ta upp till 3 timmar på grund av begränsningar på leverantörens sida. 
- Antalet profiler som du kan exportera till Mailchimp är beroende av och begränsat enligt ditt kontrakt med Mailchimp.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Mailchimp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Mailchimp uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]