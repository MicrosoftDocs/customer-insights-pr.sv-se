---
title: Berikning av företagsprofiler med tredjepartsberikning från Leadspace
description: Allmän information om tredjepartsberikningen Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269444"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="4dcc9-103">Berikning av företagsprofiler med Leadspace (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4dcc9-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="4dcc9-104">Leadspace är ett datavetenskapsföretag som tillhandahåller en B2B-kunddataplattform.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="4dcc9-105">Det gör det möjligt för kunder med enhetliga kundprofiler för företag att berika sina data.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="4dcc9-106">Berikning inkluderar ytterligare attribut, till exempel företagsstorlek, plats, industri med mera.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4dcc9-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4dcc9-107">Prerequisites</span></span>

<span data-ttu-id="4dcc9-108">Följande krav måste vara uppfyllda för att du ska kunna konfigurera Leadspace:</span><span class="sxs-lookup"><span data-stu-id="4dcc9-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4dcc9-109">Du har en aktiv Leadspace-licens och en "evig nyckel" (kallas **Leadspace-token**).</span><span class="sxs-lookup"><span data-stu-id="4dcc9-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="4dcc9-110">Kontakta direkt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) för mer information om deras produkter.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="4dcc9-111">Du har [administratörs](permissions.md#administrator)behörigheter.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="4dcc9-112">Du har [enhetliga kundprofiler](customer-profiles.md) för företag.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="4dcc9-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4dcc9-113">Configuration</span></span>

1. <span data-ttu-id="4dcc9-114">I målgruppsinsikter går du till **Data** > **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="4dcc9-115">Välj **utöka mina data** på Leadspace-panelen.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skärmbild av Leadspaces-panelen.":::

1. <span data-ttu-id="4dcc9-117">Välj **Kom igång** och ange sedan ett aktivt **Leadspace-token** (evig nyckel).</span><span class="sxs-lookup"><span data-stu-id="4dcc9-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="4dcc9-118">Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="4dcc9-119">Bekräfta båda indata genom att välja **Anslut till Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="4dcc9-120">Välj **Mappa data** och välj den datauppsättning som du vill berika med företagsdata från Leadspace.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="4dcc9-121">Du kan välja entiteten *Kund* för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Välj mellan kundprofil och segmentberikning.":::

1. <span data-ttu-id="4dcc9-123">Klicka på **Nästa** och definiera vilka fält från dina enhetliga profiler som ska användas för att söka efter matchande företagsdata från Leadspace.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="4dcc9-124">Fältet **Företagets namn** är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-124">The **Name of company** field is required.</span></span> <span data-ttu-id="4dcc9-125">För högre matchningsnoggrannhet kan upp till två ytterligare fält, **Företagets webbplats** och **Företagets plats**, läggas till.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Fältmappningsfönstret för Leadspace.":::
   
1. <span data-ttu-id="4dcc9-127">Välj **Tillämpa** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="4dcc9-128">Välj **Kör** för att berika företagsprofilerna.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="4dcc9-129">Hur lång tid en berikning tar beror på antalet enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="4dcc9-130">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="4dcc9-130">Enrichment results</span></span>

<span data-ttu-id="4dcc9-131">När du har uppdaterat en anrikning kan du granska de nya data som har utökats under [Mina berikningar](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="4dcc9-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="4dcc9-132">Du kan hitta tidpunkten för den senaste uppdateringen och antalet berikade profiler.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4dcc9-133">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="4dcc9-134">Mer information finns på [API:er för Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="4dcc9-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4dcc9-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4dcc9-135">Next steps</span></span>

<span data-ttu-id="4dcc9-136">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4dcc9-137">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4dcc9-138">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="4dcc9-138">Data privacy and compliance</span></span>

<span data-ttu-id="4dcc9-139">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Leadspace tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4dcc9-140">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Leadspace uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4dcc9-141">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4dcc9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4dcc9-142">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="4dcc9-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]