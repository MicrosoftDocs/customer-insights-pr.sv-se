---
title: Mappa entiteter för datasammanslutningen
description: Mappa data för att skapa enhetliga kundprofiler.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407098"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="212e5-103">Mappa entiteter och attribut</span><span class="sxs-lookup"><span data-stu-id="212e5-103">Map entities and attributes</span></span>

<span data-ttu-id="212e5-104">**Mappning** är det första steget i datasammanslutningsprocessen i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="212e5-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="212e5-105">Mappningen består av tre faser:</span><span class="sxs-lookup"><span data-stu-id="212e5-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="212e5-106">*Entitetsurval*: identifiera de entiteter som leder till en datauppsättning med mer fullständig information om kunderna.</span><span class="sxs-lookup"><span data-stu-id="212e5-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="212e5-107">*Val av attribut*: identifiera kolumnerna som du vill kombinera och stämma av i faserna *matchning* och *koppling* för varje entitet.</span><span class="sxs-lookup"><span data-stu-id="212e5-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="212e5-108">Dessa kolumner kallas *Attribut*.</span><span class="sxs-lookup"><span data-stu-id="212e5-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="212e5-109">*Primär nyckel och semantisk typ markering*: för varje entitet identifierar du ett attribut som du vill definiera som primär nyckel för den entiteten och identifierar en semantisk typ som bäst beskriver attributet.</span><span class="sxs-lookup"><span data-stu-id="212e5-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="212e5-110">Mer information om det allmänna flödet av dataförening finns i [förena](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="212e5-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="212e5-111">Välj de första entiteterna</span><span class="sxs-lookup"><span data-stu-id="212e5-111">Select the first entities</span></span>

1. <span data-ttu-id="212e5-112">I målgruppsinsikter går du till **Data** > **Slå samman** > **Mappa**.</span><span class="sxs-lookup"><span data-stu-id="212e5-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="212e5-113">Starta mappningsfasen genom att välja **Välj entiteter**.</span><span class="sxs-lookup"><span data-stu-id="212e5-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="212e5-114">Välj de entiteter och attribut du vill använda i faserna *matchning* och *koppla*.</span><span class="sxs-lookup"><span data-stu-id="212e5-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="212e5-115">Du kan välja de attribut som krävs separat från en entitet eller ta med alla attribut från en entitet genom att markera kryssrutan **Inkludera alla fält** på entitetsnivån.</span><span class="sxs-lookup"><span data-stu-id="212e5-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="212e5-116">Vi rekommenderar att du väljer minst två entiteter att dra nytta av föreningsprocessen för data.</span><span class="sxs-lookup"><span data-stu-id="212e5-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="212e5-117">![Lägg till entitetsexempel](media/data-manager-configure-map-add-entities-example.png "Lägg till entitetsexempel")</span><span class="sxs-lookup"><span data-stu-id="212e5-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="212e5-118">I det här exemplet lägger vi till entiteterna **eCommerceContacts** och **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="212e5-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="212e5-119">Genom att välja de här entiteterna kan du få insikter om vilka av de online-kunder som är medlemmar i ett förmånsprogram.</span><span class="sxs-lookup"><span data-stu-id="212e5-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="212e5-120">Du kan söka på nyckelord för alla attribut och entiteter för att välja vilka attribut som ska mappas.</span><span class="sxs-lookup"><span data-stu-id="212e5-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="212e5-121">![Exempel på sökfält](media/data-manager-configure-map-search-fields-example.png "Exempel på sökfält")</span><span class="sxs-lookup"><span data-stu-id="212e5-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="212e5-122">Välj **Bekräfta** för att bekräfta dina val.</span><span class="sxs-lookup"><span data-stu-id="212e5-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="212e5-123">Välj primär nyckel och semantisk typ för attribut</span><span class="sxs-lookup"><span data-stu-id="212e5-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="212e5-124">När du har valt entiteter **Karta** visas de valda entiteterna i översiktssidan för recensionen.</span><span class="sxs-lookup"><span data-stu-id="212e5-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="212e5-125">Definiera primär nyckeln för en entitet och identifiera semantisk typ för ett attribut i entiteten.</span><span class="sxs-lookup"><span data-stu-id="212e5-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="212e5-126">**Primärnyckel**: Markera ett attribut som primärnyckel för varje entitet.</span><span class="sxs-lookup"><span data-stu-id="212e5-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="212e5-127">För att ett attribut ska vara en giltig primär nyckel bör det inte innehålla dubblettvärden, saknade värden och null-värden.</span><span class="sxs-lookup"><span data-stu-id="212e5-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="212e5-128">Attribut av typen sträng, heltal och GUID-datatyp stöds som primära nycklar och visas i ett fält där du kan välja från.</span><span class="sxs-lookup"><span data-stu-id="212e5-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="212e5-129">**Attribut semantisk typ**: kategorier för attribut, t.ex. e-postadress eller namn.</span><span class="sxs-lookup"><span data-stu-id="212e5-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="212e5-130">Om du vill använda AI-modeller för smart prediktion av semantik, spara tid och förbättra precisionen, anger du **Intelligent mappning** till **PÅ**.</span><span class="sxs-lookup"><span data-stu-id="212e5-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="212e5-131">Intelligent mappningen visar rekommendation av AI-baserad semantik i fältet **Typ**.</span><span class="sxs-lookup"><span data-stu-id="212e5-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="212e5-132">Om du väljer **AV** ser du våra rekommendationer för regelbunden mappning.</span><span class="sxs-lookup"><span data-stu-id="212e5-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="212e5-133">Du kan välja valfri semantisk typ i listan med tillgängliga alternativ och ersätta det föreslagna urvalet.</span><span class="sxs-lookup"><span data-stu-id="212e5-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="212e5-134">![Attributtyp och semantisk prediktion](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtyp och semantisk prediktion")</span><span class="sxs-lookup"><span data-stu-id="212e5-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="212e5-135">Det går också att lägga till en anpassad entitetstyp.</span><span class="sxs-lookup"><span data-stu-id="212e5-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="212e5-136">Välj typfältet för ett attribut och ange namnet på den anpassade semantiska typen.</span><span class="sxs-lookup"><span data-stu-id="212e5-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="212e5-137">PÅ så sätt kan du också ändra vilka attributtyper som identifieras av systemet.</span><span class="sxs-lookup"><span data-stu-id="212e5-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="212e5-138">Alla attribut för vilka en semantisk typ identifieras identifieras automatiskt i avsnittet **granska mappade fält**.</span><span class="sxs-lookup"><span data-stu-id="212e5-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="212e5-139">Granska attributen och deras semantiska typer eftersom de används för att kombinera entiteterna i kopplingssteget av dataföreningen.</span><span class="sxs-lookup"><span data-stu-id="212e5-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="212e5-140">Attribut som inte mappas automatiskt till en semantisk typ grupperas i **definiera data i avsnittet omappade fält**.</span><span class="sxs-lookup"><span data-stu-id="212e5-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="212e5-141">Välj fältet semantisk typ för de omappade attributen eller ange ett eget namn för attributtypen.</span><span class="sxs-lookup"><span data-stu-id="212e5-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="212e5-142">![Primärnyckel och attributtyp](media/data-manager-configure-map-add-attributes.png "Primärnyckel och attributtyp")</span><span class="sxs-lookup"><span data-stu-id="212e5-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="212e5-143">Ett fält ska mappas till den semantiska typen Person.FullName som fyller i kundnamnet på kundkortet.</span><span class="sxs-lookup"><span data-stu-id="212e5-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="212e5-144">Annars visas inget namn på kundkorten.</span><span class="sxs-lookup"><span data-stu-id="212e5-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="212e5-145">Lägga till och ta bort attribut och entiteter</span><span class="sxs-lookup"><span data-stu-id="212e5-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="212e5-146">I **Förena** > **Karta**, välj **Redigera fält**.</span><span class="sxs-lookup"><span data-stu-id="212e5-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="212e5-147">I rutan **Redigera fält** lägger du till eller tar bort attribut och entiteter.</span><span class="sxs-lookup"><span data-stu-id="212e5-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="212e5-148">Använd sökningen eller bläddra för att hitta och välja dina attribut och enheter av intresse.</span><span class="sxs-lookup"><span data-stu-id="212e5-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="212e5-149">Du kan inte ta bort ett attribut eller en entitet om de redan har matchats.</span><span class="sxs-lookup"><span data-stu-id="212e5-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="212e5-150">![Lägg till eller ta bort attribut](media/configure-data-map-edit.png "Lägg till eller ta bort attribut")</span><span class="sxs-lookup"><span data-stu-id="212e5-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="212e5-151">Välj **tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="212e5-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="212e5-152">Lägg till bilder i profiler</span><span class="sxs-lookup"><span data-stu-id="212e5-152">Add images to profiles</span></span>

<span data-ttu-id="212e5-153">Om en entitet innehåller URL:er till allmänt tillgängliga profilbilder eller logotyper kan du lägga till dem i den enhetliga kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="212e5-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="212e5-154">Välj entiteten och leta upp det fält som innehåller URL-adressen till profilbilden.</span><span class="sxs-lookup"><span data-stu-id="212e5-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="212e5-155">I inmatningsfältet **Typ** anger du manuellt följande värde:</span><span class="sxs-lookup"><span data-stu-id="212e5-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="212e5-156">För en person: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="212e5-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="212e5-157">För en organisation: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="212e5-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="212e5-158">Fortsätt med föreningsstegen och se till att attributet som innehåller bild-URL också läggs till i steget [sammanslagning](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="212e5-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="212e5-159">Ange attribut för organisationer</span><span class="sxs-lookup"><span data-stu-id="212e5-159">Set attributes for organizations</span></span>

<span data-ttu-id="212e5-160">För organisationer (förhandsgranskning) ska attributtypen mappas till "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="212e5-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="212e5-161">![Primärnyckel och attributtyp B2B](media/configure-data-map-edit-b2b.png "Primärnyckel och attributtyp B2B")</span><span class="sxs-lookup"><span data-stu-id="212e5-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="212e5-162">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="212e5-162">Next step</span></span>

<span data-ttu-id="212e5-163">Som en del av föreningsprocessen för dat går du till sidan **matchning**.</span><span class="sxs-lookup"><span data-stu-id="212e5-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="212e5-164">Besök [**matchning**](match-entities.md) om du vill ha mer information om den här fasen.</span><span class="sxs-lookup"><span data-stu-id="212e5-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="212e5-165">Se följande videoklipp: [komma igång: skapa en enhetlig kundprofil](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="212e5-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
