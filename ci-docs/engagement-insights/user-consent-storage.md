---
title: Hantera cookies och användargodkännande för att lagra användardata
description: Förstå hur cookies och användargodkännande används för att identifiera webbplatsbesökare.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036760"
---
# <a name="manage-cookies-and-user-consent"></a>Hantera cookies och användarmedgivande

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights funktionen engagemangsinsikter använder cookies och lokal lagring (`localStorage`) för att identifiera webbplatsbesökare.

Cookies är små filer som lagrar information om en användares interaktioner med webbplatsen. De lagras i webbläsare. När en användare besöker en webbplats där användarna har lagrat cookies, skickar webbläsaren den informationen till servern, som returnerar en unik information för användaren. Den här tekniken gör det till exempel möjligt för en onlineanvändare att behålla valda objekt i den även om en användare navigerar bort från webbplatsen.

## <a name="user-consent"></a>Användarmedgivande

[Den allmänna dataskyddsförordningen (GDPR)](/dynamics365/get-started/gdpr/) är en EU-förordning som styr hur organisationer ska hantera sina användares sekretess och säkerhet. Cookies lagrar eller samlar ofta in "personuppgifter", t.ex. en online-identifierare, som omfattas av GDPR. Om ditt företag använder och/eller säljer till eu-registrerade ämnen påverkas du av GDPR. [Läs mer om hur Microsoft kan hjälpa dig att uppfylla GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

För att tillåta att SDK för engagemangsinsikter lagrar cookies eller annan känslig information måste du ange om dina användare har gett sitt godkännande. Detta sker vid initieringen av SDK.

Om du anger att det inte finns något användargodkännande lagras inga data i SDK och inga händelser som kan användas för att spåra användarbeteenden kommer att skickas. Tidigare lagrade data tas bort i webbläsaren.

Om inget värde för användargodkännande anges förutsätter SDK att användaren har gett sitt godkännande. Det innebär att om du (som vår kund) inte anger ett värde för användargodkännande i SDK kommer data att samlas in. Men om du anger att värdet för användargodkännande måste vara "sant" samlas data in inte om en användare avböjer eller misslyckas med att ge uttryckligt godkännande.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Lagring av besöksdata i funktionen engagemangsinsikter

### <a name="cookies"></a>Kakor

- _msei
    - Sparar det anonyma användar-ID:t. Cookien anges i kunddomänen och förfaller om 365 dagar.

### <a name="local-storage"></a>Lokal lagring

Funktionen engagemangsinsikter använder också lokal lagring (`localStorage`) för att spåra icke-känsliga data. Dessa data lagras helt i själva webbläsaren, utan att någon trafik skickas till eller från dina servrar.

- *EISession.Id* 
    - Lagrar information om den pågående användarsessionen, till exempel sessions-ID, när den startade och när den förfaller.
- *EISession.Previous*
    - Sparar URL-adressen till den sida som har besökts tidigare i den aktuella sessionen.
    
Nycklar i lokalt lagringsutrymme förfaller inte automatiskt. SDK återställs under nästa session.

## <a name="deleting-cookies"></a>Ta bort cookies

Dina kunder kan när som helst manuellt ta bort cookies och lokala lagringsnycklar via sina webbläsares inställningar.


[!INCLUDE[footer-include](../includes/footer-banner.md)]