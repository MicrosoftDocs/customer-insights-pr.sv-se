---
title: Exportera Customer Insights-data till Microsoft Advertising
description: Lär dig hur du konfigurerar anslutningen och exporterar till Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124558"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="099d1-103">Exportera segment till Microsoft Advertising (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="099d1-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="099d1-104">Exportera Customer Insights-segment till Microsoft Advertising för att skapa Customer Match-målgrupper.</span><span class="sxs-lookup"><span data-stu-id="099d1-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="099d1-105">Använd dessa målgrupper för dina annonskampanjer.</span><span class="sxs-lookup"><span data-stu-id="099d1-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="099d1-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="099d1-106">Prerequisites</span></span>

-   <span data-ttu-id="099d1-107">Ett [Microsoft Advertising-konto](https://ads.microsoft.com/) och motsvarande autentiseringsuppgifter för administratör.</span><span class="sxs-lookup"><span data-stu-id="099d1-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="099d1-108">Du har accepterat användarvillkoren för Customer Match.</span><span class="sxs-lookup"><span data-stu-id="099d1-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="099d1-109">[Konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="099d1-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="099d1-110">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält med en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="099d1-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="099d1-111">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="099d1-111">Known limitations</span></span>

- <span data-ttu-id="099d1-112">Du kan exportera upp till 500 000 profiler per export till Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="099d1-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="099d1-113">Export till Microsoft Advertising är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="099d1-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="099d1-114">Det kan ta upp till 10 minuter att exportera upp till 500 000 profiler till Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="099d1-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="099d1-115">Upprätta anslutningen till Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="099d1-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="099d1-116">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="099d1-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="099d1-117">Välj **Lägg till anslutning** och välj **Microsoft Advertising** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="099d1-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="099d1-118">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="099d1-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="099d1-119">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="099d1-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="099d1-120">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="099d1-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="099d1-121">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="099d1-121">Choose who can use this connection.</span></span> <span data-ttu-id="099d1-122">Standardinställningen är administratörer.</span><span class="sxs-lookup"><span data-stu-id="099d1-122">The default is administrators.</span></span> <span data-ttu-id="099d1-123">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="099d1-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="099d1-124">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="099d1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="099d1-125">Välj **Anslut** om du vill initiera anslutningen till Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="099d1-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="099d1-126">Välj **Autentisera med Microsoft Advertising** och ange dina administratörsuppgifter för Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="099d1-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="099d1-127">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="099d1-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="099d1-128">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="099d1-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="099d1-129">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="099d1-129">Configure an export</span></span>

<span data-ttu-id="099d1-130">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="099d1-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="099d1-131">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="099d1-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="099d1-132">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="099d1-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="099d1-133">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="099d1-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="099d1-134">I fältet **Anslutning för export**, välj en anslutning från avsnittet Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="099d1-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="099d1-135">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="099d1-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="099d1-136">Välj de segment som ska exporteras.</span><span class="sxs-lookup"><span data-stu-id="099d1-136">Select the segments to export.</span></span> <span data-ttu-id="099d1-137">Customer Match-målgrupperna i Microsoft Advertising skapas automatiskt med namnet på de segment som valts för export.</span><span class="sxs-lookup"><span data-stu-id="099d1-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="099d1-138">Varje segment resulterar i en separat Customer Match-målgrupp.</span><span class="sxs-lookup"><span data-stu-id="099d1-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="099d1-139">Ange ditt **kund-ID och konto-ID för Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="099d1-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="099d1-140">Du hittar kund-ID (`cid`) och konto-ID (`aid`) i parametrarna för webbadressen när du är inloggad på Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="099d1-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="099d1-141">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du fältet i din enhetliga kundprofil som innehåller kundens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="099d1-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="099d1-142">Det krävs för att exportera segment till Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="099d1-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="099d1-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="099d1-143">Select **Save**.</span></span>

<span data-ttu-id="099d1-144">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="099d1-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="099d1-145">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="099d1-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="099d1-146">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="099d1-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="099d1-147">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="099d1-147">Data privacy and compliance</span></span>

<span data-ttu-id="099d1-148">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Microsoft Advertising tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="099d1-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="099d1-149">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Microsoft Advertising uppfyller alla eventuella sekretess- eller säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="099d1-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="099d1-150">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="099d1-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="099d1-151">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort det här exportmålet för att stoppa användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="099d1-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
