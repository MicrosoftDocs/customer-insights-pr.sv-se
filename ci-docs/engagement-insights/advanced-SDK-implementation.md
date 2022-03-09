---
title: Avancerade webb-SDK scenarier
description: Avancerade scenarier att tänka på när du instrumenterar webbplatsen med ett SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227220"
---
# <a name="advanced-web-sdk-instrumentation"></a>Avancerad instrumentering för webb-SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Den här artikeln guidar dig genom avancerade scenarier som du kan tänka på när [instrumenterar webbplatsen](instrument-website.md) med en Dynamics 365 Customer Insights engagemangsinsikter funktions-SDK.

## <a name="setting-user-details-for-your-event"></a>Ange användarinformation för händelsen

Med SDK kan du definiera användarinformation som kan skickas för alla händelser. Du kan ange användarinformationen i en egenskap som kallas `user` (de förväntade data för den här egenskapen är objektet `IUser`), liknande `src`, `name`, och `cfg` i konfiguration av kodavsnitt.

Objektet `IUser` innehåller följande strängegenskaper:

- **localId**: Användarens lokala ID.
- **authId**: Det autentiserade användar-ID:t.
- **authType**: Den autentiseringstyp som används för att hämta det autentiserade användar-ID:t.
- **name**: Användarens namn.
- **email**: Användarens e-postadress.

I följande exempel visas ett kodavsnitt skickar användarinformation. Om funktioner som föregås av en asterisk* visas ersätter du den funktionen med din anpassade implementering:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Du kan också ange användarinformation genom att anropa `setUser(user: IUser)`-API. Telemetri som skickas efter anrop till `setUser`-API innehåller användarinformationen.

## <a name="adding-custom-properties-for-each-event"></a>Lägga till anpassade egenskaper för varje händelse

Med SDK kan du ange anpassade egenskaper som kan skickas för alla händelser. Du kan ange de anpassade egenskaperna som ett objekt som innehåller nyckel/värde-par (värdet kan vara av typen `string | number | boolean`). Du kan lägga till objektet i en egenskap, `props`, liknande `src`, `name` och `cfg` i konfigurationen av kodavsnittet.

I följande exempel visas ett kodavsnitt skickar anpassade egenskaper:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Du kan också ange anpassade egenskaper enskilt genom att anropa `setProperty(name: string, value: string | number | boolean)`-API.

## <a name="sending-custom-events"></a>Skapa anpassade händelser

Du kan använda SDK för att skicka anpassade händelser. Du måste ange ett namn för händelsen och egenskaperna som ska skickas med händelsen.

I följande exempel visas ett kodavsnitt spårar en anpassad händelse. NAME är värdet i nyckeln `name` i konfiguration av kodavsnitt. Det är också variabelnamnet i fönstrets objekt där SDK läses in.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
