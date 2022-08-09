---
title: Power Automate anslutningsprogram (förhandsversion) | Microsoft Docs
description: Skapa flöden i Microsoft Power Automate från Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196140"
---
# <a name="power-automate-connector-preview"></a>Power Automate anslutningsprogram (förhandsversion)

Utlös specifika händelser automatiskt när data ändras och hantera mer komplicerade flöden direkt i [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Kända begränsningar

- Du kan göra maximalt 100 samtal per 60 sekunder. Använd [$skip-parameter](/connectors/customerinsights/#get-items-from-an-entity) att anropa API-slutpunkten flera gånger.

## <a name="power-automate-triggers"></a>Power Automate-utlösare

Med utlösare kan du skapa molnflöden och automatisera repetitiva uppgifter, till exempel meddelanden eller mer avancerade åtgärder. Använd utlösare när:

- En uppdatering av datakälla misslyckas.
- En uppdatering av datakällan lyckas.
- Tröskelvärde passeras i ett segment. Utlösaren begränsas till att passera över tröskelvärdet.
- Ett tröskelvärde passeras i ett affärsmått. Endast affärsmått utan dimension stöds. Utlösaren begränsas till att passera över tröskelvärdet.
- En fullständig schemalagd uppdatering är klar. Den här utlösaren fungerar inte för uppdateringar som startas manuellt.
- En uppdatering av föreningsprocessen är klar.

[Konfigurera utlösarna i Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-åtgärder

Power Automate-anslutaren tillhandahåller andra åtgärder än de tillgängliga utlösarna. Mer information finns i [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Skapa ett Power Automate-flöde

1. Gå till **Admin** > **Anslutningar**.

1. I panelen **Power Automate**, välj **Konfigurera**.

1. Customer Insights-anslutningsprogrammet (förhandsversion) i Power Automate öppnas. **Logga in på** till Power Automate.

1. Välj en av de tillgängliga utlösarna och lägg till fler steg i det nya flödet. Mer information finns i [Skapa ett molnflöde i Power Automate](/power-automate/get-started-logic-flow).

Exempel på hur flöden kan användas: 
- Publicera ett meddelande till en Microsoft Teams-kanal om en datakälla inte går att uppdatera. 
- Skicka ett e-postmeddelande till dataägarna när en tröskel för ett segment överskrids.

[!INCLUDE [footer-include](includes/footer-banner.md)]
