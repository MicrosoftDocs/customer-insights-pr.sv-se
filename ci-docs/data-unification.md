---
title: Översikt över dataförening
description: Gå igenom samordningen av data med dina data och skapa en enda datauppsättning med Unified customer profile.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139540"
---
# <a name="data-unification-overview"></a>Översikt över dataförening

När du har [konfigurerat datakällorna](data-sources.md) kan du ena data. Dataförening låter dig förena en gång disparata datakällor till en enda huvuddatauppsättning som ger en enhetlig vy av dessa data. För enskilda användare (B-till-C) där informationen är centrerad kring enskilda personer ger den en enhetlig bild av dina kunder. För företagskonton (B-till-B) där informationen är centrerad kring konton ger den en enhetlig bild av dina konton.

Data kan vara enhetliga på samma entitet eller flera entiteter. Samordning utförs i följande ordning:

1. [Källfält](map-entities.md) (kallas tidigare mappning): Välj entiteter och fält som ska ingå i entiteterna i processen för källfält. Mappa fält till en vanlig typ av språktyp som beskriver syftet med fältet.

1. [Dubblettposter](remove-duplicates.md) (tidigare en del av matchning): I steget med dubblettposter kan du även definiera regler för att ta bort dubblettkundposter från varje entitet.

1. [Matchande villkor](match-entities.md) (kallas tidigare matchning): I matchningsvillkorssteget definierar du regler som matchar kundposter mellan entiteter. När en kund finns i två eller flera entiteter skapas en konsoliderad post med alla kolumner och data från varje entitet.

1. [Enhetliga kundfält](merge-entities.md) (kallas tidigare sammanslå): I steget för enhetliga kundfält avgör du vilka källfält som ska tas med, uteslutas eller slås samman i Unified customer profile.  

1. [Granska](review-unification.md) och skapa en enhetlig profil.

När du har slutfört dataförening kan du också:

- [Ange relationer mellan entiteter](relationships.md) för att skapa sofistikerade segment.
- [Utöka dina data](enrichment-hub.md) så att du får en större mängd information om kunderna.
- [Definiera aktiviteter](activities.md) från några av de inmatade attributen.
- [Skapa åtgärder](measures.md) för att få en bättre förståelse av kundbeteenden och affärsresultat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
