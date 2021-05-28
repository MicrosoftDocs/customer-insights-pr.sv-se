---
title: Utöka adressförbättringar
description: Utöka och normalisera adressuppgifter i kundprofiler med Microsoft-modeller.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965600"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Utöka kundprofiler med förbättrade adresser

Adresser i dina data kan vara oadresserade, ofullständiga eller felaktiga. Med Microsoft-modeller kan du normalisera och utöka adresserna i formatet [Common Data Model](/common-data-model/schema/core/applicationcommon/address) för bättre precision och insikter.

## <a name="how-we-enhance-addresses"></a>Hur vi förbättrar adresser

Vår modell går igenom en process i två steg för att förbättra en adress. Först parsas adressen för att identifiera komponenterna och placerar dem i ett strukturerat format. Sedan använder vi intelligent information för att korrigera, slutföra och standardisera värdena i adressen.

### <a name="example"></a>Exempel

Adressinformationen kan vara i ett annat format än standardformatet och innehålla stavningsfel. Modellen kan åtgärda dessa problem och skapa konsekventa adresser i enhetliga kundprofiler.

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

Modellen använder maskininlärningsbaserade tekniker för att förbättra adresser. Vi tillämpar ett högt förtroendevärde för när modellen ändrar ett indatavärde, precis som med andra 100 %-baserade modeller.

## <a name="supported-countries-or-regions"></a>Länder eller regioner som stöds

För närvarande stöder vi ut utöka adresser i dessa länder eller regioner: 

- Australien
- Kanada
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
   > Land/region är obligatoriskt både i adress med ett attribut och med flera attribut. Adresser som inte innehåller giltiga värden för land eller regioner som stöds kommer inte att berikas

1.  Mappa adressfälten från en enhetlig kundentitet.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Förbättrad sida för adressfältmappning.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett namn för berikningen och den utgående enheten.

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på dina kunddata.

När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.

[!INCLUDE[footer-include](../includes/footer-banner.md)]