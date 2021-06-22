---
title: Relationer mellan entiteter och entiteters sökvägar
description: Skapa och hantera relationer mellan entiteter från flera datakällor.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171186"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="c6553-103">Relationer mellan entiteter</span><span class="sxs-lookup"><span data-stu-id="c6553-103">Relationships between entities</span></span>

<span data-ttu-id="c6553-104">Relationer ansluter entiteter och definierar ett diagram över dina data när entiteter delar en gemensam identifierare, en utländsk nyckel.</span><span class="sxs-lookup"><span data-stu-id="c6553-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="c6553-105">Den här utländska nyckeln kan refereras från en entitet till en annan.</span><span class="sxs-lookup"><span data-stu-id="c6553-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="c6553-106">Med anslutna entiteter kan du definiera segment och mått baserat på flera datakällor.</span><span class="sxs-lookup"><span data-stu-id="c6553-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="c6553-107">Det finns tre typer av relationer:</span><span class="sxs-lookup"><span data-stu-id="c6553-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="c6553-108">Icke-redigerbara systemrelationer, skapat av systemet som en del av datasammansättningsprocessen</span><span class="sxs-lookup"><span data-stu-id="c6553-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="c6553-109">Icke-redigerbara relationer, som skapas automatiskt från att mata in datakällor</span><span class="sxs-lookup"><span data-stu-id="c6553-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="c6553-110">Redigerbara anpassade relationer, skapad och konfigurerad av användare</span><span class="sxs-lookup"><span data-stu-id="c6553-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="c6553-111">Icke-redigerbara systemrelationer</span><span class="sxs-lookup"><span data-stu-id="c6553-111">Non-editable system relationships</span></span>

<span data-ttu-id="c6553-112">Under dataenandet skapas systemrelationer automatiskt baserat på intelligent matchning.</span><span class="sxs-lookup"><span data-stu-id="c6553-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="c6553-113">Med hjälp av dessa relationer kan kundprofilposterna relateras till motsvarande entiteter.</span><span class="sxs-lookup"><span data-stu-id="c6553-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="c6553-114">Följande diagram illustrerar skapandet av tre systembaserade relationer.</span><span class="sxs-lookup"><span data-stu-id="c6553-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="c6553-115">Kundentiteten matchas med andra entiteter för att producera den enhetliga *kundentiteten*.</span><span class="sxs-lookup"><span data-stu-id="c6553-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram med relationsvägar för kundentiteten med tre 1-n-relationer.":::

- <span data-ttu-id="c6553-117">\***CustomerToContact\*-relation** skapades mellan entiteten *Kund* och entiteten *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="c6553-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="c6553-118">Entiteten *Kund* får nyckelfältet **Contact_contactID** att relatera till entiteten *Kontakt* s nyckelfält **contactID**.</span><span class="sxs-lookup"><span data-stu-id="c6553-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="c6553-119">\***CustomerToAccount\*-relation** skapades mellan entiteten *Kund* och entiteten *Konto*.</span><span class="sxs-lookup"><span data-stu-id="c6553-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="c6553-120">Entiteten *Kund* hämtar nyckelfält **Account_accountID** som relaterar till entiteten *Konto* s nyckelfält **accountID**.</span><span class="sxs-lookup"><span data-stu-id="c6553-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="c6553-121">\***CustomerToWebAccount\*-relation** skapades mellan entiteten *Kund* och entiteten *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="c6553-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="c6553-122">Entiteten *Kund* hämtar nyckelfältet **WebAccount_webaccountID** för att relatera till entiteten *WebAccount* s nyckelfält **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="c6553-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="c6553-123">Icke-redigerbara ärvda relationer</span><span class="sxs-lookup"><span data-stu-id="c6553-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="c6553-124">Under datainmatningsprocessen kontrollerar systemet datakällor för befintliga relationer.</span><span class="sxs-lookup"><span data-stu-id="c6553-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="c6553-125">Om det inte finns någon relation skapas de automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c6553-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="c6553-126">Dessa relationer används också i nedströmsprocesser.</span><span class="sxs-lookup"><span data-stu-id="c6553-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="c6553-127">Skapa en anpassad relation</span><span class="sxs-lookup"><span data-stu-id="c6553-127">Create a custom relationship</span></span>

<span data-ttu-id="c6553-128">Relationen består av en *källentitet* som innehåller den utländska nyckeln och en *målentitet* som källentitetens utländska nyckel pekar mot.</span><span class="sxs-lookup"><span data-stu-id="c6553-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="c6553-129">I målgruppsinsikter går du till **Data** > **Relationer**.</span><span class="sxs-lookup"><span data-stu-id="c6553-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c6553-130">Välj **Ny relation**.</span><span class="sxs-lookup"><span data-stu-id="c6553-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="c6553-131">I fönstret **Ny relation** anger du följande information:</span><span class="sxs-lookup"><span data-stu-id="c6553-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Nytt relationsfönster med tomma inmatningsfält.":::

   - <span data-ttu-id="c6553-133">**Relationsnamn**: Namn som återspeglar relationens syfte.</span><span class="sxs-lookup"><span data-stu-id="c6553-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="c6553-134">Exempel: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="c6553-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="c6553-135">**Beskrivning**: Beskrivning av relationsrollen.</span><span class="sxs-lookup"><span data-stu-id="c6553-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="c6553-136">**Källentitet**: Entitet som används som källa i relationen.</span><span class="sxs-lookup"><span data-stu-id="c6553-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="c6553-137">Exempel: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="c6553-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="c6553-138">**Målentitet**: Entitet som används som mål i relationen.</span><span class="sxs-lookup"><span data-stu-id="c6553-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="c6553-139">Exempel: Kund.</span><span class="sxs-lookup"><span data-stu-id="c6553-139">Example: Customer.</span></span>
   - <span data-ttu-id="c6553-140">**Källkardinalitet**: Ange källentitetens kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="c6553-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="c6553-141">Kardinalitet beskriver antalet möjliga element i en uppsättning.</span><span class="sxs-lookup"><span data-stu-id="c6553-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="c6553-142">Det har alltid att göra med målkardinaliteten.</span><span class="sxs-lookup"><span data-stu-id="c6553-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="c6553-143">Du kan välja mellan **En** och **Många**.</span><span class="sxs-lookup"><span data-stu-id="c6553-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="c6553-144">Det går bara att använda många till en-relationer och en till en-relationer.</span><span class="sxs-lookup"><span data-stu-id="c6553-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="c6553-145">Många till en: Flera källposter kan relatera till en målpost.</span><span class="sxs-lookup"><span data-stu-id="c6553-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="c6553-146">Exempel: Flera supportärenden från en enskild kund.</span><span class="sxs-lookup"><span data-stu-id="c6553-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="c6553-147">En-till-en: En enda källpost relaterar till en målpost.</span><span class="sxs-lookup"><span data-stu-id="c6553-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="c6553-148">Exempel: Ett lojalitets-ID för en enskild kund.</span><span class="sxs-lookup"><span data-stu-id="c6553-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c6553-149">Många till många-relationer kan skapas med två många-till-en-relationer och en länkande entitet, som förbinder källentiteten och målentiteten.</span><span class="sxs-lookup"><span data-stu-id="c6553-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="c6553-150">**Målets kardinalitet**: Välj kardinalitet för målentitetsposterna.</span><span class="sxs-lookup"><span data-stu-id="c6553-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="c6553-151">**Källnyckelfält**: Fältet för främmande nyckel i källentiteten.</span><span class="sxs-lookup"><span data-stu-id="c6553-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="c6553-152">Exempel: SupportCase kan använda CaseID som ett fält med främmande nyckel.</span><span class="sxs-lookup"><span data-stu-id="c6553-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="c6553-153">**Fältet Målnyckel**: nyckelfältet för målentiteten.</span><span class="sxs-lookup"><span data-stu-id="c6553-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="c6553-154">Exempel: Kund kan använda nyckelfältet **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="c6553-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="c6553-155">Välj **Spara** för att skapa den anpassade relationen.</span><span class="sxs-lookup"><span data-stu-id="c6553-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="c6553-156">Visa relationer</span><span class="sxs-lookup"><span data-stu-id="c6553-156">View relationships</span></span>

<span data-ttu-id="c6553-157">På Relationer-sidan visas alla relationer som har skapats.</span><span class="sxs-lookup"><span data-stu-id="c6553-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="c6553-158">Varje rad representerar en relation, som också innehåller information om källentiteten, målentiteten och kardinaliteten.</span><span class="sxs-lookup"><span data-stu-id="c6553-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista över relationer och alternativ i åtgärdsfältet på Relationer-sidan.":::

<span data-ttu-id="c6553-160">Den här sidan innehåller en uppsättning alternativ för befintliga och nya relationer:</span><span class="sxs-lookup"><span data-stu-id="c6553-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="c6553-161">**Ny relation**: [Skapa en anpassad relation](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="c6553-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="c6553-162">**Visualiserare**: [Utforska relationsvisualiseraren](#explore-the-relationship-visualizer) för att se ett nätverksdiagram över befintliga relationer och deras kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="c6553-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="c6553-163">**Filtrera efter**: Välj vilken typ av relationer som ska visas i listan.</span><span class="sxs-lookup"><span data-stu-id="c6553-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="c6553-164">**Sök relationer**: Använd en textbaserad sökning efter egenskaper för relationer.</span><span class="sxs-lookup"><span data-stu-id="c6553-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="c6553-165">Utforska relationsvisualiseraren</span><span class="sxs-lookup"><span data-stu-id="c6553-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="c6553-166">Relationsvisualiseraren visar ett nätverksdiagram över befintliga relationer mellan anslutna entiteter och deras kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="c6553-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="c6553-167">Om du vill anpassa vyn kan du ändra rutornas placering genom att dra dem på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="c6553-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skärmbild av relationsvisualiseringsnätverksdiagrammet med anslutningar mellan relaterade entiteter.":::

<span data-ttu-id="c6553-169">Tillgängliga alternativ:</span><span class="sxs-lookup"><span data-stu-id="c6553-169">Available options:</span></span> 
- <span data-ttu-id="c6553-170">**Exportera som bild**: Spara den aktuella vyn som en bildfil.</span><span class="sxs-lookup"><span data-stu-id="c6553-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="c6553-171">**Ändra till vågrät/lodrät layout**: Ändra justeringen för entiteterna och relationer.</span><span class="sxs-lookup"><span data-stu-id="c6553-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="c6553-172">**Redigera**: Uppdatera egenskaper för anpassade relationer i redigeringsfönstret och spara ändringar.</span><span class="sxs-lookup"><span data-stu-id="c6553-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="c6553-173">Hantera befintliga relationer</span><span class="sxs-lookup"><span data-stu-id="c6553-173">Manage existing relationships</span></span> 

<span data-ttu-id="c6553-174">På sidan Relationer representeras varje relation av en rad.</span><span class="sxs-lookup"><span data-stu-id="c6553-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="c6553-175">Välj en relation och välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="c6553-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="c6553-176">**Redigera**: Uppdatera egenskaper för anpassade relationer i redigeringsfönstret och spara ändringar.</span><span class="sxs-lookup"><span data-stu-id="c6553-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="c6553-177">**Ta bort**: Ta bort anpassade relationer.</span><span class="sxs-lookup"><span data-stu-id="c6553-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="c6553-178">**Visa**: Visa systemskapade och ärvda relationer.</span><span class="sxs-lookup"><span data-stu-id="c6553-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="c6553-179">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c6553-179">Next step</span></span>

<span data-ttu-id="c6553-180">System och anpassade relationer används för att [skapa segment](segments.md) utifrån flera datakällor som inte längre är silor.</span><span class="sxs-lookup"><span data-stu-id="c6553-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
