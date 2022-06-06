---
title: Indata via en Power Query-koppling (innehåller video)
description: Anslutningsprogram för datakällor som bygger på Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800211"
---
# <a name="connect-to-a-power-query-data-source"></a>Anslut till en Power Query-datakälla

Power Query erbjuder en mängd anslutningsprogram till indata. De flesta av dessa anslutningar stöds av Dynamics 365 Customer Insights. 

Att lägga till datakällor baserade på Power Query-kopplingar följer vanligtvis stegen i det här avsnittet. Beroende på vilken anslutning du använder krävs emellertid olika uppgifter. Mer information finns i dokumentationen för enskilda anslutningsprogram i [Power Query-kopplingsreferensen](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Skapa en ny datakälla

1. Gå till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Välj **Microsoft Power Query**.

1. Ange ett **namn** på datakälla och välj **nästa** om du vill skapa datakälla.

1. Välj ett av [tillgängliga anslutningsprogram](#available-power-query-data-sources). I det här exemplet väljer du kopplingen **Text/CSV**.

1. Ange obligatoriska uppgifter i **anslutningsinställningar** för den valda anslutningen och välj **Nästa** om du vill visa en förhandsgranskning av informationen.

1. Välj **Transformera data**. I det här steget lägger du till entiteter i datakälla. Entiteter är datauppsättningar. Om du har en databas som innehåller flera datauppsättningar är varje datauppsättning en egen entitet.

1. I dialogrutan **Power Query - Redigera frågor** kan du granska och förfina data. De entiteter som identifieras i den valda datakälla visas i den vänstra rutan.

   > [!div class="mx-imgBorder"]
   > ![Dialogrutan Redigera frågor.](media/data-manager-configure-edit-queries.png "Dialogrutan Redigera frågor")

1. Du kan även omvandla dina data. Välj en entitet att redigera eller omvandla. Använd alternativen i Power Query-fönstret för att tillämpa omvandlingar. Varje omvandling visas under **tillämpade steg**. Power Query innehåller många förbyggda omvandlingsalternativ. Mer information finns i [Power Query Omvandlingar](/power-query/power-query-what-is-power-query#transformations).

   Vi rekommenderar att du använder följande omvandlingar:

   - Om du samlar in data från en CSV-fil innehåller den första raden ofta rubriker. Gå till **Omvandla** och välj **Använd första raden som rubriker**.
   - Kontrollera att datatypen har definierats korrekt. För datumfält väljer du till exempel en datumtyp.

1. Om du vill lägga till ytterligare entiteter i datakällan i dialogrutan **Redigera frågor**, går du till **Hem** och väljer **Hämta data**.

1. Välj **Spara** längst ned i Power Query-fönstret för att spara omvandlingarna. När du har sparat informationen hittar du datakälla på **Data** > **Datakällor**.

1. På sidan **Datakällor** kommer du att lägga märke till att den nya datakälla är i status **uppdatera**.

## <a name="available-power-query-data-sources"></a>Tillgängliga Power Query-datakällor

Se [Power Query-kopplingsreferensen](/power-query/connectors/) för en lista över anslutningsprogram som du kan använda för att importera data till Customer Insights. 

Anslutningsprogram med en bock i kolumnen **Customer Insights (dataflöden)** är tillgängliga om du vill skapa nya datakällor utifrån Power Query. Läs dokumentationen för en specifik kontakt om du vill ha mer information om dess krav, begränsningar och annan information.

## <a name="edit-power-query-data-sources"></a>Redigera Power Query-datakällor

> [!NOTE]
> Det kanske inte går att göra ändringar i datakällor som för närvarande används i någon av appens processer (*segmentering*, *matchning* eller *koppling*). 
>
> På sidan **inställningar** kan du följa upp förloppet för varje aktiv process. När en process har slutförts kan du gå tillbaka till sidan **datakällor** och göra ändringar.

1. Gå till **Data** > **Datakällor**.

2. Välj den stående ellipsen (&vellip;) bredvid den datakälla du vill ändra och välj sedan **Redigera** i listrutan.

   > [!div class="mx-imgBorder"]
   > ![Alternativet Redigera.](media/edit-option-data-sources.png "Redigera alternativ")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Tillämpa ändringarna och omvandlingarna i dialogrutan **Power Query – Redigera frågor** enligt beskrivningen i avsnittet [Skapa en ny datakälla](#create-a-new-data-source).

4. Välj **Spara** i Power Query när du har slutfört redigeringarna för att spara ändringarna.


[!INCLUDE [footer-include](includes/footer-banner.md)]
