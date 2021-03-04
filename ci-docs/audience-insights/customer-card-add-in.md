---
title: Installera och konfigurera Tillägget för kundkort
description: Installera och konfigurera tillägget kundkort för Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268066"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="d6899-103">Tillägget för kundkort (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="d6899-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d6899-104">Få en 360-graders vy över dina kunder direkt i Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="d6899-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="d6899-105">Visa tidslinjer för demografiska data och aktiviteter med kundkorttillägget.</span><span class="sxs-lookup"><span data-stu-id="d6899-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6899-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d6899-106">Prerequisites</span></span>

- <span data-ttu-id="d6899-107">Dynamics 365-app (t.ex. Försäljningsnav eller Kundtjänstnav) version 9.0 och senare med enhetligt gränssnitt aktiverat.</span><span class="sxs-lookup"><span data-stu-id="d6899-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="d6899-108">Kundprofiler som [matats in från Dynamics 365-appen med Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d6899-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="d6899-109">Användare av tillägget Kundkort måste [läggas till som användare](permissions.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="d6899-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="d6899-110">[Konfigurerade sök- och filterfunktioner](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d6899-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="d6899-111">Demografisk kontroll: Demografiska fält (till exempel ålder eller kön) är tillgängliga i den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="d6899-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="d6899-112">Berikningskontroll: kräver aktiva [berikningar](enrichment-hub.md) som tillämpas på kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="d6899-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="d6899-113">Intelligenskontroll: Kräver data som genererats med Azure Machine Learning ([prediktionsmodeller](predictions.md) eller [anpassade modeller](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="d6899-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="d6899-114">Måttkontroll: Kräver [konfigurerade åtgärder](measures.md).</span><span class="sxs-lookup"><span data-stu-id="d6899-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="d6899-115">Tidslinjekontroll: Kräver [konfigurerade aktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="d6899-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="d6899-116">Installera tillägget för kundkort</span><span class="sxs-lookup"><span data-stu-id="d6899-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="d6899-117">Kundkort-tillägget är en lösning för Customer Engagement-appar i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6899-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="d6899-118">Om du vill installera lösningen går du till AppSource och söker efter **Dynamics kundkort**.</span><span class="sxs-lookup"><span data-stu-id="d6899-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="d6899-119">Välj [Tillägget för kundkort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) och välj **Skaffa det nu**.</span><span class="sxs-lookup"><span data-stu-id="d6899-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="d6899-120">Du kan behöva logga in med administratörsautentiseringsuppgifter för Dynamics 365-appen för att installera lösningen.</span><span class="sxs-lookup"><span data-stu-id="d6899-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="d6899-121">Det kan ta en stund innan lösningen har installerats i din miljö.</span><span class="sxs-lookup"><span data-stu-id="d6899-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="d6899-122">Konfigurera tillägget för kundkortet</span><span class="sxs-lookup"><span data-stu-id="d6899-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="d6899-123">Som administratör går du till avsnittet **Inställningar** i Dynamics 365 och väljer **lösningar**.</span><span class="sxs-lookup"><span data-stu-id="d6899-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="d6899-124">Markera länken **visningsnamn** för lösningen **Dynamics 365 Customer Insights tillägg för kundkort (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="d6899-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6899-125">![Välj visningsnamn](media/select-display-name.png "Välj visningsnamn")</span><span class="sxs-lookup"><span data-stu-id="d6899-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="d6899-126">Välj **Logga in** och ange autentiseringsuppgifterna för administratörskontot som du använder för att konfigurera Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d6899-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d6899-127">Kontrollera att webbläsarens popup-blockerare inte blockerar verifieringsfönstret när du klickar på knappen **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="d6899-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="d6899-128">Välj vilken miljö du vill hämta data från.</span><span class="sxs-lookup"><span data-stu-id="d6899-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="d6899-129">Definiera fältmappningen till poster i Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="d6899-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="d6899-130">Om du vill mappa med en kontakt markerar du fältet i entiteten Kund som matchar ID för din kontaktentitet.</span><span class="sxs-lookup"><span data-stu-id="d6899-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="d6899-131">Om du vill mappa med ett konto markerar du fältet i entiteten Kund som matchar ID för din kontoentitet.</span><span class="sxs-lookup"><span data-stu-id="d6899-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6899-132">![Fältet kontakt-ID](media/contact-id-field.png "Fältet kontakt-ID")</span><span class="sxs-lookup"><span data-stu-id="d6899-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="d6899-133">Välj **Spara konfiguration** för att spara inställningen.</span><span class="sxs-lookup"><span data-stu-id="d6899-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="d6899-134">Härnäst måste du tilldela säkerhetsroller i Dynamics 365 så att användarna kan anpassa och se kundkortet.</span><span class="sxs-lookup"><span data-stu-id="d6899-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="d6899-135">I Dynamics 365 går du till **Inställningar** > **Säkerhet** > **Användare**.</span><span class="sxs-lookup"><span data-stu-id="d6899-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="d6899-136">Markera användarna som du vill redigera användarroller för och välj **hantera roller**.</span><span class="sxs-lookup"><span data-stu-id="d6899-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="d6899-137">Tilldela rollen **Anpassare av Customer Insights-kort** för användare som ska anpassa innehållet som visas på kortet för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="d6899-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="d6899-138">Lägga till Kundkortskontroller i formulär</span><span class="sxs-lookup"><span data-stu-id="d6899-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="d6899-139">Om du vill lägga till kundkortskontrollerna i kontaktformuläret går du till **inställningar** > **anpassningar** i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6899-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="d6899-140">Välj **Anpassa systemet**</span><span class="sxs-lookup"><span data-stu-id="d6899-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="d6899-141">Bläddra till entiteten **kontakt**, expandera den och välj sedan **formulär**.</span><span class="sxs-lookup"><span data-stu-id="d6899-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="d6899-142">Välj det kontaktformulär där du vill lägga till kundkortskontrollerna.</span><span class="sxs-lookup"><span data-stu-id="d6899-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d6899-143">![Välj kontaktformulär](media/contact-active-forms.png "Välj kontaktformulär")</span><span class="sxs-lookup"><span data-stu-id="d6899-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="d6899-144">Om du vill lägga en kontroll för formulärredigerare drar du ett fält från **fältutforskaren** till den plats där du vill att den visas.</span><span class="sxs-lookup"><span data-stu-id="d6899-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="d6899-145">Markera det fält på formuläret som du just har lagt till och välj **Ändra egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="d6899-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="d6899-146">Gå till fliken **Kontroller** och välj **Lägg till kontroll**.</span><span class="sxs-lookup"><span data-stu-id="d6899-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="d6899-147">Välj en av de tillgängliga anpassade kontrollerna och välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d6899-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="d6899-148">I dialogrutan **Fältegenskaper** avmarkera kryssrutan **Visa etiketten i formuläret**.</span><span class="sxs-lookup"><span data-stu-id="d6899-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="d6899-149">Välj alternativet **webb** för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="d6899-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="d6899-150">För berikningskontrollen väljer du vilken typ av berikning du vill visa genom att konfigurera fältet **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="d6899-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="d6899-151">Lägg till en separat berikningskontroll för varje berikningstyp.</span><span class="sxs-lookup"><span data-stu-id="d6899-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="d6899-152">Klicka på **Spara** och **Publicera** om du vill publicera det uppdaterade kontaktformuläret.</span><span class="sxs-lookup"><span data-stu-id="d6899-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="d6899-153">Gå till det publicerade kontaktformuläret.</span><span class="sxs-lookup"><span data-stu-id="d6899-153">Go to the published contact form.</span></span> <span data-ttu-id="d6899-154">Den nyligen tillagda kontrollen visas.</span><span class="sxs-lookup"><span data-stu-id="d6899-154">You'll see the newly added control.</span></span> <span data-ttu-id="d6899-155">Du kan behöva logga in första gången du använder den.</span><span class="sxs-lookup"><span data-stu-id="d6899-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="d6899-156">Du kan anpassa vad som ska visas på den anpassade kontrollen genom att klicka på knappen Redigera i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="d6899-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="d6899-157">Uppgradera tillägget för kundkort</span><span class="sxs-lookup"><span data-stu-id="d6899-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="d6899-158">Kundkortstillägget uppgraderas inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d6899-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="d6899-159">Uppgradera till den senaste versionen genom att följa stegen i appen Dynamics 365 som har tillägget installerat.</span><span class="sxs-lookup"><span data-stu-id="d6899-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="d6899-160">I appen Dynamics 365 går du till **Inställningar** > **Anpassning** och väljer **Lösningar**.</span><span class="sxs-lookup"><span data-stu-id="d6899-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="d6899-161">I tabellen med tillägg söker du efter **CustomerInsightsCustomerCard** och väljer raden.</span><span class="sxs-lookup"><span data-stu-id="d6899-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="d6899-162">Välj **Tillämpa lösningsuppgradering** i åtgärdsfältet.</span><span class="sxs-lookup"><span data-stu-id="d6899-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Uppgradera lösningen i området Anpassning i Dynamics 365-appar":::

1. <span data-ttu-id="d6899-164">När du har startat uppgraderingsprocessen visas en inläsningssymbol tills uppgraderingen är klar.</span><span class="sxs-lookup"><span data-stu-id="d6899-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="d6899-165">Om det inte finns någon senare version visas ett felmeddelande för uppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="d6899-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]