---
title: Teamrobot för Dynamics 365 Customer Insights (förhandsversion)
description: Slå upp enhetliga kundprofiler i Microsoft Teams med hjälp av en robot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195864"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teamrobot för Dynamics 365 Customer Insights (förhandsversion)

Anslut med Microsoft Teams för att låta en robot slå upp enhetliga kundprofiler i Teams-kanaler.

:::image type="content" source="media/teams-bot.png" alt-text="Teams-robot som visar en kundpost":::

## <a name="prerequisites"></a>Förutsättningar

- Minst en [datakälla har lagts till](data-sources.md).
- [Föreningsprocessen](data-unification.md) har slutförts.
- Fält läggs till i [Sök- och filterindex](search-filter-index.md).
- Customer Insights och Teams finns i samma organisation.
- Din miljö har den primära målgruppen inställd på enskilda kunder. Affärskonton stöds inte.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurera roboten

1. Gå till **Admin** > **Anslutningar**.
1. I panelen Microsoft Teams, välj **Konfigurera**.
1. Du omdirigeras då till området **appar** i Teams. Du kan också öppna Teams och välja **appar** längst ned till vänster eller [Hämta den direkt från AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Sök efter **Customer Insights** och välj appen.
1. Markera **Lägg till**.
1. Logga in på Customer Insights i Teams. Ett välkomstmeddelande visas.

## <a name="things-you-can-do-with-the-bot"></a>Saker du kan göra med roboten

Roboten har uppslagsfunktioner för enhetliga kundprofiler.

- Ange **sökning** följt av ett namn, en e-postadress eller ett annat fält i den enhetliga kundprofilen som läggs till i sök- och filterindexet.

  Du får ett kort med upp till 15 fält från den resulterande kundprofilen. Flera matchningar returnerar en resultatlista där du kan välja en profil. Du kan lägga till sökterm i dubbla citattecken för att slå upp en exakt matchning.

- Om organisationen underhåller flera Customer Insights-miljöer i samma organisation kan du ange **switchinstance** för att välja vilken miljö du vill ansluta roboten till.

- Ange **Hjälp** för att visa en lista över tillgängliga kommandon för robot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]