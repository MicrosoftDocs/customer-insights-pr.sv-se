---
title: Utöka kundprofiler med förbättrade adresser (innehåller videoklipp)
description: Utöka och normalisera adressuppgifter i kundprofiler med Microsoft-modeller.
ms.date: 06/10/2022
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
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081736"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Utöka kundprofiler med förbättrade adresser

Adresser i dina data kan vara oadresserade, ofullständiga eller felaktiga. Med Microsoft-modeller kan du normalisera och utöka adresserna i formatet [Common Data Model](/common-data-model/schema/core/applicationcommon/address) för bättre precision och insikter.

Du kan också [utöka adresser i datakällor](data-sources-enrichment.md) om du vill förbättra matchningsprecisionen i dataföreningsprocessen. 

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

Modellen använder maskininlärningsbaserade tekniker för att förbättra adresser. Precis som med andra maskinutbildningsbaserade modeller är inte hundraprocentig precision garanterat.

## <a name="supported-countries-or-regions"></a>Länder eller regioner som stöds

För närvarande stöder vi ut utöka adresser i dessa länder eller regioner:

- Australien
- Kanada
- Frankrike
- Tyskland
- Italien
- Japan
- Storbritannien och Nordirland
- USA

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **Förbättrade adresser**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skärmbild av panelen Förbättrade adresser.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj **Kunddatauppsättning** och välj den profil eller det segment du vill berika. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Ange hur adresser ska formateras i datauppsättningen. Välj **Adress med ett attribut** om ett enskilt fält används i adresserna i dina data. Välj **Adress med flera attribut** om flera fält används i adresserna i dina data.

1. Välj **Nästa** och mappa adressfälten från entiteten för en enhetlig kund.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Förbättrad sida för adressfältmappning.":::

   > [!NOTE]
   > Land/region är obligatoriskt i adresser med såväl ett som flera attribut. Adresser som inte innehåller giltiga värden för land eller regioner som stöds kommer inte att berikas.

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett **Namn** för berikningen och **utgående enhet**.

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="view-enrichment-results"></a>Visa resultat för berikande

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal berikade kunder efter fält** ger detaljerad information om omfattningen för respektive berikat fält.

### <a name="overview-card"></a>Översiktskort

Kortet **Översikt över kundändringar** innehåller information om omfattningen av berikande:

- **Adresser som bearbetats och ändrats**: Antalet kundprofiler med adresser som har förts vidare.
- **Adresser som bearbetats och inte ändrats**: Antalet kundprofiler med adresser som har erkänts men inte ändrats. Det händer oftast när indata är giltiga och inte kan förbättras av berikningen.
- **Adresser som inte bearbetats och inte ändrats**: Antalet profiler med adresser som inte har erkänts. Vanligtvis för indata som är ogiltiga eller som inte stöds av berikande.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
