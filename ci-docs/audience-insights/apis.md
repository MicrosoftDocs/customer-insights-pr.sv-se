---
title: Arbeta med API:er
description: Använd API:er och förstå begränsningar.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267546"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="53983-103">Arbeta med API:er i Customer Insights</span><span class="sxs-lookup"><span data-stu-id="53983-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="53983-104">Dynamics 365 Customer Insights tillhandahåller API:er för att bygga egna program baserat på data från dig i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="53983-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53983-105">Detaljer om dessa API:er anges i [referens om Customer Insights API:er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="53983-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="53983-106">De innehåller ytterligare information om operationer, parametrar och svar.</span><span class="sxs-lookup"><span data-stu-id="53983-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="53983-107">Den här artikeln guidar dig till åtkomst till Customer Insights-API:erna, till hur du skapar en Azure App-registrering och hjälper dig att komma igång med de tillgängliga klientbiblioteken.</span><span class="sxs-lookup"><span data-stu-id="53983-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="53983-108">Kom igång med att prova API:erna för Customer Insights</span><span class="sxs-lookup"><span data-stu-id="53983-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="53983-109">[Logga in](https://home.ci.ai.dynamics.com) på Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="53983-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="53983-110">Om du inte har någon prenumeration ännu [registrerar du dig för en utvärderingsversion av Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="53983-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="53983-111">Om du vill aktivera API:er på Customer Insights-miljön går du till **Admin** > **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="53983-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="53983-112">Du behöver administratörsbehörighet för att kunna göra det.</span><span class="sxs-lookup"><span data-stu-id="53983-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="53983-113">Gå till fliken **API:er** och välj knappen **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="53983-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="53983-114">Att aktivera API:erna skapar en primär och sekundär prenumerationsnyckel för din instans som används i API-begäranden.</span><span class="sxs-lookup"><span data-stu-id="53983-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="53983-115">Du kan återskapa nycklarna genom att välja **Återskapa primär** eller **Återskapa sekundär** på **Admin** > **Behörigheter** > **API:er**.</span><span class="sxs-lookup"><span data-stu-id="53983-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktivera Customer Insights-API:er":::

1. <span data-ttu-id="53983-117">Välj **Utforska våra API:er** för att prova API:erna.</span><span class="sxs-lookup"><span data-stu-id="53983-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="53983-118">Välj en API-åtgärd och välj **Prova den**.</span><span class="sxs-lookup"><span data-stu-id="53983-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="53983-119">I sidorutan anger du värdet i listmenyn **Auktorisering** till **implicit**.</span><span class="sxs-lookup"><span data-stu-id="53983-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="53983-120">Rubriken `Authorization` får med ett ägartoken tillagt.</span><span class="sxs-lookup"><span data-stu-id="53983-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="53983-121">Din prenumerationsnyckel kommer att fyllas i automatiskt.</span><span class="sxs-lookup"><span data-stu-id="53983-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="53983-122">Lägg alternativt till alla nödvändiga frågeparametrar.</span><span class="sxs-lookup"><span data-stu-id="53983-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="53983-123">Rulla längst ned i sidorutan och välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="53983-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="53983-124">HTTP-svaret visas snart nedan.</span><span class="sxs-lookup"><span data-stu-id="53983-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="53983-125">Skapa en ny appregistrering i Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="53983-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="53983-126">Med hjälp av de här stegen kan du komma igång med att använda Customer Insights-API:erna i ett Azure-program med hjälp av delegerade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="53983-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="53983-127">Se till att ha slutfört [Komma igång-avsnittet](#get-started-trying-the-customer-insights-apis) först.</span><span class="sxs-lookup"><span data-stu-id="53983-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="53983-128">Logga in på [Azure-portalen](https://portal.azure.com) med det konto som kan komma åt Customer Insights-data.</span><span class="sxs-lookup"><span data-stu-id="53983-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="53983-129">Till vänster väljer du **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="53983-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="53983-130">Välj **Ny registrering**, tillhandahåll ett programnamn och välj kontotyp.</span><span class="sxs-lookup"><span data-stu-id="53983-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="53983-131">Lägg alternativt till en omdirigerings-URL.</span><span class="sxs-lookup"><span data-stu-id="53983-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="53983-132">http://localhost är tillräcklig för att utveckla ett program på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="53983-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="53983-133">På din nya App-registrering går du till **API-behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="53983-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="53983-134">Välj **Lägg till en behörighet** och välj **Customer Insights** i sidorutan.</span><span class="sxs-lookup"><span data-stu-id="53983-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="53983-135">För **Behörighetstyp** väljer du **Delegerade behörigheter** och väljer behörigheten **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="53983-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="53983-136">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="53983-136">Select **Add permissions**.</span></span> <span data-ttu-id="53983-137">Om du behöver komma åt API:et utan att någon användare loggat in granskar du avsnittet [Server-till-server-programbehörigheter](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="53983-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="53983-138">Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.</span><span class="sxs-lookup"><span data-stu-id="53983-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="53983-139">Du kan använda Program-/klient-ID för den här appregistreringen med Microsoft Authentication Library (MSAL) för att få ett ägartoken att skicka med din begäran till API:et.</span><span class="sxs-lookup"><span data-stu-id="53983-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="53983-140">Mer information om MSAL finns i [Översikt över MSAL (Microsoft Authentication Library)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="53983-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="53983-141">Mer information om appregistrering i Azure finns i [den nya upplevelsen av registrering av Azure Portal-appen](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="53983-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="53983-142">Information om hur du använder API:er som våra klientbibliotek finns i [Customer Insights-klientbibliotek](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="53983-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="53983-143">Programbehörigheter för server till server</span><span class="sxs-lookup"><span data-stu-id="53983-143">Server-to-server application permissions</span></span>

<span data-ttu-id="53983-144">Avsnittet för [registrering av appar](#create-a-new-app-registration-in-the-azure-portal) beskriver hur du registrerar en app som kräver att en användare loggar in för autentisering.</span><span class="sxs-lookup"><span data-stu-id="53983-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="53983-145">Lär dig hur du skapar en appregistrering som inte behöver användarinteraktion och som kan köras på en server.</span><span class="sxs-lookup"><span data-stu-id="53983-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="53983-146">På din app-registrering i Azure Portal går du till **API-behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="53983-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="53983-147">Välj **Lägg till en behörighet** och välj **Customer Insights** i sidorutan.</span><span class="sxs-lookup"><span data-stu-id="53983-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="53983-148">För **Behörighetstyp** väljer du **Programbehörigheter** och väljer behörigheten **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="53983-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="53983-149">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="53983-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="53983-150">För att ge administratörsmedgivande på denna programbehörighet måste du lägga till ett Service Principal.</span><span class="sxs-lookup"><span data-stu-id="53983-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="53983-151">Installera Azure Active Directory PowerShell-modulen (AD): `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="53983-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="53983-152">Anslut till ditt AD-konto: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="53983-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="53983-153">Du hittar klientorganisationens ID på **Översikt** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="53983-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="53983-154">Kör följande kommando för att lägga till Azure AD Service Principal `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parametern AppId gäller API-appen Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="53983-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Exempel på huvudkonto för tjänsten":::

1. <span data-ttu-id="53983-156">Gå tillbaka till **API-behörigheter** för din app-registrering.</span><span class="sxs-lookup"><span data-stu-id="53983-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="53983-157">Välj **Bevilja admin-godkännande för...** för att slutföra registreringen av appen.</span><span class="sxs-lookup"><span data-stu-id="53983-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="53983-158">Slutligen måste vi lägga till namnet på appregistreringen som användare i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="53983-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="53983-159">Öppna Customer Insights, gå till **Admin** > **Behörigheter** och välj **Lägg till användare**.</span><span class="sxs-lookup"><span data-stu-id="53983-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="53983-160">Sök efter namnet på din appregistrering, välj den bland sökresultaten och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="53983-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="53983-161">Klientbibliotek för Customer Insights</span><span class="sxs-lookup"><span data-stu-id="53983-161">Customer Insights client libraries</span></span>

<span data-ttu-id="53983-162">Det här avsnittet hjälper dig att komma igång med att använda klientbiblioteken som är tillgängliga för Customer Insights-API:erna.</span><span class="sxs-lookup"><span data-stu-id="53983-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="53983-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="53983-163">C# NuGet</span></span>

<span data-ttu-id="53983-164">Lär dig hur du kommer igång med att använda C#-klientbiblioteken från NuGet.org. Mer information om paketet NuGet finns i [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="53983-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="53983-165">För närvarande riktar detta paket in sig på ramverken netstandard2.0 och netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="53983-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="53983-166">Lägga till C#-klientbiblioteket i ett C#-projekt</span><span class="sxs-lookup"><span data-stu-id="53983-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="53983-167">I Visual Studio öppnar du **NuGet-pakethanteraren** för ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="53983-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="53983-168">Sök efter **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="53983-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="53983-169">Välj **Installera** för att lägga till paketet i projektet.</span><span class="sxs-lookup"><span data-stu-id="53983-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="53983-170">Alternativt kan du köra det här kommandot i **pakethanterarkonsolen för NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="53983-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Lägg till NuGet-paket i Visual Studio-projekt":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="53983-172">Använda klientbiblioteket C#</span><span class="sxs-lookup"><span data-stu-id="53983-172">Use the C# client library</span></span>

1. <span data-ttu-id="53983-173">Använd [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) för att få ett `AccessToken` med hjälp av din befintliga [Azure-appregistrering](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="53983-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="53983-174">När du har autentiserat och fått ett token skapar du en ny eller använder en befintlig `HttpClient` med **DefaultRequestHeaders "Auktorisering"** inställd på **Ägare <access token>** och **Ocp-Apim-Subscription-Key** inställd på [**prenumerationsnyckel** från din Customer Insights-miljö](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="53983-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="53983-175">Återställ rubriken **Auktorisering** när det är lämpligt.</span><span class="sxs-lookup"><span data-stu-id="53983-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="53983-176">Till exempel när token löpt ut.</span><span class="sxs-lookup"><span data-stu-id="53983-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="53983-177">Skicka denna `HttpClient` i konstruktionen av `CustomerInsights`-klienten.</span><span class="sxs-lookup"><span data-stu-id="53983-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Exempel på httpclient":::

1. <span data-ttu-id="53983-179">Ringa samtal med klienten till "tilläggsmetoderna", till exempel `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="53983-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="53983-180">Om tillgång till underliggande `Microsoft.Rest.HttpOperationResponse` är att föredra, använd "http-meddelandemetoderna", till exempel `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="53983-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="53983-181">Svaret kommer sannolikt att vara av typen `object` eftersom metoden kan returnera flera typer (till exempel `IList<InstanceInfo>` och `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="53983-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="53983-182">Om du vill kontrollera returtypen kan du säkert typkonvertera objekten i de svarstyper som anges på [API-informationssidan](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) för den åtgärden.</span><span class="sxs-lookup"><span data-stu-id="53983-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="53983-183">Om mer information om begäran behövs använder du **metoderna för http-meddelande** för att komma åt råsvarsobjekt.</span><span class="sxs-lookup"><span data-stu-id="53983-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]