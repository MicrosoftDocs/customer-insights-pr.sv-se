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
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064913"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="7819e-103">Utöka kundprofiler med varumärkes- och intressetillhörighet (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="7819e-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="7819e-104">Använd tillverkarspecifika data från Microsoft för att berika kunddata med intresse och varumärke.</span><span class="sxs-lookup"><span data-stu-id="7819e-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="7819e-105">Dessa intressetillhörigheter bestäms utifrån data från personer som har liknande demografiska kunder.</span><span class="sxs-lookup"><span data-stu-id="7819e-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="7819e-106">Med hjälp av den här informationen kan du bättre förstå och segmentera dina kunder utifrån deras tillhörigheter till särskilda varumärken och intressen.</span><span class="sxs-lookup"><span data-stu-id="7819e-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="7819e-107">I målgruppsinsikter går du till **Data** > **Berikning** för att [konfigurera och visa berikningar](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="7819e-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="7819e-108">Om du vill konfigurera berikning för varumärkestillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Varumärken**.</span><span class="sxs-lookup"><span data-stu-id="7819e-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="7819e-109">Om du vill konfigurera berikning av intressetillhörighet kan du gå till fliken **Upptäck** och välja **Berika mina data** på ikonen **Intressen**.</span><span class="sxs-lookup"><span data-stu-id="7819e-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7819e-110">![Paneler för varumärken och intressen](media/BrandsInterest-tile-Hub.png "Paneler för varumärken och intressen")</span><span class="sxs-lookup"><span data-stu-id="7819e-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="7819e-111">Så här avgör vi intresse</span><span class="sxs-lookup"><span data-stu-id="7819e-111">How we determine affinities</span></span>

<span data-ttu-id="7819e-112">Vi använder Microsofts onlinesökningsdata för att hitta intressegrupper och intressen i olika demografiska segment (definierade efter ålder, kön eller plats).</span><span class="sxs-lookup"><span data-stu-id="7819e-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="7819e-113">Om du söker online efter ett varumärke eller en ränta bestäms hur mycket tillhörighet som ett demografiskt segment ska jämföras med andra segment, det vill säga det varumärket.</span><span class="sxs-lookup"><span data-stu-id="7819e-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="7819e-114">Tillhörighetsnivå och poäng</span><span class="sxs-lookup"><span data-stu-id="7819e-114">Affinity level and score</span></span>

<span data-ttu-id="7819e-115">I varje berikad kundprofil tillhandahåller vi två relaterade värden – tillhörighetsnivå och tillhörighetspoäng.</span><span class="sxs-lookup"><span data-stu-id="7819e-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="7819e-116">Dessa värden hjälper dig att avgöra hur starkt tillhörigheten är för den profilens demografiska segment, för ett varumärke eller intresse, jämfört med andra demografiska segment.</span><span class="sxs-lookup"><span data-stu-id="7819e-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="7819e-117">*Tillhörighetsnivå* består av fyra nivåer och *tillhörighetspoäng* beräknas på en skala med 100 poäng som mappas till tillhörighetsnivåerna.</span><span class="sxs-lookup"><span data-stu-id="7819e-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="7819e-118">Tillhörighetsnivå</span><span class="sxs-lookup"><span data-stu-id="7819e-118">Affinity level</span></span> |<span data-ttu-id="7819e-119">Tillhörighetspoäng</span><span class="sxs-lookup"><span data-stu-id="7819e-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="7819e-120">Mycket högt</span><span class="sxs-lookup"><span data-stu-id="7819e-120">Very high</span></span>     | <span data-ttu-id="7819e-121">85–100</span><span class="sxs-lookup"><span data-stu-id="7819e-121">85-100</span></span>       |
|<span data-ttu-id="7819e-122">Högt</span><span class="sxs-lookup"><span data-stu-id="7819e-122">High</span></span>     | <span data-ttu-id="7819e-123">70–84</span><span class="sxs-lookup"><span data-stu-id="7819e-123">70-84</span></span>        |
|<span data-ttu-id="7819e-124">Medium</span><span class="sxs-lookup"><span data-stu-id="7819e-124">Medium</span></span>     | <span data-ttu-id="7819e-125">35–69</span><span class="sxs-lookup"><span data-stu-id="7819e-125">35-69</span></span>        |
|<span data-ttu-id="7819e-126">Lågt</span><span class="sxs-lookup"><span data-stu-id="7819e-126">Low</span></span>     | <span data-ttu-id="7819e-127">1–34</span><span class="sxs-lookup"><span data-stu-id="7819e-127">1-34</span></span>        |

<span data-ttu-id="7819e-128">Beroende på vilken granularitet du vill använda för att mäta tillhörigheten kan du använda antingen tillhörighetsnivå eller poäng.</span><span class="sxs-lookup"><span data-stu-id="7819e-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="7819e-129">Med tillhörighetspoäng får du mer exakt kontroll.</span><span class="sxs-lookup"><span data-stu-id="7819e-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="7819e-130">Länder/regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="7819e-130">Supported countries/regions</span></span>

<span data-ttu-id="7819e-131">Vi stöder för närvarande följande alternativ för land: Australien, Kanada (engelska), Frankrike, Tyskland, Storbritannien och USA (engelska).</span><span class="sxs-lookup"><span data-stu-id="7819e-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="7819e-132">Om du vill välja ett land öppnar du **varumärken** eller **intressen** och väljer **ändra** bredvid **land/region**.</span><span class="sxs-lookup"><span data-stu-id="7819e-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="7819e-133">I fönstret **inställningar för land/region** väljer du ett alternativ och väljer **tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="7819e-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="7819e-134">Effekter relaterade till val av land</span><span class="sxs-lookup"><span data-stu-id="7819e-134">Implications related to country selection</span></span>

- <span data-ttu-id="7819e-135">När [du väljer dina ega märken](#define-your-brands-or-interests) ger systemet förslag utifrån valt land eller vald region.</span><span class="sxs-lookup"><span data-stu-id="7819e-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="7819e-136">När [du väljer en bransch](#define-your-brands-or-interests) får du de mest relevanta märkena eller intressena utifrån valt land eller vald region.</span><span class="sxs-lookup"><span data-stu-id="7819e-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="7819e-137">När [du berikar profiler](#refresh-enrichment) berikar vi alla kundprofiler som vi får data för för de valda märkena och intressena.</span><span class="sxs-lookup"><span data-stu-id="7819e-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="7819e-138">Inklusive profiler som inte finns i det valda landet eller den valda regionen.</span><span class="sxs-lookup"><span data-stu-id="7819e-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="7819e-139">Om du till exempel valde Tyskland utökar vi profiler i USA om det finns tillgängliga data för valda tillverkare och intressen i USA.</span><span class="sxs-lookup"><span data-stu-id="7819e-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="7819e-140">Konfigurera berikning</span><span class="sxs-lookup"><span data-stu-id="7819e-140">Configure Enrichment</span></span>

<span data-ttu-id="7819e-141">En guidad upplevelse hjälper dig genom konfigurationen av berikningar.</span><span class="sxs-lookup"><span data-stu-id="7819e-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="7819e-142">Definiera dina varumärken eller intressen</span><span class="sxs-lookup"><span data-stu-id="7819e-142">Define your brands or interests</span></span>

<span data-ttu-id="7819e-143">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="7819e-143">Select one of the following options:</span></span>

- <span data-ttu-id="7819e-144">**Bransch**: Systemet identifierar de främsta varumärkena och intressena som är relevanta för din bransch, och berikar dina kunddata med dem.</span><span class="sxs-lookup"><span data-stu-id="7819e-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="7819e-145">**Välj en egen**: Välj upp till fem objekt i en lista med varumärken eller intressen som är mest relevanta för organisationen.</span><span class="sxs-lookup"><span data-stu-id="7819e-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="7819e-146">Om du vill lägga till ett varumärke eller ett intresse anger du det i inmatningsområdet för att få förslag utifrån matchande termer.</span><span class="sxs-lookup"><span data-stu-id="7819e-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="7819e-147">Om vi inte visar ett varumärke eller intresse som du letar efter kan du skicka feedback med hjälp av **föreslå** länk.</span><span class="sxs-lookup"><span data-stu-id="7819e-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="7819e-148">Granska inställningar för berikning</span><span class="sxs-lookup"><span data-stu-id="7819e-148">Review enrichment preferences</span></span>

<span data-ttu-id="7819e-149">Gå igenom standardinställningarna för berikning och uppdatera dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="7819e-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skärmbild av fönstret med inställningar för berikning.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="7819e-151">Välj en entitet att berika</span><span class="sxs-lookup"><span data-stu-id="7819e-151">Select entity to enrich</span></span>

<span data-ttu-id="7819e-152">Välj **Berikad entitet** och välj den datauppsättning du vill berika med företagsdata från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7819e-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="7819e-153">Du kan välja entiteten Kund för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="7819e-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="7819e-154">Mappa dina fält</span><span class="sxs-lookup"><span data-stu-id="7819e-154">Map your fields</span></span>

<span data-ttu-id="7819e-155">Mappa fält från en enhetlig kundentitet och definiera det demografiska segment som du vill att systemet ska använda för att berika kunddata.</span><span class="sxs-lookup"><span data-stu-id="7819e-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="7819e-156">Mappa land/region och åtminstone attributen Födelsedatum eller Kön.</span><span class="sxs-lookup"><span data-stu-id="7819e-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="7819e-157">Du måste också mappa minst en av Ort (och Region) eller Postnummer.</span><span class="sxs-lookup"><span data-stu-id="7819e-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="7819e-158">Välj **redigera** om du vill definiera mappningen av fälten och välj **Tillämpa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7819e-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="7819e-159">Välj **Spara** för att slutföra fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="7819e-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="7819e-160">Följande format och värden stöds är värden inte skiftlägeskänsliga:</span><span class="sxs-lookup"><span data-stu-id="7819e-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="7819e-161">**Födelsedatum**: Vi rekommenderar att födelsedatumet konverteras till typen DateTime under datainmatning.</span><span class="sxs-lookup"><span data-stu-id="7819e-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="7819e-162">Det kan också vara en sträng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatet "åååå-MM-dd" eller "åååå-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="7819e-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="7819e-163">**Kön**: man, kvinna, okänd</span><span class="sxs-lookup"><span data-stu-id="7819e-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="7819e-164">**Postnummer**: femsiffriga postnummer för oss, standard postnummer i övriga</span><span class="sxs-lookup"><span data-stu-id="7819e-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="7819e-165">**Ort**: Ortens namn på engelska</span><span class="sxs-lookup"><span data-stu-id="7819e-165">**City**: City name in English</span></span>
- <span data-ttu-id="7819e-166">**Region**: en förkortning på två bokstäver för USA och Kanada.</span><span class="sxs-lookup"><span data-stu-id="7819e-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="7819e-167">Två eller tre bokstavsförkortningar för Australien.</span><span class="sxs-lookup"><span data-stu-id="7819e-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="7819e-168">Gäller inte för Frankrike, Tyskland eller Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="7819e-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="7819e-169">**Land/region**:</span><span class="sxs-lookup"><span data-stu-id="7819e-169">**Country/Region**:</span></span>

  - <span data-ttu-id="7819e-170">USA: Amerikas förenta stater, Förenta staterna, USA, US och Amerika</span><span class="sxs-lookup"><span data-stu-id="7819e-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="7819e-171">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="7819e-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="7819e-172">GB: Förenade kungariket, Storbritannien, GB, Förenade kungariket av Storbritannien och Nordirland, Förenade kungariket av Storbritannien</span><span class="sxs-lookup"><span data-stu-id="7819e-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="7819e-173">AU: Australien, AU, Australiska statsförbundet</span><span class="sxs-lookup"><span data-stu-id="7819e-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="7819e-174">FR: Frankrike, FR, Republiken Frankrike</span><span class="sxs-lookup"><span data-stu-id="7819e-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="7819e-175">DE: Tyskland, tyska, Deutschland, Allemagne, DE, Förbundsrepubliken Tyskland</span><span class="sxs-lookup"><span data-stu-id="7819e-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="7819e-176">Granska och ge berikningen ett namn</span><span class="sxs-lookup"><span data-stu-id="7819e-176">Review and name the enrichment</span></span>

<span data-ttu-id="7819e-177">Slutligen får du granska informationen och ange ett namn för berikning.</span><span class="sxs-lookup"><span data-stu-id="7819e-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Sidan för intressegranskning och namn.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="7819e-179">Uppdatera berikning</span><span class="sxs-lookup"><span data-stu-id="7819e-179">Refresh enrichment</span></span>

<span data-ttu-id="7819e-180">Kör berikningen när du har konfigurerat varumärken, intressen och fältmappningen för demografiska mål.</span><span class="sxs-lookup"><span data-stu-id="7819e-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="7819e-181">Starta processen genom att välja **Kör** på konfigurationssidan för varumärket eller intresset.</span><span class="sxs-lookup"><span data-stu-id="7819e-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="7819e-182">Du kan även låta systemet köra anrikningen automatiskt som en del av en schemalagd uppdatering.</span><span class="sxs-lookup"><span data-stu-id="7819e-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="7819e-183">Beroende på storleken på kundens data kan det ta flera minuter innan en anrikning har slutförts.</span><span class="sxs-lookup"><span data-stu-id="7819e-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="7819e-184">Det finns [sex typer av status](system.md#status-types) för uppgifter/processer.</span><span class="sxs-lookup"><span data-stu-id="7819e-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7819e-185">Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7819e-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7819e-186">Du kan välja status för en process om du vill visa information om förloppet för hela jobbet.</span><span class="sxs-lookup"><span data-stu-id="7819e-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7819e-187">När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.</span><span class="sxs-lookup"><span data-stu-id="7819e-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="7819e-188">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="7819e-188">Enrichment results</span></span>

<span data-ttu-id="7819e-189">När du har kört berikningsprocessen går du till **Mina berikningar** för att granska det totala antalet berikade kunder och en uppdelning av varumärken eller intressen ii de berikade kundprofilerna.</span><span class="sxs-lookup"><span data-stu-id="7819e-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Förhandsgranskning av resultatet efter att processen har körts":::

<span data-ttu-id="7819e-191">Granska utökad data genom att välja **Visa utökad data** i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="7819e-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="7819e-192">Berikad data för varumärken skickas till entiteten **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="7819e-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="7819e-193">Data för intressen finns i entiteten **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="7819e-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="7819e-194">Du hittar också de här entiteterna i gruppen **Berikande** i **Data** > **Entiteter**.</span><span class="sxs-lookup"><span data-stu-id="7819e-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="7819e-195">Visa berikande data på kundkortet</span><span class="sxs-lookup"><span data-stu-id="7819e-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="7819e-196">Varumärkes- och räntetillhörigheter kan också visas på enskilda kundkort.</span><span class="sxs-lookup"><span data-stu-id="7819e-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="7819e-197">Gå till **kunder** och välj en kundprofil.</span><span class="sxs-lookup"><span data-stu-id="7819e-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="7819e-198">På kundkortet hittar du diagram för de varumärken eller intressen som personer i den kundens demografiska profil har tillhörighet för.</span><span class="sxs-lookup"><span data-stu-id="7819e-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundkort med berikad data":::

## <a name="next-steps"></a><span data-ttu-id="7819e-200">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7819e-200">Next steps</span></span>

<span data-ttu-id="7819e-201">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="7819e-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7819e-202">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="7819e-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
