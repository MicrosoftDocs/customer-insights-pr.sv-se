---
title: Exportera Customer Insights-data till Omnisend
description: Lär dig hur du konfigurerar anslutningen och exporterar till Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124559"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="98694-103">Exportera segment till Omnisend (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="98694-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="98694-104">Exportera segment med enhetliga kundprofiler till Omnisend och använd dem för marknadsföringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="98694-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98694-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="98694-105">Prerequisites</span></span>

-   <span data-ttu-id="98694-106">Du har ett [Omnisend-konto](https://www.omnisend.com/) och motsvarande autentiseringsuppgifter för administratör.</span><span class="sxs-lookup"><span data-stu-id="98694-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="98694-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="98694-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="98694-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="98694-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="98694-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="98694-109">Known limitations</span></span>

- <span data-ttu-id="98694-110">Du kan exportera upp till 1 miljon profiler per export till Omnisend och det kan ta upp till 4 timmar att slutföra.</span><span class="sxs-lookup"><span data-stu-id="98694-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="98694-111">Export till Omnisend är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="98694-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="98694-112">Antalet profiler som du kan exportera till Omnisend beror på ditt kontrakt med Omnisend.</span><span class="sxs-lookup"><span data-stu-id="98694-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="98694-113">Konfigurera anslutningen till Omnisend</span><span class="sxs-lookup"><span data-stu-id="98694-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="98694-114">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="98694-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="98694-115">Välj **Lägg till anslutning** och välj **Omnisend** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="98694-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="98694-116">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="98694-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="98694-117">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="98694-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="98694-118">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="98694-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="98694-119">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="98694-119">Choose who can use this connection.</span></span> <span data-ttu-id="98694-120">Som standard är det bara administratörer.</span><span class="sxs-lookup"><span data-stu-id="98694-120">By default it's only administrators.</span></span> <span data-ttu-id="98694-121">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="98694-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="98694-122">Ange din [Omnisend API-nyckel](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="98694-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="98694-123">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="98694-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="98694-124">Välj **Anslut** om du vill initiera anslutningen till Omnisend.</span><span class="sxs-lookup"><span data-stu-id="98694-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="98694-125">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98694-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="98694-126">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="98694-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="98694-127">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="98694-127">Configure an export</span></span>

<span data-ttu-id="98694-128">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="98694-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="98694-129">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="98694-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="98694-130">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="98694-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="98694-131">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="98694-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="98694-132">I fältet **Anslutning för export**, välj en anslutning från avsnittet Omnisend.</span><span class="sxs-lookup"><span data-stu-id="98694-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="98694-133">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="98694-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="98694-134">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="98694-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="98694-135">Det krävs för att exportera segment till Omnisend.</span><span class="sxs-lookup"><span data-stu-id="98694-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="98694-136">Alternativt kan du exportera Förnamn, Efternamn, Adress, Land/Region, Delstat, Ort och Postnummer för att skapa mer anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="98694-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="98694-137">Välj **Lägg till attribut** för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="98694-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="98694-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98694-138">Select **Save**.</span></span>

<span data-ttu-id="98694-139">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="98694-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="98694-140">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="98694-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="98694-141">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="98694-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="98694-142">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="98694-142">Data privacy and compliance</span></span>

<span data-ttu-id="98694-143">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Omnisend tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="98694-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="98694-144">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Omnisend uppfyller alla eventuella sekretess- eller säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="98694-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="98694-145">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="98694-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="98694-146">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="98694-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
