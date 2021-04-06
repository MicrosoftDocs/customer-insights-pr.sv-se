---
title: Berikning med tredjepartsberikningen Experian
description: Allmän information om tredjepartsberikningen Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597809"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="44a5f-103">Berika kundprofiler med demografisk information från Experian (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="44a5f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="44a5f-104">Experian är en global ledare inom konsument- och affärskreditrapportering och marknadsföringstjänster.</span><span class="sxs-lookup"><span data-stu-id="44a5f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="44a5f-105">Med Experians databerikningstjänster kan du skapa en djupare förståelse för dina kunder genom att berika dina kundprofiler med demografiska uppgifter som hushållsstorlek, inkomst och mer.</span><span class="sxs-lookup"><span data-stu-id="44a5f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44a5f-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="44a5f-106">Prerequisites</span></span>

<span data-ttu-id="44a5f-107">För att konfigurera Experian måste följande villkor vara uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="44a5f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="44a5f-108">Du har en aktiv Experian-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="44a5f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="44a5f-109">Om du vill få en prenumeration [kontaktar du Experian](https://www.experian.com/marketing-services/contact) direkt.</span><span class="sxs-lookup"><span data-stu-id="44a5f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="44a5f-110">[Läs mer om Experian databerikande](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="44a5f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="44a5f-111">Du har användar-ID, part-ID och modellnummer för ditt SSH-aktiverade Secure Transport-konto (ST) som Experian skapat åt dig.</span><span class="sxs-lookup"><span data-stu-id="44a5f-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="44a5f-112">Du har [administratörs](permissions.md#administrator)behörigheter i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="44a5f-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="44a5f-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="44a5f-113">Configuration</span></span>

1. <span data-ttu-id="44a5f-114">Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.</span><span class="sxs-lookup"><span data-stu-id="44a5f-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="44a5f-115">Välj **Berika mina data** på Experian-panelen.</span><span class="sxs-lookup"><span data-stu-id="44a5f-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="44a5f-116">![Experian-panel](media/experian-tile.png "Experian-panel")</span><span class="sxs-lookup"><span data-stu-id="44a5f-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="44a5f-117">Välj **komma igång** och ange användar-ID, part-ID och modellnummer för ditt Experian Secure Transport-konto.</span><span class="sxs-lookup"><span data-stu-id="44a5f-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="44a5f-118">Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="44a5f-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="44a5f-119">Bekräfta alla indata genom att välja **tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="44a5f-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="44a5f-120">Mappa dina fält</span><span class="sxs-lookup"><span data-stu-id="44a5f-120">Map your fields</span></span>

1.  <span data-ttu-id="44a5f-121">Välj **Lägg till data** och välj den **kunddatauppsättning** du vill berika med demografidata från Experian.</span><span class="sxs-lookup"><span data-stu-id="44a5f-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="44a5f-122">Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="44a5f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="44a5f-123">Välj nyckelidentifierare från **Namn och adress**, **E-post** eller **Telefon** att skicka till Experian för identitetslösning.</span><span class="sxs-lookup"><span data-stu-id="44a5f-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="44a5f-124">Fler nyckel-ID-attribut som skickas till Experian ger troligen en högre matchningsfrekvens.</span><span class="sxs-lookup"><span data-stu-id="44a5f-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="44a5f-125">Välj **Nästa** och mappa motsvarande attribut från entiteten Enhetlig kund för de valda nyckel-ID-fälten.</span><span class="sxs-lookup"><span data-stu-id="44a5f-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="44a5f-126">Välj **Lägg till attribut** för att mappa ytterligare attribut som du vill skicka till Experian.</span><span class="sxs-lookup"><span data-stu-id="44a5f-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="44a5f-127">Välj **Spara** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="44a5f-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44a5f-128">![Experian fältmappning](media/experian-field-mapping.png "Experian fältmappning")</span><span class="sxs-lookup"><span data-stu-id="44a5f-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="44a5f-129">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="44a5f-129">Enrichment results</span></span>

<span data-ttu-id="44a5f-130">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="44a5f-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="44a5f-131">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="44a5f-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="44a5f-132">Bearbetningstiden beror på storleken på kundens data och de eventuella processer som har konfigurerats för ditt konto av Experian.</span><span class="sxs-lookup"><span data-stu-id="44a5f-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="44a5f-133">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="44a5f-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="44a5f-134">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="44a5f-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="44a5f-135">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="44a5f-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44a5f-136">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="44a5f-136">Next steps</span></span>

<span data-ttu-id="44a5f-137">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="44a5f-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="44a5f-138">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="44a5f-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="44a5f-139">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="44a5f-139">Data privacy and compliance</span></span>

<span data-ttu-id="44a5f-140">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Experian tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="44a5f-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="44a5f-141">Microsoft kommer att överföra dessa data i din instruktion, men du ansvarar för att Experian uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="44a5f-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="44a5f-142">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="44a5f-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="44a5f-143">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="44a5f-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]