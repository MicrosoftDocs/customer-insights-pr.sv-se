---
title: Exportera Customer Insights-data till AdRoll
description: Lär dig hur du konfigurerar anslutningen till AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697096"
---
# <a name="connector-for-adroll-preview"></a>Anslutningsprogram för AdRoll (förhandsversion)

Exportera segment med enhetliga kundprofiler till AdRoll och använd dem för annonsering. 

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [AdRoll-konto](https://www.adroll.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="connect-to-adroll"></a>Anslut till AdRoll

1. Gå till **Administratör** > **Exportera mål**.

1. Under **AdRoll** väljer du **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurationsfönster för anslutning till AdRoll.":::

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till AdRoll.

1. Välj **Autentisera med AdRoll** och ange dina autentiseringsuppgifter som administratör för AdRoll. 

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Ange ditt **ID som AdRoll-annonsör** [AdRoll-annonsör](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Det krävs för att exportera segment till AdRoll.

1. Välj de segment som du vill exportera. Välj ett segment med minst 100 medlemmar. Det går inte att exportera mindre segment. Dessutom är det maximala värdet för ett segment som ska exporteras 250 000 medlemmar per export. 

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till totalt 250 000 profiler per export till AdRoll.
- Du kan inte exportera segment med färre än 100 profiler till AdRoll. 
- Export till AdRoll är begränsad till segment.
- Det kan ta upp till 10 minuter att exportera upp till 250 000 profiler till AdRoll. 
- Antalet profiler som du kan exportera till AdRoll är beroende av och begränsat enligt ditt kontrakt med AdRoll.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till AdRoll tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att AdRoll uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
