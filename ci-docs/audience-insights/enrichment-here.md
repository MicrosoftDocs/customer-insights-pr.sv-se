---
title: Berikning med tredjepartsberikningen HERE Technologies
description: Allmän information om tredjepartsberikningen HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269536"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="e31a2-103">Berikning av kundprofiler med HERE Technologies (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="e31a2-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="e31a2-104">HERE Technologies är ett plattformsföretag som tillhandahåller platsrelaterade data och tjänster.</span><span class="sxs-lookup"><span data-stu-id="e31a2-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="e31a2-105">Med HERE Technologies databerikande tjänster kan du få en mer exakt förståelse för kundens plats, med adress, latitud och longitud och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e31a2-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e31a2-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e31a2-106">Prerequisites</span></span>

<span data-ttu-id="e31a2-107">Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera HERE Technologies-berikning:</span><span class="sxs-lookup"><span data-stu-id="e31a2-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e31a2-108">Du har en aktiv HERE Technologies-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e31a2-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="e31a2-109">Om du vill få en prenumeration kan du [registrera dig hä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkt.</span><span class="sxs-lookup"><span data-stu-id="e31a2-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="e31a2-110">Läs mer om HERE Technologies platsberikning.</span><span class="sxs-lookup"><span data-stu-id="e31a2-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="e31a2-111">Du använder HERE Technologies API-nyckel.</span><span class="sxs-lookup"><span data-stu-id="e31a2-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="e31a2-112">Du har [administratörs](permissions.md#administrator)behörigheter.</span><span class="sxs-lookup"><span data-stu-id="e31a2-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="e31a2-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e31a2-113">Configuration</span></span>

1. <span data-ttu-id="e31a2-114">Gå till **Data** > **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="e31a2-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="e31a2-115">Välj **Berika mina data** i panelen HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e31a2-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e31a2-116">![HERE Technologies-panel](media/HERE-tile.png "HERE Technologies-panel")</span><span class="sxs-lookup"><span data-stu-id="e31a2-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="e31a2-117">Ange en aktiv **API-nyckel för HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="e31a2-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="e31a2-118">Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="e31a2-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="e31a2-119">Bekräfta båda indata genom att välja **Anslut till HERE**.</span><span class="sxs-lookup"><span data-stu-id="e31a2-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="e31a2-120">Välj **Lägg till data** och välj den **kunddatauppsättning** du vill berika med platsdata från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e31a2-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="e31a2-121">Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="e31a2-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. <span data-ttu-id="e31a2-123">Välj om du vill mappa fält till den primära och/eller sekundära adressen.</span><span class="sxs-lookup"><span data-stu-id="e31a2-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="e31a2-124">Du kan ange en fältmappning för båda adresserna (t.ex. hem- och affärsadress) och berika profilerna för båda adresserna separat.</span><span class="sxs-lookup"><span data-stu-id="e31a2-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="e31a2-125">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e31a2-125">Select **Next**.</span></span>

1. <span data-ttu-id="e31a2-126">Definiera vilka fält från dina enhetliga profiler som ska användas för att söka efter matchande platsdata från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e31a2-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="e31a2-127">Fälten **Gata 1** och **Postnummer** är obligatoriska för den valda primära och/eller sekundära adressen.</span><span class="sxs-lookup"><span data-stu-id="e31a2-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="e31a2-128">För en högre matchningsnoggrannhet kan fler fält läggas till.</span><span class="sxs-lookup"><span data-stu-id="e31a2-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e31a2-129">![Sida för konfiguration av HERE Technologies-berikning](media/enrichment-HERE-configuration.png "Sida för konfiguration av HERE Technologies-berikning")</span><span class="sxs-lookup"><span data-stu-id="e31a2-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="e31a2-130">Välj **Tillämpa** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="e31a2-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e31a2-131">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="e31a2-131">Enrichment results</span></span>

<span data-ttu-id="e31a2-132">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="e31a2-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e31a2-133">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e31a2-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e31a2-134">Bearbetningstiden beror på storleken på kunddata och API-svarstiderna från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e31a2-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="e31a2-135">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="e31a2-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e31a2-136">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="e31a2-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e31a2-137">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="e31a2-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e31a2-138">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e31a2-138">Next steps</span></span>

<span data-ttu-id="e31a2-139">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="e31a2-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e31a2-140">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="e31a2-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e31a2-141">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="e31a2-141">Data privacy and compliance</span></span>

<span data-ttu-id="e31a2-142">När du aktiverar Dynamics 365 Customer Insights för att överföra data till HERE Technologies tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e31a2-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e31a2-143">Microsoft kommer att överföra dessa data på din instruktion, men du ansvarar för att HERE Technologies uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="e31a2-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e31a2-144">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e31a2-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e31a2-145">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="e31a2-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]