---
title: Tillägget för kundkort för Dynamics 365-appar (innehåll video)
description: Visa data från målinsikter i Dynamics 365-appar med det här tillägget.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: d67d8e2cb30cf20de204bfb293bb8ce81c7bb2f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353887"
---
# <a name="customer-card-add-in-preview"></a>Tillägget för kundkort (förhandsversion)



Få en 360-graders vy över dina kunder direkt i Dynamics 365-appar. Med tillägget Kundkort installerat i en Dynamics 365-app som stöds kan du välja att visa fält för kundprofil, insikter och aktivitetstidstid. Tillägget hämtar data från Customer Insights utan att det påverkar data i den anslutna Dynamics 365-appen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Förutsättningar

- Tillägget fungerar bara med Dynamics 365 modellbaserade appar, till exempel Sales eller kundtjänst, version 9.0 och senare.
- För att dina Dynamics 365-data ska mappas till målinsikternas kundprofiler rekommenderar vi att de [tas in i appen Dynamics 365 med hjälp av kopplingen Microsoft Dataverse](connect-power-query.md). Om du använder en annan metod för att mata in Dynamics 365-kontakter (eller konton), måste du se till att fält `contactid` (eller `accountid`) anges som [primärnyckeln för den datakällan i kartsteget i datasammanslutningsprocessen](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Alla Dynamics 365-användare av tillägget kundkort måste [läggas till som användare](permissions.md) målinsikter för att kunna se dessa data.
- [Konfigurerade sök- och filterfunktioner](search-filter-index.md) i målinsikter krävs för att slå upp data som ska fungera.
- För varje tilläggskontroll används specifika data målinsikter. Vissa data och kontroller är endast tillgängliga i miljöer av specifika typer. Tilläggets konfiguration meddelar dig om en kontroll inte är tillgänglig på grund av den valda miljötypen. Läs mer om [miljöanvändningsfall](work-with-business-accounts.md).
  - **Måttkontroll**: Kräver [konfigurerade mått](measures.md) för typen kundattribut.
  - **Intelligent kontroll**: Kräver data som genereras med hjälp av [prediktioner eller anpassade modeller](predictions-overview.md).
  - **Kontroll för kundinformation**: Alla fält från profilen är tillgängliga i den enhetliga kundprofilen.
  - **Berikningskontroll**: kräver aktiva [berikningar](enrichment-hub.md) som tillämpas på kundprofiler. Korttillägget stöder dessa berikningar: [Varumärken](enrichment-microsoft.md) som tillhandahålls av Microsoft, [Intressen](enrichment-microsoft.md) som tillhandahålls av Microsoft och [Office engagemangsdata](enrichment-office.md) som tillhandahålls av Microsoft.
  - **Kontaktkontroll**: Kräver definition av entitet för utformning av typkontakter.
  - **Tidslinjekontroll**: Kräver [konfigurerade aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installera tillägget för kundkort

Kundkort-tillägget är en lösning för Customer Engagement-appar i Dynamics 365. Om du vill installera lösningen går du till AppSource och söker efter **Dynamics kundkort**. Välj [Tillägget för kundkort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) och välj **Skaffa det nu**.

Du kan behöva logga in med administratörsautentiseringsuppgifter för Dynamics 365-appen för att installera lösningen. Det kan ta en stund innan lösningen har installerats i din miljö.

## <a name="configure-the-customer-card-add-in"></a>Konfigurera tillägget för kundkortet

1. Som administratör går du till avsnittet **Inställningar** i Dynamics 365 och väljer **lösningar**.

1. Markera länken **visningsnamn** för lösningen **Dynamics 365 Customer Insights tillägg för kundkort (förhandsversion)**.

   > [!div class="mx-imgBorder"]
   > ![Välj visningsnamn.](media/select-display-name.png "Välj visningsnamn.")

1. Välj **Logga in** och ange autentiseringsuppgifterna för administratörskontot som du använder för att konfigurera Customer Insights.

   > [!NOTE]
   > Kontrollera att webbläsarens popup-blockerare inte blockerar verifieringsfönstret när du klickar på knappen **Logga in**.

1. Välj vilken Customer Insights-miljön du vill hämta data från.

1. Definiera fältmappningen till poster i Dynamics 365-appen. Beroende på dina data i Customer Insights kan du välja att mappa följande alternativ:
   - Om du vill mappa med en kontakt markerar du fältet i entiteten Kund som matchar ID för din kontaktentitet.
   - Om du vill mappa med ett konto markerar du fältet i entiteten Kund som matchar ID för din kontoentitet.

   > [!div class="mx-imgBorder"]
   > ![Fältet kontakt-ID.](media/contact-id-field.png "Fältet kontakt-ID.")

1. Välj **Spara konfiguration** för att spara inställningen.

1. Härnäst måste du tilldela säkerhetsroller i Dynamics 365 så att användarna kan anpassa och se kundkortet. I Dynamics 365 går du till **Inställningar** > **Säkerhet** > **Användare**. Markera användarna som du vill redigera användarroller för och välj **hantera roller**.

1. Tilldela rollen **Anpassare av Customer Insights-kort** för användare som ska anpassa innehållet som visas på kortet för hela organisationen.

## <a name="add-customer-card-controls-to-forms"></a>Lägga till Kundkortskontroller i formulär

Beroende på ditt scenario kan du välja att lägga till kontroller till antingen **kontaktformuläret** eller **kontoformuläret**. Om din miljö för målgruppsinsikter är för företagskonton rekommenderar vi att du lägger till kontrollerna i kontoformuläret. I så fall ersätter du "kontakt" i stegen nedan med "konto".

1. Om du vill lägga till kundkortskontrollerna i kontaktformuläret går du till **inställningar** > **anpassningar** i Dynamics 365.

1. Välj **Anpassa systemet**

1. Bläddra till entiteten **kontakt**, expandera den och välj sedan **formulär**.

1. Välj det kontaktformulär där du vill lägga till kundkortskontrollerna.

    > [!div class="mx-imgBorder"]
    > ![Välj kontaktformuläret.](media/contact-active-forms.png "Välj kontaktformulär.")

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

## <a name="troubleshooting"></a>Felsökning

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontroller från tillägget Kundkort hittar inga data

**Problem:**

Även med korrekt konfigurerade ID-fält går det inte att hitta data för någon kund med kontrollerna.  

**Lösning:**

1. Se till att du har konfigurerat korttillägget enligt instruktionerna: [Konfigurera tillägget Kundkort](#configure-the-customer-card-add-in) 

1. Granska konfigurationen av datainmatningen. Redigera datakälla för Dynamics 365-systemet som innehåller kontakt-ID GUID. Om kontakt-ID GUID visas med versaler i Power Query-redigeraren gör du följande: 
    1. Redigera datakällan för att öppna datakällan i Power Query-redigeraren.
    1. Välj kolumnen för kontakt-ID.
    1. Välj **Omvandla** i rubrikfältet om du vill visa tillgängliga åtgärder.
    1. Markera **gemener**. Kontrollera att GUID i tabellen nu är i gemener.
    1. Spara datakällan.
    1. Kör datainmatning, förening och nedströmsprocesser för att föra över ändringarna till GUID. 

När den fullständiga uppdateringen har slutförts ska de förväntade data visas i kontrollerna för tillägget Kundkort. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
