---
title: Utöka adressförbättringar (innehåller videoklipp)
description: Utöka och normalisera adressuppgifter i kundprofiler med Microsoft-modeller.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 067757019078d3a46b224ba259d2d097dfbbe381
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353658"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Utöka kundprofiler med förbättrade adresser

Adresser i dina data kan vara oadresserade, ofullständiga eller felaktiga. Med Microsoft-modeller kan du normalisera och utöka adresserna i formatet [Common Data Model](/common-data-model/schema/core/applicationcommon/address) för bättre precision och insikter.

## <a name="how-we-enhance-addresses"></a>Hur vi förbättrar adresser

Vår modell går igenom en process i två steg för att förbättra en adress. Först parsas adressen för att identifiera komponenterna och placerar dem i ett strukturerat format. Därefter använder vi AI för att korrigera, slutföra och standardisera värdena i adressen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Exempel

Adressinformationen kan vara i ett icke-standardformat och innehålla stavningsfel. Modellen kan åtgärda dessa problem och skapa konsekventa adresser i enhetliga kundprofiler.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Begränsningar

Förbättrade adresser fungerar bara med värden som redan finns i dina hämtade adressdata. Modellen kommer inte att: 

1. Kontrollera att adressen är en giltig adress.
2. Kontrollera att något av värdena, t.ex. postnummer eller gatunamn, är giltiga.
3. Ändra värden som inte känns igen.

Modellen använder maskininlärningsbaserade tekniker för att förbättra adresser. Även om vi tillämpar ett tröskelvärde för högt förtroende för när modellen ändrar ett indatavärde kan, precis som med andra maskininlärningsbaserade modeller, hundraprocentig precision inte garanteras.

## <a name="supported-countries-or-regions"></a>Länder eller regioner som stöds

För närvarande stöder vi ut utöka adresser i dessa länder eller regioner: 

- Australien
- Kanada
- Frankrike
- Tyskland
- Italien
- Japan
- Storbritannien
- USA

Adresserna måste innehålla ett land-/regionvärde. Vi behandlar inte adresser för länder eller regioner som inte har stöd och adresser som inte har angetts av något land eller en region.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning**.

1. Välj **Utöka mina data** på panelen **Förbättrade adresser**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skärmbild av panelen Förbättrade adresser.":::

1. Välj **Kunddatauppsättning** och välj den entitet som innehåller de adresser du vill utöka. Du kan välja entiteten *Kund* om du vill utöka adresser i alla kundprofiler eller välja en segmententitet om du endast vill utöka adresser i kundprofiler inom det segmentet.

1. Ange hur adresser ska formateras i datauppsättningen. Välj **Adress med ett attribut** om ett enskilt fält används i adresserna i dina data. Välj **Adress med flera attribut** om flera fält används i adresserna i dina data.

   > [!NOTE]
   > Land/region är obligatoriskt i adresser med såväl ett som flera attribut. Adresser som inte innehåller giltiga värden för land eller regioner som stöds kommer inte att berikas.

1.  Mappa adressfälten från en enhetlig kundentitet.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Förbättrad sida för adressfältmappning.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett namn för berikningen och den utgående enheten.

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på dina kunddata.

När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan visa ett exempel på utökade data i panelen **Förhandsgranskning av berikade kunder**. Välj **Visa mer** och välj fliken **Data** om du vill få tillgång till en detaljerad vy över alla profiler.

### <a name="overview-card"></a>Översiktskort

Översiktskort innehåller information om omfattningen av berikande. 

* **Adresser som bearbetats och ändrats**: Antalet kundprofiler med adresser som har förts vidare.

* **Adresser som bearbetats och inte ändrats**: Antalet kundprofiler med adresser som har erkänts men inte ändrats. Det händer oftast när indata är giltiga och inte kan förbättras av berikningen.

* **Adresser som inte bearbetats och inte ändrats**: Antalet profiler med adresser som inte har erkänts. Vanligtvis för indata som är ogiltiga eller som inte stöds av berikande.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
