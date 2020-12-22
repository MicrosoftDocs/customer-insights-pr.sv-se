---
title: Berikning med tredjepartsberikningen HERE Technologies
description: Allmän information om tredjepartsberikningen HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668700"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="fe760-103">Berikning av kundprofiler med HERE Technologies (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="fe760-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="fe760-104">HERE Technologies är ett plattformsföretag som tillhandahåller platsrelaterade data och tjänster.</span><span class="sxs-lookup"><span data-stu-id="fe760-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="fe760-105">Med HERE Technologies databerikande tjänster kan du få en mer exakt förståelse för kundens plats, med adress, latitud och longitud och så vidare.</span><span class="sxs-lookup"><span data-stu-id="fe760-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe760-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="fe760-106">Prerequisites</span></span>

<span data-ttu-id="fe760-107">Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera HERE Technologies-berikning:</span><span class="sxs-lookup"><span data-stu-id="fe760-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fe760-108">Du har en aktiv HERE Technologies-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="fe760-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="fe760-109">Om du vill få en prenumeration kan du [registrera dig hä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkt.</span><span class="sxs-lookup"><span data-stu-id="fe760-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="fe760-110">Läs mer om HERE Technologies platsberikning.</span><span class="sxs-lookup"><span data-stu-id="fe760-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="fe760-111">Du använder HERE Technologies API-nyckel.</span><span class="sxs-lookup"><span data-stu-id="fe760-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="fe760-112">Du har [administratörs](permissions.md#administrator)behörigheter.</span><span class="sxs-lookup"><span data-stu-id="fe760-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="fe760-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="fe760-113">Configuration</span></span>

1. <span data-ttu-id="fe760-114">Gå till **Data** > **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="fe760-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="fe760-115">Välj **Berika mina data** i panelen HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="fe760-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe760-116">![HERE Technologies-panel](media/HERE-tile.png "HERE Technologies-panel")</span><span class="sxs-lookup"><span data-stu-id="fe760-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="fe760-117">Ange en aktiv **API-nyckel för HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="fe760-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="fe760-118">Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="fe760-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="fe760-119">Bekräfta båda indata genom att välja **Anslut till HERE**.</span><span class="sxs-lookup"><span data-stu-id="fe760-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="fe760-120">Välj **Lägg till data** och välj om du vill mappa fält till den primära och/eller sekundära adressen.</span><span class="sxs-lookup"><span data-stu-id="fe760-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="fe760-121">Du kan ange en fältmappning för båda adresserna (t.ex. hem- och affärsadress) och berika profilerna för båda adresserna separat.</span><span class="sxs-lookup"><span data-stu-id="fe760-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="fe760-122">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe760-122">Select **Next**.</span></span>

1. <span data-ttu-id="fe760-123">Definiera vilka fält från dina enhetliga profiler som ska användas för att söka efter matchande platsdata från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="fe760-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="fe760-124">Fälten **Gata 1** och **Postnummer** är obligatoriska för den valda primära och/eller sekundära adressen.</span><span class="sxs-lookup"><span data-stu-id="fe760-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="fe760-125">För en högre matchningsnoggrannhet kan fler fält läggas till.</span><span class="sxs-lookup"><span data-stu-id="fe760-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe760-126">![Sida för konfiguration av HERE Technologies-berikning](media/enrichment-HERE-configuration.png "Sida för konfiguration av HERE Technologies-berikning")</span><span class="sxs-lookup"><span data-stu-id="fe760-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="fe760-127">Välj **Tillämpa** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="fe760-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fe760-128">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="fe760-128">Enrichment results</span></span>

<span data-ttu-id="fe760-129">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="fe760-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fe760-130">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fe760-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fe760-131">Bearbetningstiden beror på storleken på kunddata och API-svarstiderna från HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="fe760-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="fe760-132">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="fe760-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="fe760-133">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="fe760-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fe760-134">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="fe760-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe760-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fe760-135">Next steps</span></span>

<span data-ttu-id="fe760-136">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="fe760-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fe760-137">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="fe760-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fe760-138">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="fe760-138">Data privacy and compliance</span></span>

<span data-ttu-id="fe760-139">När du aktiverar Dynamics 365 Customer Insights för att överföra data till HERE Technologies tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fe760-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fe760-140">Microsoft kommer att överföra dessa data på din instruktion, men du ansvarar för att HERE Technologies uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="fe760-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fe760-141">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fe760-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fe760-142">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="fe760-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
