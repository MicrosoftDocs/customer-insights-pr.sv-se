---
title: Berika företagsprofiler med berikade företagsdata
description: Utöka och normalisera företagsdata med Microsoft-modeller.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054270"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Berika företagsprofiler med berikade företagsdata

Använd Microsoft-modeller och kompilerade företagsdata för att korrigera, komplettera och standardisera dina företagsprofiler. Vi använder [formatet Common Data Model](/common-data-model/schema/core/applicationcommon/account) för bättre precision och insikter.

Du kan också [utöka företagsdata i datakällor](data-sources-enrichment.md) om du vill förbättra matchningsprecisionen i dataföreningsprocessen.

För offentliga företag i USA är information som intäkter, börssymbol, bransch med mera tillgänglig.  

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

Modellen kommer inte att:

- Bekräfta företagets identitet. Vi kontrollerar inte om indata är en befintlig organisation eller om ett företag använder utdata som standardnamn.
- Täcker företag globalt. Microsofts sammanställda företagsdata har global täckning, men erbjuder mest täckning i Australien, Kanada, Storbritannien och USA.
- Standardisera företagsadresser globalt. Vi stöder för närvarande standardiserade adresser i dessa länder eller regioner: Australien, Kanada, Frankrike, Tyskland, Italien, Japan, Storbritannien och USA.
- Garanterar att data är korrekta eller nya. När affärsinformationen ofta ändras kan vi inte garantera att den förbättrade företagsdatan alltid är exakt eller uppdaterad.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **Berikade företagsdata**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Panelen Berika i berikningsnavet för företagsdata.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj **Kunddatauppsättning** och välj den profil eller det segment du vill berika. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Välj vilken typ av fält i dina företagsprofiler som ska användas för att matcha med Microsofts kompilerade företagsdata. Det här valet påverkar mappningsfälten du har åtkomst till i nästa steg.

1. Välj **Nästa**.

1. Mappa dina företagsfält till företagsdata från Microsoft. Lägg till fler fält för bättre matchningsnoghet.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datamappningssteg när du konfigurerar ett företagsberikning.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett **Namn** för berikningen och **utgående enhet**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="view-enrichment-results"></a>Visa resultat för berikande

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Översiktskort

Panelen **Översikt över kundändringar** innehåller information om omfattningen av berikande

- **Företag som bearbetats och ändrats**: Antalet kundföretagsprofiler som har förts vidare.
- **Företag som bearbetats och inte ändrats**: Antalet kundföretagsprofiler som har erkänts men inte ändrats. Det händer oftast när indata är giltiga och inte kan förbättras av berikningen.
- **Företag som inte bearbetats och inte ändrats**: Antalet kundföretagsprofiler som inte har erkänts. Detta sker vanligtvis för indata som är ogiltiga eller som inte stöds av berikande.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
