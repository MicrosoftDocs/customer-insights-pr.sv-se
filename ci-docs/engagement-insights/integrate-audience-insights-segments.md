---
title: Använd segment för målgruppsinsikter för att filtrera rapporter om engagemangsinsikter
description: Använd segment med målgruppsinsikter i interaktiva funktioner för att registrera beteendedata som har fångats in av engagemangsinsikter på en kunds webbplats.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230508"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Använd segment för målgruppsinsikter för att filtrera rapporter om engagemangsinsikter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med engagemangsinsikter kan du använda målgruppsinsikter i interaktiva funktioner för att registrera beteendedata som har fångats in av engagemangsinsikter på din webbplats.

## <a name="prerequisite"></a>Förutsättningar

- En miljö med engagemangsinsikter där du har segmentdata med målgruppsinsikter kopplade till miljöer med målgruppsinsikter där segmenten och kundprofilerna skapas. Mer information finns i [Skapa en länk mellan målgruppsinsikter och engagemangsinsikter](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Skapa segment med målgruppsinsikter 

> [!IMPORTANT]
> För segment med målgruppsinsikter att visa i engagemangsinsikter måste du först [köra kopplade och nedströmsprocesser ](../audience-insights/merge-entities.md). Processer nedströms är viktiga eftersom de genererar en unik tabell som förbereder segment av målgruppsinsikter som ska delas med engagemangsinsikter. (Om en systemuppdatering schemaläggs inkluderas processer nedströms automatiskt.)

Du kan använda segment med målgruppsinsikter i engagemangsinsikter i färdiga rapporterna eller anpassade rapporter som du har skapat. Mer information finns i de befintliga [färdiga profilrapporterna](profile-reports.md) och [Skapa och redigera anpassade rapporter](custom-reports.md).

**Använd segment för målgruppsinsikter i rapporter om engagemangsinsikter**

1. Från sidan **Arbetsyta** välj **Data** och välj fliken **Segment**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Välj fliken Segment.":::

   >[!NOTE]
   > Genom att välja ett segment för målgruppsinsikter tar du dig till målgruppsinsikter, där du kan ta reda på hur det segmentet skapades när det gäller regler och logik. Mer information om segment för målgruppsinsikter finns i [Visa och skapa segment](../audience-insights/segments.md).

2. Markera en färdig rapport eller [skapa en anpassad rapport](custom-reports.md) och välj sedan **Lägg till villkor**. (I det här exemplet valde vi rapporten **Sidvyer**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Lägg till ett villkor.":::

3. Välj **Filtrera efter segment**, expandera listan **Segmenttyp** och välj sedan **Demografisk**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Välj den demografiska segmenttypen.":::

4. Expandera listan med **segmentnamn** och välj sedan ett segment med målgruppsinsikter.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text=" Välj ett segment.":::

5. Du kan använda ett eller flera segment, inklusive beteendeinsikter (engagemangsinsikter) och demografisk information (målgruppsinsikter). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Sidan visar en rapport som är begränsad till segmenten USA-kunder och startsida.":::

I den föregående bilden har segmenten **USA-kunder** och **Startsidan** har valts, vilket begränsar rapporten **Sidvyer** för att visa endast de två segmenter. 


>[!NOTE]
> Du kan använda segment med målgruppsinsikter i filtrera färdiga rapporter, anpassade rapporter och trattar i engagemangsinsikter. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]