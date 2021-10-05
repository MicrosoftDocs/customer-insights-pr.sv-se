---
title: Lägg till koden till webbplatsen
description: Så här lägger du till ett kodavsnitt för att samla in Dynamics 365 Customer Insights-händelser på din webbplats.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558933"
---
# <a name="install-the-web-sdk-on-a-website"></a>Installera webb-SDK på en webbplats

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I artikeln beskrivs hur en administratör installerar webbverktyget SDK (Web Software Development Toolkit) på en webbplats. Kort efter arrangemanget av webbplatsen börjar händelser visas på din arbetsyta. För mer information, se [Hantera arbetsytor och miljö](manage-environments-workspaces.md). Information om hur du samlar in händelser i mobilappar finns i [Översikt över utvecklarresurser](developer-resources.md).


### <a name="prerequisites"></a>Förutsättningar

* Du måste ha administratör behörighet för arbetsytan för att kunna lagra data.
* Din webbplats eller ditt projekt måste vara online för att skicka aktivitetsdata. Data som skickas från en lokal fil accepteras inte av servern.


## <a name="add-web-sdk-to-your-website"></a>Lägg till webb-SDK på din webbplats

Gå till **Administratör** > **Arbetsyta** och välj sedan **Installationsguide**. Det finns två alternativ för att installera webb-SDK. Det första är att använda en hämtningslänk och det andra är att installera ett nodpaketverktyg (NPM, Node Package Manager).

### <a name="option-1-using-the-download-link"></a>Alternativ 1: Använda hämtningslänk

1. Välj **Kopiera kod** om du vill kopiera kodavsnitt. Som standard är insamlingsnyckeln för arbetsytan i kodavsnitt.
  :::image type="content" source="media/copy-code.png" alt-text="Skärmdump av sidan kodavsnitt.":::

1. Lägg till den kopierade koden på din webbplats nära <head> taggen och innan några andra skript eller CSS-taggar.
1. Publicera den uppdaterade webbplatsen och vänta några minuter med att registrera den inkommande webbtrafiken.
1. Om du vill visa dina data markerar du arbetsytan i arbetsyteväljaren i navigeringsfönstret. Välj sedan en av rapporterna i avsnittet **Upptäck** Upptäck.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Alternativ 2: Använda nodpaketverktyget (rekommenderas för JavaScript-baserade webbappar)

1. Gå till vår [NPM-webbsida](https://www.npmjs.com/package/engagementinsights-web) och följ instruktionerna för att installera och konfigurera nodpaketverktyget för webb-SDK.
1. Publicera den uppdaterade webbplatsen och vänta några minuter med att registrera den inkommande webbtrafiken.
1. Om du vill visa dina data markerar du arbetsytan i arbetsyteväljaren i navigeringsfönstret. Välj sedan en av rapporterna i avsnittet **Upptäck** Upptäck.

## <a name="configuration-options"></a>Konfigurationsalternativ

Du kan ändra följande konfigurationsalternativ i koden för kodavsnitt:

- **ingestionKey**: Den insamlingsnyckel som används för att skicka händelser till din arbetsyta. Du kan ändra insamlingsnyckeln om du vill skicka händelser till en annan arbetsyta. En insamlingsnyckel är unik för varje arbetsyta.
- **autoCapture**: Anger om sidvisningar och interaktioner med webbplatsen samlas in. Den har två alternativ:
    - **vy**: Ange till *true* för att samla in sidvyer. Sidvyer visas som *Vy* [händelser](glossary.md#event), en typ [bashändelse](glossary.md#base-event).
    - **klicka**: Ange till *true* för att samla in besökarens interaktioner på webbplatsen. Interaktioner samlas in som *Åtgärd* [händelser](glossary.md#event), en typ av [bashändelse](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
