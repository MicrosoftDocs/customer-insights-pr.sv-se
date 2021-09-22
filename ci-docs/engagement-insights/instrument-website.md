---
title: Lägg till koden till webbplatsen
description: Så här lägger du till ett kodavsnitt för att samla in händelser på webbplatsen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035116"
---
# <a name="install-the-code-snippet-on-a-website"></a>Installera kodavsnitt på en webbplats

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I den här artikeln beskrivs hur administratören installerar kodavsnitt på en webbplats. Du kommer snart att börja se händelser på arbetsytan när du har lagt till skriptet på webbplatsen. För mer information, se [Hantera arbetsytor och miljö](manage-environments-workspaces.md). Information om hur du samlar in händelser i mobilappar finns i [Översikt över utvecklarresurser](developer-resources.md).


### <a name="prerequisites"></a>Förutsättningar

* Du måste ha administratör behörighet för arbetsytan för att kunna lagra data.
* Din webbplats eller ditt projekt måste vara online för att skicka aktivitetsdata. Data som skickas från en lokal fil accepteras inte av servern.


## <a name="add-code-to-your-website"></a>Lägg till koden till webbplatsen
1.  Gå till **Administratör** > **Arbetsyta** och välj sedan **Installationsguide**.
1. Välj **Kopiera kod** om du vill kopiera kodavsnitt. Som standard är insamlingsnyckeln för arbetsytan i kodavsnitt.
:::image type="content" source="media/copy-code.png" alt-text="Skärmdump av sidan kodavsnitt.":::
3. Lägg till den kopierade kodavsnitt till webbplatsen, nära <head> taggen och innan några andra skript eller CSS-taggar.
4.  Publicera den uppdaterade webbplatsen och vänta några minuter med att registrera den inkommande webbtrafiken.
5.  Om du vill visa dina data markerar du arbetsytan i arbetsyteväljaren i navigeringsfönstret. Välj sedan en av rapporterna i avsnittet **Upptäck** Upptäck.

## <a name="configuration-options"></a>Konfigurationsalternativ

Du kan ändra följande konfigurationsalternativ i koden för kodavsnitt:

- **ingestionKey**: Den insamlingsnyckel som används för att skicka händelser till din arbetsyta. Du kan ändra insamlingsnyckeln om du vill skicka händelser till en annan arbetsyta. En insamlingsnyckel är unik för varje arbetsyta. 
- **autoCapture**: Anger om sidvisningar och interaktioner med webbplatsen samlas in. Den har två alternativ:
    - **vy**: Ange till *true* för att samla in sidvyer. Sidvyer visas som *Vy* [händelser](glossary.md#event), en typ [bashändelse](glossary.md#base-event).
    - **klicka**: Ange till *true* för att samla in besökarens interaktioner på webbplatsen. Interaktioner samlas in som *Åtgärd* [händelser](glossary.md#event), en typ av [bashändelse](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
