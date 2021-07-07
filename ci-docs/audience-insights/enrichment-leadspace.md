---
title: Berikning av företagsprofiler med tredjepartsberikning från Leadspace
description: Allmän information om tredjepartsberikningen Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305224"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="6f042-103">Berikning av företagsprofiler med Leadspace (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="6f042-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="6f042-104">Leadspace är ett datavetenskapsföretag som tillhandahåller en B2B-kunddataplattform.</span><span class="sxs-lookup"><span data-stu-id="6f042-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="6f042-105">Det gör det möjligt för kunder med enhetliga kundprofiler för företag att berika sina data.</span><span class="sxs-lookup"><span data-stu-id="6f042-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="6f042-106">Berikningar omfattar fler attribut, till exempel företagsstorlek, plats, industri med mera.</span><span class="sxs-lookup"><span data-stu-id="6f042-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f042-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="6f042-107">Prerequisites</span></span>

<span data-ttu-id="6f042-108">Följande krav måste vara uppfyllda för att du ska kunna konfigurera Leadspace:</span><span class="sxs-lookup"><span data-stu-id="6f042-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6f042-109">Du har en aktiv Leadspace-licens.</span><span class="sxs-lookup"><span data-stu-id="6f042-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="6f042-110">Du har [enhetliga kundprofiler](customer-profiles.md) för företag.</span><span class="sxs-lookup"><span data-stu-id="6f042-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="6f042-111">En Leadspace-anslutning har redan konfigurerats av en administratör eller så har du behörigheterna [administratör](permissions.md#administrator) och “evig nyckel” (kallas för **Leadspace-token**).</span><span class="sxs-lookup"><span data-stu-id="6f042-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="6f042-112">Kontakta [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkt för mer information om produkten.</span><span class="sxs-lookup"><span data-stu-id="6f042-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="6f042-113">Konfiguration av berikning</span><span class="sxs-lookup"><span data-stu-id="6f042-113">Configure the enrichment</span></span>

1. <span data-ttu-id="6f042-114">I målgruppsinsikter går du till **Data** > **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="6f042-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="6f042-115">Välj **Utöka mina data** på panelen Leadspace och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="6f042-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skärmbild av Leadspaces-panelen.":::

1. <span data-ttu-id="6f042-117">Välj en [anslutning](connections.md) i listrutan.</span><span class="sxs-lookup"><span data-stu-id="6f042-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="6f042-118">Kontakta en administratör om det inte finns någon anslutning.</span><span class="sxs-lookup"><span data-stu-id="6f042-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="6f042-119">Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="6f042-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="6f042-120">Välj **Anslut till Leadspace** för att bekräfta anslutningen.</span><span class="sxs-lookup"><span data-stu-id="6f042-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="6f042-121">Välj **Nästa** och välj den **kunddatauppsättning** du vill utöka med företagsdata från Leadspace.</span><span class="sxs-lookup"><span data-stu-id="6f042-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="6f042-122">Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="6f042-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. <span data-ttu-id="6f042-124">Välj **Nästa** och definiera vilka fält från dina enhetliga profiler som används för att söka efter matchande företagsdata från Leadspace.</span><span class="sxs-lookup"><span data-stu-id="6f042-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="6f042-125">Fältet **Företagets namn** är obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="6f042-125">The **Name of company** field is required.</span></span> <span data-ttu-id="6f042-126">För högre matchningsnoggrannhet kan upp till två ytterligare fält, **Företagets webbplats** och **Företagets plats**, läggas till.</span><span class="sxs-lookup"><span data-stu-id="6f042-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Fältmappningsfönstret för Leadspace.":::

1. <span data-ttu-id="6f042-128">Välj **Nästa** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="6f042-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="6f042-129">Ange ett namn för berikning och välj **Spara berikning** efter att ha granskat dina val.</span><span class="sxs-lookup"><span data-stu-id="6f042-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="6f042-130">Konfigurera anslutningen för Leadspace</span><span class="sxs-lookup"><span data-stu-id="6f042-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="6f042-131">Du måste vara en administratör för att konfigurera anslutningar.</span><span class="sxs-lookup"><span data-stu-id="6f042-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="6f042-132">Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på Leadspace-panelen.</span><span class="sxs-lookup"><span data-stu-id="6f042-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="6f042-133">Välj **Komma igång**.</span><span class="sxs-lookup"><span data-stu-id="6f042-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="6f042-134">Ange ett namn för anslutningen i rutan **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="6f042-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="6f042-135">Ange en giltig Leadspace-token.</span><span class="sxs-lookup"><span data-stu-id="6f042-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="6f042-136">Granska och ge ditt samtycke till **Data sekretess och efterlevnad** genom att välja **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="6f042-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="6f042-137">Välj **Verifiera** om konfigurationen ska verifieras.</span><span class="sxs-lookup"><span data-stu-id="6f042-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="6f042-138">Välj **Spara** när verifieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="6f042-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfigurationssida för Leadspace-anslutning":::

## <a name="enrichment-results"></a><span data-ttu-id="6f042-140">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="6f042-140">Enrichment results</span></span>

<span data-ttu-id="6f042-141">När du har uppdaterat en anrikning kan du granska de nya data som har utökats under [Mina berikningar](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="6f042-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="6f042-142">Du kan hitta tidpunkten för den senaste uppdateringen och antalet berikade profiler.</span><span class="sxs-lookup"><span data-stu-id="6f042-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6f042-143">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="6f042-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="6f042-144">Mer information finns på [API:er för Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="6f042-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f042-145">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6f042-145">Next steps</span></span>

<span data-ttu-id="6f042-146">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="6f042-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6f042-147">Skapa [segment](segments.md) och [mått](measures.md) och till och med [exportera datan](export-destinations.md) för att leverera anpassade upplevelser till dina kunder.</span><span class="sxs-lookup"><span data-stu-id="6f042-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6f042-148">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="6f042-148">Data privacy and compliance</span></span>

<span data-ttu-id="6f042-149">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Leadspace tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="6f042-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6f042-150">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Leadspace uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="6f042-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6f042-151">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6f042-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6f042-152">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="6f042-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
