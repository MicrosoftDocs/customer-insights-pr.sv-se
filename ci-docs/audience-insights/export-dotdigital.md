---
title: Exportera Customer Insights-data till DotDigital
description: Lär dig hur du konfigurerar anslutningen till DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598039"
---
# <a name="connector-for-dotdigital-preview"></a>Anslutningsprogram för DotDigital (förhandsversion)

Exportera segment med enhetliga kundprofiler till DotDigital-adressböcker och använd dem för kampanjer, skicka marknadsföring via e-post och skapa kundsegment med DotDigital. 

## <a name="prerequisites"></a>Förutsättningar

-   Du har ett [DotDigital-konto](https://dotdigital.com/) och motsvarande administratörsautentiseringsuppgifter.
-   Det finns befintliga adressböcker i DotDigital och motsvarande ID. ID hittar du i URL-adressen när du väljer och öppnar en adressbok. Mer information finns i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Du har [konfigurerade segment](segments.md) i målgruppsinsikter.
-   Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.

## <a name="connect-to-dotdigital"></a>Ansluta till DotDigital

1. Gå till **Administratör** > **Exportera mål**.

1. Under **DotDigita** väljer du **Konfigurera**.

1. Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurationsfönster för DotDigital-export.":::

1. Ange ditt **användarnamn och lösenord för DotDigital**.

1. Ange ditt **[ID till DotDigital-adressboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.

1. Välj **Anslut** om du vill initiera anslutningen till DotDigital.

1. Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.

1. Välj **Nästa** du vill konfigurera exporten.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress. Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Fullständigt namn**, **Kön** och **Postnummer**.

1. Välj de segment som du vill exportera. Du kan exportera upp till totalt 1 000 000 kundprofiler till DotDigital.

1. Välj **Spara**.

## <a name="export-the-data"></a>Exportera data

Du kan [Exportera data på begäran](export-destinations.md). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab). I DotDigital kan du nu hitta segment i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Kända begränsningar

- Upp till 1 000 000 profiler per export till DotDigital.
- Export till DotDigital är begränsad till segment.
- Export av segment med totalt 1 000 000 profiler kan ta upp till 3 timmar på grund av begränsningar på leverantörens sida. 
- Antalet profiler som du kan exportera till DotDigital är beroende av och begränsat enligt ditt kontrakt med DotDigital.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till DotDigital tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att DotDigital uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]