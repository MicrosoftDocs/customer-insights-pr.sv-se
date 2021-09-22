---
title: Android SDK-exempel
description: Exempelprojekt som lär dig mer om Android-SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035848"
---
# <a name="run-the-android-sdk-sample"></a>Kör Android SDK-exemplet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Detta Android-exempelprojekt hjälper dig att förstå hur SDK fungerar i en app. Du behöver inte skriva kod. Lägg bara till inmatningsnyckeln, så visas händelser på arbetsytan direkt.

## <a name="prerequisites"></a>Förutsättningar

- [Android Studio](https://developer.android.com/studio)
- [Inmatningsnyckel](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Ladda ned Android SDK-exemplet

1. [Hämta Android SDK-exemplet för engagemangsinsikter](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Packa upp den komprimerade filen `ei-android-sample.zip`.
1. Öppna den uppackade mappen i Android Studio.
1. I filen `AndroidManifest.xml` ersätter du strängen `"Your-Ingestion-Key"` med din inmatningsnyckel för arbetsyta från engagemangsinsikterna under **Administratör** > **Arbetsyta** > **Installationsguide**. 

   > [!NOTE]
   > Du behöver inte byta ut avsnittet `${applicationId}`. Det ska fyllas i automatiskt.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Välj **Kör** om du vill starta exempelprojektet.
1. Visa händelserna på arbetsytan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
