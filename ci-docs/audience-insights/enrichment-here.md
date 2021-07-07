---
title: Berikande med tredjepartsberikande HERE Technologies
description: Allmän information om tredjepartsberikningen HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305316"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="e6d98-103">Berikning av kundprofiler med HERE Technologies (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="e6d98-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="e6d98-104">HERE Technologies är ett plattformsföretag som tillhandahåller platsrelaterade data och tjänster.</span><span class="sxs-lookup"><span data-stu-id="e6d98-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="e6d98-105">Med HERE Technologies databerikande tjänster kan du få en mer exakt förståelse för kundens plats, med adress, latitud och longitud och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e6d98-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6d98-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e6d98-106">Prerequisites</span></span>

<span data-ttu-id="e6d98-107">Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera HERE Technologies-berikning:</span><span class="sxs-lookup"><span data-stu-id="e6d98-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e6d98-108">Du har en aktiv HERE Technologies-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e6d98-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="e6d98-109">Om du vill få en prenumeration kan du [registrera dig här](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkt.</span><span class="sxs-lookup"><span data-stu-id="e6d98-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="e6d98-110">Läs mer om HERE Technologies platsberikning.</span><span class="sxs-lookup"><span data-stu-id="e6d98-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="e6d98-111">En HERE-[anslutning](connections.md) är tillgänglig *eller* också har du [administratörs](permissions.md#administrator)behörigheter och API-nyckel för HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e6d98-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e6d98-112">Konfiguration av berikning</span><span class="sxs-lookup"><span data-stu-id="e6d98-112">Configure the enrichment</span></span>

1. <span data-ttu-id="e6d98-113">Gå till **Data** > **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="e6d98-114">Välj **Utöka mina data** på panelen HERE Technologies och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6d98-115">![HERE Technologies-panel](media/HERE-tile.png "HERE Technologies-panel")</span><span class="sxs-lookup"><span data-stu-id="e6d98-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="e6d98-116">Välj en [anslutning](connections.md) i listrutan.</span><span class="sxs-lookup"><span data-stu-id="e6d98-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="e6d98-117">Kontakta en administratör om det inte finns någon anslutning.</span><span class="sxs-lookup"><span data-stu-id="e6d98-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="e6d98-118">Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="e6d98-119">Välj **HERE Technologies** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="e6d98-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="e6d98-120">Välj **Anslut till HERE Technologies** för att bekräfta anslutningsvalet.</span><span class="sxs-lookup"><span data-stu-id="e6d98-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="e6d98-121">Välj **Nästa** och välj den **kunddatauppsättning** du vill utöka med platsdata från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e6d98-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="e6d98-122">Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="e6d98-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. <span data-ttu-id="e6d98-124">Välj om du vill mappa fält till den primära och/eller sekundära adressen.</span><span class="sxs-lookup"><span data-stu-id="e6d98-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="e6d98-125">Du kan ange en fältmappning för både adresser och utöka profilerna för båda adresserna separat.</span><span class="sxs-lookup"><span data-stu-id="e6d98-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="e6d98-126">Till exempel om det finns ett hem och en affärsadress.</span><span class="sxs-lookup"><span data-stu-id="e6d98-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="e6d98-127">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-127">Select **Next**.</span></span>

1. <span data-ttu-id="e6d98-128">Definiera vilka fält från dina enhetliga profiler som ska användas för att söka efter matchande platsdata från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e6d98-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="e6d98-129">Fälten **Gata 1** och **Postnummer** är obligatoriska för den valda primära och/eller sekundära adressen.</span><span class="sxs-lookup"><span data-stu-id="e6d98-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="e6d98-130">För en högre matchningsnoggrannhet kan fler fält läggas till.</span><span class="sxs-lookup"><span data-stu-id="e6d98-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6d98-131">![Sida för konfiguration av HERE Technologies-berikning](media/enrichment-HERE-configuration.png "Sida för konfiguration av HERE Technologies-berikning")</span><span class="sxs-lookup"><span data-stu-id="e6d98-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="e6d98-132">Välj **Nästa** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="e6d98-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="e6d98-133">Ange ett namn för anrikningen.</span><span class="sxs-lookup"><span data-stu-id="e6d98-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="e6d98-134">Välj **Spara berikning** när du har granskat dina val.</span><span class="sxs-lookup"><span data-stu-id="e6d98-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="e6d98-135">Konfigurera anslutningen för HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="e6d98-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="e6d98-136">Du måste vara en administratör för att konfigurera anslutningar.</span><span class="sxs-lookup"><span data-stu-id="e6d98-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e6d98-137">Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på HERE technologies.</span><span class="sxs-lookup"><span data-stu-id="e6d98-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="e6d98-138">Ange ett namn för anslutningen i rutan **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e6d98-139">Ange en giltig API-nyckel för HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e6d98-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="e6d98-140">Granska och ge ditt samtycke till **Data sekretess och efterlevnad** genom att välja **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="e6d98-141">Välj **Verifiera** om konfigurationen ska verifieras.</span><span class="sxs-lookup"><span data-stu-id="e6d98-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e6d98-142">Välj **Spara** när verifieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="e6d98-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6d98-143">![Konfigurationssida för HERE technologies-anslutning](media/enrichment-HERE-connection.png "Konfigurationssida för HERE technologies-anslutning")</span><span class="sxs-lookup"><span data-stu-id="e6d98-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e6d98-144">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="e6d98-144">Enrichment results</span></span>

<span data-ttu-id="e6d98-145">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="e6d98-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e6d98-146">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6d98-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6d98-147">Bearbetningstiden beror på storleken på kunddata och API-svarstiderna från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e6d98-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="e6d98-148">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e6d98-149">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="e6d98-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e6d98-150">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="e6d98-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6d98-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e6d98-151">Next steps</span></span>

<span data-ttu-id="e6d98-152">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="e6d98-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e6d98-153">Skapa [segment](segments.md) och [mått](measures.md) och till och med [exportera datan](export-destinations.md) för att leverera anpassade upplevelser till dina kunder.</span><span class="sxs-lookup"><span data-stu-id="e6d98-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e6d98-154">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="e6d98-154">Data privacy and compliance</span></span>

<span data-ttu-id="e6d98-155">När du aktiverar Dynamics 365 Customer Insights för att överföra data till HERE Technologies tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e6d98-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e6d98-156">Microsoft kommer att överföra dessa data på din instruktion, men du ansvarar för att HERE Technologies uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="e6d98-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e6d98-157">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e6d98-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e6d98-158">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="e6d98-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
