---
title: Power Automate anslutningsprogram | Microsoft Docs
description: Skapa flöden i Microsoft Power Automate från Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407061"
---
# <a name="power-automate-connector-preview"></a>Power Automate anslutningsprogram (förhandsversion)

Utlös specifika händelser automatiskt när data ändras och hantera mer komplicerade flöden direkt i [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate-utlösare

Du kan använda en mängd olika utlösare som gör det möjligt att skapa flöden för att automatisera återkommande uppgifter, till exempel aviseringar eller mer avancerade åtgärder. 

- Utlöses när en uppdatering av en datakälla misslyckas. 
- Utlöses när en uppdatering av en datakälla lyckas.
- Utlöses när ett tröskelvärde passeras i ett segment. Utlösaren begränsas till att passera över tröskelvärdet.
- Utlöses när ett tröskelvärde passeras i ett affärsmått. Utlösaren begränsas till att passera över tröskelvärdet.
- Utlösa när en fullständig uppdatering av (datakällor, segment, mått ...) är slutförd.
- Utlöses när en uppdatering av föreningsprocessen (mappning, matchning, sammanslagning) har slutförts.

[Konfigurera utlösarna i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate-åtgärder
Power Automate-anslutaren tillhandahåller andra åtgärder än de tillgängliga utlösarna. Mer information finns i [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Skapa ett Power Automate-flöde i målgruppsinsikter

1. I målgruppsinsikter går du till **Admin** > **System**.

1. På sidan **System**, välj fliken **Status**.

1. I avsnittet **Datakällor**, välj **Flöden** och välj **Skapa ett flöde** i den nedrullningsbara listan.
   > [!div class="mx-imgBorder"]
   > ![Power Automate anslutningsprogram med skapa en flödesåtgärd](media/power-automate-connector-create-flow.png "Power Automate anslutningsprogram med skapa en flödesåtgärd")

1. I Power Automate väljer du en av de tillgängliga utlösarna för att skapa det önskade flödet. Om du skapar ditt första flöde måste du först autentisera med Power Automate-anslutningen.
