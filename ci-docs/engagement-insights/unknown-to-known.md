---
title: Identifiera webbhändelser från tidigare autentiserade besökare (från okända till kända)
description: Med funktionen &quot;okänd till känd&quot; kan du associera händelser på en webbplats med besökare som tidigare autentiserats.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230702"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Identifiera webbhändelser från tidigare autentiserade besökare

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funktionen **okända till kända** i funktionen för interaktionsinsikt gör det möjligt att associera händelser på en webbplats med besökare som tidigare autentiserats. Om funktionen är inaktiverad identifieras inte besökare som autentiserade sig under ett tidigare besök och sedan lämnade, detta om de inte autentiserade sig igen när de kom tillbaka. 

En person har till exempel besökt en webbplats föregående vecka, loggat in på sitt användarkonto på webbplatsen och bläddrat i produktkatalogen. Personen återvänder nästföljande vecka för att söka bland fler produkter utan att logga in på kontot. Webbplatsägaren som använder funktionen **okänd till känd** vet då att samma person återvänt och vad denne gjort på webbplatsen. Detta möjliggör mer exakt rapportering och analys av webbplatsaktiviteter.

## <a name="enable-unknown-to-known"></a>Aktivera okänd till känd

Du måste inneha rollen som [arbetsyteadministratör](user-roles.md) för att aktivera denna funktion. 

1. I interaktionsinsikterna går du till **Administratör** > **Arbetsyta**. 
2. Välj fliken **Inställningar**.
3. I avsnittet **Okänd till känd** anger du inställningen som **Aktiverad**.

![Aktivera okänd till känd](media/U2Ktoggle.png "Aktivera okänd till känd")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Lägga till JavaScript-kod i kodavsnittet för webbplatsspårning

En webbplats kan registrera **auktoriserings-ID för användare (user authId)** med följande JavaScript-exempel med hjälp av [webb-SDK för interaktionsinsikter](advanced-SDK-implementation.md). För att funktionen **okänd till känd** ska fungera måste du registrera authId *och* aktivera &quot;userMapping:True&quot; i ditt JavaScript-kodavsnitt enligt nedanstående exempel.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
