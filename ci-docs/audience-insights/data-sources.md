---
title: Använd datakällor för att mata in data
description: Lär dig hur du importerar data från olika källor.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595969"
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

> [!NOTE]
> Du kan inte lägga till data från lokala datakällor ännu.

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

3. Datakällan aktiveras nu för en manuell uppdatering. Att uppdatera en datakälla uppdaterar både entitetsschemat och data för alla entiteter som specificerats i datakällan.

4. Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.

## <a name="delete-a-data-source"></a>Ta bort datakällan

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Markera den lodräta ellipsen bredvid datakällan du vill ta bort och välj **ta bort** i den nedrullningsbara menyn.

3. Bekräfta borttagningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]