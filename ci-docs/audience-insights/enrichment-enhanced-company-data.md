---
title: Berikning av företagsdata
description: Utöka och normalisera företagsdata med Microsoft-modeller.
ms.date: 12/16/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 616efe723313a6fbec7f1c7219c236a8f0aab3b2
ms.sourcegitcommit: e141a6a34a985cca68f03082a700ed27f2f3c0c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2021
ms.locfileid: "7927604"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Berika företagsprofiler med berikade företagsdata

Använd Microsoft-modeller och kompilerade företagsdata för att korrigera, komplettera och standardisera dina företagsprofiler. Vi använder [formatet Common Data Model](/common-data-model/schema/core/applicationcommon/account) för bättre precision och insikter.

## <a name="how-we-enhance-company-data"></a>Hur vi berikar företagsdata

Vår modell går igenom en process i två steg för att förbättra en företagsprofil. Först normaliseras företagsnamnet. Exempelvis korrigeras och standardiseras *Microsoft Corp* till *Microsoft Corporation*. Den försöker hitta en matchning i Microsofts kompilerade företagsdata. Om en matchning hittas utökar vi företagsprofilen med information från vårt sammanställda företagsdata, inklusive företagsnamnet.


### <a name="example"></a>Exempel

Företagsinformation kanske inte följer ett standardiserat format och innehåller stavningsfel. Modellen försöker åtgärda dessa problem och skapa enhetlig information.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Begränsningar

Det finns några begränsningar med den förbättrade informationen. Objekten i listan nedan stöds inte av modellen.

1.  Bekräfta företagets identitet. Vi kontrollerar inte om indata är en befintlig organisation eller om ett företag använder utdata som standardnamn.
2.  Täcker företag globalt. Microsofts sammanställda företagsdata har global täckning, men erbjuder mest täckning i Australien, Kanada, Storbritannien och USA.
3.  Standardisera företagsadresser globalt. Vi stöder för närvarande standardiserade adresser i dessa länder eller regioner: Australien, Kanada, Frankrike, Tyskland, Italien, Japan, Storbritannien och USA.
4.  Garanterar att data är korrekta eller nya. När affärsinformationen ofta ändras kan vi inte garantera att den förbättrade företagsdatan alltid är exakt eller uppdaterad.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning**.

1. Välj **Utöka mina data** på panelen **Berikade företagsdata**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Panelen Berika i berikningsnavet för företagsdata.":::

1. Välj **Kunddatauppsättning** och välj den entitet som innehåller de adresser du vill utöka. Du kan välja entiteten *Kund* om du vill utöka adresser i alla kundprofiler eller välja en segmententitet om du endast vill utöka adresser i kundprofiler inom det segmentet.

1. Välj vilken typ av fält i dina företagsprofiler som ska användas för att matcha med Microsofts kompilerade företagsdata. Det här valet påverkar mappningsfälten du har åtkomst till i nästa steg.

1.  Mappa företagsfälten från en enhetlig kundentitet. Ju fler nyckelidentifierare och fält du mappar, desto större chans har du att få en högre matchningstakt.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datamappningssteg när du konfigurerar ett företagsberikning.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett namn för berikningen och den utgående enheten.

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på dina kunddata.

När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive utökad profil genom att markera **Visa utökade data**.

### <a name="overview-card"></a>Översiktskort

Översiktskort innehåller information om omfattningen av berikande. 

* **Kunder som bearbetats och ändrats**: Antalet kundprofiler som har förts vidare.

* **Kunder som bearbetats och inte ändrats**: Antalet kundprofiler som har erkänts men inte ändrats. Det händer oftast när indata är giltiga och inte kan förbättras av berikningen.

* **Kunder som inte bearbetats och inte ändrats**: Antalet profiler som har erkänts men inte erkänts. Vanligtvis för indata som är ogiltiga eller som inte stöds av berikande.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
