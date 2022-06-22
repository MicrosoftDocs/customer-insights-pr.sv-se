---
title: Vanliga frågor om utvärderingsversion Dynamics 365 Customer Insights
description: Lösningar på vanliga frågor relaterade till Customer Insights inställning och hantering av utvärderingsversion. Läs om hur du stänger plattforms- och appspecifika problem.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 46a67e58f79029246029e2d06789525c2131f100
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011909"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Vanliga frågor och svar om Dynamics 365 Customer Insights utvärderingsversion

## <a name="sign-up"></a>Registrera dig

### <a name="what-are-the-system-requirements-for-the-trial"></a>Vilka är systemkraven för utvärderingen?

Denna app är en molnbaserad tjänst som inte kräver någon särskild programvara annat än en uppdaterad webbläsare, men vissa begränsningar gäller. För att få den bästa testupplevelsen, undvik att komma till testwebbplatsen i inkognitoläge och välj testplatsen närmast dig. [Läs mer om krav för webbappen.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Hur registrerar jag mig för utvärderingsversionen utan en Microsoft 365-klientorganisation?

Du kan ange en e-postadress som inte är en jobbadress, så skapar vi ett konto och en klientorganisation åt dig.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Kan jag registrera mig för flera Dynamics 365-appar som Sales, Marknadsföring och kundtjänst?

Ja, det kan du. Om du vill visa alla tillgängliga utvärderingsversioner [besöker du sidan för utvärderingsnav](https://dynamics.microsoft.com/dynamics-365-free-trial). Du kan använda samma e-postkonto för att registrera dig för olika utvärderingsversioner. Det är emellertid inte möjligt att ha flera appar på samma utvärderingswebbplats. Med varje provperiod följer en annan organisation och URL. Utvärderingsdata delas inte mellan appar.

## <a name="trial-app"></a>Utvärderingsapp

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Jag har inte fått e-postmeddelandet med utvärderingsinformationen efter registreringen – vad ska jag göra?

När du registrerar dig för utvärderingsversionen får du ett e-postmeddelande med utvärderingsinformationen. Om du inte ser e-postmeddelandet i inkorgen kontrollerar du skräppostmappen. Du kan också använda följande steg för att komma åt din app:

1. Gå till provperiodens webbplats och välj **Prova gratis**.
1. Ange det e-post-ID som du använde för att registrera dig för utvärderingsversionen. Du omdirigeras till utvärderingsappen.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Hur lägger jag till fler användare i en utvärderingsversion?

Om du vill lägga till användare går du till [Microsoft 365-administrationscentret](https://admin.microsoft.com) med hjälp av administrationskontot för utvärderingsversionen. Följ [vägledningen för administrationscentret](/microsoft-365/admin/add-users/add-users) om du vill lägga till användare upp till licensgränsen för utvärderingsversionen. Om användaren du lägger till redan har ett Microsoft 365-konto tilldelar du denne en lämplig säkerhetsroll i utvärderingsorganisationen. Mer information finns i [Tilldela en säkerhetsroll för en användare](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Hur många användare kan jag lägga till i min utvärderingsmiljö?

Det går att lägga till hur många användare till testmiljön.

### <a name="how-do-i-reset-the-trial-environment"></a>Hur återställer jag min utvärderingsmiljö?

Du kan inte återställa utvärderingsmiljön. Du kan emellertid vänta tills utvärderingsperioden avslutas och sedan registrera dig igen för en ny utvärderingsversion.

## <a name="trial-expiration-and-extension"></a>Förfallodatum för och förlängning av utvärderingsversion

### <a name="how-do-i-extend-the-trial"></a>Hur förlänger jag min utvärderingsversion?

Du kan utöka utvärderingsversionen direkt i appen. Du kan förlänga utvärderingsversionen en gång.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Kan jag konvertera provperioden till en betald licens?

Vanligtvis rekommenderar vi att du börjar om från början med dina egna data när du uppgraderar till betalversionen av Customer Insights. 

Alternativt, om du bara använder Customer Insights, kan du kopiera dina data från en utvärderingsmiljö om du köper Customer Insights. Du måste vara administratör av utvärderingsversionen av Customer Insights och den globala administratören av Microsoft 365-klientorganisationen, eller Dynamics 365-administratör i organisationen om du vill migrera inställningarna från en utvärderingsmiljö till en betald miljö.

När du har loggat in på din betalinstans av Customer Insights för första gången uppmanas du att skapa en ny miljö. I den här processen kan du välja att kopiera konfigurationen från en befintlig miljö och migrera de flesta inställningar. Om du har de behörigheter som anges ovan visas utvärderingsmiljön i den här listan. Mer information finns i [Kopiera miljökonfigurationen](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Vilka är begränsningarna och kvoterna för utvärderingsversionen?

- Du kan inte använda ditt eget Azure Data Lake Storage-konto för att lagra utdata under en provversion av Customer Insights. Du kan däremot mata in data från ett Data Lake Storage-konto.
- Du kan spara upp till 3 GB data i den Dataverse-miljö som tillhandahålls automatiskt när du startar en utvärderingsversion av Customer Insights.

## <a name="customer-insights-specific-questions"></a>Customer Insights-frågor

### <a name="how-do-i-start-using-the-trial"></a>Hur börjar jag använda min utvärderingsversion?

När du har registrerat dig för provperioden kommer du fram till appens huvudskärm. Huvudskärmen innehåller länkar till användarhandledningar och självstudier. Mer information finns i länkarna i [Ytterligare resurser](trial-signup.md#additional-resources) på sidan för registrering av utvärderingsversion.

### <a name="what-features-are-available-in-the-trial"></a>Vilka funktioner finns tillgängliga i utvärderingsversionen?

De flesta funktionerna i Customer Insights är tillgängliga under utvärderingsperioden.

Följande funktioner är **inte tillgängliga**:

- Du kan inte skapa nya miljöer som använder ditt eget Azure Data Lake Storage-konto.
- Du kan inte ta bort utvärderingsmiljön.

### <a name="how-long-does-the-trial-last"></a>Hur länge varar utvärderingsversionen?

Utvärderingsversionen av Customer Insights varar i 30 dagar. Du kan förlänga utvärderingsversionen en gång efter 23 dagar när du loggar in i din utvärderingsmiljö.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Hur tar jag bort exempeldata från utvärderingsversionen?

Du kan inte ta bort exempeldata från utvärderingsversionen.
