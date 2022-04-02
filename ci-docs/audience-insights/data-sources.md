---
title: Använd datakällor för att mata in data
description: Lär dig hur du importerar data från olika källor.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464096"
---
# <a name="data-sources-overview"></a>Översikt över datakällor



Kapaciteten för målgruppsinsikter i Dynamics 365 Customer Insights ansluter till data från en bred uppsättning källor. Anslutning till en datakälla kallas ofta för *datainmatning*. När du har inmatat dina data kan du [ena](data-unification.md) och vidta åtgärder.

## <a name="add-a-data-source"></a>Lägg till en datakälla

Detaljerade artiklar innehåller information om hur du lägger till datakälla, beroende på vilket alternativ du väljer.

Du kan lägga till följande datakällor:

- [Genom dussintals Power Query-anslutningar](connect-power-query.md)
- [Från en Common Data Model-mapp](connect-common-data-model.md)
- [Från din egen Microsoft Dataverse sjö](connect-dataverse-managed-lake.md)
- [Från en Azure Synapse Analytics-databas](connect-synapse.md)

> [!NOTE]
> Om du använder provversionen innehåller avsnittet importmetoder ett **databibliotek för Customer Insights**. Välj det här alternativet om du vill datauppsättning exempel för olika branscher. Mer information finns i [Dynamics 365 Customer Insights-utvärdering](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Lägga till data lokala datakällor

Inmatning av data från lokala datakällor i målgruppinsikter stöds baserat på Microsoft Power Platform-dataflöden. Du kan aktivera dataflöden i Customer Insights genom att [ange Microsoft Dataverse miljö-URL](create-environment.md) när du ställer in miljön.

Datakällor som skapas efter att en Dataverse miljö associerats med Customer Insights använder du [Power Platform dataflöden](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflöden stöder lokal anslutning med datagateway. Du kan ta bort och återskapa datakällor som fanns innan en Dataverse miljö associerades med [använda lokala datagateway](/data-integration/gateway/service-gateway-app).

Datagateways från en befintlig Power BI eller Power Apps-miljö kommer att synas och du kan återanvända i Customer Insights. På sidan för datakällor visas länkar som går till den Microsoft Power Platform-miljö där du kan visa och konfigurera lokal data-gateways.

> [!IMPORTANT]
> Kontrollera att dina gateways är uppdaterade till den senaste versionen. Du kan installera en uppdatering och konfigurera om en gateway från en fråga som visas på skärmen gateway direkt, eller också [hämta den senaste versionen](https://powerapps.microsoft.com/downloads/). Om du inte använder den senaste gateway-versionen misslyckas uppdateringen av dataflödet med felmeddelanden som **Nyckelordet stödsinte: konfigurationsegenskaper. Parameternamn: nyckelord**.

## <a name="review-ingested-data"></a>Granska inmatade data
Om miljön innehåller Power Platform-dataflöden visas tre avsnitt på sidan **Datakällor**: 
- **Delad**: Datakällor som kan hanteras av alla Customer Insights-administratörer. Power BI-dataflöden, ditt eget lagringskonto och bifogande till Dataverse-hanterad datakälla är exempel på delade datakällor.
- **Hanteras av mig**: Power Platform-dataflöden som skapats och bara kan hanteras av dig. Andra Customer Insights-administratörer kan visa dessa dataflöden men inte redigera, uppdatera eller ta bort dem.
- **Hanteras av andra**: Power Platform-dataflöden som skapats av andra administratörer. Du kan bara visa dem. Här finns en lista över ägarna av dataflödet som ska kontaktas för hjälp.
> [!NOTE]
> Alla entiteter kan visas och användas av andra användare. Användarens kontextualitet gäller endast datakällorna och inte entiteterna som är resultatet av dessa dataflöden.

Om inga Power Platform-dataflöden används, visas inga grupper eller avsnitt. Sidan **Datakällor** innehåller endast en lista över alla datakällor.

Du ser namnet på varje inmatad datakälla, dess status och sista gången data uppdaterades för källan. Du kan sortera listan över datakällor efter varje kolumn.

> [!div class="mx-imgBorder"]
> ![Tillagd datakälla.](media/configure-data-datasource-added.png "Tillagd datakälla")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan **entiteter**. Mer information finns i [Entiteter](entities.md).

## <a name="refresh-a-data-source"></a>Uppdatera en datakälla

Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran. 

Gå till **Admin** > **System** > [**Schema**](system.md#schedule-tab) för att konfigurera schemalagda uppdateringar av alla dina inmatade datakällor.

Uppdatera en datakälla på begäran så här:

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Välj den stående ellipsen bredvid den datakälla du vill uppdatera och välj sedan **Uppdatera** i listrutan.

3. Datakällan aktiveras nu för en manuell uppdatering. Om du uppdaterar datakälla uppdateras både entitetsschemat och data för alla entiteter som anges i datakälla.

4. Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.

## <a name="delete-a-data-source"></a>Ta bort datakällan

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Välj den stående ellipsen bredvid den datakälla du vill ta bort och välj sedan **Ta bort** i listrutan.

3. Bekräfta borttagningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
