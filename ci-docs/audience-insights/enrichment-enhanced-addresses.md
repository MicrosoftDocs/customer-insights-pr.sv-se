---
title: Utöka adressförbättringar
description: Utöka och normalisera adressuppgifter i kundprofiler med Microsoft-modeller.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305454"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="03fb2-103">Utöka kundprofiler med förbättrade adresser</span><span class="sxs-lookup"><span data-stu-id="03fb2-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="03fb2-104">Adresser i dina data kan vara oadresserade, ofullständiga eller felaktiga.</span><span class="sxs-lookup"><span data-stu-id="03fb2-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="03fb2-105">Med Microsoft-modeller kan du normalisera och utöka adresserna i formatet [Common Data Model](/common-data-model/schema/core/applicationcommon/address) för bättre precision och insikter.</span><span class="sxs-lookup"><span data-stu-id="03fb2-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="03fb2-106">Hur vi förbättrar adresser</span><span class="sxs-lookup"><span data-stu-id="03fb2-106">How we enhance addresses</span></span>

<span data-ttu-id="03fb2-107">Vår modell går igenom en process i två steg för att förbättra en adress.</span><span class="sxs-lookup"><span data-stu-id="03fb2-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="03fb2-108">Först parsas adressen för att identifiera komponenterna och placerar dem i ett strukturerat format.</span><span class="sxs-lookup"><span data-stu-id="03fb2-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="03fb2-109">Därefter använder vi AI för att korrigera, slutföra och standardisera värdena i adressen.</span><span class="sxs-lookup"><span data-stu-id="03fb2-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="03fb2-110">Exempel</span><span class="sxs-lookup"><span data-stu-id="03fb2-110">Example</span></span>

<span data-ttu-id="03fb2-111">Adressinformationen kan vara i ett icke-standardformat och innehålla stavningsfel.</span><span class="sxs-lookup"><span data-stu-id="03fb2-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="03fb2-112">Modellen kan åtgärda dessa problem och skapa konsekventa adresser i enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="03fb2-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="03fb2-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="03fb2-113">Limitations</span></span>

<span data-ttu-id="03fb2-114">Förbättrade adresser fungerar bara med värden som redan finns i dina hämtade adressdata.</span><span class="sxs-lookup"><span data-stu-id="03fb2-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="03fb2-115">Modellen kommer inte att:</span><span class="sxs-lookup"><span data-stu-id="03fb2-115">The model doesn't:</span></span> 

1. <span data-ttu-id="03fb2-116">Kontrollera att adressen är en giltig adress.</span><span class="sxs-lookup"><span data-stu-id="03fb2-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="03fb2-117">Kontrollera att något av värdena, t.ex. postnummer eller gatunamn, är giltiga.</span><span class="sxs-lookup"><span data-stu-id="03fb2-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="03fb2-118">Ändra värden som inte känns igen.</span><span class="sxs-lookup"><span data-stu-id="03fb2-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="03fb2-119">Modellen använder maskininlärningsbaserade tekniker för att förbättra adresser.</span><span class="sxs-lookup"><span data-stu-id="03fb2-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="03fb2-120">Även om vi tillämpar ett tröskelvärde för högt förtroende för när modellen ändrar ett indatavärde kan, precis som med andra maskininlärningsbaserade modeller, hundraprocentig precision inte garanteras.</span><span class="sxs-lookup"><span data-stu-id="03fb2-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="03fb2-121">Länder eller regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="03fb2-121">Supported countries or regions</span></span>

<span data-ttu-id="03fb2-122">För närvarande stöder vi ut utöka adresser i dessa länder eller regioner:</span><span class="sxs-lookup"><span data-stu-id="03fb2-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="03fb2-123">Australien</span><span class="sxs-lookup"><span data-stu-id="03fb2-123">Australia</span></span>
- <span data-ttu-id="03fb2-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="03fb2-124">Canada</span></span>
- <span data-ttu-id="03fb2-125">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="03fb2-125">United Kingdom</span></span>
- <span data-ttu-id="03fb2-126">USA</span><span class="sxs-lookup"><span data-stu-id="03fb2-126">United States</span></span>

<span data-ttu-id="03fb2-127">Adresserna måste innehålla ett land-/regionvärde.</span><span class="sxs-lookup"><span data-stu-id="03fb2-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="03fb2-128">Vi behandlar inte adresser för länder eller regioner som inte har stöd och adresser som inte har angetts av något land eller en region.</span><span class="sxs-lookup"><span data-stu-id="03fb2-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="03fb2-129">Konfiguration av berikning</span><span class="sxs-lookup"><span data-stu-id="03fb2-129">Configure the enrichment</span></span>

1. <span data-ttu-id="03fb2-130">Gå till **Data** > **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="03fb2-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="03fb2-131">Välj **Utöka mina data** på panelen **Förbättrade adresser**.</span><span class="sxs-lookup"><span data-stu-id="03fb2-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skärmbild av panelen Förbättrade adresser.":::

1. <span data-ttu-id="03fb2-133">Välj **Kunddatauppsättning** och välj den entitet som innehåller de adresser du vill utöka.</span><span class="sxs-lookup"><span data-stu-id="03fb2-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="03fb2-134">Du kan välja entiteten *Kund* om du vill utöka adresser i alla kundprofiler eller välja en segmententitet om du endast vill utöka adresser i kundprofiler inom det segmentet.</span><span class="sxs-lookup"><span data-stu-id="03fb2-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="03fb2-135">Ange hur adresser ska formateras i datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="03fb2-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="03fb2-136">Välj **Adress med ett attribut** om ett enskilt fält används i adresserna i dina data.</span><span class="sxs-lookup"><span data-stu-id="03fb2-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="03fb2-137">Välj **Adress med flera attribut** om flera fält används i adresserna i dina data.</span><span class="sxs-lookup"><span data-stu-id="03fb2-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="03fb2-138">Land/region är obligatoriskt i adresser med såväl ett som flera attribut.</span><span class="sxs-lookup"><span data-stu-id="03fb2-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="03fb2-139">Adresser som inte innehåller giltiga värden för land eller regioner som stöds kommer inte att berikas.</span><span class="sxs-lookup"><span data-stu-id="03fb2-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="03fb2-140">Mappa adressfälten från en enhetlig kundentitet.</span><span class="sxs-lookup"><span data-stu-id="03fb2-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Förbättrad sida för adressfältmappning.":::

1. <span data-ttu-id="03fb2-142">Välj **Nästa** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="03fb2-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="03fb2-143">Ange ett namn för berikningen och den utgående enheten.</span><span class="sxs-lookup"><span data-stu-id="03fb2-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="03fb2-144">Välj **Spara berikning** när du har granskat dina val.</span><span class="sxs-lookup"><span data-stu-id="03fb2-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="03fb2-145">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="03fb2-145">Enrichment results</span></span>

<span data-ttu-id="03fb2-146">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="03fb2-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="03fb2-147">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="03fb2-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="03fb2-148">Bearbetningstiden beror på storleken på dina kunddata.</span><span class="sxs-lookup"><span data-stu-id="03fb2-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="03fb2-149">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="03fb2-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="03fb2-150">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="03fb2-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="03fb2-151">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="03fb2-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03fb2-152">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="03fb2-152">Next steps</span></span>

<span data-ttu-id="03fb2-153">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="03fb2-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="03fb2-154">Skapa [segment](segments.md) och [mått](measures.md) och till och med [exportera datan](export-destinations.md) för att leverera anpassade upplevelser till dina kunder.</span><span class="sxs-lookup"><span data-stu-id="03fb2-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
