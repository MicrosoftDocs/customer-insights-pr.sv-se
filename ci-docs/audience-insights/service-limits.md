---
title: Tjänstbegränsningar
description: Förstå gränser och begränsningar.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034886"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Tjänstbegränsningar i funktionen målgruppsinsikter i Dynamics 365 Customer Insights

I den här artikeln beskrivs de inbyggda begränsningarna för Customer Insights-tjänsten som är utformade för att säkerställa tjänstens tillförlitlighet och stabilitet. Alla förfrågningar om ändringar kan göras via [Idéforum](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Ytdiagram  | Gränser  | OBS! |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segment och mått | 100 segment eller mått. | Det totala antalet aktiva [segment](segments.md) och [mått](measures.md) kan inte tillsammans överstiga 100.  |
| Relationer | 20 djupnivåer för relationer i entitetssökvägar. | När du skapar [segment](segments.md) eller [mått](measures.md) med hjälp av verktygsgränssnittet kan entitetssökvägar ha upp till 20 relationshopp mellan start- och målentiteterna.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]