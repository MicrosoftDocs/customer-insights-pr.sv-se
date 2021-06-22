---
title: Exportera Customer Insights-data till Campaign Monitor
description: Lär dig hur du konfigurerar anslutningen och exporterar till Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124203"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="5414e-103">Exportera segment till Campaign Monitor (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="5414e-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="5414e-104">Exportera segment med enhetliga kundprofiler till Campaign Monitor och använd dem för marknadsföringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="5414e-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5414e-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="5414e-105">Prerequisites</span></span>

-   <span data-ttu-id="5414e-106">Du har ett [Campaign Monitor-konto](https://www.campaignmonitor.com/) och motsvarande autentiseringsuppgifter för administratör.</span><span class="sxs-lookup"><span data-stu-id="5414e-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5414e-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="5414e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5414e-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5414e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5414e-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="5414e-109">Known limitations</span></span>

- <span data-ttu-id="5414e-110">Du kan exportera upp till en miljoner profiler per export till Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="5414e-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="5414e-111">Export till Campaign Monitor är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="5414e-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="5414e-112">Det kan ta upp till 20 minuter att exportera upp till 1 miljon profiler till Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="5414e-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="5414e-113">Hur många profiler du kan exportera till Campaign Monitor beror på och begränsas av ditt kontrakt med Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="5414e-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="5414e-114">Konfigurera anslutning till Campaign Monitor </span><span class="sxs-lookup"><span data-stu-id="5414e-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="5414e-115">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="5414e-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5414e-116">Välj **Lägg till anslutning** och välj **Campaign Monitor** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5414e-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="5414e-117">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="5414e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5414e-118">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="5414e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5414e-119">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5414e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5414e-120">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5414e-120">Choose who can use this connection.</span></span> <span data-ttu-id="5414e-121">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="5414e-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5414e-122">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5414e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5414e-123">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="5414e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5414e-124">Välj **Anslut** om du vill initiera anslutningen till Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="5414e-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="5414e-125">Välj **Autentisera med Campaign Monitor** och ange dina administratörsuppgifter för Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="5414e-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="5414e-126">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5414e-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5414e-127">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5414e-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5414e-128">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="5414e-128">Configure an export</span></span>

<span data-ttu-id="5414e-129">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="5414e-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5414e-130">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5414e-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5414e-131">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="5414e-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5414e-132">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="5414e-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5414e-133">I fältet **Anslutning för export**, välj en anslutning från avsnittet Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="5414e-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="5414e-134">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="5414e-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5414e-135">Ange [**Campaign Monitor list-ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="5414e-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="5414e-136">[Generera API-nyckeln](https://www.campaignmonitor.com/api/getting-started/) från **Kontoinställningar** i Campaign Monitor  först för att visa API-list-ID:t.</span><span class="sxs-lookup"><span data-stu-id="5414e-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="5414e-137">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5414e-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5414e-138">Det krävs att exportera segment till Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="5414e-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="5414e-139">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5414e-139">Select **Save**.</span></span>

<span data-ttu-id="5414e-140">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="5414e-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5414e-141">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5414e-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5414e-142">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5414e-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5414e-143">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="5414e-143">Data privacy and compliance</span></span>

<span data-ttu-id="5414e-144">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Campaign Monitor, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="5414e-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5414e-145">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Campaign Monitor uppfyller alla eventuella sekretess- eller säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="5414e-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5414e-146">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5414e-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5414e-147">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="5414e-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
