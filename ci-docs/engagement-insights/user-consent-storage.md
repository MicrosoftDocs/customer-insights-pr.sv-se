---
title: Hantera cookies och användargodkännande att lagra användardata i Dynamics 365 Customer Insights
description: Förstå hur cookies och användargodkännande används för att identifiera webbplatsbesökare.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229007"
---
# <a name="manage-cookies-and-user-consent"></a>Hantera cookies och användarmedgivande

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights funktioner för engagemangsinsikter använder cookies och (`localStorage`)-nycklar för att identifiera webbplatsbesökare.

Cookies är små filer som lagrar information om en användares interaktioner med webbplatsen. De lagras i webbläsare. När en användare besöker en webbplats där användarna har lagrat cookies, skickar webbläsaren den informationen till servern, som returnerar en unik information för användaren. Den här tekniken gör det till exempel möjligt för en onlineanvändare att behålla valda objekt i den även om en användare navigerar bort från webbplatsen.

## <a name="user-consent"></a>Användarmedgivande

[Den allmänna dataskyddsförordningen (GDPR)](/dynamics365/get-started/gdpr/) är en EU-förordning som styr hur organisationer ska hantera sina användares sekretess och säkerhet. Cookies lagrar eller samlar ofta in "personuppgifter", t.ex. en online-identifierare, som omfattas av GDPR. Om ditt företag använder och/eller säljer till eu-registrerade ämnen påverkas du av GDPR. [Läs mer om hur Microsoft kan hjälpa dig att uppfylla GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

För att tillåta att SDK för engagemangsinsikter lagrar cookies eller annan känslig information måste du ange om dina användare har gett sitt godkännande. Detta sker vid initieringen av SDK genom att ange ett `userConsent` fält i konfigurationen.

Om du anger att det inte finns något användargodkännande lagras inga data i SDK och inga händelser som kan användas för att spåra användarbeteenden kommer att skickas. Tidigare lagrade data tas bort i webbläsaren.

Om inget värde för användargodkännande anges förutsätter SDK att användaren har gett sitt godkännande. Det innebär att om du (som vår kund) inte anger ett värde för användargodkännande i SDK kommer data att samlas in. Men om du anger att värdet för användargodkännande måste vara "sant" samlas data in inte om en användare avböjer eller misslyckas med att ge uttryckligt godkännande.

Nedan följer ett kodavsnitt för att initiera webb-SDK med användargodkännande:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Lagring av besöksdata i funktionen engagemangsinsikter

### <a name="cookies"></a>Kakor

- _msei
    - Sparar det anonyma användar-ID:t. Cookien anges i kunddomänen och förfaller om 365 dagar.

### <a name="local-storage"></a>Lokal lagring

Funktionerna för engagemangsinsikter använder också (`localStorage`)-nycklar för att spåra icke-känsliga data. Dessa data lagras helt i själva webbläsaren, utan att någon trafik skickas till eller från dina servrar.

- *EISession.Id*
    - Lagrar information om den pågående användarsessionen, till exempel sessions-ID, när den startade och när den förfaller.
- *EISession.Previous*
    - Sparar URL-adressen till den sida som har besökts tidigare i den aktuella sessionen.

Nycklar som är sparade lokalt förfaller inte automatiskt och de återställs vid nästkommande SDK-session.

## <a name="deleting-cookies"></a>Ta bort cookies

Dina kunder kan när som helst manuellt ta bort cookies och lokala lagringsnycklar via sina webbläsares inställningar.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
