---
title: Använd datakällor för att mata in data
description: Lär dig hur du importerar data från olika källor.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887916"
---
# <a name="data-sources-overview"></a>Översikt över datakällor

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kapaciteten för målgruppsinsikter i Dynamics 365 Customer Insights ansluter till data från en bred uppsättning källor. Anslutning till en datakälla kallas ofta för *datainmatning*. När du har inmatat dina data kan du [ena](data-unification.md) och vidta åtgärder.

## <a name="add-a-data-source"></a>Lägg till en datakälla

Se de detaljerade artiklarna om hur du lägger till en datakälla beroende på vilket alternativ du väljer.

Du kan lägga till en datakälla på tre huvudsakliga sätt:

- [Efter dussintals Power Query-anslutningar](connect-power-query.md)
- [Från en Common Data Model-mapp](connect-common-data-model.md)
- [Från din egen Common Data Service sjö](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Lägga till data lokala datakällor

Det finns stöd för lokala datakällor i målgruppinsikter bygger på Power Platform-dataflöden. Dataflöden kan aktiveras i Customer Insights av [ange Microsoft Dataverse miljö-URL](manage-environments.md#create-an-environment-in-an-existing-organization) när du ställer in miljön.

Datakällor som skapas efter att ha associerat en Dataverse-miljö med Customer Insights kommer att använda [Power Platform dataflöden](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default. Dataflöden stöder lokal anslutning med datagateways. Ta bort och återskapa datakällor som fanns innan en Dataverse-miljö associerades för att använda lokal datagateways.

Datagateways från en befintlig Power BI eller Power Apps-miljö kommer att synas och du kan återanvända i Customer Insights. På sidan för datakällor visas länkar som går till den Power Platform-miljö där du kan visa och konfigurera lokal datagateways.

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Skärmbild på sidan med datakällor som visar länkar som pekar till Power Platform-miljön.":::

## <a name="review-ingested-data"></a>Granska inmatade data

Du ser namnet på varje inmatad datakälla, dess status och sista gången data uppdaterades för källan. Du kan sortera listan över datakällor efter varje kolumn.

> [!div class="mx-imgBorder"]
> ![Tillagd datakälla](media/configure-data-datasource-added.png "Tillagd datakälla")

|Status  |Beskrivning  |
|---------|---------|
|Lyckades   |Datakälla har matats in om en tidpunkt nämns i kolumnen **Uppdaterad**.
|Inte startad   |Datakällan har inga inmatade data än eller är fortfarande i utkastläge.         |
|Uppdaterar    |Datainmatning pågår. Du kan avbryta åtgärden genom att välja **Avbryt uppdatering** i kolumnen **åtgärder**. Om du stoppar uppdateringen av en datakälla återställs den till dess senaste uppdateringstillstånd.       |
|Misslyckad     |Datahämtning har stött på fel.         |

Välj värdet i kolumnen **Status** för en datakälla för att se mer information. I rutan **Förloppsinformation** visar du **Datakällor**. Välj **Se information** för mer information om uppdateringsstatusen, inklusive felinformation och uppdateringar om nedströmsprocesser.

Inläsning av data kan ta en stund. Efter en lyckad uppdatering kan hämtade data granskas från sidan **entiteter**. Mer information finns i [Entiteter](entities.md).

## <a name="refresh-a-data-source"></a>Uppdatera en datakälla

Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran. 

Gå till **Admin** > **System** > [**Schema**](system.md#schedule-tab) för att konfigurera schemalagda uppdateringar av alla dina inmatade datakällor.

Uppdatera en datakälla på begäran så här:

1. I målgruppsinsikter går du till **Data** > **Datakällor**

2. Välj den lodräta ellipsen bredvid den datakälla som du vill uppdatera och välj **Uppdatera** från listrutan.

3. Datakällan aktiveras nu för en manuell uppdatering. Om du uppdaterar datakälla uppdateras både entitetsschemat och data för alla entiteter som anges i datakälla.

4. Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.

## <a name="delete-a-data-source"></a>Ta bort datakällan

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Markera den lodräta ellipsen bredvid datakällan du vill ta bort och välj **ta bort** i den nedrullningsbara menyn.

3. Bekräfta borttagningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
