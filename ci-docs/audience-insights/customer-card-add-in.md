---
title: Installera och konfigurera Tillägget för kundkort
description: Installera och konfigurera tillägget kundkort för Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644065"
---
# <a name="customer-card-add-in-preview"></a>Tillägget för kundkort (förhandsversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Få en 360-graders vy över dina kunder direkt i Dynamics 365-appar. Visa tidslinjer för demografiska data och aktiviteter med kundkorttillägget.

## <a name="prerequisites"></a>Förutsättningar

- Dynamics 365-app (t.ex. Försäljningsnav eller Kundtjänstnav) version 9.0 och senare med enhetligt gränssnitt aktiverat.
- Kundprofiler som [matats in från Dynamics 365-appen med Common Data Service](connect-power-query.md).
- Användare av tillägget Kundkort måste [läggas till som användare](permissions.md) i målgruppsinsikter.
- [Konfigurerade sök- och filterfunktioner](search-filter-index.md).
- Demografisk kontroll: Demografiska fält, till exempel ålder eller kön är tillgängliga i den enhetliga kundprofilen.
- Berikningskontroll: kräver aktiva [berikningar](enrichment-hub.md) som tillämpas på kundprofiler.
- Intelligenskontroll: Kräver data som genererats med Azure Machine Learning ([prediktionsmodeller](predictions.md) eller [anpassade modeller](custom-models.md))
- Måttkontroll: Kräver [konfigurerade åtgärder](measures.md).
- Tidslinjekontroll: Kräver [konfigurerade aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installera tillägget för kundkort

Kundkort-tillägget är en lösning för Customer Engagement-appar i Dynamics 365. Om du vill installera lösningen går du till AppSource och söker efter **Dynamics kundkort**. Välj [Tillägget för kundkort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) och välj **Skaffa det nu**.

Du kan behöva logga in med administratörsautentiseringsuppgifter för Dynamics 365-appen för att installera lösningen.

Det kan ta en stund innan lösningen har installerats i din miljö.

## <a name="configure-the-customer-card-add-in"></a>Konfigurera tillägget för kundkortet

1. Som administratör går du till avsnittet **Inställningar** i Dynamics 365 och väljer **lösningar**.

1. Markera länken **visningsnamn** för lösningen **Dynamics 365 Customer Insights tillägg för kundkort (förhandsversion)**.

   > [!div class="mx-imgBorder"]
   > ![Välj visningsnamn](media/select-display-name.png "Välj visningsnamn")

1. Välj **Logga in** och ange autentiseringsuppgifterna för administratörskontot som du använder för att konfigurera Customer Insights.

   > [!NOTE]
   > Kontrollera att webbläsarens popup-blockerare inte blockerar verifieringsfönstret när du klickar på knappen **Logga in**.

1. Välj vilken miljö du vill hämta data från.

1. Definiera fältmappningen till poster i Dynamics 365-appen.
   - Om du vill mappa med en kontakt markerar du fältet i entiteten Kund som matchar ID för din kontaktentitet.
   - Om du vill mappa med ett konto markerar du fältet i entiteten Kund som matchar ID för din kontoentitet.

   > [!div class="mx-imgBorder"]
   > ![Fältet kontakt-ID](media/contact-id-field.png "Fältet kontakt-ID")

1. Välj **Spara konfiguration** för att spara inställningen.

1. Härnäst måste du tilldela säkerhetsroller i Dynamics 365 så att användarna kan anpassa och se kundkortet. I Dynamics 365 går du till **Inställningar** > **Säkerhet** > **Användare**. Markera användarna som du vill redigera användarroller för och välj **hantera roller**.

1. Tilldela rollen **Anpassare av Customer Insights-kort** för användare som ska anpassa innehållet som visas på kortet för hela organisationen.

## <a name="add-customer-card-controls-to-forms"></a>Lägga till Kundkortskontroller i formulär
  
1. Om du vill lägga till kundkortskontrollerna i kontaktformuläret går du till **inställningar** > **anpassningar** i Dynamics 365.

1. Välj **Anpassa systemet**

1. Bläddra till entiteten **kontakt**, expandera den och välj sedan **formulär**.

1. Välj det kontaktformulär där du vill lägga till kundkortskontrollerna.

    > [!div class="mx-imgBorder"]
    > ![Välj kontaktformulär](media/contact-active-forms.png "Välj kontaktformulär")

1. Om du vill lägga en kontroll för formulärredigerare drar du ett fält från **fältutforskaren** till den plats där du vill att den visas.

1. Markera det fält på formuläret som du just har lagt till och välj **Ändra egenskaper**.

1. Gå till fliken **Kontroller** och välj **Lägg till kontroll**. Välj en av de tillgängliga anpassade kontrollerna och välj **Lägg till**.

1. I dialogrutan **Fältegenskaper** avmarkera kryssrutan **Visa etiketten i formuläret**.

1. Välj alternativet **webb** för kontrollen. För berikningskontrollen väljer du vilken typ av berikning du vill visa genom att konfigurera fältet **enrichmentType**. Du måste lägga till en separat berikningskontroll för varje typ av berikning.

1. Klicka på **Spara** och **Publicera** om du vill publicera det uppdaterade kontaktformuläret.

1. Gå till det publicerade kontaktformuläret. Den nyligen tillagda kontrollen visas. Du kan behöva logga in första gången du använder den.

1. Du kan anpassa vad som ska visas på den anpassade kontrollen genom att klicka på knappen Redigera i det övre högra hörnet.