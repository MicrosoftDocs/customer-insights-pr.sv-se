---
title: Exportera Customer Insights-data till Autopilot
description: Lär dig hur du konfigurerar anslutningen till Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269260"
---
# <a name="connector-for-autopilot-preview"></a>Anslutningsprogram för Autopilot (förhandsversion)

Exportera segment med enhetliga kundprofiler till Autopilot och använd dem för e-postmarknadsföring i Autopilot. 

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Autopilot-konto](https://www.autopilothq.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="connect-to-autopilot"></a>Anslut till Autopilot

1. Gå till **Administratör** > **Exportera mål**.

1. Under **Autopilot** väljer du **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurationsfönster för Anslutning till Autopilot.":::

1. Ange **API-nyckeln till Autopilot** [API-nyckel till Autopilot](https://autopilot.docs.apiary.io/#).

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till Autopilot.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**.

1. Välj de segment som du vill exportera. Vi rekommenderar **starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till Autopilot. 

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).

## <a name="known-limitations"></a>Kända begränsningar

- Du kan exportera upp till totalt 100 000 profiler till Autopilot.
- Export till Autopilot är begränsad till segment.
- Att exportera upp till 100 000 profiler till Autopilot kan ta upp till några timmar att genomföra. 
- Antalet profiler som du kan exportera till Autopilot är beroende av och begränsat enligt ditt kontrakt med Autopilot.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Autopilot tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Autopilot uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]