---
title: Tillägget för kundkort i Dynamics 365-appar
description: Visa data från målinsikter i Dynamics 365-appar med det här tillägget.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059610"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="061c5-103">Tillägget för kundkort (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="061c5-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="061c5-104">Få en 360-graders vy över dina kunder direkt i Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="061c5-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="061c5-105">Med kundkortstillägget installerat i en Dynamics 365-app som stöds kan du välja att visa demografi, insikter och aktivitetstid.</span><span class="sxs-lookup"><span data-stu-id="061c5-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="061c5-106">Tillägget hämtar data från Customer Insights utan att det påverkar data i den anslutna Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="061c5-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="061c5-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="061c5-107">Prerequisites</span></span>

- <span data-ttu-id="061c5-108">Tillägget fungerar bara med Dynamics 365 modellbaserade appar, till exempel Sales eller kundtjänst, version 9.0 och senare.</span><span class="sxs-lookup"><span data-stu-id="061c5-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="061c5-109">För att dina Dynamics 365-data ska mappas till målinsikternas kundprofiler måste de [tas in i appen Dynamics 365 med hjälp av kopplingen Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="061c5-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="061c5-110">Alla Dynamics 365-användare av tillägget kundkort måste [läggas till som användare](permissions.md) målinsikter för att kunna se dessa data.</span><span class="sxs-lookup"><span data-stu-id="061c5-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="061c5-111">[Konfigurerade sök- och filterfunktioner](search-filter-index.md) i målinsikter krävs för att slå upp data som ska fungera.</span><span class="sxs-lookup"><span data-stu-id="061c5-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="061c5-112">För varje tilläggskontroll används specifika data målinsikter:</span><span class="sxs-lookup"><span data-stu-id="061c5-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="061c5-113">Måttkontroll: Kräver [konfigurerade åtgärder](measures.md).</span><span class="sxs-lookup"><span data-stu-id="061c5-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="061c5-114">Intelligent kontroll: Kräver data som genereras med hjälp av [prediktioner](predictions.md) eller [anpassade modeller](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="061c5-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="061c5-115">Demografisk kontroll: Demografiska fält (till exempel ålder eller kön) är tillgängliga i den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="061c5-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="061c5-116">Berikningskontroll: kräver aktiva [berikningar](enrichment-hub.md) som tillämpas på kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="061c5-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="061c5-117">Tidslinjekontroll: Kräver [konfigurerade aktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="061c5-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="061c5-118">Installera tillägget för kundkort</span><span class="sxs-lookup"><span data-stu-id="061c5-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="061c5-119">Kundkort-tillägget är en lösning för Customer Engagement-appar i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="061c5-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="061c5-120">Om du vill installera lösningen går du till AppSource och söker efter **Dynamics kundkort**.</span><span class="sxs-lookup"><span data-stu-id="061c5-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="061c5-121">Välj [Tillägget för kundkort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) och välj **Skaffa det nu**.</span><span class="sxs-lookup"><span data-stu-id="061c5-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="061c5-122">Du kan behöva logga in med administratörsautentiseringsuppgifter för Dynamics 365-appen för att installera lösningen.</span><span class="sxs-lookup"><span data-stu-id="061c5-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="061c5-123">Det kan ta en stund innan lösningen har installerats i din miljö.</span><span class="sxs-lookup"><span data-stu-id="061c5-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="061c5-124">Konfigurera tillägget för kundkortet</span><span class="sxs-lookup"><span data-stu-id="061c5-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="061c5-125">Som administratör går du till avsnittet **Inställningar** i Dynamics 365 och väljer **lösningar**.</span><span class="sxs-lookup"><span data-stu-id="061c5-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="061c5-126">Markera länken **visningsnamn** för lösningen **Dynamics 365 Customer Insights tillägg för kundkort (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="061c5-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="061c5-127">![Välj visningsnamn](media/select-display-name.png "Välj visningsnamn")</span><span class="sxs-lookup"><span data-stu-id="061c5-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="061c5-128">Välj **Logga in** och ange autentiseringsuppgifterna för administratörskontot som du använder för att konfigurera Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="061c5-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="061c5-129">Kontrollera att webbläsarens popup-blockerare inte blockerar verifieringsfönstret när du klickar på knappen **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="061c5-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="061c5-130">Välj vilken Customer Insights-miljön du vill hämta data från.</span><span class="sxs-lookup"><span data-stu-id="061c5-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="061c5-131">Definiera fältmappningen till poster i Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="061c5-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="061c5-132">Beroende på dina data i Customer Insights kan du välja att mappa följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="061c5-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="061c5-133">Om du vill mappa med en kontakt markerar du fältet i entiteten Kund som matchar ID för din kontaktentitet.</span><span class="sxs-lookup"><span data-stu-id="061c5-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="061c5-134">Om du vill mappa med ett konto markerar du fältet i entiteten Kund som matchar ID för din kontoentitet.</span><span class="sxs-lookup"><span data-stu-id="061c5-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="061c5-135">![Fältet kontakt-ID](media/contact-id-field.png "Fältet kontakt-ID")</span><span class="sxs-lookup"><span data-stu-id="061c5-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="061c5-136">Välj **Spara konfiguration** för att spara inställningen.</span><span class="sxs-lookup"><span data-stu-id="061c5-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="061c5-137">Härnäst måste du tilldela säkerhetsroller i Dynamics 365 så att användarna kan anpassa och se kundkortet.</span><span class="sxs-lookup"><span data-stu-id="061c5-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="061c5-138">I Dynamics 365 går du till **Inställningar** > **Säkerhet** > **Användare**.</span><span class="sxs-lookup"><span data-stu-id="061c5-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="061c5-139">Markera användarna som du vill redigera användarroller för och välj **hantera roller**.</span><span class="sxs-lookup"><span data-stu-id="061c5-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="061c5-140">Tilldela rollen **Anpassare av Customer Insights-kort** för användare som ska anpassa innehållet som visas på kortet för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="061c5-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="061c5-141">Lägga till Kundkortskontroller i formulär</span><span class="sxs-lookup"><span data-stu-id="061c5-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="061c5-142">Om du vill lägga till kundkortskontrollerna i kontaktformuläret går du till **inställningar** > **anpassningar** i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="061c5-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="061c5-143">Välj **Anpassa systemet**</span><span class="sxs-lookup"><span data-stu-id="061c5-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="061c5-144">Bläddra till entiteten **kontakt**, expandera den och välj sedan **formulär**.</span><span class="sxs-lookup"><span data-stu-id="061c5-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="061c5-145">Välj det kontaktformulär där du vill lägga till kundkortskontrollerna.</span><span class="sxs-lookup"><span data-stu-id="061c5-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="061c5-146">![Välj kontaktformulär](media/contact-active-forms.png "Välj kontaktformulär")</span><span class="sxs-lookup"><span data-stu-id="061c5-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="061c5-147">Om du vill lägga en kontroll för formulärredigerare drar du ett fält från **fältutforskaren** till den plats där du vill att den visas.</span><span class="sxs-lookup"><span data-stu-id="061c5-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="061c5-148">Markera det fält på formuläret som du just har lagt till och välj **Ändra egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="061c5-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="061c5-149">Gå till fliken **Kontroller** och välj **Lägg till kontroll**.</span><span class="sxs-lookup"><span data-stu-id="061c5-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="061c5-150">Välj en av de tillgängliga anpassade kontrollerna och välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="061c5-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="061c5-151">I dialogrutan **Fältegenskaper** avmarkera kryssrutan **Visa etiketten i formuläret**.</span><span class="sxs-lookup"><span data-stu-id="061c5-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="061c5-152">Välj alternativet **webb** för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="061c5-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="061c5-153">För berikningskontrollen väljer du vilken typ av berikning du vill visa genom att konfigurera fältet **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="061c5-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="061c5-154">Lägg till en separat berikningskontroll för varje berikningstyp.</span><span class="sxs-lookup"><span data-stu-id="061c5-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="061c5-155">Klicka på **Spara** och **Publicera** om du vill publicera det uppdaterade kontaktformuläret.</span><span class="sxs-lookup"><span data-stu-id="061c5-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="061c5-156">Gå till det publicerade kontaktformuläret.</span><span class="sxs-lookup"><span data-stu-id="061c5-156">Go to the published contact form.</span></span> <span data-ttu-id="061c5-157">Den nyligen tillagda kontrollen visas.</span><span class="sxs-lookup"><span data-stu-id="061c5-157">You'll see the newly added control.</span></span> <span data-ttu-id="061c5-158">Du kan behöva logga in första gången du använder den.</span><span class="sxs-lookup"><span data-stu-id="061c5-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="061c5-159">Du kan anpassa vad som ska visas på den anpassade kontrollen genom att klicka på knappen Redigera i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="061c5-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="061c5-160">Uppgradera tillägget för kundkort</span><span class="sxs-lookup"><span data-stu-id="061c5-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="061c5-161">Kundkortstillägget uppgraderas inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="061c5-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="061c5-162">Uppgradera till den senaste versionen genom att följa stegen i appen Dynamics 365 som har tillägget installerat.</span><span class="sxs-lookup"><span data-stu-id="061c5-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="061c5-163">I appen Dynamics 365 går du till **Inställningar** > **Anpassning** och väljer **Lösningar**.</span><span class="sxs-lookup"><span data-stu-id="061c5-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="061c5-164">I tabellen med tillägg söker du efter **CustomerInsightsCustomerCard** och väljer raden.</span><span class="sxs-lookup"><span data-stu-id="061c5-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="061c5-165">Välj **Tillämpa lösningsuppgradering** i åtgärdsfältet.</span><span class="sxs-lookup"><span data-stu-id="061c5-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Uppgradera lösningen i området Anpassning i Dynamics 365-appar":::

1. <span data-ttu-id="061c5-167">När du har startat uppgraderingsprocessen visas en inläsningssymbol tills uppgraderingen är klar.</span><span class="sxs-lookup"><span data-stu-id="061c5-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="061c5-168">Om det inte finns någon senare version visas ett felmeddelande för uppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="061c5-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
