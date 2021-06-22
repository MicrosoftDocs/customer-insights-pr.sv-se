---
title: Exportera Customer Insights-data till LinkedIn Ads
description: Lär dig hur du konfigurerar anslutningen och exporterar till LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124560"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="e7ff0-103">Exportera segment till LinkedIn Ads (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="e7ff0-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="e7ff0-104">Exportera segment med enhetliga kundprofiler till LinkedIn Ads för att skapa matchade målgrupper.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="e7ff0-105">Använd de matchade målgrupperna för företagsinriktning och kontaktinriktning.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7ff0-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e7ff0-106">Prerequisites</span></span>

-   <span data-ttu-id="e7ff0-107">Du har ett [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e7ff0-108">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e7ff0-109">Kundprofiler i de exporterade segmenten innehåller ett fält med en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e7ff0-110">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="e7ff0-110">Known limitations</span></span>

- <span data-ttu-id="e7ff0-111">Du kan exportera upp till 100 000 profiler per export till LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="e7ff0-112">Export till LinkedIn Ads är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="e7ff0-113">Det kan ta upp till 10 minuter att exportera upp till 100 000 profiler till LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="e7ff0-114">Upprätta anslutningen till LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="e7ff0-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="e7ff0-115">I målgruppsinsikter, gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e7ff0-116">Välj **Lägg till anslutning** och välj **LinkedIn Ads** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="e7ff0-117">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e7ff0-118">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e7ff0-119">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e7ff0-120">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-120">Choose who can use this connection.</span></span> <span data-ttu-id="e7ff0-121">Om du inte gör något blir standardvärdet administratörer.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="e7ff0-122">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e7ff0-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e7ff0-123">Ange ditt [LinkedIn Campaign Manager-konto-ID](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="e7ff0-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="e7ff0-124">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e7ff0-125">Välj **Anslut** om du vill initiera anslutningen till Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="e7ff0-126">Välj **Autentisera med LinkedIn** och tillhandahåll dina administratörsautentiseringsuppgifter för LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="e7ff0-127">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e7ff0-128">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e7ff0-129">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="e7ff0-129">Configure an export</span></span>

<span data-ttu-id="e7ff0-130">Du kan konfigurera en export om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="e7ff0-131">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e7ff0-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e7ff0-132">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7ff0-133">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e7ff0-134">I fältet **Anslutning för export**, välj en anslutning från avsnittet LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="e7ff0-135">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e7ff0-136">Välj om du vill exportera data för att göra [kontaktinriktning](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [företagsinriktning](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="e7ff0-137">I avsnittet **Datamatchning** väljer du fältet i den enhetliga kundprofilen som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e7ff0-138">Det krävs för att exportera segment till LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="e7ff0-139">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-139">Select the segments you want to export.</span></span> <span data-ttu-id="e7ff0-140">De matchade målgrupperna i LinkedIn Campaign Manager skapas automatiskt med namnet på de segment som du har valt att exportera.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="e7ff0-141">Varje segment resulterar i en separat matchad målgrupp.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="e7ff0-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-142">Select **Save**.</span></span>

<span data-ttu-id="e7ff0-143">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e7ff0-144">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e7ff0-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e7ff0-145">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e7ff0-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e7ff0-146">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="e7ff0-146">Data privacy and compliance</span></span>

<span data-ttu-id="e7ff0-147">När du aktiverar Dynamics 365 Customer Insights för att överföra data till LinkedIn Ads tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e7ff0-148">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att LinkedIn Ads uppfyller alla eventuella sekretess- eller säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e7ff0-149">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e7ff0-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e7ff0-150">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort det här exportmålet för att stoppa användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="e7ff0-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
