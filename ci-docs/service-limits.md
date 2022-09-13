---
title: Tjänstbegränsningar i Customer Insights
description: Att förstå begränsningar i Customer Insights SaaS-tjänsten.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411807"
---
# <a name="service-limits-in-customer-insights"></a>Tjänstbegränsningar i Customer Insights

 Customer Insights har inbyggda gränser utformade för att säkerställa tjänstens tillförlitlighet och stabilitet. Alla förfrågningar om ändringar kan göras via [Idéforum](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Ytdiagram  | Gränser  | OBS! |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segment, mått och förutsägelser | 300  | Totalt antal [segment](segments.md), [mått](measures.md) och [prognoser](predictions-overview.md) får tillsammans inte överstiga 300.  |
| Relationer | 20 djupnivåer för relationer i entitetssökvägar. | När du skapar [segment](segments.md) eller [mått](measures.md) med hjälp av verktygsgränssnittet kan entitetssökvägar ha upp till 20 relationshopp mellan start- och målentiteterna.  |

## <a name="fair-scheduling-of-jobs"></a>Rättvis schemaläggning av jobb

Customer Insights är en SaaS-tjänst som använder delade Azure-resurser. Kunder har olika arbetsbelastning och har olika scheman. För att säkerställa en god åtkomst till de underliggande resurserna ser vi till att systemprocesserna utförs i rätt ordning. Exempel på systemprocesser är jobb relaterade till data, segmentuppdateringar eller måttberäkning. Med en schysst schemaläggning skyddas du från att köa för resurser om det finns många begärda jobb. Samtidigt kan Customer Insights inte garantera att alla jobb som du köar bearbetas samtidigt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
