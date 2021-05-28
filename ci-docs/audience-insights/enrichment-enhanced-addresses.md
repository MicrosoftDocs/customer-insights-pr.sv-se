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
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965600"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="78256-103">Utöka kundprofiler med förbättrade adresser</span><span class="sxs-lookup"><span data-stu-id="78256-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="78256-104">Adresser i dina data kan vara oadresserade, ofullständiga eller felaktiga.</span><span class="sxs-lookup"><span data-stu-id="78256-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="78256-105">Med Microsoft-modeller kan du normalisera och utöka adresserna i formatet [Common Data Model](/common-data-model/schema/core/applicationcommon/address) för bättre precision och insikter.</span><span class="sxs-lookup"><span data-stu-id="78256-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="78256-106">Hur vi förbättrar adresser</span><span class="sxs-lookup"><span data-stu-id="78256-106">How we enhance addresses</span></span>

<span data-ttu-id="78256-107">Vår modell går igenom en process i två steg för att förbättra en adress.</span><span class="sxs-lookup"><span data-stu-id="78256-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="78256-108">Först parsas adressen för att identifiera komponenterna och placerar dem i ett strukturerat format.</span><span class="sxs-lookup"><span data-stu-id="78256-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="78256-109">Sedan använder vi intelligent information för att korrigera, slutföra och standardisera värdena i adressen.</span><span class="sxs-lookup"><span data-stu-id="78256-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="78256-110">Exempel</span><span class="sxs-lookup"><span data-stu-id="78256-110">Example</span></span>

<span data-ttu-id="78256-111">Adressinformationen kan vara i ett annat format än standardformatet och innehålla stavningsfel.</span><span class="sxs-lookup"><span data-stu-id="78256-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="78256-112">Modellen kan åtgärda dessa problem och skapa konsekventa adresser i enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="78256-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

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

### <a name="limitations"></a><span data-ttu-id="78256-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="78256-113">Limitations</span></span>

<span data-ttu-id="78256-114">Förbättrade adresser fungerar bara med värden som redan finns i dina hämtade adressdata.</span><span class="sxs-lookup"><span data-stu-id="78256-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="78256-115">Modellen kommer inte att:</span><span class="sxs-lookup"><span data-stu-id="78256-115">The model doesn't:</span></span> 

1. <span data-ttu-id="78256-116">Kontrollera att adressen är en giltig adress.</span><span class="sxs-lookup"><span data-stu-id="78256-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="78256-117">Kontrollera att något av värdena, t.ex. postnummer eller gatunamn, är giltiga.</span><span class="sxs-lookup"><span data-stu-id="78256-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="78256-118">Ändra värden som inte känns igen.</span><span class="sxs-lookup"><span data-stu-id="78256-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="78256-119">Modellen använder maskininlärningsbaserade tekniker för att förbättra adresser.</span><span class="sxs-lookup"><span data-stu-id="78256-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="78256-120">Vi tillämpar ett högt förtroendevärde för när modellen ändrar ett indatavärde, precis som med andra 100 %-baserade modeller.</span><span class="sxs-lookup"><span data-stu-id="78256-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="78256-121">Länder eller regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="78256-121">Supported countries or regions</span></span>

<span data-ttu-id="78256-122">För närvarande stöder vi ut utöka adresser i dessa länder eller regioner:</span><span class="sxs-lookup"><span data-stu-id="78256-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="78256-123">Australien</span><span class="sxs-lookup"><span data-stu-id="78256-123">Australia</span></span>
- <span data-ttu-id="78256-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="78256-124">Canada</span></span>
- <span data-ttu-id="78256-125">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="78256-125">United Kingdom</span></span>
- <span data-ttu-id="78256-126">USA</span><span class="sxs-lookup"><span data-stu-id="78256-126">United States</span></span>

<span data-ttu-id="78256-127">Adresserna måste innehålla ett land-/regionvärde.</span><span class="sxs-lookup"><span data-stu-id="78256-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="78256-128">Vi behandlar inte adresser för länder eller regioner som inte har stöd och adresser som inte har angetts av något land eller en region.</span><span class="sxs-lookup"><span data-stu-id="78256-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="78256-129">Konfiguration av berikning</span><span class="sxs-lookup"><span data-stu-id="78256-129">Configure the enrichment</span></span>

1. <span data-ttu-id="78256-130">Gå till **Data** > **Berikning**.</span><span class="sxs-lookup"><span data-stu-id="78256-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="78256-131">Välj **Utöka mina data** på panelen **Förbättrade adresser**.</span><span class="sxs-lookup"><span data-stu-id="78256-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skärmbild av panelen Förbättrade adresser.":::

1. <span data-ttu-id="78256-133">Välj **Kunddatauppsättning** och välj den entitet som innehåller de adresser du vill utöka.</span><span class="sxs-lookup"><span data-stu-id="78256-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="78256-134">Du kan välja entiteten *Kund* om du vill utöka adresser i alla kundprofiler eller välja en segmententitet om du endast vill utöka adresser i kundprofiler inom det segmentet.</span><span class="sxs-lookup"><span data-stu-id="78256-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="78256-135">Ange hur adresser ska formateras i datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="78256-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="78256-136">Välj **Adress med ett attribut** om ett enskilt fält används i adresserna i dina data.</span><span class="sxs-lookup"><span data-stu-id="78256-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="78256-137">Välj **Adress med flera attribut** om flera fält används i adresserna i dina data.</span><span class="sxs-lookup"><span data-stu-id="78256-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="78256-138">Land/region är obligatoriskt både i adress med ett attribut och med flera attribut.</span><span class="sxs-lookup"><span data-stu-id="78256-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="78256-139">Adresser som inte innehåller giltiga värden för land eller regioner som stöds kommer inte att berikas</span><span class="sxs-lookup"><span data-stu-id="78256-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="78256-140">Mappa adressfälten från en enhetlig kundentitet.</span><span class="sxs-lookup"><span data-stu-id="78256-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Förbättrad sida för adressfältmappning.":::

1. <span data-ttu-id="78256-142">Välj **Nästa** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="78256-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="78256-143">Ange ett namn för berikningen och den utgående enheten.</span><span class="sxs-lookup"><span data-stu-id="78256-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="78256-144">Välj **Spara berikning** när du har granskat dina val.</span><span class="sxs-lookup"><span data-stu-id="78256-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="78256-145">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="78256-145">Enrichment results</span></span>

<span data-ttu-id="78256-146">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="78256-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="78256-147">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="78256-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="78256-148">Bearbetningstiden beror på storleken på dina kunddata.</span><span class="sxs-lookup"><span data-stu-id="78256-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="78256-149">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="78256-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="78256-150">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="78256-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="78256-151">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="78256-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="78256-152">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="78256-152">Next steps</span></span>

<span data-ttu-id="78256-153">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="78256-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="78256-154">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="78256-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
