---
title: Relationer mellan entiteter och entiteters sökvägar
description: Skapa och hantera relationer mellan entiteter från flera datakällor.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595234"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="96674-103">Relationer mellan entiteter</span><span class="sxs-lookup"><span data-stu-id="96674-103">Relationships between entities</span></span>

<span data-ttu-id="96674-104">Relationer hjälper dig att ansluta entiteter och skapa ett diagram över dina data när entiteter delar en gemensam identifierare (sekundär nyckel) som kan refereras från en entitet till en annan.</span><span class="sxs-lookup"><span data-stu-id="96674-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="96674-105">Med anslutna entiteter kan du definiera segment och mått baserat på flera datakällor.</span><span class="sxs-lookup"><span data-stu-id="96674-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="96674-106">Det finns två typer av relationer.</span><span class="sxs-lookup"><span data-stu-id="96674-106">There are two types of relationships.</span></span> <span data-ttu-id="96674-107">Systemrelationer som inte kan redigeras, som skapas automatiskt och anpassade relationer skapas och konfigureras av användare.</span><span class="sxs-lookup"><span data-stu-id="96674-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="96674-108">Under matchnings- och sammanslagningsprocesserna skapas systemrelationer i bakgrunden, baserat på intelligent matchning.</span><span class="sxs-lookup"><span data-stu-id="96674-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="96674-109">Med hjälp av dessa relationer kan kund profilposterna relateras till andra motsvarande entiteter.</span><span class="sxs-lookup"><span data-stu-id="96674-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="96674-110">Följande diagram illustrerar skapandet av tre systemrelationer när entiteten kund matchas med ytterligare entiteter för att producera den slutliga entiteten för kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="96674-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96674-111">![Skapar relation](media/relationships-entities-merge.png "Skapar relation")</span><span class="sxs-lookup"><span data-stu-id="96674-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="96674-112">***CustomerToContact* relationen** skapades mellan entiteten kund och entiteten kontakt.</span><span class="sxs-lookup"><span data-stu-id="96674-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="96674-113">Entiteten Kund hämtar nyckelfält **Contact_contactId** som relaterar till nyckelfältet kontaktentitet **contactId**.</span><span class="sxs-lookup"><span data-stu-id="96674-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="96674-114">***CustomerToAccount* relationen** skapades mellan entiteten kund och entiteten konto.</span><span class="sxs-lookup"><span data-stu-id="96674-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="96674-115">Entiteten Kund hämtar nyckelfält **Account_accountId** som relaterar till nyckelfältet kontoentitet **accountId**.</span><span class="sxs-lookup"><span data-stu-id="96674-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="96674-116">***CustomerToWebAccount* relationen** skapades mellan entiteten kund och entiteten WebAccount.</span><span class="sxs-lookup"><span data-stu-id="96674-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="96674-117">Entiteten Kund hämtar nyckelfält **WebAccount_webaccountId** som relaterar till nyckelfältet WebAccount-entitet **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="96674-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="96674-118">Skapa en relation</span><span class="sxs-lookup"><span data-stu-id="96674-118">Create a relationship</span></span>

<span data-ttu-id="96674-119">Definiera anpassade relationer på sidan **Relationer**.</span><span class="sxs-lookup"><span data-stu-id="96674-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="96674-120">Varje relation består av en källentitet (entiteten som innehåller sekundär nyckeln) och en målentitet (den entitet som källentitetens externa nyckel refererar till).</span><span class="sxs-lookup"><span data-stu-id="96674-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="96674-121">I målgruppsinsikter går du till **Data** > **Relationer**.</span><span class="sxs-lookup"><span data-stu-id="96674-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="96674-122">Välj **Ny relation**.</span><span class="sxs-lookup"><span data-stu-id="96674-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="96674-123">I fönstret **Lägg till relationer** anger du följande information:</span><span class="sxs-lookup"><span data-stu-id="96674-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96674-124">![Ange relationsdetaljer](media/relationships-add.png "Ange relationsdetaljer")</span><span class="sxs-lookup"><span data-stu-id="96674-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="96674-125">**Relationsnamn**: namn som återspeglar syftet med relationen (t.ex. **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="96674-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="96674-126">**Beskrivning**: Beskrivning av relationsrollen.</span><span class="sxs-lookup"><span data-stu-id="96674-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="96674-127">**Källentiteten**: Välj den entitet som används som källa i relationen (t.ex. WebLog).</span><span class="sxs-lookup"><span data-stu-id="96674-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="96674-128">**Kardinalitet**: Välj kardinalitet för källentitetsposterna.</span><span class="sxs-lookup"><span data-stu-id="96674-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="96674-129">Exempelvis betyder "många" att flera bloggposter är relaterade till ett enda WebAccount.</span><span class="sxs-lookup"><span data-stu-id="96674-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="96674-130">**Fältet Källnyckel**: Detta representerar det externa nyckel fältet källentiteten.</span><span class="sxs-lookup"><span data-stu-id="96674-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="96674-131">Till exempel WebLog har **accountId** externa nyckelfältet.</span><span class="sxs-lookup"><span data-stu-id="96674-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="96674-132">**Målentiteten**: Välj den entitet som används som mål i relationen (t.ex. WebAccount).</span><span class="sxs-lookup"><span data-stu-id="96674-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="96674-133">**Målets kardinalitet**: Välj kardinalitet för målentitetsposterna.</span><span class="sxs-lookup"><span data-stu-id="96674-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="96674-134">Exempelvis betyder "en" att flera bloggposter är relaterade till ett enda WebAccount.</span><span class="sxs-lookup"><span data-stu-id="96674-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="96674-135">**Fältet Målnyckel**: det här fältet representerar nyckelfältet för målentiteten.</span><span class="sxs-lookup"><span data-stu-id="96674-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="96674-136">Till exempel WebAccount har **accountId** nyckelfältet.</span><span class="sxs-lookup"><span data-stu-id="96674-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="96674-137">Det går bara att använda många till en-relationer och en till en-relationer.</span><span class="sxs-lookup"><span data-stu-id="96674-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="96674-138">Många till många-relationer kan skapas med två många till en-relationer och en länkentitet (en entitet som används för att ansluta källentiteten och målentiteten).</span><span class="sxs-lookup"><span data-stu-id="96674-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="96674-139">Ta bort en relation</span><span class="sxs-lookup"><span data-stu-id="96674-139">Delete a relationship</span></span>

1. <span data-ttu-id="96674-140">I målgruppsinsikter går du till **Data** > **Relationer**.</span><span class="sxs-lookup"><span data-stu-id="96674-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="96674-141">Markera kryssrutan för de relationer du väljer att radera.</span><span class="sxs-lookup"><span data-stu-id="96674-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="96674-142">Välj **Radera** längst upp i tabellen **Relationer**.</span><span class="sxs-lookup"><span data-stu-id="96674-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="96674-143">Bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="96674-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="96674-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="96674-144">Next step</span></span>

<span data-ttu-id="96674-145">System och anpassade relationer används för att skapa segment utifrån flera datakällor som inte längre är silor.</span><span class="sxs-lookup"><span data-stu-id="96674-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="96674-146">Mer information finns [Segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="96674-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]