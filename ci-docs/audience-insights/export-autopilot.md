---
title: Exportera Customer Insights-data till Autopilot
description: Lär dig hur du konfigurerar anslutningen till Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269260"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="3531d-103">Anslutningsprogram för Autopilot (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="3531d-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="3531d-104">Exportera segment med enhetliga kundprofiler till Autopilot och använd dem för e-postmarknadsföring i Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3531d-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3531d-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="3531d-105">Prerequisites</span></span>

-   <span data-ttu-id="3531d-106">Du har ett [Autopilot-konto](https://www.autopilothq.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3531d-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3531d-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="3531d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3531d-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="3531d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="3531d-109">Anslut till Autopilot</span><span class="sxs-lookup"><span data-stu-id="3531d-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="3531d-110">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="3531d-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3531d-111">Under **Autopilot** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="3531d-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="3531d-112">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="3531d-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurationsfönster för Anslutning till Autopilot.":::

1. <span data-ttu-id="3531d-114">Ange **API-nyckeln till Autopilot** [API-nyckel till Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="3531d-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="3531d-115">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="3531d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3531d-116">Välj **Anslut** om du vill initiera anslutningen till Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3531d-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="3531d-117">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3531d-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3531d-118">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="3531d-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3531d-119">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="3531d-119">Configure the connector</span></span>

1. <span data-ttu-id="3531d-120">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="3531d-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3531d-121">Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**.</span><span class="sxs-lookup"><span data-stu-id="3531d-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="3531d-122">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="3531d-122">Select the segments you want to export.</span></span> <span data-ttu-id="3531d-123">Vi rekommenderar **starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3531d-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="3531d-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3531d-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3531d-125">Exportera data</span><span class="sxs-lookup"><span data-stu-id="3531d-125">Export the data</span></span>

<span data-ttu-id="3531d-126">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3531d-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3531d-127">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3531d-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3531d-128">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="3531d-128">Known limitations</span></span>

- <span data-ttu-id="3531d-129">Du kan exportera upp till totalt 100 000 profiler till Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3531d-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="3531d-130">Export till Autopilot är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="3531d-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="3531d-131">Att exportera upp till 100 000 profiler till Autopilot kan ta upp till några timmar att genomföra.</span><span class="sxs-lookup"><span data-stu-id="3531d-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="3531d-132">Antalet profiler som du kan exportera till Autopilot är beroende av och begränsat enligt ditt kontrakt med Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3531d-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3531d-133">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="3531d-133">Data privacy and compliance</span></span>

<span data-ttu-id="3531d-134">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Autopilot tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3531d-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3531d-135">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Autopilot uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="3531d-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3531d-136">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3531d-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3531d-137">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="3531d-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]