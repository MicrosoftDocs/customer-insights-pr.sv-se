---
title: Visa kundprofiler
description: Få en kombinerad vy över dina enhetliga kunddata.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8ab55d101f98169b8f794ce580ddd0a71ede6642
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554640"
---
# <a name="customer-profiles"></a>Kundprofiler

Sidan **Kunder** visar en kombinerad vy över dina kunder, baserat på profildata som samlats in från [alla datakällor](data-sources.md). Kundprofiler är tillgängliga när du [har skapat en enhetlig kundentitet](data-unification.md). Kontrollera att du har slutfört föreningsprocessen för data för att få bättre vyer över dina kunder. På sidan kan du också söka efter kunder.

Kunder kan vara enskilda personer eller organisationer (förhandsgranskning). Varje kund- eller organisations profil representeras av en panel. Välj en panel om du vill visa ytterligare information om just den kunden eller organisationen. Använd sidbrytningskontrollerna längst ned på sidan om du vill visa fler poster.

> [!div class="mx-imgBorder"] 
> ![B2C-kundprofiler.](media/profiles-customers.png "B2C-kundprofil")

Organisationer (förhandsversion)
> [!div class="mx-imgBorder"] 
> ![B2B-kundprofiler.](media/profile-customers-b2b.png "B2B-kundprofil")

> [!NOTE]
> Om du inte ser panelerna när du väljer **kunder** i navigeringen måste administratören [definiera minst ett sökbart attribut](search-filter-index.md) i **Sök och filtrera index**.

## <a name="search-for-customers"></a>Sök efter kunder

Sök efter kunder genom att ange ett namn eller ett annat attribut i sökrutan. Sökningen fungerar endast inom entiteten kundprofil som skapades under föreningsprocessen för data.

Som administratör kan du konfigurera de sökbara attributen med hjälp av sidan **Sök- och filterindex**. Mer information finns i [Hantera sök- och filterindex](search-filter-index.md).

## <a name="filter-customers"></a>Filtrera kunder

Du kan filtrera kunder efter entitetsfältet kundprofil. Precis som du söker måste din administratör först definiera fälten som filtrerbar med hjälp av sida **Sök- och filtrera index**.

1. Välj **Filter** på sidan **Kunder**.

2. Markera rutorna bredvid attribut som du vill filtrera kunder efter.

   > [!div class="mx-imgBorder"] 
   > ![Kundprofiler.](media/profiles-customers3.png "Kundprofiler")

3. Ta bort dina filter genom att välja **Rensa filter** på sidan **Kunder**.

##  <a name="customer-details-page"></a>Kundinformationsfönstret

Välj någon av kundpanelerna för att öppna **kundinformationsfönstret**. Den här vyn innehåller enhetlig information för den valda kunden.

Kundinformation innefattar:

-   **Kundprofilspanel**: Denna panel visar de olika värdena från den enhetliga kundprofilsentiteten. Informationen kan vara e-postadress, namn, stad och så vidare. 

-   **Potentiella intressen, potentiella varumärken**: Visar om du har konfigurerat en förstapartsberikning. Den representerar potentiella intressen och samhörigheter för en kund som har en profil som liknar den som kunden har. Mer information finns i [berika kundprofiler med samhörigheter med varumärke och intresse](enrichment-microsoft.md).

-   **Mått**: Visar om du har konfigurerat ett eller flera mått av en specifik typ: kundattributmått. De inkluderar beräknade KPI:er runt dina kunder på den enskilda kundnivån. Mer information finns i [Definiera och hantera mått](measures.md).

-   **Aktivitetstidslinje**: Visar om du har konfigurerat aktiviteter. Vyn tidslinje innehåller kronologiskt sorterade aktiviteter för kunden, med start från den senaste aktiviteten. Mer information finns i [Kundaktiviteter](activities.md).

Välj **Tillbaka till kunder** för att återgå till kundsöksidan.

## <a name="next-steps"></a>Nästa steg

[Lägg till fler datakällor](data-sources.md) eller [Skapa kundsegment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
