---
title: Skapa en enhetlig vy av kunderna
description: Gå igenom samordningen av data med dina data och skapa en enda huvudprofil datauppsättning för konto eller kundprofiler.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304449"
---
# <a name="data-unification-overview"></a>Översikt över dataförening

När du har [konfigurerat datakällorna](data-sources.md) kan du ena data. Dataförening låter dig förena en gång disparata datakällor till en enda huvuddatauppsättning som ger en enhetlig vy av dessa data.

För enskilda användare (B-till-C) där informationen är centrerad kring enskilda personer ger den en enhetlig bild av dina kunder. För företagskonton (B-till-B) där informationen är centrerad kring konton ger den en enhetlig bild av dina konton. [Kontaktförening (förhandsgranskning)](data-unification-contacts.md) tillåter att kontakter för dessa konton kan kopplas ihop separat och associeras med kontona.

Data kan vara enhetliga på samma entitet eller flera entiteter.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

Föreningsprocessen mappar kunddata från dina datakällor, tar bort dubbletter, matchar data över entiteter och skapar en enhetlig profil. Samordning utförs i följande ordning:

1. [Källfält](map-entities.md) (kallas tidigare mappning): Välj entiteter och fält som ska ingå i entiteterna i processen för källfält. Mappa fält till en vanlig typ av språktyp som beskriver syftet med fältet.

1. [Dubblettposter](remove-duplicates.md) (tidigare en del av matchning): I steget med dubblettposter kan du även definiera regler för att ta bort dubblettkundposter från varje entitet.

1. [Matchande villkor](match-entities.md) (kallas tidigare matchning): I matchningsvillkorssteget definierar du regler som matchar kundposter mellan entiteter. När en kund finns i två eller flera entiteter skapas en konsoliderad post med alla kolumner och data från varje entitet.

1. [Enhetliga kundfält](merge-entities.md) (kallas tidigare sammanslå): I steget för enhetliga kundfält avgör du vilka källfält som ska tas med, uteslutas eller slås samman i Unified customer profile.  

1. [Granska](review-unification.md) och skapa en enhetlig profil.

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

Föreningsprocessen mappar kontodata från dina datakällor, tar bort dubbletter, matchar data över entiteter och skapar en enhetlig profil. Samordning utförs i följande ordning:

1. [Källfält](map-entities.md) (kallas tidigare mappning): Välj entiteter och fält som ska ingå i entiteterna i processen för förena konto. Mappa fält till en vanlig typ av språktyp som beskriver syftet med fältet.

1. [Dubblettposter](remove-duplicates.md) (tidigare en del av matchning): I steget med dubblettposter kan du även definiera regler för att ta bort dubblettkontoposter från varje entitet.

1. [Matchande villkor](match-entities.md) (kallas tidigare matchning): I matchningsvillkorssteget definierar du regler som matchar kontoposter mellan entiteter. När ett konto finns i två eller flera entiteter skapas en konsoliderad post med alla kolumner och data från varje entitet.

1. [Enhetliga kundfält](merge-entities.md) (kallas tidigare sammanslå): I steget för enhetliga kundfält avgör du vilka källfält som ska tas med, uteslutas eller slås samman i Unified customer profile.  

1. [Granska](review-unification.md) och skapa en enhetlig profil.

När du har förenat kontona kan du eventuellt [förena kontakter (förhandsversion)](data-unification-contacts.md) för dessa konton och länka de enhetliga kontakterna till de enhetliga kontona.

---

När du har slutfört dataförening kan du också:

- [Ange relationer mellan entiteter](relationships.md) för att skapa sofistikerade segment.
- [Utöka dina data](enrichment-hub.md) så att du får en större mängd information om kunderna.
- [Definiera aktiviteter](activities.md) från några av de inmatade attributen.
- [Skapa åtgärder](measures.md) för att få en bättre förståelse av kundbeteenden och affärsresultat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
