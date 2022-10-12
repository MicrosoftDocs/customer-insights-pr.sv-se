---
title: Översikt över datakällor
description: Lär dig hur du importerar eller importerar data från olika källor.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610074"
---
# <a name="data-sources-overview"></a>Översikt över datakällor

Dynamics 365 Customer Insights ger anslutningar för att hämta data från en mängd olika källor. Anslutning till en datakälla kallas ofta för *datainmatning*. När du har fört in data kan du [ena](data-unification.md), skapa insikter och aktivera data för att skapa anpassade erfarenheter.

## <a name="add-or-edit-data-sources"></a>Lägg till eller redigera datakällor

Du kan bifoga eller importera datakällor till Customer Insights. Länkarna nedan ger instruktioner om hur du lägger till och redigerar datakällor.

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

## <a name="manage-existing-data-sources"></a>Hantera befintliga datakällor

Gå till **Data** > **Datakällor** för att visa namnet på varje inmatad datakälla, dess status och senaste gången data uppdaterades för den källan. Du kan sortera listan datakällor efter valfri kolumn eller använda sökrutan för att hitta det datakälla du vill hantera.

Välj en datakälla om du vill visa tillgängliga åtgärder.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Tillagd datakälla.":::

- [**Redigera**](#add-or-edit-data-sources) datakällan för att ändra dess egenskaper.
- [**Uppdatera**](#refresh-data-sources) datakällan för att inkludera de senaste uppgifterna.
- [**Utöka**](data-sources-enrichment.md) datakällan innan sammanslagningen.
- **Ta bort** datakällan. En datakälla kan endast raderas om informationen inte används i någon bearbetning som förening, insikter, aktivering eller export.

## <a name="refresh-data-sources"></a>Uppdatera datakällor

Datakällor kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran. [Lokala datakällor](connect-power-query.md#add-data-from-on-premises-data-sources) uppdateras enligt sina egna scheman som konfigureras vid datainmatning. Om du vill ha felsökningstips går du till [Felsöka PPDF Power Query-baserad datakälla uppdatera problem](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

För bifogade datakällor används senaste data från den aktuella datakälla.

Gå till **Admin** > **System** > [**Schema**](schedule-refresh.md) om du vill konfigurera system schemalagda uppdateringar för de inmatade datakällorna.

Så här uppdaterar du en datakälla på begäran:

1. Gå till **Data** > **Datakällor**.

1. Markera datakälla du vill uppdatera och välj **Uppdatera**. Datakällan aktiveras nu för en manuell uppdatering. Om du uppdaterar datakälla uppdateras både entitetsschemat och data för alla entiteter som anges i datakälla.

1. Välj status för att öppna rutan **Förloppsinformation** och se framstegen. Om du vill avbryta jobbet väljer du **Avbryt jobbet** längst ned i fönstret.

## <a name="corrupt-data-sources"></a>Skadade datakällor

Data som inmatas kan ha skadade poster som kan leda till att datainmatningsprocessen slutförs med fel eller varningar.

> [!NOTE]
> Om datainmatningen slutförs med fel, kommer efterföljande bearbetning (t.ex. skapande av data eller aktivitetsgenerering) som använder datakälla att hoppas över. Om meddelandet har slutförts med varningar fortsätter efterföljande bearbetning men en del av posterna kanske inte ingår.

Felen visas i uppgiftsinformationen.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Uppgiftsdetalj som visar skadade datafel.":::

Skadade poster visas i systemskapade enheter.

### <a name="fix-corrupt-data"></a>Åtgärda skadade data

1. För att visa skadade data, gå till **Data** > **Entiteter** och leta efter skadade entiteter i avsnittet **System**. Namnschema för skadade entiteter: &quot;DataSourceName_EntityName_corrupt&quot;.

1. Välj en korrupt enhet och sedan **Data**.

1. Identifiera de skadade fälten i en post och orsaken.

   :::image type="content" source="media/corruption-reason.png" alt-text="Orsak till fel." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Data** > **Entiteter** visar endast en del av de skadade posterna. Om du vill visa alla skadade poster exporterar du filerna till en behållare i lagringskontot med hjälp av [exportprocessen Customer Insights](export-destinations.md). Om du använde ditt eget lagringskonto kan du också titta på mappen Customer Insights i ditt lagringskonto.

1. Korigera skadad data. Exempelvis för Azure Data Lake datakällor, [åtgärdar du data i Data Lake Storage eller uppdaterar datatyperna i filen manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). För Power Query datakällor åtgärdar du data i källfilen och [korrigerar datatypen som omvandlingssteget](connect-power-query.md#data-type-does-not-match-data) på sidan **Power Query – Redigera frågor**.

Efter nästa uppdatering av datakällan skickas de korrigerade posterna till Customer Insights och sedan vidare till processer nedströms.

Exempelvis har datatypen &quot;datum&quot; angetts för kolumnen &quot;födelsedag&quot;. En kundpost har födelsedagen angiven som &quot;1977-01-01&quot;. Systemet flaggar då denna post som skadad. Ändra födelsedagen i källsystemet till 1977. Efter en automatisk uppdatering av datakällor har fältet nu ett giltigt format och posten tas bort från den skadade entiteten.

[!INCLUDE [footer-include](includes/footer-banner.md)]
