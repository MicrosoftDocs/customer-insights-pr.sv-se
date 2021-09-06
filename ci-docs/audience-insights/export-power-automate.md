---
title: Power Automate anslutningsprogram | Microsoft Docs
description: Skapa flöden i Microsoft Power Automate från Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 95e0fcbfb43f2b3e7e2d0e8a1690dc7ff5a44433402b7ef3d437710eb0efff15
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035621"
---
# <a name="power-automate-connector-preview"></a>Power Automate anslutningsprogram (förhandsversion)

Utlös specifika händelser automatiskt när data ändras och hantera mer komplicerade flöden direkt i [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate-utlösare

Med utlösare kan du skapa molnflöden och automatisera repetitiva uppgifter, till exempel meddelanden eller mer avancerade åtgärder. 

- Utlöses när en uppdatering av en datakälla misslyckas. 
- Utlöses när en uppdatering av en datakälla lyckas.
- Utlöses när ett tröskelvärde passeras i ett segment. Utlösaren begränsas till att passera över tröskelvärdet.
- Utlöses när ett tröskelvärde passeras i ett affärsmått. Endast affärsmått utan dimension stöds. Utlösaren begränsas till att passera över tröskelvärdet.
- Utlösa när en fullständig uppdatering av (datakällor, segment, mått ...) har slutförts.
- Utlöses när en uppdatering av föreningsprocessen (mappning, matchning, sammanslagning) har slutförts.

[Konfigurera utlösarna i Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-åtgärder

Power Automate-anslutaren tillhandahåller andra åtgärder än de tillgängliga utlösarna. Mer information finns i [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Skapa ett Power Automate-flöde

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. I panelen **Power Automate**, välj **Konfigurera**.

1. Customer Insights-anslutningsprogrammet (förhandsversion) i Power Automate öppnas. **Logga in på** till Power Automate.

1. Välj en av de tillgängliga utlösarna och lägg till fler steg i det nya flödet. Mer information finns i [Skapa ett molnflöde i Power Automate](/power-automate/get-started-logic-flow).

Exempel på hur flöden kan användas: 
- Publicera ett meddelande till en Microsoft Teams-kanal om en datakälla inte går att uppdatera. 
- Skicka ett e-postmeddelande till dataägarna när en tröskel för ett segment överskrids.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
