---
title: Översikt över datakällor
description: Lär dig hur du importerar eller importerar data från olika källor.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051475"
---
# <a name="data-sources-overview"></a>Översikt över datakällor

Dynamics 365 Customer Insights ger anslutningar för att hämta data från en mängd olika källor. Anslutning till en datakälla kallas ofta för *datainmatning*. När du har fört in data kan du [ena](data-unification.md), skapa insikter och aktivera data för att skapa anpassade erfarenheter.

## <a name="add-data-sources"></a>Lägg till datakällor

Du kan bifoga eller importera datakällor till Customer Insights. Länkarna nedan innehåller instruktioner om hur du lägger till datakällor.

**Bifoga en datakälla**

Om du har förberett data i en av Microsofts Azure-datatjänster kan Customer Insights enkelt ansluta till datakälla utan att behöva mata in data igen. Välj ett av följande alternativ:
- [Azure Data Lake Storage (csv- eller parquet-filer i mappen Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (Lake databaser)](connect-synapse.md)
- [Microsoft Dataverse Data Lake](connect-dataverse-managed-lake.md)

**Importera och omvandla**

Om du använder lokala datakällor, Microsoft eller data från tredje part importerar du och omvandlar data med hjälp av Power Query anslutningar.
- [Power Query-anslutningsprogram](connect-power-query.md)

## <a name="review-data-sources"></a>Granska datakällor

Om din miljö har konfigurerats att använda lagringsutrymmet för Customer Insights och du använder lokala datakällor använder du Power Platform dataflöden. Med Power Platform dataflöden kan du visa delade datakällor och datakällor som hanterats av andra. På sidan **Datakällor** visas datakällorna i tre avsnitt:
- **Delad**: Datakällor som kan hanteras av alla Customer Insights-administratörer. Power Platform-dataflöden, ditt eget lagringskonto och bifogande till Dataverse-hanterad datakälla är exempel på delade datakällor.
- **Hanteras av mig**: Power Platform-dataflöden som skapats och bara kan hanteras av dig. Andra Customer Insights-administratörer kan visa dessa dataflöden men inte redigera, uppdatera eller ta bort dem.
- **Hanteras av andra**: Power Platform-dataflöden som skapats av andra administratörer. Du kan bara visa dem. Här finns en lista över ägarna av dataflödet som ska kontaktas för hjälp.
> [!NOTE]
> Alla entiteter kan visas och användas av andra användare. Medan datakällor ägs av den användare som skapade dem kan alla användare av Customer Insights använda de entiteter som skapas utifrån informationen.

Om dataflöden inte används i Power Platform miljön innehåller sidan **Datakällor** endast en lista över alla datakällor. Inga avsnitt visas.

Gå till **Data** > **Datakällor** för att visa namnet på varje inmatad datakälla, dess status och senaste gången data uppdaterades för den källan. Du kan sortera listan över datakällor efter varje kolumn.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Tillagd datakälla.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan **entiteter**. Mer information finns i [Entiteter](entities.md).

## <a name="refresh-data-sources"></a>Uppdatera datakällor

Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran. [Lokala datakällor](connect-power-query.md#add-data-from-on-premises-data-sources) uppdateras enligt sina egna scheman som konfigureras vid datainmatning. För bifogade datakällor används senaste data från den aktuella datakälla.

Gå till **Admin** > **System** > [**Schema**](system.md#schedule-tab) om du vill konfigurera system schemalagda uppdateringar för de inmatade datakällorna.

Uppdatera en datakälla på begäran så här:

1. Gå till **Data** > **Datakällor**.

1. Välj den stående ellipsen (&vellip;) bredvid den datakälla du vill uppdatera och välj sedan **Uppdatera** i listrutan. Datakällan aktiveras nu för en manuell uppdatering. Om du uppdaterar datakälla uppdateras både entitetsschemat och data för alla entiteter som anges i datakälla.

1. Välj **Avbryt uppdatering** om du vill avbryta en pågående uppdatering, så återgår datakällan till den senaste uppdateringsstatusen.

## <a name="delete-a-data-source"></a>Ta bort datakällan

En datakälla kan endast raderas om informationen inte används i någon bearbetning som förening, insikter, aktivering eller export.

1. Gå till **Data** > **Datakällor**.

2. Välj den stående ellipsen (&vellip;) bredvid den datakälla du vill ta bort och välj sedan **Ta bort** i listrutan.

3. Bekräfta borttagningen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
