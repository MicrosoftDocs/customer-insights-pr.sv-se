---
title: Köra ett exempel på webb-SDK
description: Lär dig hur du anpassar och kör ett exempel på webb-SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225353"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Kör exempel på webb-SDK för funktionen Dynamics 365 Customer Insights engagemangsinsikter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funktionen engagemangsinsikter webb-SDK bibliotek är JavaScript-bibliotek med exempelkod som du kan använda på din webbplats.

## <a name="prerequisites"></a>Förutsättningar

- Installera [Visual Studio Code](https://code.visualstudio.com/).
- [Installera Live Server-tillägget](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) i Visual Studio Code och bekanta dig med hur du kör Live Server.
- Du måste ha en [Arbetsyta för engagemangsinsikter](create-workspace.md).

## <a name="run-sample"></a>Kör exempel

1. [Ladda ned exempel på webb-SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Packa upp den komprimerade filen `ei_websdk_sample.zip`.

1. Öppna den uppackade mappen i Visual Studio Code.

1. Gå till portalen för engagemangsinsikter för din arbetsyta. Välj **Admin** > **Arbetsyta** och sedan **Installationshandbok**. Följ det första alternativet och välj **Kopiera kod** för att kopiera JavaScript-kodavsnitt.

1. I `ei_websdk_sample.html` fil, klistra in kodavsnittet som du just kopierade under den här raden:

   - <-- KLISTRA IN JAVASCRIPT-KODAVSNITT FRÅN PORTALEN ENGAGEMANGSINSIKTER HÄR NEDANFÖR RADEN -->

1. Öppna filen `ei_websdk_sample.html` med Live Server i Visual Studio Code genom att välja **Publicera** från statusfältet.

1. När en vyhändelse öppnas ska den skickas automatiskt. Om du klickar på någon av knapparna på sidan skickas åtgärdshändelser. Knappen **Spåra händelser** skickar även anpassade händelser. Om du väljer knappen **Gå till Bing** skickas en åtgärdshändelse innan du navigerar till Bing-webbplats.

1. Titta på händelser som strömmas när du navigerar till arbetsytan. Den här arbetsytan associeras med insamlingsnyckeln som anges i steg 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
