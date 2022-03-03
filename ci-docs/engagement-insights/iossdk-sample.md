---
title: Kör iOS SDK-exemplet
description: Exempelprojekt som lär dig mer om iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232864"
---
# <a name="run-the-ios-sdk-sample"></a>Kör iOS SDK-exemplet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Detta iOS-exempelprojekt hjälper dig att förstå hur SDK fungerar i en app. Du behöver inte skriva kod. Lägg bara till inmatningsnyckeln, så visas händelser på arbetsytan direkt.

## <a name="prerequisites"></a>Förutsättningar

- [Xcode version 9+](https://developer.apple.com/xcode/downloads/)
- [Inmatningsnyckel](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Ladda ner iOS-appexemplet

1. [Hämta iOS SDK-exemplet för engagemangsinsikter](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Packa upp den komprimerade filen `ei-ios-sample.zip`.
1. Öppna exempelapprojektet i Xcode.
1. I filen `EIConfig.plist` ersätter du strängen `“YOUR-INGESTION-KEY”` i fältet `ingestionKey` med din inmatningsnyckel för arbetsyta från engagemangsinsikterna under **Administratör** > **Arbetsyta** > **Installationsguide**.
1. Välj **Kör** om du vill starta exempelprojektet.
1. Visa händelserna på arbetsytan.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
