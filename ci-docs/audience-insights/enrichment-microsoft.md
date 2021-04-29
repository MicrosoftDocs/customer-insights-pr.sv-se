---
title: Berika kundprofiler med data från Microsoft
description: Använd tillverkarspecifika data från Microsoft för att berika kunddata med intresse och varumärke.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896624"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="2d205-103">Utöka kundprofiler med varumärkes- och intressetillhörighet (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="2d205-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="2d205-104">Använd tillverkarspecifika data från Microsoft för att berika kunddata med intresse och varumärke.</span><span class="sxs-lookup"><span data-stu-id="2d205-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="2d205-105">Dessa intressetillhörigheter bestäms utifrån data från personer som har liknande demografiska kunder.</span><span class="sxs-lookup"><span data-stu-id="2d205-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="2d205-106">Med hjälp av den här informationen kan du bättre förstå och segmentera dina kunder utifrån deras tillhörigheter till särskilda varumärken och intressen.</span><span class="sxs-lookup"><span data-stu-id="2d205-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="2d205-107">I målgruppsinsikter går du till **Data** > **Berikning** för att [konfigurera och visa berikningar](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="2d205-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="2d205-108">Om du vill konfigurera berikning för varumärkestillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Varumärken**.</span><span class="sxs-lookup"><span data-stu-id="2d205-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="2d205-109">Om du vill konfigurera berikning av intressetillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Intressen**.</span><span class="sxs-lookup"><span data-stu-id="2d205-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d205-110">![Paneler för varumärken och intressen](media/BrandsInterest-tile-Hub.png "Paneler för varumärken och intressen")</span><span class="sxs-lookup"><span data-stu-id="2d205-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="2d205-111">Så här avgör vi intresse</span><span class="sxs-lookup"><span data-stu-id="2d205-111">How we determine affinities</span></span>

<span data-ttu-id="2d205-112">Vi använder Microsofts onlinesökningsdata för att hitta intressegrupper och intressen i olika demografiska segment (definierade efter ålder, kön eller plats).</span><span class="sxs-lookup"><span data-stu-id="2d205-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="2d205-113">Om du söker online efter ett varumärke eller en ränta bestäms hur mycket tillhörighet som ett demografiskt segment ska jämföras med andra segment, det vill säga det varumärket.</span><span class="sxs-lookup"><span data-stu-id="2d205-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="2d205-114">varumärke eller intresse.</span><span class="sxs-lookup"><span data-stu-id="2d205-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="2d205-115">Tillhörighetsnivå och poäng</span><span class="sxs-lookup"><span data-stu-id="2d205-115">Affinity level and score</span></span>

<span data-ttu-id="2d205-116">I varje berikad kundprofil tillhandahåller vi två relaterade värden – tillhörighetsnivå och tillhörighetspoäng.</span><span class="sxs-lookup"><span data-stu-id="2d205-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="2d205-117">Dessa värden hjälper dig att avgöra hur starkt tillhörigheten är för den profilens demografiska segment, för ett varumärke eller intresse, jämfört med andra demografiska segment.</span><span class="sxs-lookup"><span data-stu-id="2d205-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="2d205-118">*Tillhörighetsnivå* består av fyra nivåer och *tillhörighetspoäng* beräknas på en skala med 100 poäng som mappas till tillhörighetsnivåerna.</span><span class="sxs-lookup"><span data-stu-id="2d205-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="2d205-119">Tillhörighetsnivå</span><span class="sxs-lookup"><span data-stu-id="2d205-119">Affinity level</span></span> |<span data-ttu-id="2d205-120">Tillhörighetspoäng</span><span class="sxs-lookup"><span data-stu-id="2d205-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="2d205-121">Mycket högt</span><span class="sxs-lookup"><span data-stu-id="2d205-121">Very high</span></span>     | <span data-ttu-id="2d205-122">85–100</span><span class="sxs-lookup"><span data-stu-id="2d205-122">85-100</span></span>       |
|<span data-ttu-id="2d205-123">Högt</span><span class="sxs-lookup"><span data-stu-id="2d205-123">High</span></span>     | <span data-ttu-id="2d205-124">70–84</span><span class="sxs-lookup"><span data-stu-id="2d205-124">70-84</span></span>        |
|<span data-ttu-id="2d205-125">Medium</span><span class="sxs-lookup"><span data-stu-id="2d205-125">Medium</span></span>     | <span data-ttu-id="2d205-126">35–69</span><span class="sxs-lookup"><span data-stu-id="2d205-126">35-69</span></span>        |
|<span data-ttu-id="2d205-127">Lågt</span><span class="sxs-lookup"><span data-stu-id="2d205-127">Low</span></span>     | <span data-ttu-id="2d205-128">1–34</span><span class="sxs-lookup"><span data-stu-id="2d205-128">1-34</span></span>        |

<span data-ttu-id="2d205-129">Beroende på vilken granularitet du vill använda för att mäta tillhörigheten kan du använda antingen tillhörighetsnivå eller poäng.</span><span class="sxs-lookup"><span data-stu-id="2d205-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="2d205-130">Med tillhörighetspoäng får du mer exakt kontroll.</span><span class="sxs-lookup"><span data-stu-id="2d205-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="2d205-131">Länder/regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="2d205-131">Supported countries/regions</span></span>

<span data-ttu-id="2d205-132">Vi stöder för närvarande följande alternativ för land: Australien, Kanada (engelska), Frankrike, Tyskland, Storbritannien och USA (engelska).</span><span class="sxs-lookup"><span data-stu-id="2d205-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="2d205-133">Om du vill välja ett land öppnar du **varumärken** eller **intressen** och väljer **ändra** bredvid **land/region**.</span><span class="sxs-lookup"><span data-stu-id="2d205-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="2d205-134">I fönstret **inställningar för land/region** väljer du ett alternativ och väljer **tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="2d205-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="2d205-135">Effekter relaterade till val av land</span><span class="sxs-lookup"><span data-stu-id="2d205-135">Implications related to country selection</span></span>

- <span data-ttu-id="2d205-136">När [du väljer dina ega märken](#define-your-brands-or-interests) ger systemet förslag utifrån valt land eller vald region.</span><span class="sxs-lookup"><span data-stu-id="2d205-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="2d205-137">När [du väljer en bransch](#define-your-brands-or-interests) får du de mest relevanta märkena eller intressena utifrån valt land eller vald region.</span><span class="sxs-lookup"><span data-stu-id="2d205-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="2d205-138">När [du berikar profiler](#refresh-enrichment) berikar vi alla kundprofiler som vi får data för för de valda märkena och intressena.</span><span class="sxs-lookup"><span data-stu-id="2d205-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="2d205-139">Inklusive profiler som inte finns i det valda landet eller den valda regionen.</span><span class="sxs-lookup"><span data-stu-id="2d205-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="2d205-140">Om du till exempel valde Tyskland utökar vi profiler i USA om det finns tillgängliga data för valda tillverkare och intressen i USA.</span><span class="sxs-lookup"><span data-stu-id="2d205-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="2d205-141">Konfigurera berikning</span><span class="sxs-lookup"><span data-stu-id="2d205-141">Configure Enrichment</span></span>

<span data-ttu-id="2d205-142">En guidad upplevelse hjälper dig genom konfigurationen av berikningar.</span><span class="sxs-lookup"><span data-stu-id="2d205-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="2d205-143">Definiera dina varumärken eller intressen</span><span class="sxs-lookup"><span data-stu-id="2d205-143">Define your brands or interests</span></span>

<span data-ttu-id="2d205-144">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="2d205-144">Select one of the following options:</span></span>

- <span data-ttu-id="2d205-145">**Bransch**: Systemet identifierar de främsta varumärkena och intressena som är relevanta för din bransch, och berikar dina kunddata med dem.</span><span class="sxs-lookup"><span data-stu-id="2d205-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="2d205-146">**Välj en egen**: Välj upp till fem objekt i en lista med varumärken eller intressen som är mest relevanta för organisationen.</span><span class="sxs-lookup"><span data-stu-id="2d205-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="2d205-147">Om du vill lägga till ett varumärke eller ett intresse anger du det i inmatningsområdet för att få förslag utifrån matchande termer.</span><span class="sxs-lookup"><span data-stu-id="2d205-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="2d205-148">Om vi inte visar ett varumärke eller intresse som du letar efter kan du skicka feedback med hjälp av **föreslå** länk.</span><span class="sxs-lookup"><span data-stu-id="2d205-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="2d205-149">Granska inställningar för berikning</span><span class="sxs-lookup"><span data-stu-id="2d205-149">Review enrichment preferences</span></span>

<span data-ttu-id="2d205-150">Gå igenom standardinställningarna för berikning och uppdatera dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="2d205-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skärmbild av fönstret med inställningar för berikning.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="2d205-152">Välj en entitet att berika</span><span class="sxs-lookup"><span data-stu-id="2d205-152">Select entity to enrich</span></span>

<span data-ttu-id="2d205-153">Välj **Berikad entitet** och välj den datauppsättning du vill berika med företagsdata från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d205-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="2d205-154">Du kan välja entiteten Kund för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="2d205-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="2d205-155">Mappa dina fält</span><span class="sxs-lookup"><span data-stu-id="2d205-155">Map your fields</span></span>

<span data-ttu-id="2d205-156">Mappa fält från en enhetlig kundentitet och definiera det demografiska segment som du vill att systemet ska använda för att berika kunddata.</span><span class="sxs-lookup"><span data-stu-id="2d205-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="2d205-157">Mappa land/region och åtminstone attributen Födelsedatum eller Kön.</span><span class="sxs-lookup"><span data-stu-id="2d205-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="2d205-158">Du måste också mappa minst en av Ort (och Region) eller Postnummer.</span><span class="sxs-lookup"><span data-stu-id="2d205-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="2d205-159">Välj **redigera** om du vill definiera mappningen av fälten och välj **Tillämpa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="2d205-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="2d205-160">Välj **Spara** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="2d205-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="2d205-161">Följande format och värden stöds är värden inte skiftlägeskänsliga:</span><span class="sxs-lookup"><span data-stu-id="2d205-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="2d205-162">**Födelsedatum**: Vi rekommenderar att födelsedatumet konverteras till typen DateTime under datainmatning.</span><span class="sxs-lookup"><span data-stu-id="2d205-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="2d205-163">Det kan också vara en sträng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatet "åååå-MM-dd" eller "åååå-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="2d205-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="2d205-164">**Kön**: man, kvinna, okänd</span><span class="sxs-lookup"><span data-stu-id="2d205-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="2d205-165">**Postnummer**: femsiffriga postnummer för oss, standard postnummer i övriga</span><span class="sxs-lookup"><span data-stu-id="2d205-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="2d205-166">**Ort**: Ortens namn på engelska</span><span class="sxs-lookup"><span data-stu-id="2d205-166">**City**: City name in English</span></span>
- <span data-ttu-id="2d205-167">**Region**: en förkortning på två bokstäver för USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="2d205-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="2d205-168">Två eller tre bokstavsförkortningar för Australien.</span><span class="sxs-lookup"><span data-stu-id="2d205-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="2d205-169">Gäller inte för Frankrike, Tyskland eller Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="2d205-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="2d205-170">**Land/region**:</span><span class="sxs-lookup"><span data-stu-id="2d205-170">**Country/Region**:</span></span>

  - <span data-ttu-id="2d205-171">USA: Amerikas förenta stater, Förenta staterna, USA, US och Amerika</span><span class="sxs-lookup"><span data-stu-id="2d205-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="2d205-172">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="2d205-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="2d205-173">GB: Förenade kungariket, Storbritannien, GB, Förenade kungariket av Storbritannien och Nordirland, Förenade kungariket av Storbritannien</span><span class="sxs-lookup"><span data-stu-id="2d205-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="2d205-174">AU: Australien, AU, Australiska statsförbundet</span><span class="sxs-lookup"><span data-stu-id="2d205-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="2d205-175">FR: Frankrike, FR, Republiken Frankrike</span><span class="sxs-lookup"><span data-stu-id="2d205-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="2d205-176">DE: Tyskland, tyska, Deutschland, Allemagne, DE, Förbundsrepubliken Tyskland</span><span class="sxs-lookup"><span data-stu-id="2d205-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="2d205-177">Granska och ge berikningen ett namn</span><span class="sxs-lookup"><span data-stu-id="2d205-177">Review and name the enrichment</span></span>

<span data-ttu-id="2d205-178">Slutligen får du granska informationen och ange ett namn för berikning.</span><span class="sxs-lookup"><span data-stu-id="2d205-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Sidan för intressegranskning och namn.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="2d205-180">Uppdatera berikning</span><span class="sxs-lookup"><span data-stu-id="2d205-180">Refresh enrichment</span></span>

<span data-ttu-id="2d205-181">Kör berikningen när du har konfigurerat varumärken, intressen och fältmappningen för demografiska mål.</span><span class="sxs-lookup"><span data-stu-id="2d205-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="2d205-182">Starta processen genom att välja **Kör** på konfigurationssidan för varumärket eller intresset.</span><span class="sxs-lookup"><span data-stu-id="2d205-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="2d205-183">Du kan även låta systemet köra anrikningen automatiskt som en del av en schemalagd uppdatering.</span><span class="sxs-lookup"><span data-stu-id="2d205-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="2d205-184">Beroende på storleken på kundens data kan det ta flera minuter innan en anrikning har slutförts.</span><span class="sxs-lookup"><span data-stu-id="2d205-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="2d205-185">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="2d205-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2d205-186">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2d205-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2d205-187">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="2d205-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2d205-188">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="2d205-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2d205-189">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="2d205-189">Enrichment results</span></span>

<span data-ttu-id="2d205-190">När du har kört berikningsprocessen går du till **Mina berikningar** för att granska det totala antalet berikade kunder och en uppdelning av varumärken eller intressen ii de berikade kundprofilerna.</span><span class="sxs-lookup"><span data-stu-id="2d205-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Förhandsgranskning av resultatet efter att processen har körts":::

<span data-ttu-id="2d205-192">Granska utökad data genom att välja **Visa utökad data** i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="2d205-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="2d205-193">Berikad data för varumärken skickas till entiteten **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="2d205-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2d205-194">Data för intressen finns i entiteten **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="2d205-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2d205-195">Du hittar också de här entiteterna i gruppen **Berikande** i **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="2d205-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="2d205-196">Visa berikande data på kundkortet</span><span class="sxs-lookup"><span data-stu-id="2d205-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="2d205-197">Varumärkes- och räntetillhörigheter kan också visas på enskilda kundkort.</span><span class="sxs-lookup"><span data-stu-id="2d205-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="2d205-198">Gå till **kunder** och välj en kundprofil.</span><span class="sxs-lookup"><span data-stu-id="2d205-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="2d205-199">På kundkortet hittar du diagram för de varumärken eller intressen som personer i den kundens demografiska profil har tillhörighet för.</span><span class="sxs-lookup"><span data-stu-id="2d205-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundkort med berikad data":::

## <a name="next-steps"></a><span data-ttu-id="2d205-201">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2d205-201">Next steps</span></span>

<span data-ttu-id="2d205-202">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="2d205-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2d205-203">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="2d205-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
