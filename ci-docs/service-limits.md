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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350429"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Tjänstebegränsningar i Customer Service-funktioner

I den här artikeln beskrivs de inbyggda begränsningarna för Customer Insights-tjänsten som är utformade för att säkerställa tjänstens tillförlitlighet och stabilitet. Alla förfrågningar om ändringar kan göras via [Idéforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Målgruppsinsikter

| Ytdiagram  | Gränser  | OBS! |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segment, mått och förutsägelser | 300  | Totalt antal [segment](audience-insights/segments.md), [mått](audience-insights/measures.md) och [prognoser](audience-insights/predictions.md) får tillsammans inte överstiga 300.  |
| Relationer | 20 djupnivåer för relationer i entitetssökvägar. | När du skapar [segment](audience-insights/segments.md) eller [mått](audience-insights/measures.md) med hjälp av verktygsgränssnittet kan entitetssökvägar ha upp till 20 relationshopp mellan start- och målentiteterna.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
