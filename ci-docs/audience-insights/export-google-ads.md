---
title: Exportera Customer Insights-data till Google Ads
description: Lär dig hur du konfigurerar anslutningen till Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268984"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="d8f61-103">Anslutningsprogram för Google Ads (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="d8f61-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="d8f61-104">Exportera segment av enhetliga kundprofiler till Google Ads målgruppslista och använd dem för att annonsera i Google Sök, Gmail, YouTube och Googles Display-nätverk.</span><span class="sxs-lookup"><span data-stu-id="d8f61-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d8f61-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d8f61-105">Prerequisites</span></span>

-   <span data-ttu-id="d8f61-106">Du har ett [Google Ads-konto](https://ads.google.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d8f61-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d8f61-107">Det finns befintliga målgrupper i Google Ads och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="d8f61-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="d8f61-108">Mer information finns i [Målgrupper för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="d8f61-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="d8f61-109">Du har [konfigurerat segment](segments.md)</span><span class="sxs-lookup"><span data-stu-id="d8f61-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="d8f61-110">Enhetliga kundprofiler i de exporterade segmenten innehåller fält som representerar en e-postadress, ett förnamn och ett efternamn</span><span class="sxs-lookup"><span data-stu-id="d8f61-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="d8f61-111">Anslut till Google Ads</span><span class="sxs-lookup"><span data-stu-id="d8f61-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="d8f61-112">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d8f61-113">Under **Google Ads** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="d8f61-114">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d8f61-115">Ange ditt **[kund-ID för Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="d8f61-116">Ange ditt **[Google Ads-godkända utvecklartoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="d8f61-117">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d8f61-118">Ange ditt **[målgrupps-ID för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** och välj **Anslut** för att initiera anslutningen till Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d8f61-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="d8f61-119">Välj **Autentisera med Google Ads** och ange dina Google Ads-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d8f61-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="d8f61-120">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d8f61-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportera skärmbild för Google Ads-anslutning":::

1. <span data-ttu-id="d8f61-122">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="d8f61-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d8f61-123">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="d8f61-123">Configure the connector</span></span>

1. <span data-ttu-id="d8f61-124">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d8f61-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d8f61-125">Upprepa samma steg för fälten **Förnamn** och **Efternamn**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="d8f61-126">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="d8f61-126">Select the segments you want to export.</span></span> <span data-ttu-id="d8f61-127">Du kan exportera upp till totalt 1 000 000 kundprofiler till Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d8f61-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="d8f61-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d8f61-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d8f61-129">Exportera data</span><span class="sxs-lookup"><span data-stu-id="d8f61-129">Export the data</span></span>

<span data-ttu-id="d8f61-130">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d8f61-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d8f61-131">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d8f61-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d8f61-132">I Google Ads kan du nu hitta dina segment under [Google Ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="d8f61-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d8f61-133">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="d8f61-133">Known limitations</span></span>

- <span data-ttu-id="d8f61-134">Upp till 1 000 000 profiler per export till Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d8f61-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="d8f61-135">Export till Google Ads är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="d8f61-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="d8f61-136">Export av segment med totalt 1 000 000 profiler kan ta upp till 5 minuter på grund av begränsningar på leverantörens sida.</span><span class="sxs-lookup"><span data-stu-id="d8f61-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="d8f61-137">Matchningen i Google Ads kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="d8f61-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d8f61-138">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="d8f61-138">Data privacy and compliance</span></span>

<span data-ttu-id="d8f61-139">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Google Ads tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d8f61-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d8f61-140">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Google Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="d8f61-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d8f61-141">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d8f61-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d8f61-142">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="d8f61-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]