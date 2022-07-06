---
title: Kundprofiler
description: Visa enhetliga kunddata, bland annat söka och filtrera
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 279c8e1291c6449005d593244f1979e871610a77
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052211"
---
# <a name="customer-profiles"></a>Kundprofiler

Sidan **Kunder** visar en kombinationsvy över dina enhetliga kundprofiler. Kundprofilerna är tillgängliga när du har skapat [entiteten enhetlig kund](data-unification.md). På sidan kan du söka efter kunder och definiera index för den sökningen.

Kunderna kan vara enskilda personer eller organisationer. Varje kundprofil representeras av en panel. Hämta fler poster med sidnumreringskontrollerna. Kortet visar fält från entiteten *Kund* enligt definitionen i **Sök- och filterindex**. Ordningen på fälten inom varje kort väljs av systemet.

Välj en panel om du vill visa data för den valda kunden på en dedicerad sida med namnet [Kundinformationssida](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"]
> ![Sidan Kunder som visar resultatpaneler](media/customers-page-result-tiles-B2C.png "Sidan Kunder som visar resultatpaneler")

> [!NOTE]
> Om du inte kan se panelerna när du väljer **Kunder** i navigeringen måste administratörer [definiera minst ett sökbart attribut](search-filter-index.md) i **Sök och filtrera index**.

## <a name="search-for-customers"></a>Sök efter kunder

Sök efter kunder genom att ange ett namn eller ett annat attribut i sökrutan. Sökningen fungerar bara inom entiteten *Kund* som skapas under föreningsprocessen för data.

Som administratör kan du konfigurera de sökbara attributen med hjälp av sidan **Sök- och filterindex**. Mer information finns i [Hantera sökning och filtrera index](search-filter-index.md).

## <a name="filter-customers"></a>Filtrera kunder

Du kan filtrera kunder efter entitetsfälten *Kund*. Precis som du söker måste din administratör först definiera fälten som filtrerbar med hjälp av sida **Sök- och filtrera index**.

1. Välj **Visa filter** på sidan **Kunder**.

1. Markera rutorna bredvid attribut som du vill filtrera kunder efter.

1. Ta bort dina filter genom att välja **Rensa filter** på sidan **Kunder**.

## <a name="customer-details-page"></a>Kundinformationsfönstret

Välj någon av kundpanelerna för att öppna **kundinformationsfönstret**. Den här vyn innehåller enhetlig information för den valda kunden. Kundinformationen innehåller följande innehåll:

**Panelen kundprofil**: Den här panelen visar de olika värdena från entiteten enhetlig *kund*. Om ett fält inte har något värde för den valda kundprofilen visas inte det förutom adressfältet. Panelen är strukturerad i avsnitt:

- I det första avsnittet visas en fördefinierad uppsättning fält som följs av alla fält som ingår i sök- och filterindex. Alla adressrelaterade fält kombineras till en enda rad, som visar även om profilen inte innehåller någon adressinformation.
- **Kontaktpersoner för den här kunden**: I miljöer för affärskonton ser du alla relaterade kontakter för den här kunden som det andra avsnittet. Varje kontakt visas med sina fält. Tomma fält är dolda.
- **Ytterligare fält**: Visar återstående fält för den valda kunden, förutom ID.
- **ID**: Anger alla ID under deras motsvarande entitetsnamn. Fält identifieras som ID med hjälp av deras semantik, som kategoriserar dem som sådana.

**Aktivitetstidslinje**: Visar data om du har konfigurerat aktiviteter. Tidslinjevyn innehåller kronologiskt sorterade aktiviteter för den valda kunden, med den senaste aktiviteten som utgångspunkt. Mer information finns i [Kundaktiviteter](activities.md).

**Insikter**:

- **Mått**: Visar om du konfigurerat en eller flera mått på kundattribut. De inkluderar beräknade KPI:er runt dina kunder på den enskilda kundnivån. Mer information finns i [Definiera och hantera åtgärder](measures.md).

- **Potentiella intressen, potentiella varumärken**: Visar om du har konfigurerat ett varumärke eller en intressetilldelning. Den representerar potentiella intressen och samhörigheter med varumärken baserade på andra kunder vars profil liknar den valda kundprofilen. Mer information finns i [Utöka kundprofiler med samhörigheter med varumärken och intressen](enrichment-microsoft.md).

Gå tillbaka till kundsöksidan genom att välja **Tillbaka till kunder**.

## <a name="next-steps"></a>Nästa steg

[Lägg till fler datakällor](data-sources.md), [berika enhetliga profiler](enrichment-hub.md) eller [skapa segment](segments.md) att arbeta med enhetliga kundprofiler i andra appar.

[!INCLUDE [footer-include](includes/footer-banner.md)]