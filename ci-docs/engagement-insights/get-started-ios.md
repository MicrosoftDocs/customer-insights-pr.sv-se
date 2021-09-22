---
title: Kom i gång med iOS SDK
description: Lär dig anpassa och köra iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036895"
---
# <a name="get-started-with-the-ios-sdk"></a>Kom i gång med iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denna självstudie guidar dig genom processen för att arrangera ditt iOS-program med en Dynamics 365 Customer Insights-SDK för engagemangsinsikter. Du kommer att börja se händelser i portalen inom fem minuter eller tidigare.

## <a name="configuration-options"></a>Konfigurationsalternativ

Följande konfigurationsalternativ kan skickas till SDK via den medföljande filen `EIConfig.plist`:

- **indionKey**: Den Inmatningsyckel som används för att skicka händelser till ditt projekt.
- **autocollectAction**: Ett booleskt värde som aktiverar eller inaktiverar automatisk instrumentering av åtgärdshändelsen.
- **autocollectView**: Ett booleskt värde som aktiverar eller inaktiverar automatisk instrumentering av visningshändelsen.
- **endpointUrl**: Den slutpunkts-URL där händelserna ska dirigeras.

## <a name="prerequisites"></a>Förutsättningar

- Xcode version 9+
- iOS-version 8.2+
- En inmatningsyckel (se instruktionerna nedan för information om hur du hämtar)

## <a name="integrate-the-sdk-into-your-application"></a>Integrera SDK i programmet

Påbörja processen genom att välja en arbetsyta att arbeta i, välja iOS-mobilplattformen och hämta SDK.

- Använd arbetsyteväljaren i det vänstra navigeringsfönstret för att välja din arbetsyta.

- Om du inte har en befintlig arbetsyta väljer du **Ny arbetsyta** och följer stegen för att skapa en [ny arbetsyta](create-workspace.md).

## <a name="configure-the-sdk"></a>Konfigurera SDK

När du har hämtat SDK kan du arbeta med det i Xcode för att aktivera och definiera händelser.

1. När du har skapat en arbetsyta går du till **Administratör** > **Arbetsyta** och väljer sedan **Installationshandbok**.

1. Hämta [iOS-SDK för engagemangsinsikter](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) och placera filen `EIObjC.xcframework` i mappen `Frameworks`.

1. Om en `Frameworks`-mapp inte finns skapar du en i projektmappen.

## <a name="enable-auto-instrumentation"></a>Aktivera automatisk instrumentering
 
Du kan enkelt aktivera automatisk instrumentering utan kod. När projektet körs spåras händelserna `view` och `action` automatiskt med hjälp av den konfigurerade Inmatningsyckeln. 

1. Uppdatera och ta med den medföljande filen `EIConfig.plist` i projektkatalogmappen för följande fält:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = JA
    - autocollectAction = JA

2. Lägg sedan till filen `EIConfig.plist` i projektet i Xcode. 



Om du vill inaktivera automatisk instrumentering uppdaterar du följande fält i medföljande fil `EIConfig.plist` i din projektkatalogmapp. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementera anpassade händelser

1. Öppna ditt projekt i Xcode och navigera till inställningarna under **Allmänt**. 
1. Lägg till `EIObjC.xcframework` i projektet under avsnittet "Ramverk, bibliotek och inbäddat innehåll".

1. Importera framework-rubrikfilen i AppDelegate.m med följande kodavsnitt:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Initiera SDK för engagemangsinsikter från följande program: didFinishLaunchingWithOptions.
1. Kopiera XML-kodavsnittet från **installationsguiden**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Spåra en händelse:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Ange användarinformation för händelsen

Med SDK kan du definiera användarinformation som kan skickas för alla händelser. Du kan ange användarinformation genom att anropa API `setUser:(nonnull EIUser *)user` i SDK.

Att ange användarinformation på nivån `Analytics` innebär att alla telemetrier får denna information. Om du emellertid anger på händelsenivå genom att anropa API `setUser:(nonnull EIUser *)user` för objektet EIEvent kommer endast den specifika händelsen att innehålla informationen.

Dataklassen `EIUser` innehåller följande NSString-egenskaper:

- **localId**: Användarens lokala ID.
- **authId**: Det autentiserade användar-ID:t.
- **authType**: Den autentiseringstyp som används för att hämta det autentiserade användar-ID:t.
- **name**: Användarens namn.
- **email**: Användarens e-postadress.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
