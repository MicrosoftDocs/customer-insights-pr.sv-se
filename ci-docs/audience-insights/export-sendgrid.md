---
title: Exportera Customer Insights-data till SendGrid
description: Lär dig hur du konfigurerar anslutningen till SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268754"
---
# <a name="connector-for-sendgrid-preview"></a>Anslutningsprogram för SendGrid (förhandsversion)

Exportera segment med enhetliga kundprofiler till SendGrid-kontaktlistor och använd dem för kampanjer och e-postmarknadsföring i SendGrid. 

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [SendGrid-konto](https://sendgrid.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga kontaktlistor i SendGrid och motsvarande ID. Mer information finns i [SendGrid – Hantera kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="connect-to-sendgrid"></a>Ansluta till SendGrid

1. Gå till **Administratör** > **Exportera mål**.

1. Under **SendGrid** väljer du **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Konfigurationsfönstret för export av SendGrid.":::

1. Ange **SendGrids API-nyckel** [SendGrids API-nyckel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Ange ditt **[ID för SendGrid-lista](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till SendGrid.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Land/region**, **Delstat**, **Stad** och **Postnummer**.

1. Välj de segment som du vill exportera. Vi **rekommenderar starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till SendGrid. 

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 100 000 profiler totalt till SendGrid.
- Export till SendGrid är begränsad till segment.
- Att exportera upp till 100 000 profiler till SendGrid kan ta upp till några timmar att genomföra. 
- Antalet profiler som du kan exportera till SendGrid är beroende av och begränsat enligt ditt kontrakt med SendGrid.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till SendGrid tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att SendGrid uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]