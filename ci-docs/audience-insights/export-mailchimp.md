---
title: Exportera Customer Insights-data till Mailchimp
description: Lär dig hur du konfigurerar anslutningen till Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598223"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="fa6c0-103">Anslutningsprogram för Mailchimp (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="fa6c0-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="fa6c0-104">Exportera segment av enhetliga kundprofiler till Mailchimp för att skapa nyhetsbrev och e-postkampanjer.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa6c0-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="fa6c0-105">Prerequisites</span></span>

-   <span data-ttu-id="fa6c0-106">Du har ett [Mailchimp-konto](https://mailchimp.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fa6c0-107">Det finns befintliga målgrupper i Mailchimp och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="fa6c0-108">Mer information finns i [Målgrupper för Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="fa6c0-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="fa6c0-109">Du har [konfigurerat segment](segments.md)</span><span class="sxs-lookup"><span data-stu-id="fa6c0-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="fa6c0-110">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="fa6c0-111">Anslut till Mailchimp</span><span class="sxs-lookup"><span data-stu-id="fa6c0-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="fa6c0-112">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fa6c0-113">Under **Mailchimp** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="fa6c0-114">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fa6c0-115">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fa6c0-116">Ange ditt **[målgrupps-ID för Mailchimp](https://mailchimp.com/help/find-audience-id/)** och välj **Anslut** för att initiera anslutningen till Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="fa6c0-117">Välj **Autentisera med Mailchimp** och ange dina Mailchimp-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="fa6c0-118">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportera skärmbild för Mailchimp-anslutning":::

1. <span data-ttu-id="fa6c0-120">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="fa6c0-121">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="fa6c0-121">Configure the connector</span></span>

1. <span data-ttu-id="fa6c0-122">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="fa6c0-123">Alternativt kan du exportera **Förnamn** och **Efternamn** som ytterligare fält för att skapa mer personligt anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="fa6c0-124">Välj **Lägg till attribut** för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="fa6c0-125">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-125">Select the segments you want to export.</span></span> <span data-ttu-id="fa6c0-126">Du kan exportera upp till totalt 1 000 000 kundprofiler till Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Välj fält och segment som ska exporteras till Mailchimp":::

1. <span data-ttu-id="fa6c0-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fa6c0-129">Exportera data</span><span class="sxs-lookup"><span data-stu-id="fa6c0-129">Export the data</span></span>

<span data-ttu-id="fa6c0-130">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fa6c0-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fa6c0-131">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fa6c0-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fa6c0-132">I Mailchimp kan du nu hitta dina segment under [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="fa6c0-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fa6c0-133">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="fa6c0-133">Known limitations</span></span>

- <span data-ttu-id="fa6c0-134">Upp till 1 000 000 profiler per export till Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="fa6c0-135">Export till Mailchimp är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="fa6c0-136">Export av segment med totalt 1 000 000 profiler kan ta upp till 3 timmar på grund av begränsningar på leverantörens sida.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="fa6c0-137">Antalet profiler som du kan exportera till Mailchimp är beroende av och begränsat enligt ditt kontrakt med Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fa6c0-138">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="fa6c0-138">Data privacy and compliance</span></span>

<span data-ttu-id="fa6c0-139">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Mailchimp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fa6c0-140">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Mailchimp uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fa6c0-141">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fa6c0-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fa6c0-142">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="fa6c0-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]