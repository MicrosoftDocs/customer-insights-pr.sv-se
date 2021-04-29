---
title: Exportera Customer Insights-data till RollWorks
description: Lär dig hur du konfigurerar anslutningen och exporterar till RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760648"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="59e90-103">Exportera segmentlistor till RollWorks (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="59e90-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="59e90-104">Exportera segment med enhetliga kundprofiler till RollWorks och använd dem för annonser.</span><span class="sxs-lookup"><span data-stu-id="59e90-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="59e90-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="59e90-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="59e90-106">Du har ett [RollWorks-konto](https://www.rollworks.com/) och motsvarande autentiseringsuppgifter för administratör.</span><span class="sxs-lookup"><span data-stu-id="59e90-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="59e90-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="59e90-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="59e90-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="59e90-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="59e90-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="59e90-109">Known limitations</span></span>

- <span data-ttu-id="59e90-110">Du kan exportera upp till 250 000 profiler per export till RollWorks.</span><span class="sxs-lookup"><span data-stu-id="59e90-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="59e90-111">Du kan inte exportera segment med färre än 100 profiler till RollWorks.</span><span class="sxs-lookup"><span data-stu-id="59e90-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="59e90-112">Export till RollWorks är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="59e90-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="59e90-113">Det kan ta upp till 250 000 profiler till RollWorks kan ta upp till 10 minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="59e90-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="59e90-114">Hur många profiler du kan exportera till RollWorks beror på och begränsas av ditt kontrakt med RollWorks.</span><span class="sxs-lookup"><span data-stu-id="59e90-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="59e90-115">Konfigurera anslutningen RollWorks</span><span class="sxs-lookup"><span data-stu-id="59e90-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="59e90-116">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="59e90-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="59e90-117">Välj **Lägg till anslutning** och välj **RollWorks** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59e90-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="59e90-118">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="59e90-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="59e90-119">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="59e90-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="59e90-120">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59e90-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="59e90-121">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59e90-121">Choose who can use this connection.</span></span> <span data-ttu-id="59e90-122">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="59e90-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="59e90-123">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="59e90-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="59e90-124">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="59e90-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="59e90-125">Välj **Anslut** om du vill initiera anslutningen till RollWorks.</span><span class="sxs-lookup"><span data-stu-id="59e90-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="59e90-126">Välj **Autentisera med RollWorks** och ange dina administratörsuppgifter för RollWorks.</span><span class="sxs-lookup"><span data-stu-id="59e90-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="59e90-127">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="59e90-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="59e90-128">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59e90-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="59e90-129">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="59e90-129">Configure an export</span></span>

<span data-ttu-id="59e90-130">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="59e90-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="59e90-131">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="59e90-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="59e90-132">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="59e90-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="59e90-133">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="59e90-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="59e90-134">I fältet **Anslutning för export**, välj en anslutning från avsnittet RollWorks.</span><span class="sxs-lookup"><span data-stu-id="59e90-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="59e90-135">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="59e90-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="59e90-136">Ange din **RollWorks annonsörs-ID** [RollWorks-annonserbar](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="59e90-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="59e90-137">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="59e90-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="59e90-138">Det krävs att exportera segment till RollWorks.</span><span class="sxs-lookup"><span data-stu-id="59e90-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="59e90-139">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="59e90-139">Select the segments you want to export.</span></span> <span data-ttu-id="59e90-140">Välj ett segment med minst 100 medlemmar.</span><span class="sxs-lookup"><span data-stu-id="59e90-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="59e90-141">Det går inte att exportera mindre segment.</span><span class="sxs-lookup"><span data-stu-id="59e90-141">You can't export smaller segments.</span></span> <span data-ttu-id="59e90-142">Dessutom är det maximala värdet för ett segment som ska exporteras 250 000 medlemmar per export.</span><span class="sxs-lookup"><span data-stu-id="59e90-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="59e90-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="59e90-143">Select **Save**.</span></span>

<span data-ttu-id="59e90-144">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="59e90-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="59e90-145">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="59e90-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="59e90-146">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="59e90-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="59e90-147">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="59e90-147">Data privacy and compliance</span></span>

<span data-ttu-id="59e90-148">När du aktiverar Dynamics 365 Customer Insights för att överföra data till RollWorks, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="59e90-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="59e90-149">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att RollWorks uppfyller alla eventuella sekretess- eller säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="59e90-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="59e90-150">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="59e90-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="59e90-151">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="59e90-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
