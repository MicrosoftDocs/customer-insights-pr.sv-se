---
title: Dataförening
description: Läs om hur du enar inmatade data.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407069"
---
# <a name="data-unification"></a>Dataförening

När du har [konfigurerat datakällorna](data-sources.md) kan du ena data. Dataförening innehåller tre steg: **karta**, **matchning** och **koppling**.

Med föreningsprocessen för data kan du förena en och samma datakällor till en enda huvuddatauppsättning som ger kunderna en enhetlig vy. Föreningsstadier är obligatoriska och utförs i följande ordning:

1. [Mappning](map-entities.md)
2. [Matcha](match-entities.md)
3. [Koppla](merge-entities.md)

När du har slutfört dataförening kan du också

- [konfigurera relationer mellan entiteter](relationships.md) för att skapa sofistikerade segment
- [berika dina data](enrichment-hub.md) så att du får en större mängd information om kunderna
- [definiera aktiviteter](activities.md) från några av de inmatade attributen
