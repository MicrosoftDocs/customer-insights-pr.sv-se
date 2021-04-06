---
title: Arbeta med API:er
description: Använd API:er och förstå begränsningar.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710482"
---
# <a name="work-with-customer-insights-apis"></a>Arbeta med API:er i Customer Insights

Dynamics 365 Customer Insights tillhandahåller API:er för att bygga egna program baserat på data från dig i Customer Insights.

> [!IMPORTANT]
> Detaljer om dessa API:er anges i [referens om Customer Insights API:er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). De innehåller ytterligare information om operationer, parametrar och svar.

Den här artikeln guidar dig till åtkomst till Customer Insights-API:erna, till hur du skapar en Azure App-registrering och hjälper dig att komma igång med de tillgängliga klientbiblioteken.

## <a name="get-started-trying-the-customer-insights-apis"></a>Kom igång med att prova API:erna för Customer Insights

1. [Logga in](https://home.ci.ai.dynamics.com) på Customer Insights. Om du inte har någon prenumeration ännu [registrerar du dig för en utvärderingsversion av Customer Insights](https://aka.ms/tryci).

1. Om du vill aktivera API:er på Customer Insights-miljön går du till **Admin** > **Behörigheter**. Du behöver administratörsbehörighet för att kunna göra det.

1. Gå till fliken **API:er** och välj knappen **Aktivera**.    
   Att aktivera API:erna skapar en primär och sekundär prenumerationsnyckel för din instans som används i API-begäranden. Du kan återskapa nycklarna genom att välja **Återskapa primär** eller **Återskapa sekundär** på **Admin** > **Behörigheter** > **API:er**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktivera Customer Insights-API:er":::

1. Välj **Utforska våra API:er** för att [prova API:erna](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Välj en API-åtgärd och välj **Prova den**.

1. I sidorutan anger du värdet i listmenyn **Auktorisering** till **implicit**. Rubriken `Authorization` får med ett ägartoken tillagt. Din prenumerationsnyckel kommer att fyllas i automatiskt.
  
1. Lägg alternativt till alla nödvändiga frågeparametrar.

1. Rulla längst ned i sidorutan och välj **Skicka**.

HTTP-svaret visas snart nedan.


   :::image type="content" source="media/try-apis.gif" alt-text="En animerad gif som visar hur man väljer att testa API:er.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Skapa en ny appregistrering i Azure-portalen

Med hjälp av de här stegen kan du komma igång med att använda Customer Insights-API:erna i ett Azure-program med hjälp av delegerade behörigheter. Se till att ha slutfört [Komma igång-avsnittet](#get-started-trying-the-customer-insights-apis) först.

1. Logga in på [Azure-portalen](https://portal.azure.com) med det konto som kan komma åt Customer Insights-data.

1. Till vänster väljer du **Appregistreringar**.

1. Välj **Ny registrering**, tillhandahåll ett programnamn och välj kontotyp.
   Lägg alternativt till en omdirigerings-URL. http://localhost är tillräcklig för att utveckla ett program på din lokala dator.

1. På din nya App-registrering går du till **API-behörigheter**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="En animerad gif för att ange API-behörighet i appregistrering.":::

1. Välj **Lägg till en behörighet** och välj **Customer Insights** i sidorutan.

1. För **Behörighetstyp** väljer du **Delegerade behörigheter** och väljer behörigheten **user_impersonation**.

1. Välj **Lägg till behörigheter**. Om du behöver komma åt API:et utan att någon användare loggat in granskar du avsnittet [Server-till-server-programbehörigheter](#server-to-server-application-permissions).

1. Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.

Du kan använda Program-/klient-ID för den här appregistreringen med Microsoft Authentication Library (MSAL) för att få ett ägartoken att skicka med din begäran till API:et.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="En animerad gif för beviljande av administratörsmedgivande.":::

Mer information om MSAL finns i [Översikt över MSAL (Microsoft Authentication Library)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Mer information om appregistrering i Azure finns i [den nya upplevelsen av registrering av Azure Portal-appen](/azure/active-directory/develop/app-registration-portal-training-guide).

Information om hur du använder API:er som våra klientbibliotek finns i [Customer Insights-klientbibliotek](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Programbehörigheter för server till server

Avsnittet för [registrering av appar](#create-a-new-app-registration-in-the-azure-portal) beskriver hur du registrerar en app som kräver att en användare loggar in för autentisering. Lär dig hur du skapar en appregistrering som inte behöver användarinteraktion och som kan köras på en server.

1. På din app-registrering i Azure Portal går du till **API-behörigheter**.

1. Välj **Lägg till en behörighet** och välj **Customer Insights** i sidorutan.

1. För **Behörighetstyp** väljer du **Programbehörigheter** och väljer behörigheten **CustomerInsights.Api.All**.

1. Välj **Lägg till behörigheter**.

1. För att ge administratörsmedgivande på denna programbehörighet måste du lägga till ett Service Principal.

   1. Installera Azure Active Directory PowerShell-modulen (AD): `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Anslut till ditt AD-konto: `Connect-AzureAD -TenantId <your tenant id>`. Du hittar klientorganisationens ID på **Översikt** > **Azure Active Directory**.
   1. Kör följande kommando för att lägga till Azure AD Service Principal `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parametern AppId gäller API-appen Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Exempel på huvudkonto för tjänsten":::

1. Gå tillbaka till **API-behörigheter** för din app-registrering.

1. Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="En animerad gif för beviljande av administratörsmedgivande.":::

1. Slutligen måste vi lägga till namnet på appregistreringen som användare i Customer Insights.    
   Öppna Customer Insights, gå till **Admin** > **Behörigheter** och välj **Lägg till användare**.

1. Sök efter namnet på din appregistrering, välj den bland sökresultaten och välj **Spara**.

## <a name="customer-insights-client-libraries"></a>Klientbibliotek för Customer Insights

Det här avsnittet hjälper dig att komma igång med att använda klientbiblioteken som är tillgängliga för Customer Insights-API:erna. All bibliotekskällkod och alla exempelprogram finns på sidan [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Lär dig hur du kommer igång med att använda C#-klientbiblioteken från NuGet.org. Mer information om paketet NuGet finns i [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). För närvarande riktar detta paket in sig på ramverken netstandard2.0 och netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Lägga till C#-klientbiblioteket i ett C#-projekt

1. I Visual Studio öppnar du **NuGet-pakethanteraren** för ditt projekt.

1. Sök efter **Microsoft.Dynamics.CustomerInsights.Api**.

1. Välj **Installera** för att lägga till paketet i projektet.
   Alternativt kan du köra det här kommandot i **pakethanterarkonsolen för NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Lägg till NuGet-paket i Visual Studio-projekt":::

#### <a name="use-the-c-client-library"></a>Använda klientbiblioteket C#

1. Använd [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) för att få ett `AccessToken` med hjälp av din befintliga [Azure-appregistrering](#create-a-new-app-registration-in-the-azure-portal).

1. När du har autentiserat och fått ett token skapar du en ny eller använder en befintlig `HttpClient` med **DefaultRequestHeaders "Auktorisering"** inställd på **Ägare <access token>** och **Ocp-Apim-Subscription-Key** inställd på [**prenumerationsnyckel** från din Customer Insights-miljö](#get-started-trying-the-customer-insights-apis).    
   Återställ rubriken **Auktorisering** när det är lämpligt. Till exempel när token löpt ut.

1. Skicka denna `HttpClient` i konstruktionen av `CustomerInsights`-klienten.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Exempel på httpclient":::

1. Ringa samtal med klienten till "tilläggsmetoderna", till exempel `GetAllInstancesAsync`. Om tillgång till underliggande `Microsoft.Rest.HttpOperationResponse` är att föredra, använd "http-meddelandemetoderna", till exempel `GetAllInstancesWithHttpMessagesAsync`.

1. Svaret kommer sannolikt att vara av typen `object` eftersom metoden kan returnera flera typer (till exempel `IList<InstanceInfo>` och `ApiErrorResult`). Om du vill kontrollera returtypen kan du säkert typkonvertera objekten i de svarstyper som anges på [API-informationssidan](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) för den åtgärden.    
   Om mer information om begäran behövs använder du **metoderna för http-meddelande** för att komma åt råsvarsobjekt.

### <a name="nodejs-package"></a>NodeJS-paket

Använd NodeJS-klientbiblioteken som är tillgängliga via NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-paket

Använd Python-klientbiblioteken som är tillgängliga via PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
