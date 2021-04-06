---
title: Exportera Customer Insights-data till AdRoll
description: Lär dig hur du konfigurerar anslutningen till AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697096"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="33d0c-103">Anslutningsprogram för AdRoll (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="33d0c-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="33d0c-104">Exportera segment med enhetliga kundprofiler till AdRoll och använd dem för annonsering.</span><span class="sxs-lookup"><span data-stu-id="33d0c-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="33d0c-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="33d0c-105">Prerequisites</span></span>

-   <span data-ttu-id="33d0c-106">Du har ett [AdRoll-konto](https://www.adroll.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="33d0c-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="33d0c-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="33d0c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="33d0c-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="33d0c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="33d0c-109">Anslut till AdRoll</span><span class="sxs-lookup"><span data-stu-id="33d0c-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="33d0c-110">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="33d0c-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="33d0c-111">Under **AdRoll** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="33d0c-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="33d0c-112">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="33d0c-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurationsfönster för anslutning till AdRoll.":::

1. <span data-ttu-id="33d0c-114">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="33d0c-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="33d0c-115">Välj **Anslut** om du vill initiera anslutningen till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="33d0c-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="33d0c-116">Välj **Autentisera med AdRoll** och ange dina autentiseringsuppgifter som administratör för AdRoll.</span><span class="sxs-lookup"><span data-stu-id="33d0c-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="33d0c-117">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="33d0c-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="33d0c-118">Ange ditt **ID som AdRoll-annonsör** [AdRoll-annonsör](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="33d0c-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="33d0c-119">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="33d0c-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="33d0c-120">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="33d0c-120">Configure the connector</span></span>

1. <span data-ttu-id="33d0c-121">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="33d0c-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="33d0c-122">Det krävs för att exportera segment till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="33d0c-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="33d0c-123">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="33d0c-123">Select the segments you want to export.</span></span> <span data-ttu-id="33d0c-124">Välj ett segment med minst 100 medlemmar.</span><span class="sxs-lookup"><span data-stu-id="33d0c-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="33d0c-125">Det går inte att exportera mindre segment.</span><span class="sxs-lookup"><span data-stu-id="33d0c-125">You can't export smaller segments.</span></span> <span data-ttu-id="33d0c-126">Dessutom är det maximala värdet för ett segment som ska exporteras 250 000 medlemmar per export.</span><span class="sxs-lookup"><span data-stu-id="33d0c-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="33d0c-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="33d0c-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="33d0c-128">Exportera data</span><span class="sxs-lookup"><span data-stu-id="33d0c-128">Export the data</span></span>

<span data-ttu-id="33d0c-129">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="33d0c-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="33d0c-130">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="33d0c-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="33d0c-131">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="33d0c-131">Known limitations</span></span>

- <span data-ttu-id="33d0c-132">Du kan exportera upp till totalt 250 000 profiler per export till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="33d0c-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="33d0c-133">Du kan inte exportera segment med färre än 100 profiler till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="33d0c-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="33d0c-134">Export till AdRoll är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="33d0c-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="33d0c-135">Det kan ta upp till 10 minuter att exportera upp till 250 000 profiler till AdRoll.</span><span class="sxs-lookup"><span data-stu-id="33d0c-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="33d0c-136">Antalet profiler som du kan exportera till AdRoll är beroende av och begränsat enligt ditt kontrakt med AdRoll.</span><span class="sxs-lookup"><span data-stu-id="33d0c-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="33d0c-137">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="33d0c-137">Data privacy and compliance</span></span>

<span data-ttu-id="33d0c-138">När du aktiverar Dynamics 365 Customer Insights för att överföra data till AdRoll tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="33d0c-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="33d0c-139">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att AdRoll uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="33d0c-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="33d0c-140">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="33d0c-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="33d0c-141">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="33d0c-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
