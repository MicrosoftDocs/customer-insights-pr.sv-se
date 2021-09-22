---
title: Kom i gång med Android SDK
description: Lär dig anpassa och köra Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036940"
---
# <a name="get-started-with-the-android-sdk"></a>Kom i gång med Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Den här självstudien guidar dig genom processen för att arrangera ditt Android-program med en Dynamics 365 Customer Insights-SDK för engagemangsinsikter. Du kommer att börja se händelser i portalen inom fem minuter eller tidigare.

## <a name="configuration-options"></a>Konfigurationsalternativ
Följande konfigurationsalternativ kan skickas vidare till SDK:

- **indionKey**: Inmatningsnyckeln används för att skicka händelser till din arbetsyta.

## <a name="prerequisites"></a>Förutsättningar

- Android Studio

- Minsta nivå för Android-API: 16 (Jelly Bean)

- En inmatningsyckel (se nedan för instruktioner om hur du hämtar denna)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Steg 1. Integrera SDK i programmet
Påbörja processen genom att välja en arbetsyta, välja Android-mobilplattform och hämta Android SDK.

- Använd arbetsyteväljaren i det vänstra navigeringsfönstret för att välja din arbetsyta.

- Om du inte har en befintlig arbetsyta väljer du **Ny arbetsyta** och följer stegen för att skapa en [ny arbetsyta](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Steg 2. Konfigurera SDK

1. När du har skapat en arbetsyta går du till **Administratör** > **Arbetsyta** och väljer sedan **Installationshandbok**. 

1. Hämta [Android SDK för engagemangsinsikter](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) och placera filen `eiandroidsdk-debug.aar` i mappen `libs`.

1. Öppna din fil `build.gradle` på projektnivå och lägg till följande kodavsnitt:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Konfigurera SDK-konfigurationen för engagemangsinsikter genom din `AndroidManifest.xml`-fil som finns under mappen `manifests`. 
1. Kopiera XML-kodavsnittet från **installationsguiden**. `Your-Ingestion-Key` ska fyllas i automatiskt.

   > [!NOTE]
   > Du behöver inte byta ut avsnittet `${applicationId}`. Det ska fyllas i automatiskt.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Aktivera eller inaktivera autoregistrerings av `View`-händelser genom att ange ovanstående `autoCapture`-fält som `true` eller `false`.

1. (Valfritt) Andra konfigurationer omfattar att ange insamlar-URL för slutpunkt. De kan läggas till under metadata för Inmatningsyckel i `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Steg 3. Initiera SDK från MainActivity 

När du har initierat SDK kan du arbeta med händelser och deras egenskaper i MainActivity-miljön.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Ange egenskap för alla händelser (valfritt)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Följande typer stöds för egenskaper för kontexthändelse:
- String
- Datum
- Dubbel
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>Spåra en händelse

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Ange användarinformation för händelsen (valfritt)

Med SDK kan du definiera användarinformation som kan skickas för alla händelser. Du kan ange användarinformation genom att anropa `setUser(user: User)`-API på nivån `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Dataklassen `User` innehåller följande strängegenskaper:

- **localId**: Användarens lokala ID.
- **authId**: Det autentiserade användar-ID:t.
- **authType**: Den autentiseringstyp som används för att få autentiserat användar-ID.
- **name**: Användarens namn.
- **email**: Användarens e-postadress.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
