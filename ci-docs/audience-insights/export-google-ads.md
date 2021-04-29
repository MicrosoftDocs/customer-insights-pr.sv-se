---
title: Exportera Customer Insights-data till Google Ads
description: Lär dig hur du konfigurerar anslutningen och exporterar till Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759797"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="a8575-103">Exportera segment till Google Ads (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="a8575-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="a8575-104">Exportera segment av enhetliga kundprofiler till Google Ads målgruppslista och använd dem för att annonsera i Google Sök, Gmail, YouTube och Googles Display-nätverk.</span><span class="sxs-lookup"><span data-stu-id="a8575-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a8575-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="a8575-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a8575-106">Du har ett [Google Ads-konto](https://ads.google.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a8575-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a8575-107">Du har en [godkänd token för Google Ads-utvecklare](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="a8575-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="a8575-108">Du uppfyller kraven i [policyn för kundmatchning](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="a8575-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="a8575-109">Du uppfyller kraven i [storlekarna för återmarknadsföringslista](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="a8575-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="a8575-110">Det finns befintliga målgrupper i Google Ads och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="a8575-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="a8575-111">Mer information finns i [Målgrupper för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="a8575-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="a8575-112">Du har [konfigurerat segment](segments.md)</span><span class="sxs-lookup"><span data-stu-id="a8575-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="a8575-113">Enhetliga kundprofiler i de exporterade segmenten innehåller fält som representerar en e-postadress, ett förnamn och ett efternamn</span><span class="sxs-lookup"><span data-stu-id="a8575-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a8575-114">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="a8575-114">Known limitations</span></span>

- <span data-ttu-id="a8575-115">Upp till 1 000 000 profiler per export till Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a8575-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="a8575-116">Export till Google Ads är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="a8575-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="a8575-117">Export av segment med totalt 1 000 000 profiler kan ta upp till 5 minuter på grund av begränsningar på leverantörens sida.</span><span class="sxs-lookup"><span data-stu-id="a8575-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a8575-118">Matchningen i Google Ads kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="a8575-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="a8575-119">Konfigurera anslutningen Google Ads</span><span class="sxs-lookup"><span data-stu-id="a8575-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="a8575-120">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="a8575-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a8575-121">Välj **Lägg till anslutning** och välj **Google Ads** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a8575-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="a8575-122">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="a8575-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a8575-123">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="a8575-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a8575-124">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a8575-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a8575-125">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a8575-125">Choose who can use this connection.</span></span> <span data-ttu-id="a8575-126">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="a8575-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a8575-127">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a8575-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a8575-128">Ange ditt **[kund-ID för Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="a8575-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="a8575-129">Ange ditt **[Google Ads-godkända utvecklartoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="a8575-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="a8575-130">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="a8575-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a8575-131">Välj **Autentisera med Google Ads** och ange dina Google Ads-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a8575-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="a8575-132">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a8575-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a8575-133">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a8575-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a8575-134">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="a8575-134">Configure an export</span></span>

<span data-ttu-id="a8575-135">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="a8575-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a8575-136">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a8575-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a8575-137">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a8575-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8575-138">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="a8575-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a8575-139">I fältet **Anslutning för export**, välj en anslutning från avsnittet Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a8575-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="a8575-140">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="a8575-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a8575-141">Ange ditt **[målgrupps-ID för Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** och välj **Anslut** för att initiera anslutningen till Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a8575-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="a8575-142">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="a8575-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a8575-143">Upprepa samma steg för fälten **Förnamn** och **Efternamn**.</span><span class="sxs-lookup"><span data-stu-id="a8575-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="a8575-144">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="a8575-144">Select the segments you want to export.</span></span> <span data-ttu-id="a8575-145">Du kan exportera upp till totalt 1 000 000 kundprofiler till Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a8575-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="a8575-146">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="a8575-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a8575-147">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a8575-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a8575-148">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a8575-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a8575-149">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="a8575-149">Data privacy and compliance</span></span>

<span data-ttu-id="a8575-150">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Google Ads tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a8575-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a8575-151">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Google Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="a8575-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a8575-152">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a8575-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a8575-153">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a8575-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
