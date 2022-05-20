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
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741201"
---
# <a name="power-automate-connector-preview"></a>Power Automate anslutningsprogram (förhandsversion)

Utlös specifika händelser automatiskt när data ändras och hantera mer komplicerade flöden direkt i [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Kända begränsningar

- Du kan göra maximalt 100 samtal per 60 sekunder. Du kan anropa API-slutpunkt flera gånger med hjälp $skip parametern. [Läs mer om parametern $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate-utlösare

Med utlösare kan du skapa molnflöden och automatisera repetitiva uppgifter, till exempel meddelanden eller mer avancerade åtgärder.

- Utlöses när en uppdatering av en datakälla misslyckas.
- Utlöses när en uppdatering av en datakälla lyckas.
- Utlöses när ett tröskelvärde passeras i ett segment. Utlösaren begränsas till att passera över tröskelvärdet.
- Utlöses när ett tröskelvärde passeras i ett affärsmått. Endast affärsmått utan dimension stöds. Utlösaren begränsas till att passera över tröskelvärdet.
- Utlösa när en fullständig uppdatering av (datakällor, segment, mått ...) har slutförts.
- Utlöses när en uppdatering av föreningsprocessen är klar.

[Konfigurera utlösarna i Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-åtgärder

Power Automate-anslutaren tillhandahåller andra åtgärder än de tillgängliga utlösarna. Mer information finns i [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Skapa ett Power Automate-flöde

1. Gå till **Administratör** > **Exportera mål**.

1. I panelen **Power Automate**, välj **Konfigurera**.

1. Customer Insights-anslutningsprogrammet (förhandsversion) i Power Automate öppnas. **Logga in på** till Power Automate.

1. Välj en av de tillgängliga utlösarna och lägg till fler steg i det nya flödet. Mer information finns i [Skapa ett molnflöde i Power Automate](/power-automate/get-started-logic-flow).

Exempel på hur flöden kan användas: 
- Publicera ett meddelande till en Microsoft Teams-kanal om en datakälla inte går att uppdatera. 
- Skicka ett e-postmeddelande till dataägarna när en tröskel för ett segment överskrids.



[!INCLUDE [footer-include](includes/footer-banner.md)]
