---
title: Använd demografiska dimensioner för att dela upp beteendedata (modererad dimension)
description: Använd enhetliga profilerade mått för att kundprofil egenskaper för målgruppsinsikter.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466370"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Använd demografiska mått för att dela beteendedata

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Genom att använda en enhetlig profil för demografisk storlek kan användarna få tillgång profilegenskaper för målgruppsinsikter. Du kan sedan använda dessa egenskaper i interaktiva analyser av beteendedata, inklusive data som samlas in av engagemangsinsikter på din webbplats eller mobilapp.

>[!NOTE]
> Engagemangsinsikter innehåller färdiga dimensioner för händelseegenskaper. Mer information: [Visa och skapa dimensioner](dimensions.md)

## <a name="prerequisite"></a>Förutsättningar

- En miljö med engagemangsinsikter där du har kundprofildata kopplade till miljöer med målgruppsinsikter där kundprofilerna skapas. Mer information finns i [Skapa en länk mellan målgruppsinsikter och engagemangsinsikter](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> När du har skapat en länk mellan miljöer för målgruppsinsikter och engagemangsinsikter kanske du bara vill ha data specifika för kundprofilegenskaper, som kan vara användbara som mått i engagemangsinsikter. För mer information, gå till [Aktivera målgruppsinsikter, enhetliga profilattribut och segment](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Skapa en ny anpassad rapport

1. I vänstra fönstret, välj **Anpassa** > **Ny rapport** och välj sedan mätvärdet du vill ha. (I det här exemplet valde vi rapporten **Sidvyer efter timme**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Välj ett mått.":::

2. I visualiseringsredigeraren, välj **Dimensioner** och välj sedan **demografisk** i listrutan **Dimensionstyp**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Välj demografisk information.":::

3. Välj dimensionen **Signal.Customer.*xxx***. (I det här exemplet visas Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Välj en dimension.":::
  
## <a name="limitations"></a>Begränsningar

För närvarande kan du bara använda demografiska dimensioner för att dela upp beteendedata.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
