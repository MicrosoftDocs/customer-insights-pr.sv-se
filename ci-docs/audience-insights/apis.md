---
title: Arbeta med API:er
description: Använd API:er och förstå begränsningar.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 4d41d7d328dfa6699b5f5e992d3a5bf3179490d8
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016642"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="58ccf-103">Arbeta med API:er i Customer Insights</span><span class="sxs-lookup"><span data-stu-id="58ccf-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="58ccf-104">Dynamics 365 Customer Insights tillhandahåller API:er för att bygga egna program baserat på data från dig i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="58ccf-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58ccf-105">Detaljer om dessa API:er anges i [referens om Customer Insights API:er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="58ccf-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="58ccf-106">De innehåller ytterligare information om operationer, parametrar och svar.</span><span class="sxs-lookup"><span data-stu-id="58ccf-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="58ccf-107">Den här artikeln guidar dig till åtkomst till Customer Insights-API:erna, till hur du skapar en Azure App-registrering och hjälper dig att komma igång med de tillgängliga klientbiblioteken.</span><span class="sxs-lookup"><span data-stu-id="58ccf-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="58ccf-108">Kom igång med att prova API:erna för Customer Insights</span><span class="sxs-lookup"><span data-stu-id="58ccf-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="58ccf-109">[Logga in](https://home.ci.ai.dynamics.com) på Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="58ccf-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="58ccf-110">Om du inte har någon prenumeration ännu [registrerar du dig för en utvärderingsversion av Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="58ccf-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="58ccf-111">Om du vill aktivera API:er på Customer Insights-miljön går du till **Admin** > **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="58ccf-112">Du behöver administratörsbehörighet för att kunna göra det.</span><span class="sxs-lookup"><span data-stu-id="58ccf-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="58ccf-113">Gå till fliken **API:er** och välj knappen **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="58ccf-114">Att aktivera API:erna skapar en primär och sekundär prenumerationsnyckel för din instans som används i API-begäranden.</span><span class="sxs-lookup"><span data-stu-id="58ccf-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="58ccf-115">Du kan återskapa nycklarna genom att välja **Återskapa primär** eller **Återskapa sekundär** på **Admin** > **Behörigheter** > **API:er**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktivera Customer Insights-API:er":::

1. <span data-ttu-id="58ccf-117">Välj **Utforska våra API:er** för att [prova API:erna](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="58ccf-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="58ccf-118">Välj en API-åtgärd och välj **Prova den**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="58ccf-119">I sidorutan anger du värdet i listmenyn **Auktorisering** till **implicit**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="58ccf-120">Rubriken `Authorization` får med ett ägartoken tillagt.</span><span class="sxs-lookup"><span data-stu-id="58ccf-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="58ccf-121">Din prenumerationsnyckel kommer att fyllas i automatiskt.</span><span class="sxs-lookup"><span data-stu-id="58ccf-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="58ccf-122">Lägg alternativt till alla nödvändiga frågeparametrar.</span><span class="sxs-lookup"><span data-stu-id="58ccf-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="58ccf-123">Rulla längst ned i sidorutan och välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="58ccf-124">HTTP-svaret visas snart nedan.</span><span class="sxs-lookup"><span data-stu-id="58ccf-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="En animerad gif som visar hur man väljer att testa API:er.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="58ccf-126">Skapa en ny appregistrering i Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="58ccf-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="58ccf-127">Med hjälp av de här stegen kan du komma igång med att använda Customer Insights-API:erna i ett Azure-program med hjälp av delegerade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="58ccf-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="58ccf-128">Se till att ha slutfört [Komma igång-avsnittet](#get-started-trying-the-customer-insights-apis) först.</span><span class="sxs-lookup"><span data-stu-id="58ccf-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="58ccf-129">Logga in på [Azure-portalen](https://portal.azure.com) med det konto som kan komma åt Customer Insights-data.</span><span class="sxs-lookup"><span data-stu-id="58ccf-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="58ccf-130">Till vänster väljer du **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="58ccf-131">Välj **Ny registrering**, tillhandahåll ett programnamn och välj kontotyp.</span><span class="sxs-lookup"><span data-stu-id="58ccf-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="58ccf-132">Lägg alternativt till en omdirigerings-URL.</span><span class="sxs-lookup"><span data-stu-id="58ccf-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="58ccf-133">http://localhost är tillräcklig för att utveckla ett program på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="58ccf-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="58ccf-134">På din nya App-registrering går du till **API-behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="En animerad gif för att ange API-behörighet i appregistrering.":::

1. <span data-ttu-id="58ccf-136">Välj **Lägg till en behörighet** och välj **Customer Insights** i sidorutan.</span><span class="sxs-lookup"><span data-stu-id="58ccf-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="58ccf-137">För **Behörighetstyp** väljer du **Delegerade behörigheter** och väljer behörigheten **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="58ccf-138">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-138">Select **Add permissions**.</span></span> <span data-ttu-id="58ccf-139">Om du behöver komma åt API:et utan att någon användare loggat in granskar du avsnittet [Server-till-server-programbehörigheter](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="58ccf-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="58ccf-140">Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.</span><span class="sxs-lookup"><span data-stu-id="58ccf-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="58ccf-141">Du kan använda Program-/klient-ID för den här appregistreringen med Microsoft Authentication Library (MSAL) för att få ett ägartoken att skicka med din begäran till API:et.</span><span class="sxs-lookup"><span data-stu-id="58ccf-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="En animerad gif för beviljande av administratörsmedgivande.":::

<span data-ttu-id="58ccf-143">Mer information om MSAL finns i [Översikt över MSAL (Microsoft Authentication Library)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="58ccf-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="58ccf-144">Mer information om appregistrering i Azure finns i [den nya upplevelsen av registrering av Azure Portal-appen](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="58ccf-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="58ccf-145">Information om hur du använder API:er som våra klientbibliotek finns i [Customer Insights-klientbibliotek](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="58ccf-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="58ccf-146">Programbehörigheter för server till server</span><span class="sxs-lookup"><span data-stu-id="58ccf-146">Server-to-server application permissions</span></span>

<span data-ttu-id="58ccf-147">Avsnittet för [registrering av appar](#create-a-new-app-registration-in-the-azure-portal) beskriver hur du registrerar en app som kräver att en användare loggar in för autentisering.</span><span class="sxs-lookup"><span data-stu-id="58ccf-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="58ccf-148">Lär dig hur du skapar en appregistrering som inte behöver användarinteraktion och som kan köras på en server.</span><span class="sxs-lookup"><span data-stu-id="58ccf-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="58ccf-149">På din app-registrering i Azure Portal går du till **API-behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="58ccf-150">Välj **Lägg till behörighet**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="58ccf-151">Välj fliken **API:er som min organisation använder** och välj **Dynamics 365 AI för Customer Insights** från listan.</span><span class="sxs-lookup"><span data-stu-id="58ccf-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="58ccf-152">För **Behörighetstyp** väljer du **Programbehörigheter** och väljer behörigheten **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-152">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="58ccf-153">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="58ccf-154">Gå tillbaka till **API-behörigheter** för din app-registrering.</span><span class="sxs-lookup"><span data-stu-id="58ccf-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="58ccf-155">Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.</span><span class="sxs-lookup"><span data-stu-id="58ccf-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="En animerad gif för beviljande av administratörsmedgivande.":::

1. <span data-ttu-id="58ccf-157">Slutligen måste vi lägga till namnet på appregistreringen som användare i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="58ccf-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="58ccf-158">Öppna Customer Insights, gå till **Admin** > **Behörigheter** och välj **Lägg till användare**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="58ccf-159">Sök efter namnet på din appregistrering, välj den bland sökresultaten och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="58ccf-160">Klientbibliotek för Customer Insights</span><span class="sxs-lookup"><span data-stu-id="58ccf-160">Customer Insights client libraries</span></span>

<span data-ttu-id="58ccf-161">Det här avsnittet hjälper dig att komma igång med att använda klientbiblioteken som är tillgängliga för Customer Insights-API:erna.</span><span class="sxs-lookup"><span data-stu-id="58ccf-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="58ccf-162">All bibliotekskällkod och alla exempelprogram finns på sidan [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="58ccf-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="58ccf-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="58ccf-163">C# NuGet</span></span>

<span data-ttu-id="58ccf-164">Lär dig hur du kommer igång med att använda C#-klientbiblioteken från NuGet.org. Mer information om paketet NuGet finns i [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="58ccf-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="58ccf-165">För närvarande riktar detta paket in sig på ramverken netstandard2.0 och netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="58ccf-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="58ccf-166">Lägga till C#-klientbiblioteket i ett C#-projekt</span><span class="sxs-lookup"><span data-stu-id="58ccf-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="58ccf-167">I Visual Studio öppnar du **NuGet-pakethanteraren** för ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="58ccf-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="58ccf-168">Sök efter **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="58ccf-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="58ccf-169">Välj **Installera** för att lägga till paketet i projektet.</span><span class="sxs-lookup"><span data-stu-id="58ccf-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="58ccf-170">Alternativt kan du köra det här kommandot i **pakethanterarkonsolen för NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="58ccf-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Lägg till NuGet-paket i Visual Studio-projekt":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="58ccf-172">Använda klientbiblioteket C#</span><span class="sxs-lookup"><span data-stu-id="58ccf-172">Use the C# client library</span></span>

1. <span data-ttu-id="58ccf-173">Använd [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) för att få ett `AccessToken` med hjälp av din befintliga [Azure-appregistrering](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="58ccf-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="58ccf-174">När du har autentiserat och fått ett token skapar du en ny eller använder en befintlig `HttpClient` med **DefaultRequestHeaders "Auktorisering"** inställd på **Ägare <access token>** och **Ocp-Apim-Subscription-Key** inställd på [**prenumerationsnyckel** från din Customer Insights-miljö](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="58ccf-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="58ccf-175">Återställ rubriken **Auktorisering** när det är lämpligt.</span><span class="sxs-lookup"><span data-stu-id="58ccf-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="58ccf-176">Till exempel när token löpt ut.</span><span class="sxs-lookup"><span data-stu-id="58ccf-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="58ccf-177">Skicka denna `HttpClient` i konstruktionen av `CustomerInsights`-klienten.</span><span class="sxs-lookup"><span data-stu-id="58ccf-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Exempel på httpclient":::

1. <span data-ttu-id="58ccf-179">Ringa samtal med klienten till "tilläggsmetoderna", till exempel `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="58ccf-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="58ccf-180">Om tillgång till underliggande `Microsoft.Rest.HttpOperationResponse` är att föredra, använd "http-meddelandemetoderna", till exempel `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="58ccf-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="58ccf-181">Svaret kommer sannolikt att vara av typen `object` eftersom metoden kan returnera flera typer (till exempel `IList<InstanceInfo>` och `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="58ccf-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="58ccf-182">Om du vill kontrollera returtypen kan du säkert typkonvertera objekten i de svarstyper som anges på [API-informationssidan](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) för den åtgärden.</span><span class="sxs-lookup"><span data-stu-id="58ccf-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="58ccf-183">Om mer information om begäran behövs använder du **metoderna för http-meddelande** för att komma åt råsvarsobjekt.</span><span class="sxs-lookup"><span data-stu-id="58ccf-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="58ccf-184">NodeJS-paket</span><span class="sxs-lookup"><span data-stu-id="58ccf-184">NodeJS package</span></span>

<span data-ttu-id="58ccf-185">Använd NodeJS-klientbiblioteken som är tillgängliga via NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="58ccf-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="58ccf-186">Python-paket</span><span class="sxs-lookup"><span data-stu-id="58ccf-186">Python package</span></span>

<span data-ttu-id="58ccf-187">Använd Python-klientbiblioteken som är tillgängliga via PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="58ccf-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
