---
title: Berika kundprofiler med data från Microsoft
description: Använd tillverkarspecifika data från Microsoft för att berika kunddata med intresse och varumärke.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245729"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="0551d-103">Utöka kundprofiler med varumärkes- och intressetillhörighet (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0551d-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="0551d-104">Använd tillverkarspecifika data från Microsoft för att berika kunddata med intresse och varumärke.</span><span class="sxs-lookup"><span data-stu-id="0551d-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="0551d-105">Dessa intressetillhörigheter bestäms utifrån data från personer som har liknande demografiska kunder.</span><span class="sxs-lookup"><span data-stu-id="0551d-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="0551d-106">Med hjälp av den här informationen kan du bättre förstå och segmentera dina kunder utifrån deras tillhörigheter till särskilda varumärken och intressen.</span><span class="sxs-lookup"><span data-stu-id="0551d-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="0551d-107">I målgruppsinsikter går du till **Data** > **Berikning** för att [konfigurera och visa berikningar](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0551d-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="0551d-108">Om du vill konfigurera berikning för varumärkestillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Varumärken**.</span><span class="sxs-lookup"><span data-stu-id="0551d-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="0551d-109">Om du vill konfigurera berikning av intressetillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Intressen**.</span><span class="sxs-lookup"><span data-stu-id="0551d-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0551d-110">![Paneler för varumärken och intressen](media/BrandsInterest-tile-Hub.png "Paneler för varumärken och intressen")</span><span class="sxs-lookup"><span data-stu-id="0551d-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="0551d-111">Så här avgör vi intresse</span><span class="sxs-lookup"><span data-stu-id="0551d-111">How we determine affinities</span></span>

<span data-ttu-id="0551d-112">Vi använder Microsofts onlinesökningsdata för att hitta intressegrupper och intressen i olika demografiska segment (definierade efter ålder, kön eller plats).</span><span class="sxs-lookup"><span data-stu-id="0551d-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="0551d-113">Om du söker online efter ett varumärke eller en ränta bestäms hur mycket tillhörighet som ett demografiskt segment ska jämföras med andra segment, det vill säga det varumärket.</span><span class="sxs-lookup"><span data-stu-id="0551d-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="0551d-114">Tillhörighetsnivå och poäng</span><span class="sxs-lookup"><span data-stu-id="0551d-114">Affinity level and score</span></span>

<span data-ttu-id="0551d-115">I varje berikad kundprofil tillhandahåller vi två relaterade värden – tillhörighetsnivå och tillhörighetspoäng.</span><span class="sxs-lookup"><span data-stu-id="0551d-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="0551d-116">Dessa värden hjälper dig att avgöra hur starkt tillhörigheten är för den profilens demografiska segment, för ett varumärke eller intresse, jämfört med andra demografiska segment.</span><span class="sxs-lookup"><span data-stu-id="0551d-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="0551d-117">*Tillhörighetsnivå* består av fyra nivåer och *tillhörighetspoäng* beräknas på en skala med 100 poäng som mappas till tillhörighetsnivåerna.</span><span class="sxs-lookup"><span data-stu-id="0551d-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="0551d-118">Tillhörighetsnivå</span><span class="sxs-lookup"><span data-stu-id="0551d-118">Affinity level</span></span> |<span data-ttu-id="0551d-119">Tillhörighetspoäng</span><span class="sxs-lookup"><span data-stu-id="0551d-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="0551d-120">Mycket högt</span><span class="sxs-lookup"><span data-stu-id="0551d-120">Very high</span></span>     | <span data-ttu-id="0551d-121">85–100</span><span class="sxs-lookup"><span data-stu-id="0551d-121">85-100</span></span>       |
|<span data-ttu-id="0551d-122">Högt</span><span class="sxs-lookup"><span data-stu-id="0551d-122">High</span></span>     | <span data-ttu-id="0551d-123">70–84</span><span class="sxs-lookup"><span data-stu-id="0551d-123">70-84</span></span>        |
|<span data-ttu-id="0551d-124">Medium</span><span class="sxs-lookup"><span data-stu-id="0551d-124">Medium</span></span>     | <span data-ttu-id="0551d-125">35–69</span><span class="sxs-lookup"><span data-stu-id="0551d-125">35-69</span></span>        |
|<span data-ttu-id="0551d-126">Lågt</span><span class="sxs-lookup"><span data-stu-id="0551d-126">Low</span></span>     | <span data-ttu-id="0551d-127">1–34</span><span class="sxs-lookup"><span data-stu-id="0551d-127">1-34</span></span>        |

<span data-ttu-id="0551d-128">Beroende på vilken granularitet du vill använda för att mäta tillhörigheten kan du använda antingen tillhörighetsnivå eller poäng.</span><span class="sxs-lookup"><span data-stu-id="0551d-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="0551d-129">Med tillhörighetspoäng får du mer exakt kontroll.</span><span class="sxs-lookup"><span data-stu-id="0551d-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="0551d-130">Länder/regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="0551d-130">Supported countries/regions</span></span>

<span data-ttu-id="0551d-131">Vi stöder för närvarande följande alternativ för land: Australien, Kanada (engelska), Frankrike, Tyskland, Storbritannien och USA (engelska).</span><span class="sxs-lookup"><span data-stu-id="0551d-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="0551d-132">Om du vill välja ett land öppnar du **varumärken** eller **intressen** och väljer **ändra** bredvid **land/region**.</span><span class="sxs-lookup"><span data-stu-id="0551d-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="0551d-133">I fönstret **inställningar för land/region** väljer du ett alternativ och väljer **tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="0551d-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="0551d-134">Effekter relaterade till val av land</span><span class="sxs-lookup"><span data-stu-id="0551d-134">Implications related to country selection</span></span>

- <span data-ttu-id="0551d-135">När [du väljer dina ega märken](#define-your-brands-or-interests) ger systemet förslag utifrån valt land eller vald region.</span><span class="sxs-lookup"><span data-stu-id="0551d-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="0551d-136">När [du väljer en bransch](#define-your-brands-or-interests) får du de mest relevanta märkena eller intressena utifrån valt land eller vald region.</span><span class="sxs-lookup"><span data-stu-id="0551d-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="0551d-137">När [du berikar profiler](#refresh-enrichment) berikar vi alla kundprofiler som vi får data för för de valda märkena och intressena.</span><span class="sxs-lookup"><span data-stu-id="0551d-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="0551d-138">Inklusive profiler som inte finns i det valda landet eller den valda regionen.</span><span class="sxs-lookup"><span data-stu-id="0551d-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="0551d-139">Om du till exempel valde Tyskland utökar vi profiler i USA om det finns tillgängliga data för valda tillverkare och intressen i USA.</span><span class="sxs-lookup"><span data-stu-id="0551d-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="0551d-140">Konfigurera berikning</span><span class="sxs-lookup"><span data-stu-id="0551d-140">Configure Enrichment</span></span>

<span data-ttu-id="0551d-141">En guidad upplevelse hjälper dig genom konfigurationen av berikningar.</span><span class="sxs-lookup"><span data-stu-id="0551d-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="0551d-142">Definiera dina varumärken eller intressen</span><span class="sxs-lookup"><span data-stu-id="0551d-142">Define your brands or interests</span></span>

<span data-ttu-id="0551d-143">Välj upp till fem varumärken eller intressen med ett eller båda av dessa alternativ:</span><span class="sxs-lookup"><span data-stu-id="0551d-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="0551d-144">**Bransch**: Välj din bransch i listrutan och välj sedan bland de bästa varumärkena eller intressena för den branschen.</span><span class="sxs-lookup"><span data-stu-id="0551d-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="0551d-145">**Välj ditt eget**: Ange ett varumärke eller intresse som är relevant för din organisation och välj sedan bland matchande förslag.</span><span class="sxs-lookup"><span data-stu-id="0551d-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="0551d-146">Om vi inte visar ett varumärke eller intresse som du letar efter kan du skicka feedback med hjälp av **föreslå** länk.</span><span class="sxs-lookup"><span data-stu-id="0551d-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="0551d-147">Granska inställningar för berikning</span><span class="sxs-lookup"><span data-stu-id="0551d-147">Review enrichment preferences</span></span>

<span data-ttu-id="0551d-148">Gå igenom standardinställningarna för berikning och uppdatera dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="0551d-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skärmbild av fönstret med inställningar för berikning.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="0551d-150">Välj en entitet att berika</span><span class="sxs-lookup"><span data-stu-id="0551d-150">Select entity to enrich</span></span>

<span data-ttu-id="0551d-151">Välj **Berikad entitet** och välj den datauppsättning du vill berika med företagsdata från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0551d-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="0551d-152">Du kan välja entiteten Kund för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="0551d-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="0551d-153">Mappa dina fält</span><span class="sxs-lookup"><span data-stu-id="0551d-153">Map your fields</span></span>

<span data-ttu-id="0551d-154">Mappa fält från en enhetlig kundentitet och definiera det demografiska segment som du vill att systemet ska använda för att berika kunddata.</span><span class="sxs-lookup"><span data-stu-id="0551d-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="0551d-155">Mappa land/region och åtminstone attributen Födelsedatum eller Kön.</span><span class="sxs-lookup"><span data-stu-id="0551d-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="0551d-156">Du måste också mappa minst en av Ort (och Region) eller Postnummer.</span><span class="sxs-lookup"><span data-stu-id="0551d-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="0551d-157">Välj **redigera** om du vill definiera mappningen av fälten och välj **Tillämpa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="0551d-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="0551d-158">Välj **Spara** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="0551d-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="0551d-159">Följande format och värden stöds är värden inte skiftlägeskänsliga:</span><span class="sxs-lookup"><span data-stu-id="0551d-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="0551d-160">**Födelsedatum**: Vi rekommenderar att födelsedatumet konverteras till typen DateTime under datainmatning.</span><span class="sxs-lookup"><span data-stu-id="0551d-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="0551d-161">Det kan också vara en sträng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatet "åååå-MM-dd" eller "åååå-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="0551d-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="0551d-162">**Kön**: man, kvinna, okänd</span><span class="sxs-lookup"><span data-stu-id="0551d-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="0551d-163">**Postnummer**: femsiffriga postnummer för oss, standard postnummer i övriga</span><span class="sxs-lookup"><span data-stu-id="0551d-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="0551d-164">**Ort**: Ortens namn på engelska</span><span class="sxs-lookup"><span data-stu-id="0551d-164">**City**: City name in English</span></span>
- <span data-ttu-id="0551d-165">**Region**: en förkortning på två bokstäver för USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="0551d-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="0551d-166">Två eller tre bokstavsförkortningar för Australien.</span><span class="sxs-lookup"><span data-stu-id="0551d-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="0551d-167">Gäller inte för Frankrike, Tyskland eller Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="0551d-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="0551d-168">**Land/region**:</span><span class="sxs-lookup"><span data-stu-id="0551d-168">**Country/Region**:</span></span>

  - <span data-ttu-id="0551d-169">USA: Amerikas förenta stater, Förenta staterna, USA, US och Amerika</span><span class="sxs-lookup"><span data-stu-id="0551d-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="0551d-170">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="0551d-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="0551d-171">GB: Förenade kungariket, Storbritannien, GB, Förenade kungariket av Storbritannien och Nordirland, Förenade kungariket av Storbritannien</span><span class="sxs-lookup"><span data-stu-id="0551d-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="0551d-172">AU: Australien, AU, Australiska statsförbundet</span><span class="sxs-lookup"><span data-stu-id="0551d-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="0551d-173">FR: Frankrike, FR, Republiken Frankrike</span><span class="sxs-lookup"><span data-stu-id="0551d-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="0551d-174">DE: Tyskland, tyska, Deutschland, Allemagne, DE, Förbundsrepubliken Tyskland</span><span class="sxs-lookup"><span data-stu-id="0551d-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="0551d-175">Granska och ge berikningen ett namn</span><span class="sxs-lookup"><span data-stu-id="0551d-175">Review and name the enrichment</span></span>

<span data-ttu-id="0551d-176">Slutligen får du granska informationen och ange ett namn för berikning.</span><span class="sxs-lookup"><span data-stu-id="0551d-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Sidan för intressegranskning och namn.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="0551d-178">Uppdatera berikning</span><span class="sxs-lookup"><span data-stu-id="0551d-178">Refresh enrichment</span></span>

<span data-ttu-id="0551d-179">Kör berikningen när du har konfigurerat varumärken, intressen och fältmappningen för demografiska mål.</span><span class="sxs-lookup"><span data-stu-id="0551d-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="0551d-180">Starta processen genom att välja **Kör** på konfigurationssidan för varumärket eller intresset.</span><span class="sxs-lookup"><span data-stu-id="0551d-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="0551d-181">Du kan även låta systemet köra anrikningen automatiskt som en del av en schemalagd uppdatering.</span><span class="sxs-lookup"><span data-stu-id="0551d-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="0551d-182">Beroende på storleken på kundens data kan det ta flera minuter innan en anrikning har slutförts.</span><span class="sxs-lookup"><span data-stu-id="0551d-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="0551d-183">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="0551d-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0551d-184">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0551d-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0551d-185">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="0551d-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0551d-186">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="0551d-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="0551d-187">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="0551d-187">Enrichment results</span></span>

<span data-ttu-id="0551d-188">När du har kört berikningsprocessen går du till **Mina berikningar** för att granska det totala antalet berikade kunder och en uppdelning av varumärken eller intressen ii de berikade kundprofilerna.</span><span class="sxs-lookup"><span data-stu-id="0551d-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Förhandsgranskning av resultatet efter att processen har körts":::

<span data-ttu-id="0551d-190">Granska utökad data genom att välja **Visa utökad data** i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="0551d-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="0551d-191">Berikad data för varumärken skickas till entiteten **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="0551d-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="0551d-192">Data för intressen finns i entiteten **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="0551d-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="0551d-193">Du hittar också de här entiteterna i gruppen **Berikande** i **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="0551d-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="0551d-194">Visa berikande data på kundkortet</span><span class="sxs-lookup"><span data-stu-id="0551d-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="0551d-195">Varumärkes- och räntetillhörigheter kan också visas på enskilda kundkort.</span><span class="sxs-lookup"><span data-stu-id="0551d-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="0551d-196">Gå till **kunder** och välj en kundprofil.</span><span class="sxs-lookup"><span data-stu-id="0551d-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="0551d-197">På kundkortet hittar du diagram för de varumärken eller intressen som personer i den kundens demografiska profil har tillhörighet för.</span><span class="sxs-lookup"><span data-stu-id="0551d-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundkort med berikad data":::

## <a name="next-steps"></a><span data-ttu-id="0551d-199">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0551d-199">Next steps</span></span>

<span data-ttu-id="0551d-200">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="0551d-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0551d-201">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="0551d-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
