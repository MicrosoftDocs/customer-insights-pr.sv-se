---
title: Servicebegränsningar i Dynamics 365 Customer Insights
description: Förstå gränser och begränsningar.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641784"
---
# <a name="service-limits-in-customer-insights"></a>Tjänstbegränsningar i Customer Insights

I den här artikeln beskrivs de inbyggda begränsningarna för Customer Insights-tjänsten som är utformade för att säkerställa tjänstens tillförlitlighet och stabilitet. Alla förfrågningar om ändringar kan göras via [Idéforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Ytdiagram  | Gränser  | OBS! |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segment, mått och förutsägelser | 300  | Totalt antal [segment](segments.md), [mått](measures.md) och [prognoser](predictions.md) får tillsammans inte överstiga 300.  |
| Relationer | 20 djupnivåer för relationer i entitetssökvägar. | När du skapar [segment](segments.md) eller [mått](measures.md) med hjälp av verktygsgränssnittet kan entitetssökvägar ha upp till 20 relationshopp mellan start- och målentiteterna.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
