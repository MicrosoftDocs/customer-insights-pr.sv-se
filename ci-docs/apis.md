---
title: Arbeta med API:er i Customer Insights
description: Använd API:er och förstå begränsningar.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 8e8bd590d3bba9dc7b1644b6ff42b9fc53237ca9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054086"
---
# <a name="work-with-customer-insights-apis"></a>Arbeta med API:er i Customer Insights

Dynamics 365 Customer Insights tillhandahåller API:er för att bygga egna program baserat på dina data i Customer Insights.

> [!IMPORTANT]
> Detaljer om dessa API:er anges i [API-referens för Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). De innehåller ytterligare information om operationer, parametrar och svar.

I den här artikeln beskrivs hur du öppnar Customer Insights API:er, skapar en Azure-appregistrering och kommer igång med klientbibliotek.

## <a name="get-started-trying-the-customer-insights-apis"></a>Kom igång med att prova API:erna för Customer Insights

1. [Logga in](https://home.ci.ai.dynamics.com) på Customer Insights. Om du inte har någon prenumeration ännu [registrerar du dig för en utvärderingsversion av Customer Insights](https://aka.ms/tryci).

1. Om du vill aktivera API:er i din Customer Insights-miljö går du till **Administratör** > **Säkerhet**. Du behöver administratörsbehörighet för att kunna göra det.

1. Gå till fliken **API:er** och välj knappen **Aktivera**.    
 
   Att aktivera API:erna skapar en primär och sekundär prenumerationsnyckel för din instans som används i API-begäranden. Du kan återskapa nycklarna genom att välja **Återskapa primär** eller **Återskapa sekundär** i **Administratör** > **Säkerhet** > **API:er**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Välj **Utforska våra API:er** för att [prova API:erna](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Välj en API-åtgärd och välj **Prova den**.

1. I sidpanelen anger du värdet för listrutan **Auktorisering** till **implicit**. Sidhuvudet `Authorization` läggs till med en ägartoken. Din prenumerationsnyckel kommer att fyllas i automatiskt.
  
1. Lägg alternativt till alla nödvändiga frågeparametrar.

1. Rulla längst ned i sidorutan och välj **Skicka**.

HTTP-svaret visas snart nedan.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Skapa en ny appregistrering i Azure-portalen

Dessa steg hjälper dig att komma igång med API:er för Customer Insights i ett Azure-program med delegerade behörigheter. Se till att du slutför [avsnittet Komma igång](#get-started-trying-the-customer-insights-apis) först.

1. Logga in på [Azure-portalen](https://portal.azure.com) med det konto som kan komma åt Customer Insights-data.

1. Till vänster väljer du **Appregistreringar**.

1. Välj **Ny registrering**, tillhandahåll ett programnamn och välj kontotyp.

   Lägg alternativt till en omdirigerings-URL. http://localhost är tillräcklig för att utveckla ett program på din lokala dator.

1. På din nya App-registrering går du till **API-behörigheter**.

1. Välj **Lägg till en behörighet** och välj **Dynamics 365 AI för Customer Insights** i sidofönstret.

1. För **Behörighetstyp** väljer du **Delegerad behörighet** och sedan behörigheten **användarpersonifiering**.

1. Välj **Lägg till behörigheter**. Om du behöver komma åt API:et utan att någon användare loggat in granskar du avsnittet [Server-till-server-programbehörigheter](#server-to-server-application-permissions).

1. Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.

Du kan använda Program-/klient-ID för den här appregistreringen med Microsoft Authentication Library (MSAL) för att få ett ägartoken att skicka med din begäran till API:et.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Mer information om MSAL finns i [Översikt över MSAL (Microsoft Authentication Library)](/azure/active-directory/develop/msal-overview).

Mer information om appregistrering i Azure finns i [Registrera ett program](/graph/auth-register-app-v2).

Information om hur du använder API:er i våra klientbibliotek finns i [Customer Insights-klientbibliotek](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Programbehörigheter för server till server

Avsnittet för [registrering av appar](#create-a-new-app-registration-in-the-azure-portal) beskriver hur du registrerar en app som kräver att en användare loggar in för autentisering. Lär dig hur du skapar en appregistrering som inte behöver användarinteraktion och som kan köras på en server.

1. På din app-registrering i Azure Portal går du till **API-behörigheter**.

1. Välj **Lägg till behörighet**. 

1. Välj fliken **API:er som min organisation använder** och välj **Dynamics 365 AI för Customer Insights** från listan. 

1. För **Behörighetstyp** väljer du **Programbehörighet** och sedan behörigheten **CustomerInsights.Api.All**.

1. Välj **Lägg till behörigheter**.

1. Gå tillbaka till **API-behörigheter** för din app-registrering.

1. Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Slutligen måste vi lägga till namnet på appregistreringen som användare i Customer Insights.  
   
   Öppna Customer Insights, gå till **Admin** > **Security** och välj **Lägg till användare**.

1. Sök efter namnet på din appregistrering, välj den bland sökresultaten och välj **Spara**.

## <a name="sample-queries"></a>Exempelfrågor

Vi har sammanställt en kort lista med OData-exempelfrågor som fungerar med API:er: [Exempel på OData-frågor](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Klientbibliotek för Customer Insights

Det här avsnittet hjälper dig att komma igång med att använda klientbiblioteken som är tillgängliga för Customer Insights-API:erna. All bibliotekskällkod och alla exempelprogram finns på sidan [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Lär dig hur du kommer igång med att använda C#-klientbiblioteken från NuGet.org. Mer information om paketet NuGet finns i [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). För närvarande riktar detta paket in sig på ramverken netstandard2.0 och netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Lägga till C#-klientbiblioteket i ett C#-projekt

1. I Visual Studio öppnar du **NuGet-pakethanteraren** för ditt projekt.

1. Sök efter **Microsoft.Dynamics.CustomerInsights.Api**.

1. Välj **Installera** för att lägga till paketet i projektet.
 
   Alternativt kan du köra det här kommandot i **pakethanterarkonsolen för NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Använda klientbiblioteket C#

1. Använd [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) för att få ett `AccessToken` med hjälp av din befintliga [Azure-appregistrering](#create-a-new-app-registration-in-the-azure-portal).

1. Efter att ha lyckats autentisera och skaffa en token, konstruera en ny eller använd en befintlig `HttpClient` med **DefaultRequestHeaders "Authorization"** anges till **Bearer "access token"** och **Ocp-Apim-Subscription-Key** anges till [**prenumerationsnyckeln** från Customer Insights-miljö](#get-started-trying-the-customer-insights-apis).   
 
   Återställ rubriken **Auktorisering** när det är lämpligt. Till exempel när token löpt ut.

1. Skicka denna `HttpClient` i konstruktionen av `CustomerInsights`-klienten.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Gör anrop med klienten till "tilläggsmetoderna", till exempel `GetAllInstancesAsync`. Om tillgång till underliggande `Microsoft.Rest.HttpOperationResponse` är att föredra, använd "http-meddelandemetoderna", till exempel `GetAllInstancesWithHttpMessagesAsync`.

1. Svaret kommer sannolikt att vara av typen `object` eftersom metoden kan returnera flera typer (till exempel `IList<InstanceInfo>` och `ApiErrorResult`). För att kontrollera returtypen använder du objekten i de svarstyper som anges på [API-informationssidan](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) för den åtgärden.    
   
   Om mer information om begäran behövs använder du **metoderna för http-meddelande** för att komma åt råsvarsobjekt.

### <a name="nodejs-package"></a>NodeJS-paket

Använd NodeJS-klientbiblioteken som är tillgängliga via NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-paket

Använd Python-klientbiblioteken som är tillgängliga via PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]