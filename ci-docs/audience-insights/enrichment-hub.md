---
title: Berika enhetliga kundprofiler
description: Använd kapaciteter för att berika dina kunddata.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597717"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="abbc3-103">Berikning för kundprofiler (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="abbc3-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="abbc3-104">Använd data från källor som Microsoft och andra partners för att berika dina kunddata.</span><span class="sxs-lookup"><span data-stu-id="abbc3-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Sidan för berikningsnav":::

<span data-ttu-id="abbc3-106">I målgruppsinsikter går du till **Data** > **Berikning** för att arbeta med berikningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="abbc3-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="abbc3-107">Du måste ha behörighet för Deltagare eller Administratör för att kunna skapa eller redigera berikningar.</span><span class="sxs-lookup"><span data-stu-id="abbc3-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="abbc3-108">Mer information finns under [Behörigheter](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="abbc3-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="abbc3-109">På fliken **Identifiera** finns följande berikningar:</span><span class="sxs-lookup"><span data-stu-id="abbc3-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="abbc3-110">[Varumärken](enrichment-microsoft-graph.md) tillhandahålls av Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="abbc3-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="abbc3-111">[Intressen](enrichment-microsoft-graph.md) tillhandahålls av Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="abbc3-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="abbc3-112">[Företagsdata](enrichment-leadspace.md) tillhandahålls av Leadspace</span><span class="sxs-lookup"><span data-stu-id="abbc3-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="abbc3-113">[Demografi](enrichment-experian.md) tillhandahålls av Experian</span><span class="sxs-lookup"><span data-stu-id="abbc3-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="abbc3-114">[Platsdata](enrichment-here.md) tillhandahålls av HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="abbc3-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="abbc3-115">[Anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="abbc3-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="abbc3-116">På fliken **Mina berikningar** kan du se vilka berikningar du har konfigurerat och redigera deras egenskaper.</span><span class="sxs-lookup"><span data-stu-id="abbc3-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="abbc3-117">Hantera befintliga berikningar</span><span class="sxs-lookup"><span data-stu-id="abbc3-117">Manage existing enrichments</span></span>

<span data-ttu-id="abbc3-118">Gå till **Mina berikningar** för att se alla konfigurerade berikningar.</span><span class="sxs-lookup"><span data-stu-id="abbc3-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="abbc3-119">Varje berikning representeras som en rad som innehåller ytterligare information om berikningen.</span><span class="sxs-lookup"><span data-stu-id="abbc3-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="abbc3-120">Välj en berikning för att se de tillgängliga alternativen.</span><span class="sxs-lookup"><span data-stu-id="abbc3-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="abbc3-121">Alternativt kan du välja tre punkter (...) i ett listobjekt för att se alternativen.</span><span class="sxs-lookup"><span data-stu-id="abbc3-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativ för hantering av listan över berikningar":::

- <span data-ttu-id="abbc3-123">**Visa** detaljerad information om hur många kundprofiler som har berikats.</span><span class="sxs-lookup"><span data-stu-id="abbc3-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="abbc3-124">**Redigera** konfiguration för berikning.</span><span class="sxs-lookup"><span data-stu-id="abbc3-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="abbc3-125">**Kör** berikningen för att uppdatera kundprofiler med senaste data.</span><span class="sxs-lookup"><span data-stu-id="abbc3-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="abbc3-126">**Inaktivera** en befintlig berikning om du vill förhindra att den uppdateras automatiskt vid alla schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="abbc3-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="abbc3-127">Data från den senaste uppdateringen kommer fortfarande att vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="abbc3-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="abbc3-128">**Aktivera** en inaktiv anrikning för att starta om automatisk uppdatering vid alla schemalagda uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="abbc3-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="abbc3-129">**Ta bort** en berikning.</span><span class="sxs-lookup"><span data-stu-id="abbc3-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="abbc3-130">Du kan köra eller inaktivera flera berikningar samtidigt genom att markera dem i listan.</span><span class="sxs-lookup"><span data-stu-id="abbc3-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="abbc3-131">Visnings- och redigeringsalternativ är inte tillgängliga som massåtgärd och fungerar bara för en berikning åt gången.</span><span class="sxs-lookup"><span data-stu-id="abbc3-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]