---
title: Servicebegränsningar i Dynamics 365 Customer Insights
description: Förstå gränser och begränsningar.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7792002"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Tjänstebegränsningar i Customer Service-funktioner

I den här artikeln beskrivs de inbyggda begränsningarna för Customer Insights-tjänsten som är utformade för att säkerställa tjänstens tillförlitlighet och stabilitet. Alla förfrågningar om ändringar kan göras via [Idéforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Målgruppsinsikter

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Tjänstbegränsningar i funktionen målgruppsinsikter i Dynamics 365 Customer Insights

| Ytdiagram  | Gränser  | OBS! |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segment, mått och förutsägelser | 300  | Totalt antal [segment](audience-insights/segments.md), [mått](audience-insights/measures.md) och [prognoser](audience-insights/predictions.md) får tillsammans inte överstiga 300.  |
| Relationer | 20 djupnivåer för relationer i entitetssökvägar. | När du skapar [segment](audience-insights/segments.md) eller [mått](audience-insights/measures.md) med hjälp av verktygsgränssnittet kan entitetssökvägar ha upp till 20 relationshopp mellan start- och målentiteterna.  |


## <a name="engagement-insights"></a>Engagemangsinsikter

### <a name="workspace-and-event-quotas"></a>Kvoter för arbetsytor och händelser

Engagemangsinsikter är ett mycket skalbart program som kan stödja miljoner händelser i sekunden. Under en offentlig förhandsgranskning har händelser ett volymtröskelvärde. Det finns också en begränsning för antalet arbetsytor i en organisation.

### <a name="engagement-insights-limits"></a>Begränsningar av engagemangsinsikter

- Maximal händelsevolym per arbetsyta = 100 händelser per sekund

- Maximalt antal arbetsytor per organisation = 100

Om händelser överskrider tröskelvärdet kan det leda till att data i rapporter som bygger på dessa händelser går förlorade. Du kan [kontakta supporten](https://go.microsoft.com/fwlink/?linkid=2145734) om du vill begära en volymökning innan du överskrider gränserna. Vi arbetar med dig för att fastställa behovet av en volymökning och stödja din begäran.


[!INCLUDE[footer-include](includes/footer-banner.md)]
