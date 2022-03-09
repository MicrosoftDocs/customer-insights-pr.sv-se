---
title: Systemkonfiguration i målgruppsinsikter
description: Läs om systeminställningar för funktionen målgruppsinsikter i Dynamics 365 Customer Insights.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2c52f7b8a7d41ae4a985745c7b79bbc62f59bb5a
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354255"
---
# <a name="system-configuration"></a>Systemkonfiguration

För att komma åt systemkonfigurationer i målgruppsinsikter, välj i det vänstra navigeringsfältet **Admin** > **System** för att se en lista över systemuppgifter och processer.

På sidan **System** finns följande flikar:
- [Status](#status-tab)
- [Schemalägg](#schedule-tab)
- [API-användning](#api-usage-tab)
- [Om](#about-tab)
- [Allmänt](#general-tab)
- [Säkerhet](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Inställningsflikar på systemsidan.":::

## <a name="status-tab"></a>Fliken status

På fliken **Status** kan du spåra allt som har med uppgifter, dataexporter och flera andra viktiga produktprocesser att göra. Granska informationen på den här fliken för att säkerställa att dina aktiva uppgifter och processer är fullständiga.

Den här fliken innehåller tabeller med status och bearbetningsinformation för olika processer. I varje tabell spåras **namnet** på uppgiften och tillhörande entitet, **statusen** för dess senaste körning och när den **senast uppdaterades**. Du kan visa information om de senaste flera körningarna genom att välja uppgifts- eller processnamnet. 

Välj status bredvid uppgiften eller kolumnen **Status** för att öppna rutan **Förloppsinformation**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Informationsfönstret Systemförlopp":::

### <a name="status-definitions"></a>Statusdefinitioner

I systemet används följande statusar för uppgifter och processer:

|Status  |Definition  |
|---------|---------|
|Annullerad |Bearbetningen avbröts av användaren innan den slutfördes.   |
|Misslyckad   |Datahämtning har stött på fel.         |
|Misslyckades  |Bearbetningen misslyckades.  |
|Inte startat   |Datakällan har inga inmatade data än eller är fortfarande i utkastläge.         |
|Bearbetas  |Uppgift eller process pågår.  |
|Uppdaterar    |Datainmatning pågår. Du kan avbryta åtgärden genom att välja **Avbryt uppdatering** i kolumnen **åtgärder**. Om du stoppar uppdateringen av en datakälla återställs den till dess senaste uppdateringstillstånd.       |
|Hoppades över  |Uppgift eller process har hoppats över. En eller flera processer längre fram som denna uppgift är beroende av fallerar eller hoppas över.|
|Klart  |Uppgiften eller förloppet har slutförts. För datakällor anger du att data har tagits bort om en tid anges i kolumnen **Uppdaterad**.|
|I kö | Bearbetningen köas och startar när alla uppgifter och processer har slutförts. Mer information, se [uppdatera förlopp](#refresh-processes).|

### <a name="refresh-processes"></a>Uppdatera förlopp

Uppdatering för uppgifter och processer körs enligt det [konfigurerade schemat](#schedule-tab). 

|Bearbeta  |Beskrivning  |
|---------|---------|
|Aktivitet  |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. Insikter beror på behandlingen.|
|Analyskoppling |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Analysförberedelse |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Dataförberedelse   |Är beroende av sammanslagning.   |
|Datakällor   |Är inte beroende av någon annan process. Matchningen beror på att processen har slutförts.  |
|Berikningar   |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. |
|Exporterar mål |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Insikter |Körs manuellt (engångsuppdatering). Är beroende av segment.  |
|Intelligens   |Är beroende av sammanslagning.   |
|Matchning |Är beroende av behandlingen av datakällor som används i matchningsdefinitionen.      |
|Mått  |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen.  |
|Sammanslå   |Beror på att matchningsprocessen har slutförts. Segment, mått, berikning, sökning, aktiviteter, prediktion och dataförberedelse är beroende av att processen har slutförts.   |
|Profiler   |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. |
|Search   |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. |
|Segment  |Körs manuellt (engångsuppdatering). Beror på sammanfogningsprocessen. Insikter beror på behandlingen.|
|System   |Beror på att matchningsprocessen har slutförts. Segment, mått, berikning, sökning, aktiviteter, prediktion och dataförberedelse är beroende av att processen har slutförts.   |
|Användare  |Körs manuellt (engångsuppdatering). Beroende av entiteter.  |

Markera status för en process om du vill visa förloppsinformationen för hela jobbet som den fanns i. Uppdateringsprocesserna ovan kan hjälpa dig att förstå vad du kan göra för att ta itu med en **Hoppades över** eller **Köad** uppgift eller process.

## <a name="schedule-tab"></a>Fliken Schemalägg

Använd fliken **Schema** för att schemalägga automatiska uppdateringar av alla dina [inmatade datakällor](data-sources.md). Automatiska uppdateringar hjälper till att se till att uppdateringarna från dina datakällor återspeglas i dina enhetliga kundprofiler.

> [!NOTE]
> Datakällor som hanteras av dig uppdateras enligt egna scheman. Om du vill schemalägga uppdatering av datakällor som hanteras av dig konfigurerar du uppdateringsinställningarna för den specifika datakällan från sidan **Datakällor**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Inställningar för dataflödesuppdatering":::

1. I målgruppsinsikter går du till **Admin** > **System** och väljer fliken **Schema**.

2. Standardtillståndet för den schemalagda uppdateringen är **av**. För att aktivera schemalagda uppdateringar, ändra växlingsknappen överst på skärmen till **På**.

3. Välj mellan **veckovis** (standard) och **daglig** uppdatering. Om du vill schemalägga en ny veckovis uppdatering väljer du en eller flera dagar då du vill att uppdateringen ska utföras.

4. Ange din **Tidszon** och använd sedan listrutan **Tid** för att ange uppdateringstiden. När du är klar väljer du **Ange**. Om du vill schemalägga flera uppdateringar under en och samma dag väljer du **Lägg till en annan tid**.

5. Välj **Spara** för att införa ändringarna.

## <a name="about-tab"></a>Fliken Om

Fliken **Om** innehåller organisationens **Visningsnamn**, aktivt **Miljö-ID**, **Region** och **Sessions-ID**. Om du har mer än en arbetsmiljö bör du ge var och en ett lätt identifierbart visningsnamn.

## <a name="general-tab"></a>Fliken Allmänt

Du kan ändra språk och land/region-format på fliken **Allmänt**.

Customer Insights [har stöd för många språk](/dynamics365/get-started/availability). Appen använder din språkinställning för att visa element som menyn, etikettext och systemmeddelanden på det språk du föredrar.

Importerade data och information som du har angett manuellt översätts inte.

### <a name="update-the-settings"></a>Uppdatera inställningarna

Om du vill ändra önskat språk väljer du ett **språk** i listrutan.

Om du vill ändra förvald formatering för datum, tid och tal använder du listrutan **Land/region-format**. En förhandsgranskning av formatering visas under det här fältet. Systemet kommer automatiskt att föreslå ett urval när du väljer ett nytt språk.

Välj **Spara** och bekräfta dina val.

## <a name="api-usage-tab"></a>Fliken API-användning

Hitta information om API-användningen i realtid och se vilka händelser som har inträffat i en viss tidsram. Du väljer tidsram i listrutan **Välj en tidsram**. 

**API-användningen** innehåller tre avsnitt: 
- **API-anrop** – ett diagram som visualiserar det sammanlagda antalet anrop till API:et inom den valda tidsramen.

- **Dataöverföring** – ett diagram som visar mängden data som överfördes via API:et i den valda tidsramen.

-  **Åtgärder** – en tabell med rader för varje tillgänglig API-åtgärd och information om hur åtgärderna används. Du kan välja ett åtgärdsnamn för att gå till [API-referensen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Åtgärder som använder [datainmatning i realtid](real-time-data-ingestion.md) innehåller en knapp med en kikarsymbol för att visa API-användning i realtid. Välj knappen för att öppna en sidoruta som innehåller användningsdetaljer för API-användningen i realtid i den aktuella miljön.   
   Använd rutan **Gruppera efter** i fönstret **API-användning i realtid** för att välja hur realtidsinteraktioner bäst ska presenteras. Du kan gruppera data efter API-metod, kvalificerade namn för entiteter (upptagen entitet), skapade av (händelsens källa), resultat (lyckade eller misslyckade) eller felkoder. Informationen är tillgänglig som ett historikdiagram och som en tabell.

## <a name="security-tab"></a>Fliken Säkerhet

På fliken **Säkerhet** kan du länka och hantera ditt eget [Azure Key Vault](/azure/key-vault/general/basic-concepts) till miljön.
Dedikerade nyckelvalv kan användas för att arrangera och använda hemligheter i en organisations efterlevnadsgräns. Målgruppsinsikter kan använda hemligheterna i Azure Key Vault för att [konfigurera anslutningar](connections.md) till system från tredje part.

Mer information finns i [Använd ditt eget Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
