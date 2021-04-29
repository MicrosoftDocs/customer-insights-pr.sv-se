---
title: Exportera Customer Insights-data till Autopilot
description: Lär dig hur du konfigurerar anslutningen och exporterar till Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760165"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="5cd38-103">Exportera segment till Autopilot (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="5cd38-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="5cd38-104">Exportera segment med enhetliga kundprofiler till Autopilot och använd dem för e-postmarknadsföring i Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5cd38-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="5cd38-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="5cd38-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="5cd38-106">Du har ett [Autopilot-konto](https://www.autopilothq.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="5cd38-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5cd38-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="5cd38-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5cd38-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5cd38-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5cd38-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="5cd38-109">Known limitations</span></span>

- <span data-ttu-id="5cd38-110">Du kan exportera upp till totalt 100 000 profiler till Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5cd38-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="5cd38-111">Export till Autopilot är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="5cd38-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="5cd38-112">Att exportera upp till 100 000 profiler till Autopilot kan ta upp till några timmar att genomföra.</span><span class="sxs-lookup"><span data-stu-id="5cd38-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="5cd38-113">Antalet profiler som du kan exportera till Autopilot är beroende av och begränsat enligt ditt kontrakt med Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5cd38-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="5cd38-114">Upprätta anslutningen till Autopilot</span><span class="sxs-lookup"><span data-stu-id="5cd38-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="5cd38-115">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="5cd38-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5cd38-116">Välj **Lägg till anslutning** och välj **Autopilot** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5cd38-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="5cd38-117">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="5cd38-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5cd38-118">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="5cd38-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5cd38-119">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5cd38-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5cd38-120">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5cd38-120">Choose who can use this connection.</span></span> <span data-ttu-id="5cd38-121">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="5cd38-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5cd38-122">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5cd38-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="5cd38-123">Ange din [Autopilot API-nyckel](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="5cd38-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="5cd38-124">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="5cd38-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5cd38-125">Välj **Anslut** om du vill initiera anslutningen till Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5cd38-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="5cd38-126">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5cd38-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5cd38-127">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5cd38-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5cd38-128">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="5cd38-128">Configure an export</span></span>

<span data-ttu-id="5cd38-129">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="5cd38-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5cd38-130">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5cd38-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5cd38-131">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="5cd38-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5cd38-132">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="5cd38-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5cd38-133">I fältet **Anslutning för export**, välj en anslutning från avsnittet Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5cd38-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="5cd38-134">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="5cd38-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="5cd38-135">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5cd38-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5cd38-136">Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**.</span><span class="sxs-lookup"><span data-stu-id="5cd38-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="5cd38-137">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="5cd38-137">Select the segments you want to export.</span></span> <span data-ttu-id="5cd38-138">Vi rekommenderar **starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5cd38-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="5cd38-139">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5cd38-139">Select **Save**.</span></span>

<span data-ttu-id="5cd38-140">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="5cd38-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5cd38-141">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5cd38-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5cd38-142">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5cd38-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5cd38-143">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="5cd38-143">Data privacy and compliance</span></span>

<span data-ttu-id="5cd38-144">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Autopilot tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="5cd38-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5cd38-145">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Autopilot uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="5cd38-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5cd38-146">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5cd38-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5cd38-147">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="5cd38-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
