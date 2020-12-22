---
title: Exportera Customer Insights-data till Marketo
description: Lär dig hur du konfigurerar anslutningen till Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570425"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="33da9-103">Anslutningsprogram för Marketo (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="33da9-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="33da9-104">Exportera segment av enhetliga kundprofiler för att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Marketo.</span><span class="sxs-lookup"><span data-stu-id="33da9-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33da9-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="33da9-105">Prerequisites</span></span>

-   <span data-ttu-id="33da9-106">Du har ett [Marketo-konto](https://login.marketo.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="33da9-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="33da9-107">Det finns befintliga listor i Marketo och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="33da9-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="33da9-108">Mer information finns på [Marketo-listor](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="33da9-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="33da9-109">Du har [konfigurerat segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="33da9-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="33da9-110">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="33da9-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="33da9-111">Ansluta till Marketo</span><span class="sxs-lookup"><span data-stu-id="33da9-111">Connect to Marketo</span></span>

1. <span data-ttu-id="33da9-112">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="33da9-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="33da9-113">Under **Marketo** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="33da9-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="33da9-114">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="33da9-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="33da9-115">Ange ditt **[klient-ID för Marketo, din klienthemlighet och slutpunktsvärdnamnet för REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="33da9-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="33da9-116">Ange ditt **[ID för Marketo-lista](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="33da9-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="33da9-117">Välj **Jag godkänner** för att bekräfta **datasekretess och regelefterlevnad** och välj **Anslut** för att initiera anslutningen till Marketo.</span><span class="sxs-lookup"><span data-stu-id="33da9-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="33da9-118">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="33da9-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportera skärmbild för Marketo-anslutning":::

1. <span data-ttu-id="33da9-120">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="33da9-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="33da9-121">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="33da9-121">Configure the connector</span></span>

1. <span data-ttu-id="33da9-122">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="33da9-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="33da9-123">Alternativt kan du exportera **Förnamn**, **Efternamn**, **Ort**, **Delstat** och **Land/region** som ytterligare fält för att skapa mer personligt anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="33da9-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="33da9-124">Välj **Lägg till attribut** för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="33da9-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="33da9-125">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="33da9-125">Select the segments you want to export.</span></span> <span data-ttu-id="33da9-126">Du kan exportera upp till totalt 1 000 000 kundprofiler till Marketo.</span><span class="sxs-lookup"><span data-stu-id="33da9-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Välj fält och segment som ska exporteras till Marketo":::

1. <span data-ttu-id="33da9-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="33da9-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="33da9-129">Exportera data</span><span class="sxs-lookup"><span data-stu-id="33da9-129">Export the data</span></span>

<span data-ttu-id="33da9-130">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="33da9-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="33da9-131">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="33da9-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="33da9-132">I Marketo kan du nu hitta dina segment under [Marketo-listor](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="33da9-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="33da9-133">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="33da9-133">Known limitations</span></span>

- <span data-ttu-id="33da9-134">Upp till 1 000 000 profiler per export till Marketo.</span><span class="sxs-lookup"><span data-stu-id="33da9-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="33da9-135">Export till Marketo är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="33da9-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="33da9-136">Det kan ta upp till 3 timmar att exportera segment med totalt 1 000 000 profiler.</span><span class="sxs-lookup"><span data-stu-id="33da9-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="33da9-137">Antalet profiler som du kan exportera till Marketo är beroende av och begränsat enligt ditt kontrakt med Marketo.</span><span class="sxs-lookup"><span data-stu-id="33da9-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="33da9-138">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="33da9-138">Data privacy and compliance</span></span>

<span data-ttu-id="33da9-139">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Marketo tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="33da9-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="33da9-140">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Marketo uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="33da9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="33da9-141">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="33da9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="33da9-142">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="33da9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
