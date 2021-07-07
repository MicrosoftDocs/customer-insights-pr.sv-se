---
title: Exportera Customer Insights-data till ActiveCampaign
description: Lär dig hur du konfigurerar anslutningen och exporterar till ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314683"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="59875-103">Exportera segment till ActiveCampaign (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="59875-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="59875-104">Exportera segment med enhetliga kundprofiler till ActiveCampaign och använd dem för marknadsföringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="59875-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59875-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="59875-105">Prerequisites</span></span>

-   <span data-ttu-id="59875-106">Du har ett [ActiveCampaign-konto](https://www.activecampaign.com/) och motsvarande autentiseringsuppgifter för administratör.</span><span class="sxs-lookup"><span data-stu-id="59875-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="59875-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="59875-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="59875-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält med en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="59875-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="59875-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="59875-109">Known limitations</span></span>

- <span data-ttu-id="59875-110">Du kan exportera upp till 1 miljoner profiler per export till ActiveCampaign, en export som kan ta upp till 90 minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="59875-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="59875-111">Exporten till ActiveCampaign är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="59875-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="59875-112">Antalet profiler du kan exportera till ActiveCampaign beror på ditt kontrakt med ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="59875-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="59875-113">Upprätta anslutning till ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="59875-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="59875-114">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="59875-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="59875-115">Välj **Lägg till anslutning** och völj **ActiveCampaign** om du vill konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59875-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="59875-116">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="59875-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="59875-117">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="59875-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="59875-118">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59875-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="59875-119">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59875-119">Choose who can use this connection.</span></span> <span data-ttu-id="59875-120">Som standard är det bara administratörer.</span><span class="sxs-lookup"><span data-stu-id="59875-120">By default, it's only administrators.</span></span> <span data-ttu-id="59875-121">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="59875-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="59875-122">Ange din [API-nyckel för ActiveCampaign och ditt värdnamn för REST-slutpunkt](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="59875-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="59875-123">Endast slutpunktsvärdnamn för REST utan https://.</span><span class="sxs-lookup"><span data-stu-id="59875-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="59875-124">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="59875-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="59875-125">Välj **Anslut** för att initiera anslutningen till ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="59875-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="59875-126">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="59875-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="59875-127">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="59875-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="59875-128">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="59875-128">Configure an export</span></span>

<span data-ttu-id="59875-129">Du kan konfigurera en export om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="59875-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="59875-130">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="59875-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="59875-131">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="59875-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="59875-132">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="59875-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="59875-133">I fältet **Anslutning för export** väljer du en anslutning från avsnittet ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="59875-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="59875-134">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="59875-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="59875-135">Ange ditt [**List-ID för ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="59875-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="59875-136">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="59875-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="59875-137">Detta krävs för att kunna exporter segment till ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="59875-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="59875-138">Alternativt kan du exportera förnamn, efternamn och telefonnummer om du vill skapa mer anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="59875-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="59875-139">Välj Lägg till attribut för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="59875-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="59875-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="59875-140">Select **Save**.</span></span>

<span data-ttu-id="59875-141">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="59875-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="59875-142">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="59875-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="59875-143">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="59875-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="59875-144">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="59875-144">Data privacy and compliance</span></span>

<span data-ttu-id="59875-145">När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till ActiveCampaign tillåter du överföringen av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="59875-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="59875-146">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att ActiveCampaign uppfyller eventuella sekretess- och säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="59875-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="59875-147">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="59875-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="59875-148">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="59875-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
