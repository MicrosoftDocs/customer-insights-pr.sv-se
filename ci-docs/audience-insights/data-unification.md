---
title: Skapa en enhetlig vy av kunderna
description: Gå igenom samordningen av data med dina data och skapa en enda huvudprofil datauppsättning kundprofiler.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-unify
ms.openlocfilehash: 694bfd0e407975af64ca0971a73fe4c3f5ba5a23
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648093"
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