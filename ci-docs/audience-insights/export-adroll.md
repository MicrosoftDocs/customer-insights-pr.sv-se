---
title: Exportera Customer Insights-data till AdRoll
description: Lär dig hur du konfigurerar anslutningen och exporterar till AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304856"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="c545f-103">Exportera segment till AdRoll (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="c545f-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="c545f-104">Exportera segment med enhetliga kundprofiler till AdRoll och använd dem för annonsering.</span><span class="sxs-lookup"><span data-stu-id="c545f-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c545f-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="c545f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="c545f-106">Du har ett [AdRoll-konto](https://www.adroll.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c545f-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c545f-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="c545f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c545f-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="c545f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c545f-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="c545f-109">Known limitations</span></span>

- <span data-ttu-id="c545f-110">Du kan exportera upp till 250 000 profiler till AdRoll åt gången.</span><span class="sxs-lookup"><span data-stu-id="c545f-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="c545f-111">Du kan inte exportera segment med färre än 100 profiler till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c545f-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="c545f-112">Export till AdRoll är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="c545f-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="c545f-113">Det kan ta upp till 10 minuter att exportera upp till 250 000 profiler till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c545f-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="c545f-114">Antalet profiler du kan exportera till AdRoll beror på ditt kontrakt med AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c545f-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="c545f-115">Upprätta anslutningen till AdRoll</span><span class="sxs-lookup"><span data-stu-id="c545f-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="c545f-116">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="c545f-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c545f-117">Välj **Lägg till anslutning** och välj **AdRoll** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c545f-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="c545f-118">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="c545f-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c545f-119">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="c545f-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c545f-120">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c545f-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c545f-121">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c545f-121">Choose who can use this connection.</span></span> <span data-ttu-id="c545f-122">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="c545f-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c545f-123">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c545f-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c545f-124">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="c545f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c545f-125">Välj **Anslut** om du vill initiera anslutningen till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c545f-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="c545f-126">Välj **Autentisera med AdRoll** och ange dina autentiseringsuppgifter som administratör för AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c545f-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="c545f-127">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c545f-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c545f-128">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c545f-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c545f-129">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="c545f-129">Configure an export</span></span>

<span data-ttu-id="c545f-130">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="c545f-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c545f-131">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c545f-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c545f-132">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="c545f-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c545f-133">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="c545f-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c545f-134">I fältet **Anslutning för export**, välj en anslutning från avsnittet AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c545f-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="c545f-135">Om avsnittets namn inte visas är inga anslutningar av den här typen tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="c545f-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="c545f-136">Ange ditt **Annonsörs-ID för AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="c545f-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="c545f-137">Mer information finns i [Annonsörsprofiler för AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="c545f-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="c545f-138">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="c545f-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c545f-139">Det krävs för att exportera segment till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c545f-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="c545f-140">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="c545f-140">Select the segments you want to export.</span></span> <span data-ttu-id="c545f-141">Välj ett segment med minst 100 medlemmar.</span><span class="sxs-lookup"><span data-stu-id="c545f-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="c545f-142">Det går inte att exportera mindre segment.</span><span class="sxs-lookup"><span data-stu-id="c545f-142">You can't export smaller segments.</span></span> <span data-ttu-id="c545f-143">Dessutom är det maximala värdet som ett segment kan exportera 250 000 medlemmar per export.</span><span class="sxs-lookup"><span data-stu-id="c545f-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="c545f-144">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c545f-144">Select **Save**.</span></span>

<span data-ttu-id="c545f-145">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="c545f-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c545f-146">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c545f-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="c545f-147">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c545f-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c545f-148">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="c545f-148">Data privacy and compliance</span></span>

<span data-ttu-id="c545f-149">När du aktiverar Dynamics 365 Customer Insights för att överföra data till AdRoll tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c545f-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c545f-150">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att AdRoll uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="c545f-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c545f-151">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c545f-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c545f-152">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="c545f-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
