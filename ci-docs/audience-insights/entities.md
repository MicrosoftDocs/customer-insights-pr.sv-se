---
title: Entiteter och datauppsättningar
description: Visa data på sidan Entiteter.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049416"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="5fa69-103">Entiteter i målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="5fa69-103">Entities in audience insights</span></span>

<span data-ttu-id="5fa69-104">När [du har konfigurerat datakällorna](data-sources.md) går du till sidan **entiteter** för att utvärdera kvaliteten hos hämtade data.</span><span class="sxs-lookup"><span data-stu-id="5fa69-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="5fa69-105">Entiteter betraktas som datauppsättningar.</span><span class="sxs-lookup"><span data-stu-id="5fa69-105">Entities are considered datasets.</span></span> <span data-ttu-id="5fa69-106">Flera funktioner i Dynamics 365 Customer Insights är byggda runt dessa entiteter.</span><span class="sxs-lookup"><span data-stu-id="5fa69-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="5fa69-107">Om du granskar dem noga kan du kontrollera hur de funktionerna ser ut.</span><span class="sxs-lookup"><span data-stu-id="5fa69-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="5fa69-108">Sidan **entiteter** visar entiteter och flera kolumner:</span><span class="sxs-lookup"><span data-stu-id="5fa69-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="5fa69-109">**Namn**: namnet på entiteten för data.</span><span class="sxs-lookup"><span data-stu-id="5fa69-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="5fa69-110">Om en varningssymbol visas bredvid ett entitetsnamn betyder det att det inte gick att läsa in data för den entiteten.</span><span class="sxs-lookup"><span data-stu-id="5fa69-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="5fa69-111">**Källa**: typen av datakälla som hämtade entiteten</span><span class="sxs-lookup"><span data-stu-id="5fa69-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="5fa69-112">**Skapades den**: Namnet på den person som skapade entiteten</span><span class="sxs-lookup"><span data-stu-id="5fa69-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="5fa69-113">**Skapad**: datum och tid då entiteten skapades</span><span class="sxs-lookup"><span data-stu-id="5fa69-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="5fa69-114">**Uppdaterad den**: Namnet på den person som uppdaterade entiteten</span><span class="sxs-lookup"><span data-stu-id="5fa69-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="5fa69-115">**Senast uppdaterad**: datum och tid för den senaste uppdateringen av entiteten</span><span class="sxs-lookup"><span data-stu-id="5fa69-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="5fa69-116">**Senast uppdaterad**: datum och tid för när data uppdaterades senast</span><span class="sxs-lookup"><span data-stu-id="5fa69-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="5fa69-117">Utforska data för en specifik entitet</span><span class="sxs-lookup"><span data-stu-id="5fa69-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="5fa69-118">Välj en entitet för att utforska de olika fält och poster som ingår i entiteten.</span><span class="sxs-lookup"><span data-stu-id="5fa69-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5fa69-119">![Välj en entitet](media/data-manager-entities-data.png "Välj en entitet")</span><span class="sxs-lookup"><span data-stu-id="5fa69-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="5fa69-120">Fliken **Data** visar en tabell med information om enskilda poster i entiteten.</span><span class="sxs-lookup"><span data-stu-id="5fa69-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5fa69-121">![Fälttabell](media/data-manager-entities-fields.PNG "Fälttabell")</span><span class="sxs-lookup"><span data-stu-id="5fa69-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="5fa69-122">Fliken **Attribut** är markerad som standard och visar en tabell för att granska information om den valda entiteten, till exempel fältnamn, datatyper och typer.</span><span class="sxs-lookup"><span data-stu-id="5fa69-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="5fa69-123">Kolumnen **Typ** visar Common Data Model associerade typer som antingen identifieras automatiskt av systemet eller som [mappas manuellt](map-entities.md) av användarna.</span><span class="sxs-lookup"><span data-stu-id="5fa69-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="5fa69-124">Dessa är semantiska typer som kan skilja sig från attributens datatyper, t.ex. fältet *E-post* nedan har datatypen *Text* men dess (semantiska) Common Data Model-typ kan vara *E-post* eller *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="5fa69-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="5fa69-125">I båda tabellerna visas endast ett exempel på entitetens data.</span><span class="sxs-lookup"><span data-stu-id="5fa69-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="5fa69-126">Om du vill visa hela datauppsättningen går du till sidan **Datakällor**, väljer en entitet och sedan **redigera** och visar sedan entitetens data med Power Query redigeraren som förklaras i [Datakällor](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5fa69-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="5fa69-127">Om du vill lära dig mer om data som tas med i entiteten kan du få en del viktiga egenskaper för informationen, t.ex. nullvärden, saknade värden, unika värden, antal och fördelningar, som kan användas för dina data i kolumnen **Sammanfattning**.</span><span class="sxs-lookup"><span data-stu-id="5fa69-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="5fa69-128">Välj diagramikonen om du vill visa en sammanfattning av data.</span><span class="sxs-lookup"><span data-stu-id="5fa69-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5fa69-129">![Sammanfattningssymbol](media/data-manager-entities-summary.png "Datasammanfattningstabell")</span><span class="sxs-lookup"><span data-stu-id="5fa69-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="5fa69-130">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5fa69-130">Next step</span></span>

<span data-ttu-id="5fa69-131">Se ämnet [Förena](data-unification.md) för att lära dig *mappa*, *matcha* och *koppling* hämtade data.</span><span class="sxs-lookup"><span data-stu-id="5fa69-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
