---
title: Dataförening
description: Läs om hur du enar inmatade data.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: bf1bbcd31333c8a557b59b001112042a1783546ab0cd2af394d8af2953a493f4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032780"
---
# <a name="data-unification-overview"></a>Översikt över dataförening

När du har [konfigurerat datakällorna](data-sources.md) kan du ena data. Dataförening innehåller tre steg: **karta**, **matchning** och **koppling**.

Med föreningsprocessen för data kan du förena en och samma datakällor till en enda huvuddatauppsättning som ger kunderna en enhetlig vy. Föreningsstadier är obligatoriska och utförs i följande ordning:

1. [Mappning](map-entities.md)
2. [Matcha](match-entities.md)
3. [Koppla](merge-entities.md)

När du har slutfört dataförening kan du också

- [konfigurera relationer mellan entiteter](relationships.md) för att skapa sofistikerade segment
- [berika dina data](enrichment-hub.md) så att du får en större mängd information om kunderna
- [definiera aktiviteter](activities.md) från några av de inmatade attributen


[!INCLUDE[footer-include](../includes/footer-banner.md)]