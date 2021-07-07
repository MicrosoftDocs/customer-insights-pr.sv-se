---
title: Berika enhetliga kundprofiler
description: Använd kapaciteter för att berika dina kunddata.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305270"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="46c33-103">Berikning för kundprofiler (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="46c33-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="46c33-104">Använd data från källor som Microsoft och andra partners för att berika dina kunddata.</span><span class="sxs-lookup"><span data-stu-id="46c33-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Sidan för berikningsnav":::

<span data-ttu-id="46c33-106">I målgruppsinsikter går du till **Data** > **Berikning** för att arbeta med berikningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="46c33-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="46c33-107">Du måste ha behörighet för Deltagare eller Administratör för att kunna skapa eller redigera berikningar.</span><span class="sxs-lookup"><span data-stu-id="46c33-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="46c33-108">Mer information finns under [Behörigheter](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="46c33-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="46c33-109">På fliken **Identifiera** finns följande berikningar:</span><span class="sxs-lookup"><span data-stu-id="46c33-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="46c33-110">[Varumärken](enrichment-microsoft.md) som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="46c33-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="46c33-111">[Intressen](enrichment-microsoft.md) som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="46c33-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="46c33-112">[Förbättrade adresser](enrichment-enhanced-addresses.md) från Microsoft</span><span class="sxs-lookup"><span data-stu-id="46c33-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="46c33-113">[Företagsdata](enrichment-leadspace.md) tillhandahålls av Leadspace</span><span class="sxs-lookup"><span data-stu-id="46c33-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="46c33-114">[Demografiska uppgifter](enrichment-experian.md) tillhandahålls av Experian</span><span class="sxs-lookup"><span data-stu-id="46c33-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="46c33-115">[Platsdata](enrichment-here.md) tillhandahålls av HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="46c33-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="46c33-116">[Anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="46c33-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="46c33-117">På fliken **Mina berikningar** kan du se vilka berikningar du har konfigurerat och redigera deras egenskaper.</span><span class="sxs-lookup"><span data-stu-id="46c33-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="46c33-118">Hantera befintliga berikningar</span><span class="sxs-lookup"><span data-stu-id="46c33-118">Manage existing enrichments</span></span>

<span data-ttu-id="46c33-119">Gå till fliken **Mina berikningar** om du vill visa alla konfigurerade berikningar.</span><span class="sxs-lookup"><span data-stu-id="46c33-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="46c33-120">Varje berikning representeras som en rad som innehåller ytterligare information om berikningen.</span><span class="sxs-lookup"><span data-stu-id="46c33-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="46c33-121">Välj en berikning för att se de tillgängliga alternativen.</span><span class="sxs-lookup"><span data-stu-id="46c33-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="46c33-122">Du kan också välja ellips (...) på ett listobjekt om du vill visa alternativen.</span><span class="sxs-lookup"><span data-stu-id="46c33-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativ för hantering av listan över berikningar":::

- <span data-ttu-id="46c33-124">**Visa** detaljerad information om hur många kundprofiler som har berikats.</span><span class="sxs-lookup"><span data-stu-id="46c33-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="46c33-125">**Redigera** konfiguration för berikning.</span><span class="sxs-lookup"><span data-stu-id="46c33-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="46c33-126">**Kör** berikningen för att uppdatera kundprofiler med senaste data.</span><span class="sxs-lookup"><span data-stu-id="46c33-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="46c33-127">**Inaktivera** en befintlig berikning om du vill förhindra att den uppdateras automatiskt vid alla schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="46c33-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="46c33-128">Data från den senaste uppdateringen kommer fortfarande att vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="46c33-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="46c33-129">**Aktivera** en inaktiv anrikning för att starta om automatisk uppdatering vid alla schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="46c33-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="46c33-130">**Ta bort** en berikning.</span><span class="sxs-lookup"><span data-stu-id="46c33-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="46c33-131">Du kan köra eller inaktivera flera berikningar samtidigt genom att markera dem i listan.</span><span class="sxs-lookup"><span data-stu-id="46c33-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="46c33-132">Visnings- och redigeringsalternativ är inte tillgängliga som massåtgärd och fungerar bara för en berikning åt gången.</span><span class="sxs-lookup"><span data-stu-id="46c33-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="46c33-133">Berikningar och anslutningar</span><span class="sxs-lookup"><span data-stu-id="46c33-133">Enrichments and connections</span></span>

<span data-ttu-id="46c33-134">Tredjepartsutslag konfigureras med hjälp av [anslutningar](connections.md), som en administratör konfigurerar med autentiseringsuppgifter och ger sitt godkännande för informationsöverföring.</span><span class="sxs-lookup"><span data-stu-id="46c33-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="46c33-135">Anslutningen kan användas av administratörer och bidragsgivare för att konfigurera berikningar.</span><span class="sxs-lookup"><span data-stu-id="46c33-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="46c33-136">Flera berikningar av samma typ</span><span class="sxs-lookup"><span data-stu-id="46c33-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="46c33-137">Entiteten som ska utökas anges under konfiguration för berikning, vilket gör att du endast kan utöka en delmängd av dina profiler.</span><span class="sxs-lookup"><span data-stu-id="46c33-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="46c33-138">Berika till exempel endast data för ett visst segment.</span><span class="sxs-lookup"><span data-stu-id="46c33-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="46c33-139">Du kan konfigurera flera anrop av samma typ och återanvända samma anslutning.</span><span class="sxs-lookup"><span data-stu-id="46c33-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="46c33-140">För vissa berikningar begränsas antalet berikningar av samma typ som kan skapas.</span><span class="sxs-lookup"><span data-stu-id="46c33-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="46c33-141">Begränsningarna och den aktuella användningen visas på sidan **Berikningar**.</span><span class="sxs-lookup"><span data-stu-id="46c33-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
