---
title: Tillägget för kundkort i Dynamics 365-appar
description: Visa data från målinsikter i Dynamics 365-appar med det här tillägget.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0f6c922104df229980b308136a4d764938121b35d6d744f41b1530bdb5515e7f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033010"
---
# <a name="customer-card-add-in-preview"></a>Tillägget för kundkort (förhandsversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Få en 360-graders vy över dina kunder direkt i Dynamics 365-appar. Med kundkortstillägget installerat i en Dynamics 365-app som stöds kan du välja att visa demografi, insikter och aktivitetstid. Tillägget hämtar data från Customer Insights utan att det påverkar data i den anslutna Dynamics 365-appen. 

## <a name="prerequisites"></a>Förutsättningar

- Tillägget fungerar bara med Dynamics 365 modellbaserade appar, till exempel Sales eller kundtjänst, version 9.0 och senare.
- För att dina Dynamics 365-data ska mappas till målinsikternas kundprofiler måste de [tas in i appen Dynamics 365 med hjälp av kopplingen Microsoft Dataverse](connect-power-query.md).
- Alla Dynamics 365-användare av tillägget kundkort måste [läggas till som användare](permissions.md) målinsikter för att kunna se dessa data.
- [Konfigurerade sök- och filterfunktioner](search-filter-index.md) i målinsikter krävs för att slå upp data som ska fungera.
- För varje tilläggskontroll används specifika data målinsikter:
  - Måttkontroll: Kräver [konfigurerade åtgärder](measures.md).
  - Intelligent kontroll: Kräver data som genereras med hjälp av [prediktioner](predictions.md) eller [anpassade modeller](custom-models.md).
  - Demografisk kontroll: Demografiska fält (till exempel ålder eller kön) är tillgängliga i den enhetliga kundprofilen.
  - Berikningskontroll: kräver aktiva [berikningar](enrichment-hub.md) som tillämpas på kundprofiler.
  - Tidslinjekontroll: Kräver [konfigurerade aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installera tillägget för kundkort

Kundkort-tillägget är en lösning för Customer Engagement-appar i Dynamics 365. Om du vill installera lösningen går du till AppSource och söker efter **Dynamics kundkort**. Välj [Tillägget för kundkort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) och välj **Skaffa det nu**.

Du kan behöva logga in med administratörsautentiseringsuppgifter för Dynamics 365-appen för att installera lösningen.

Det kan ta en stund innan lösningen har installerats i din miljö.

## <a name="configure-the-customer-card-add-in"></a>Konfigurera tillägget för kundkortet

1. Som administratör går du till avsnittet **Inställningar** i Dynamics 365 och väljer **lösningar**.

1. Markera länken **visningsnamn** för lösningen **Dynamics 365 Customer Insights tillägg för kundkort (förhandsversion)**.

   > [!div class="mx-imgBorder"]
   > ![Välj visningsnamn.](media/select-display-name.png "Välj visningsnamn")

1. Välj **Logga in** och ange autentiseringsuppgifterna för administratörskontot som du använder för att konfigurera Customer Insights.

   > [!NOTE]
   > Kontrollera att webbläsarens popup-blockerare inte blockerar verifieringsfönstret när du klickar på knappen **Logga in**.

1. Välj vilken Customer Insights-miljön du vill hämta data från.

1. Definiera fältmappningen till poster i Dynamics 365-appen. Beroende på dina data i Customer Insights kan du välja att mappa följande alternativ:
   - Om du vill mappa med en kontakt markerar du fältet i entiteten Kund som matchar ID för din kontaktentitet.
   - Om du vill mappa med ett konto markerar du fältet i entiteten Kund som matchar ID för din kontoentitet.

   > [!div class="mx-imgBorder"]
   > ![Fältet kontakt-ID.](media/contact-id-field.png "Fältet kontakt-ID")

1. Välj **Spara konfiguration** för att spara inställningen.

1. Härnäst måste du tilldela säkerhetsroller i Dynamics 365 så att användarna kan anpassa och se kundkortet. I Dynamics 365 går du till **Inställningar** > **Säkerhet** > **Användare**. Markera användarna som du vill redigera användarroller för och välj **hantera roller**.

1. Tilldela rollen **Anpassare av Customer Insights-kort** för användare som ska anpassa innehållet som visas på kortet för hela organisationen.

## <a name="add-customer-card-controls-to-forms"></a>Lägga till Kundkortskontroller i formulär
  
1. Om du vill lägga till kundkortskontrollerna i kontaktformuläret går du till **inställningar** > **anpassningar** i Dynamics 365.

1. Välj **Anpassa systemet**

1. Bläddra till entiteten **kontakt**, expandera den och välj sedan **formulär**.

1. Välj det kontaktformulär där du vill lägga till kundkortskontrollerna.

    > [!div class="mx-imgBorder"]
    > ![Välj kontaktformuläret.](media/contact-active-forms.png "Välj kontaktformulär")

1. Om du vill lägga en kontroll för formulärredigerare drar du ett fält från **fältutforskaren** till den plats där du vill att den visas.

1. Markera det fält på formuläret som du just har lagt till och välj **Ändra egenskaper**.

1. Gå till fliken **Kontroller** och välj **Lägg till kontroll**. Välj en av de tillgängliga anpassade kontrollerna och välj **Lägg till**.

1. I dialogrutan **Fältegenskaper** avmarkera kryssrutan **Visa etiketten i formuläret**.

1. Välj alternativet **webb** för kontrollen. För berikningskontrollen väljer du vilken typ av berikning du vill visa genom att konfigurera fältet **enrichmentType**. Lägg till en separat berikningskontroll för varje berikningstyp.

1. Klicka på **Spara** och **Publicera** om du vill publicera det uppdaterade kontaktformuläret.

1. Gå till det publicerade kontaktformuläret. Den nyligen tillagda kontrollen visas. Du kan behöva logga in första gången du använder den.

1. Du kan anpassa vad som ska visas på den anpassade kontrollen genom att klicka på knappen Redigera i det övre högra hörnet.

## <a name="upgrade-customer-card-add-in"></a>Uppgradera tillägget för kundkort
Kundkortstillägget uppgraderas inte automatiskt. Uppgradera till den senaste versionen genom att följa stegen i appen Dynamics 365 som har tillägget installerat.

1. I appen Dynamics 365 går du till **Inställningar** > **Anpassning** och väljer **Lösningar**.

1. I tabellen med tillägg söker du efter **CustomerInsightsCustomerCard** och väljer raden.

1. Välj **Tillämpa lösningsuppgradering** i åtgärdsfältet.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Uppgradera lösningen i området Anpassning i Dynamics 365-appar.":::

1. När du har startat uppgraderingsprocessen visas en inläsningssymbol tills uppgraderingen är klar. Om det inte finns någon senare version visas ett felmeddelande för uppgraderingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
