---
title: Exportera Customer Insights-data till Snapchat
description: Lär dig hur du konfigurerar anslutningen och exporterar till Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124065"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="ce9be-103">Exportera segment till Snapchat (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="ce9be-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="ce9be-104">Exportera segment med enhetliga kundprofiler till Snapchat och använd dem för annonser.</span><span class="sxs-lookup"><span data-stu-id="ce9be-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ce9be-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="ce9be-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ce9be-106">Du har ett [Snapchat företagskonto](https://business.snapchat.com/), en [Snapchat-annonskonto](https://ads.snapchat.com/) och motsvarande administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ce9be-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ce9be-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="ce9be-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ce9be-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ce9be-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ce9be-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="ce9be-109">Known limitations</span></span>

- <span data-ttu-id="ce9be-110">Export till Snapchat är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="ce9be-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="ce9be-111">Det kan ta upp till 15 minuter att exportera upp till 1 miljon profiler till Snapchat.</span><span class="sxs-lookup"><span data-stu-id="ce9be-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="ce9be-112">Konfigurera anslutningen Snapchat</span><span class="sxs-lookup"><span data-stu-id="ce9be-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="ce9be-113">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="ce9be-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ce9be-114">Välj **Lägg till anslutning** och välj **Snapchat** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ce9be-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="ce9be-115">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="ce9be-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ce9be-116">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="ce9be-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ce9be-117">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ce9be-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ce9be-118">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ce9be-118">Choose who can use this connection.</span></span> <span data-ttu-id="ce9be-119">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="ce9be-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ce9be-120">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ce9be-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ce9be-121">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="ce9be-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ce9be-122">Välj **Anslut** om du vill initiera anslutningen till Snapchat.</span><span class="sxs-lookup"><span data-stu-id="ce9be-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="ce9be-123">Välj **Autentisera med Snapchat** och ange dina administratörsuppgifter för Snapchat.</span><span class="sxs-lookup"><span data-stu-id="ce9be-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="ce9be-124">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ce9be-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ce9be-125">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ce9be-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ce9be-126">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="ce9be-126">Configure an export</span></span>

<span data-ttu-id="ce9be-127">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="ce9be-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ce9be-128">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ce9be-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ce9be-129">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="ce9be-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce9be-130">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="ce9be-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ce9be-131">I fältet **Anslutning för export**, välj en anslutning från avsnittet Snapchat.</span><span class="sxs-lookup"><span data-stu-id="ce9be-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="ce9be-132">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="ce9be-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ce9be-133">Ange [**Snapchat målgrupps-ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="ce9be-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="ce9be-134">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ce9be-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ce9be-135">Det krävs att exportera segment till Snapchat.</span><span class="sxs-lookup"><span data-stu-id="ce9be-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="ce9be-136">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="ce9be-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="ce9be-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ce9be-137">Select **Save**.</span></span>

<span data-ttu-id="ce9be-138">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="ce9be-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ce9be-139">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ce9be-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ce9be-140">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ce9be-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ce9be-141">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="ce9be-141">Data privacy and compliance</span></span>

<span data-ttu-id="ce9be-142">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Snapchat, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ce9be-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ce9be-143">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Snapchat uppfyller alla eventuella sekretess- eller säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="ce9be-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ce9be-144">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ce9be-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ce9be-145">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="ce9be-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
