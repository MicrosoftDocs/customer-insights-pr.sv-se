---
title: Exportera Customer Insights-data till Marketo
description: Lär dig hur du konfigurerar anslutningen till Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570425"
---
# <a name="connector-for-marketo-preview"></a>Anslutningsprogram för Marketo (förhandsversion)

Exportera segment av enhetliga kundprofiler för att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Marketo.

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [Marketo-konto](https://login.marketo.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga listor i Marketo och motsvarande ID. Mer information finns på [Marketo-listor](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Du har [konfigurerat segment](segments.md).
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="connect-to-marketo"></a>Ansluta till Marketo

1. Gå till **Administratör** > **Exportera mål**.

1. Under **Marketo** väljer du **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

1. Ange ditt **[klient-ID för Marketo, din klienthemlighet och slutpunktsvärdnamnet för REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Ange ditt **[ID för Marketo-lista](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Välj **Jag godkänner** för att bekräfta **datasekretess och regelefterlevnad** och välj **Anslut** för att initiera anslutningen till Marketo.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportera skärmbild för Marketo-anslutning":::

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. 

1. Alternativt kan du exportera **Förnamn**, **Efternamn**, **Ort**, **Delstat** och **Land/region** som ytterligare fält för att skapa mer personligt anpassade e-postmeddelanden. Välj **Lägg till attribut** för att mappa dessa fält.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Välj fält och segment som ska exporteras till Marketo":::

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab). I Marketo kan du nu hitta dina segment under [Marketo-listor](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 000 000 profiler per export till Marketo.
- Export till Marketo är begränsad till segment.
- Det kan ta upp till 3 timmar att exportera segment med totalt 1 000 000 profiler. 
- Antalet profiler som du kan exportera till Marketo är beroende av och begränsat enligt ditt kontrakt med Marketo.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Marketo tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Marketo uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.
