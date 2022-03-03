---
title: Power Automate anslutningsprogram | Microsoft Docs
description: Skapa flöden i Microsoft Power Automate från Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dc9bbe22b7f10cf92f06cae18fbece9808b87dce
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226736"
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
