---
title: Exportera Customer Insights-data till Facebook Ads Manager
description: Lär dig hur du konfigurerar anslutningen och exporterar till Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906832"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="32f57-103">Exportera segmentlistan till Facebook Ads Manager (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="32f57-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="32f57-104">Exportera segment med enhetliga kundprofiler till Facebook Ads Manager för att skapa kampanjer på Facebook och Instagram.</span><span class="sxs-lookup"><span data-stu-id="32f57-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="32f57-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="32f57-105">Prerequisites for connection</span></span>

- <span data-ttu-id="32f57-106">Du måste ha ett [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som inkluderar ett [**Facebook företagskonto**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="32f57-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="32f57-107">Du måste vara en administratör på [**Facebook Ad-kontot**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="32f57-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="32f57-108">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="32f57-108">Known limitations</span></span>

- <span data-ttu-id="32f57-109">Upp till 10 miljoner kundprofiler per export till annonshanteraren för Facebook.</span><span class="sxs-lookup"><span data-stu-id="32f57-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="32f57-110">Export till annonshanteraren för Facebook är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="32f57-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="32f57-111">Skapa eller uppdatera anpassade målgrupper endast i Facebook av typen *kundlista*.</span><span class="sxs-lookup"><span data-stu-id="32f57-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="32f57-112">Det kan ta upp till 90 minuter att exportera segment med totalt 10 miljoner profiler.</span><span class="sxs-lookup"><span data-stu-id="32f57-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="32f57-113">Konfigurera anslutning till Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="32f57-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="32f57-114">Innan användarna kan skapa en export måste en administratör konfigurera anslutningen till tjänsten och tillåta deltagare att använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="32f57-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="32f57-115">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="32f57-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="32f57-116">Välj **Lägg till anslutning** och välj **Facebook Ads Manager** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="32f57-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="32f57-117">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="32f57-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="32f57-118">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="32f57-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="32f57-119">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="32f57-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="32f57-120">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="32f57-120">Choose who can use this connection.</span></span> <span data-ttu-id="32f57-121">Om du inte gör något blir standardvärdet **Administratörer**.</span><span class="sxs-lookup"><span data-stu-id="32f57-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="32f57-122">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="32f57-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="32f57-123">Autentisera med Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="32f57-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="32f57-124">Välj **Fortsätt med Facebook** för att logga in på ditt Facebook annonskonto.</span><span class="sxs-lookup"><span data-stu-id="32f57-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="32f57-125">Bevilja **ads_management**-behörighet efter autentisering med Facebook.</span><span class="sxs-lookup"><span data-stu-id="32f57-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="32f57-126">Välj det **Facebook Ads-konto** som du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="32f57-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="32f57-127">Välj en **befintlig anpassad publik** i listrutan eller skapa en **ny anpassad publik**.</span><span class="sxs-lookup"><span data-stu-id="32f57-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="32f57-128">Mer information finns i [**målgrupper i Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="32f57-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="32f57-129">Du kan bara skapa eller uppdatera anpassade målgrupper på Facebook av typen *kundlista* med den här exporten.</span><span class="sxs-lookup"><span data-stu-id="32f57-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="32f57-130">I vissa fall visas anpassade målgrupper av olika typer i listrutan.</span><span class="sxs-lookup"><span data-stu-id="32f57-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="32f57-131">Om du väljer en annan typ än *kundlistan* misslyckas exporten.</span><span class="sxs-lookup"><span data-stu-id="32f57-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="32f57-132">Granska **Datasekretess och överensstämmelse** och välj **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="32f57-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="32f57-133">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="32f57-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="32f57-134">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="32f57-134">Configure an export</span></span>

<span data-ttu-id="32f57-135">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="32f57-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="32f57-136">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="32f57-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="32f57-137">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="32f57-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="32f57-138">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="32f57-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="32f57-139">I **Anslutning för export**, välj en anslutning från avsnittet **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="32f57-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="32f57-140">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="32f57-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="32f57-141">I fältet **Välj din nyckelidentifierare**, välj **E-post**, **Namn och adress** eller **Telefon** som ska skickas till Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="32f57-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="32f57-142">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="32f57-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="32f57-143">Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.</span><span class="sxs-lookup"><span data-stu-id="32f57-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="32f57-144">[TIPS] De bästa chanserna för en matchning uppstår om du väljer **E-post** som nyckelidentifierare.</span><span class="sxs-lookup"><span data-stu-id="32f57-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="32f57-145">Om du lägger till ytterligare identifierare kan matchningen förbättras.</span><span class="sxs-lookup"><span data-stu-id="32f57-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="32f57-146">Välj **Lägg till attribut** för att mappa fler attribut som ska skickas till Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="32f57-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="32f57-147">Attribut från Facebook Ads Manager mappar till följande användarvänliga namn: **FN** = **förnamn**, **LN** = **efternamn**, **FI** = **första initial**, **PHONE** = **telefon**, **GEN** = **kön**, **DOB** = **födelsedatum**, **ST** = **ort**, **CT** = **City**, **ZIP** = **postnummer**, **COUNTRY** = **land/region**</span><span class="sxs-lookup"><span data-stu-id="32f57-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="32f57-148">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="32f57-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="32f57-149">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="32f57-149">Select **Save**.</span></span>

<span data-ttu-id="32f57-150">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="32f57-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="32f57-151">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="32f57-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="32f57-152">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="32f57-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="32f57-153">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="32f57-153">Data privacy and compliance</span></span>

<span data-ttu-id="32f57-154">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Facebook Ads Manager tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="32f57-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="32f57-155">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Facebook Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="32f57-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="32f57-156">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="32f57-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="32f57-157">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="32f57-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
