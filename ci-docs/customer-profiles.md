---
title: Visa kundprofiler
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
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303805"
---
# <a name="view-customer-profiles"></a>Visa kundprofiler

Kundprofiler är tillgängliga när du har [skapat en enhetlig entitet *kund*](data-unification.md). Den kombinerade vyn av dina enhetliga kundprofiler visas på sidan **Kunder**. Kunderna kan vara enskilda personer eller organisationer.

Gå till sidan **Kunder** om du vill visa dina kunder och deras profiler. Varje kundprofil representeras av en panel. Hämta fler poster med sidnumreringskontrollerna. Kortet visar fält från entiteten *Kund* enligt definitionen i **Sök- och filterindex**. Ordningen på fälten inom varje kort väljs av systemet.

> [!NOTE]
> Om du inte kan se panelerna när du väljer **Kunder** måste administratörer [definiera minst ett sökbart attribut](search-filter-index.md) i **Sök och filtrera index**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Sidan Kunder som visar resultatpaneler.":::

Välj en av följande åtgärder:
- [Visa kundinformation](#view-customer-details)
- [Hantera sök- och filterindex](search-filter-index.md) (endast administratörer)
- [Filtrera kunder](#filter-customers)
- **Visa kort** eller **dölj kort** för att visa eller dölja den information som visas på kundpanelen
- **Sortera efter** ett visst attribut
- [Sök efter kunder](#search-for-customers)

  > [!NOTE]
  > För att kunna använda sökning och filter måste administratören konfigurera de sökbara attributen och definiera de filterbara fälten med hjälp av sök- och filterindex.

## <a name="search-for-customers"></a>Sök efter kunder

Sök efter kunder genom att ange ett namn eller ett annat attribut i **Sök kunder**. De sökbara attributen definieras av administratören och kommer från entiteten enhetlig *kund*.

> [!NOTE]
> **Sträng** är den enda datatyp som ingår i sökningen. Använd den i fältet **Sök efter kunder** på sidan Kunder om du vill söka efter kunder.

## <a name="filter-customers"></a>Filtrera kunder

Filtrera kunder efter entitetsfälten *Kund*. Filterbara fält definieras av administratören.

1. På sidan **Kunder**, välj **Visa filter**. Filterrutan visas.

1. Markera rutorna bredvid attribut som du vill filtrera kunder efter.

1. Ta bort alla filter genom att markera **Avmarkera filter** eller avmarkera en kryssruta bredvid ett markerat attribut.

1. Välj **Dölj filter** för att stänga filterfönstret.

1. Om du vill spara filterresultatet som ett [segment](segments.md) väljer du **Spara filter som segment**.
   1. Ange ett namn för segment.
   1. Välj **Spara** för att spara segment.
   1. Välj om du vill köra segmentet nu genom att välja **Aktivera** eller köra det **senare**.

## <a name="view-customer-details"></a>Visa kundinformation

På sidan **Kunder** väljer du en kundpanel om du vill visa information för den valda kunden.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Kundinformationsfönstret.":::

Kundinformation innefattar:

**Panelen kundprofil**: visar de olika värdena från entiteten enhetlig *kund*. Om ett fält inte har något värde för den valda kundprofilen visas inte det förutom adressfältet. Panelen är strukturerad i avsnitt:

- I det första avsnittet visas en fördefinierad uppsättning fält som följs av alla fält som ingår i sök- och filterindex. Alla adressrelaterade fält kombineras till en enda rad, som visar även om profilen inte innehåller någon adressinformation.
- **Kontaktpersoner för den här kunden** visas i miljöer för företagskonton (B2B). Varje kontakt visas med sina fält. Tomma fält är dolda.
- **Ytterligare fält** visar återstående fält för den valda kunden, förutom ID.
- **ID** anger alla ID under deras motsvarande entitetsnamn. Fält identifieras som ID med hjälp av sina uppsättningar med fält.

**Aktivitetstidslinje** visar data om du har konfigurerat [aktiviteter](activities.md). Tidslinjevyn innehåller kronologiskt sorterade aktiviteter för den valda kunden, med den senaste aktiviteten som utgångspunkt.

**Insikter**:

- **Mått** visar om du har konfigurerat [mått på kundattribut](measures.md). De inkluderar beräknade KPI:er runt dina kunder på den enskilda kundnivån.

- **Potentiella intressen, potentiella varumärken** visar om du har konfigurerat ett [varumärke eller en intressetilldelning](enrichment-microsoft.md). Den representerar potentiella intressen och samhörigheter med varumärken baserade på andra kunder vars profil liknar den valda kundprofilen.

För att gå tillbaka **Kunder** välj **Tillbaka till kunder**.

## <a name="next-steps"></a>Nästa steg

[Lägg till fler datakällor](data-sources.md), [berika enhetliga profiler](enrichment-hub.md) eller [skapa segment](segments.md) att arbeta med enhetliga kundprofiler i andra appar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
