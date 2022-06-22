---
title: Tjänstbegränsningar i Customer Insights
description: Att förstå begränsningar i Customer Insights SaaS-tjänsten.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940690"
---
# <a name="service-limits-in-customer-insights"></a>Tjänstbegränsningar i Customer Insights

I den här artikeln beskrivs de inbyggda begränsningarna för Customer Insights-tjänsten som är utformade för att säkerställa tjänstens tillförlitlighet och stabilitet. Alla förfrågningar om ändringar kan göras via [Idéforum](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Ytdiagram  | Gränser  | OBS! |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segment, mått och förutsägelser | 300  | Totalt antal [segment](segments.md), [mått](measures.md) och [prognoser](predictions.md) får tillsammans inte överstiga 300.  |
| Relationer | 20 djupnivåer för relationer i entitetssökvägar. | När du skapar [segment](segments.md) eller [mått](measures.md) med hjälp av verktygsgränssnittet kan entitetssökvägar ha upp till 20 relationshopp mellan start- och målentiteterna.  |

## <a name="fair-scheduling-of-jobs"></a>Rättvis schemaläggning av jobb

Customer Insights är en SaaS-tjänst som använder delade Azure-resurser. Kunder har olika arbetsbelastning och har olika scheman. För att säkerställa en god åtkomst till de underliggande resurserna ser vi till att systemprocesserna utförs i rätt ordning. Exempel på systemprocesser är jobb relaterade till data, segmentuppdateringar eller måttberäkning. Med en schysst schemaläggning skyddas du från att köa för resurser om det finns många begärda jobb. Samtidigt kan Customer Insights inte garantera att alla jobb som du köar bearbetas samtidigt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
