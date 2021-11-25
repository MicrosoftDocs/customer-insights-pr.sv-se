---
title: Mata in data via ett Power Query-anslutningsprogram
description: Anslutningar för datakällor baserade på Power Query.
ms.date: 11/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 5d54d33c235e646644e8874e5b0c28898dcff11a
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732240"
---
# <a name="connect-to-a-power-query-data-source"></a>Ansluta till en Power Query-datakälla

Power Query erbjuder ett stort antal kontakter för att samla in data. De flesta av dessa anslutningar stöds av Dynamics 365 Customer Insights. Att lägga till datakällor baserade på Power Query-anslutningar följer i allmänhet de steg som beskrivs i nästa avsnitt. Beroende på vilken anslutning du använder krävs emellertid olika uppgifter. Mer information finns i dokumentationen om enskilda anslutningar i [Power Query anslutningsreferens](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Skapa en ny datakälla

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Välj metoden **Importera data** och välj **Nästa**.

1. Ange ett **namn** på datakälla och välj **nästa** om du vill skapa datakälla. Namnge riktlinjer: 
   - Inled med en bokstav.
   - Använd endast bokstäver och siffror. Specialtecken och blanksteg är inte tillåtna.
   - Använd mellan 3 och 64 tecken.

1. Välj ett av [tillgängliga anslutningsprogram](#available-power-query-data-sources). I det här exemplet väljer du anslutningen **Text/CSV**.

1. Ange obligatoriska uppgifter i **anslutningsinställningar** för den valda anslutningen och välj **Nästa** om du vill visa en förhandsgranskning av informationen.

1. Välj **Transformera data**. I det här steget lägger du till entiteter i datakälla. Entiteter är datauppsättningar. Om du har en databas som innehåller flera datauppsättningar är varje datauppsättning en egen entitet.

1. Dialogrutan **Power Query - redigera frågor** låter dig granska och förfina data. De entiteter som identifieras i den valda datakälla visas i den vänstra rutan.

   > [!div class="mx-imgBorder"]
   > ![Dialogrutan Redigera frågor.](media/data-manager-configure-edit-queries.png "Dialogrutan Redigera frågor")

1. Du kan även omvandla dina data. Välj en entitet att redigera eller omvandla. Använd alternativen i fönstret Power Query för att tillämpa omvandlingar. Varje omvandling visas under **tillämpade steg**. Power Query innehåller flera fördefinierade omvandlingsalternativ. Mer information finns i [Power Query omvandlingar](/power-query/power-query-what-is-power-query#transformations).

1. Du kan lägga till ytterligare entiteter till din datakälla genom att markera **Hämta data** i dialogrutan **Redigera frågor**.

   Dessa omvandlingar rekommenderas högt:

   - Om du samlar in data från en CSV-fil innehåller den första raden ofta rubriker. Gå till **Omvandla tabell** och välj **Använd rubriker som första rad**.
   - Kontrollera att datatypen har definierats korrekt.

1. Välj **Spara** längst ned av Power Query-fönstret för att spara omvandlingarna. När du har sparat informationen hittar du datakälla på **Data** > **Datakällor**.

1. På sidan **Datakällor** kommer du att lägga märke till att den nya datakälla är i status **uppdatera**.

## <a name="available-power-query-data-sources"></a>Tillgängliga Power Query datakällor

Se [Power Query anslutningsreferens](/power-query/connectors/) för en aktuell lista över anslutningar som du kan välja för att importera data till Customer Insights. 

Anslutningar med en bockmarkering i kolumnen **Customer Insights (dataflöden)** är tillgängliga för att skapa nya datakällor utifrån Power Query. Läs dokumentationen för en specifik kontakt om du vill ha mer information om dess krav, begränsningar och annan information.

## <a name="edit-power-query-data-sources"></a>Redigera Power Query datakällor

> [!NOTE]
> Det kanske inte går att göra ändringar i datakällor som för närvarande används i någon av appens processer (*segmentering*, *matchning* eller *koppling*). 
>
> På sidan **inställningar** kan du följa upp förloppet för varje aktiv process. När en process har slutförts kan du gå tillbaka till sidan **datakällor** och göra ändringar.

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Välj den stående ellipsen bredvid den datakälla du vill ändra och välj sedan **Redigera** i listrutan.

   > [!div class="mx-imgBorder"]
   > ![Alternativet Redigera.](media/edit-option-data-sources.png "Redigera alternativ")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Tillämpa ändringarna och omvandlingarna i dialogrutan **Power Query - redigera frågor** som beskrivs i avsnittet [Skapa en ny datakälla](#create-a-new-data-source).

4. Välj **Spara** i Power Query när du har slutfört redigeringarna och vill spara ändringarna.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
