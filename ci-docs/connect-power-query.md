---
title: Anslut till en Power Query datakälla (innehåller video)
description: Indata via en Power Query-koppling (innehåller video).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207067"
---
# <a name="connect-to-a-power-query-data-source"></a>Anslut till en Power Query-datakälla

Power Query erbjuder en mängd anslutningsprogram till indata. De flesta av dessa anslutningar stöds av Dynamics 365 Customer Insights.

Att lägga till datakällor baserade på Power Query-kopplingar följer vanligtvis stegen i det här avsnittet. Beroende på vilken anslutning du använder krävs emellertid olika uppgifter. Mer information finns i dokumentationen för enskilda anslutningsprogram i [Power Query-kopplingsreferensen](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Skapa en ny datakälla

1. Gå till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Välj **Microsoft Power Query**.

1. Ange ett **Namn** och en valfri **Beskrivning** för datakällan och välj **Nästa**.

1. Välj ett av [tillgängliga anslutningsprogram](#available-power-query-data-sources). I det här exemplet väljer du kopplingen **Text/CSV**.

1. Ange obligatoriska uppgifter i **anslutningsinställningar** för den valda anslutningen och välj **Nästa** om du vill visa en förhandsgranskning av informationen.

1. Välj **Transformera data**.

1. I dialogrutan **Power Query - Redigera frågor** kan du granska och förfina data. De entiteter som identifieras i den valda datakälla visas i den vänstra rutan.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialogrutan Redigera frågor":::

1. Du kan även omvandla dina data. Välj en entitet att redigera eller omvandla. Använd alternativen i Power Query-fönstret för att tillämpa omvandlingar. Varje omvandling visas under **Tillämpade steg**. Power Query innehåller många [förbyggda omvandlingsalternativ](/power-query/power-query-what-is-power-query#transformations).

   Vi rekommenderar att du använder följande omvandlingar:

   - Om du samlar in data från en CSV-fil innehåller den första raden ofta rubriker. Gå till **Omvandla** och välj **Använd första raden som rubriker**.
   - Kontrollera att datatypen har definierats korrekt. För datumfält väljer du till exempel en datumtyp.

1. Om du vill lägga till ytterligare entiteter i datakällan i dialogrutan **Redigera frågor**, går du till **Hem** och väljer **Hämta data**. Upprepa steg 5-10 tills du har lagt till alla entiteter för datakälla. Om du har en databas som innehåller flera datauppsättningar är varje datauppsättning en egen entitet.

1. Välj **Spara**. Sidan **Datakällor** öppnas där den nya datakälla visas i status **uppdateras**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan [**Entiteter**](entities.md).

> [!CAUTION]
> En datakälla baserad på Power Query skapa en [datakälla i Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Ändra inte namnet på ett dataflöde i administrationscentret Power Platform som används i Customer Insights. Om du byter namn på ett dataflöde orsakar det problem med referenserna mellan Customer Insights datakälla och Dataverse dataflödet.

### <a name="available-power-query-data-sources"></a>Tillgängliga Power Query-datakällor

Se [Power Query-kopplingsreferensen](/power-query/connectors/) för en lista över anslutningsprogram som du kan använda för att importera data till Customer Insights.

Anslutningsprogram med en bock i kolumnen **Customer Insights (dataflöden)** är tillgängliga om du vill skapa nya datakällor utifrån Power Query. Läs dokumentationen för en specifik anslutning om du vill veta mer om dess krav, [frågebegränsningar](/power-query/power-query-online-limits) och annan information.

## <a name="add-data-from-on-premises-data-sources"></a>Lägga till data lokala datakällor

Det finns stöd för lokal datakällor som bygger på Microsoft Power Platform dataflöden (PPDF). Du kan aktivera dataflöden i Customer Insights genom att [ange Microsoft Dataverse miljö-URL](create-environment.md) när du ställer in miljön.

Datakällor som skapas efter att en Dataverse miljö associerats med Customer Insights använder du [Power Platform dataflöden](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflöden stöder lokal anslutning med datagateway. Du kan ta bort och återskapa datakällor som fanns innan en Dataverse miljö associerades med [använda lokala datagateway](/data-integration/gateway/service-gateway-app).

Datagateways från en befintlig Power BI eller Power Apps-miljö kommer att synas och du kan återanvända i Customer Insights. På sidan för datakällor visas länkar som går till den Microsoft Power Platform-miljö där du kan visa och konfigurera lokal data-gateways.

> [!IMPORTANT]
> Kontrollera att dina gateways är uppdaterade till den senaste versionen. Du kan installera en uppdatering och konfigurera om en gateway från en fråga som visas på skärmen gateway direkt, eller också [hämta den senaste versionen](https://powerapps.microsoft.com/downloads/). Om du inte använder den senaste gateway-versionen misslyckas uppdateringen av dataflödet med felmeddelanden som **Nyckelordet stödsinte: konfigurationsegenskaper. Parameternamn: nyckelord**.
>
> Fel med lokal-data-gateways i Customer Insights orsakas ofta av konfigurationsproblem. Mer information om hur du felsöker problem med datagateway finns i [Felsöka den lokala datagatewayen](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Redigera Power Query-datakällor

> [!NOTE]
> Det kanske inte går att göra ändringar i datakällor som för närvarande används i någon av appens processer (segmentering, datasammanslutning till exempel).
>
> På sidan **inställningar** kan du följa upp förloppet för varje aktiv process. När en process har slutförts kan du gå tillbaka till sidan **datakällor** och göra ändringar.

1. Gå till **Data** > **Datakällor**.

1. Välj bredvid datakällan du vill uppdatera **Redigera**.

1. Tillämpa ändringarna och omvandlingarna i dialogrutan **Power Query – Redigera frågor** enligt beskrivningen i avsnittet [Skapa en ny datakälla](#create-a-new-data-source).

1. Klicka på **Spara** om du vill tillämpa ändringarna och återgå till sidan **Datakällor**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
