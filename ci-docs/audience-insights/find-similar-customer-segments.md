---
title: Sök efter liknande kunder med AI
description: Hitta liknande kundsegment med artificiell intelligens.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596797"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="a78c4-103">Liknande kunder (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="a78c4-103">Similar Customers (preview)</span></span>

<span data-ttu-id="a78c4-104">Med den här funktionen kan du söka efter liknande kunder i kundbasen med hjälp av artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="a78c4-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="a78c4-105">Du måste ha minst ett segment skapat för att kunna använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a78c4-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="a78c4-106">Om du utvidgar villkoren för ett befintligt segment kan du hitta kunder som liknar det segmentet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="a78c4-107">*Söka efter liknande kunder* använder automatiska metoder för att utvärdera data och göra förutsägelser baserade på dessa data och har därför möjlighet att använda som en metod för profilering, eftersom den termen definieras av allmän dataskyddsförordning ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="a78c4-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="a78c4-108">Kundens användning av den här funktionen för att bearbeta data kan vara föremål för GDPR eller andra lagar eller förordningar.</span><span class="sxs-lookup"><span data-stu-id="a78c4-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="a78c4-109">Du ansvarar för att din användning av Dynamics 365 Customer Insights, inklusive förutsägelser, följer alla tillämpliga lagar och förordningar, inklusive lagar som rör sekretess, personuppgifter, biometriska data, dataskydd och sekretess för kommunikation.</span><span class="sxs-lookup"><span data-stu-id="a78c4-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="a78c4-110">Hitta liknande kunder</span><span class="sxs-lookup"><span data-stu-id="a78c4-110">Finding similar customers</span></span>

1. <span data-ttu-id="a78c4-111">I målgruppsinsikter går du till **Segment** och väljer det segment som du vill basera ditt nya segment på.</span><span class="sxs-lookup"><span data-stu-id="a78c4-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="a78c4-112">Det är ditt *källsegment*.</span><span class="sxs-lookup"><span data-stu-id="a78c4-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="a78c4-113">Välj **Sök efter liknande kunder** i åtgärdsfältet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="a78c4-114">Granska det föreslagna namnet för det nya segmentet och ändra det vid behov.</span><span class="sxs-lookup"><span data-stu-id="a78c4-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="a78c4-115">Granska fälten som definierar det nya segmentet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="a78c4-116">Dessa fält definierar grunden för hur systemet ska försöka hitta liknande kunder i källsegmentet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="a78c4-117">Rekommenderade fält väljs som standard i systemet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="a78c4-118">Fält som avsevärt kan minska modellens prestanda utesluts automatiskt:</span><span class="sxs-lookup"><span data-stu-id="a78c4-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="a78c4-119">Fält med följande datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="a78c4-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="a78c4-120">Fält med en kardinalitet (antalet element i ett fält) som understiger 2 eller mer än 30</span><span class="sxs-lookup"><span data-stu-id="a78c4-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="a78c4-121">Välj om du vill ta med **Alla kunder** eller endast kunder i ett **specifikt befintligt segment** i det nya segmentet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="a78c4-122">Exkludera kunder i källsegmentet genom att markera kryssrutan **exkludera alla i källsegment**.</span><span class="sxs-lookup"><span data-stu-id="a78c4-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="a78c4-123">Som standard föreslår systemet även 20 % av målpublik storlek i resultatet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="a78c4-124">Redigera tröskelvärdet efter behov.</span><span class="sxs-lookup"><span data-stu-id="a78c4-124">Edit this threshold as needed.</span></span> <span data-ttu-id="a78c4-125">Om du ökar tröskelvärdet minskas precisionen.</span><span class="sxs-lookup"><span data-stu-id="a78c4-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="a78c4-126">Klicka på **kör** längst ned på sidan om du vill starta en binär klassificeringsaktivitet (en metod för maskininlärning) som analyserar datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="a78c4-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="a78c4-127">Visa liknande segment</span><span class="sxs-lookup"><span data-stu-id="a78c4-127">View the similar segment</span></span>

<span data-ttu-id="a78c4-128">När du har bearbetat liknande segment hittar du det nya segmentet på sidan **segment**.</span><span class="sxs-lookup"><span data-stu-id="a78c4-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a78c4-129">![Liknande kundsegment](media/expanded-segment.png "Liknande kundsegment")</span><span class="sxs-lookup"><span data-stu-id="a78c4-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="a78c4-130">Välj **Visa** i åtgärdsfältet för att öppna segmentdetaljen.</span><span class="sxs-lookup"><span data-stu-id="a78c4-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="a78c4-131">Den här vyn innehåller information om resultatfördelningen mellan olika [likhetsresultat](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="a78c4-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="a78c4-132">Du hittar också liknande poängvärden i **Förhandsversion av segmentmedlemmar**.</span><span class="sxs-lookup"><span data-stu-id="a78c4-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="a78c4-133">Använda utdata från ett liknande segment</span><span class="sxs-lookup"><span data-stu-id="a78c4-133">Use the output of a similar segment</span></span>

<span data-ttu-id="a78c4-134">Du kan [arbeta med resultatet av samma segment](segments.md) som med andra segment.</span><span class="sxs-lookup"><span data-stu-id="a78c4-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="a78c4-135">Du kan till exempel exportera segmentet eller bygga ett mått.</span><span class="sxs-lookup"><span data-stu-id="a78c4-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="a78c4-136">Uppdatera och redigera liknande segment</span><span class="sxs-lookup"><span data-stu-id="a78c4-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="a78c4-137">Om du vill uppdatera ett liknande segment markerar du det på sidan **Segment** och välj **Uppdatera** i åtgärdsfältet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="a78c4-138">Om du redigerar ett liknande segment bearbetas dina data på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="a78c4-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="a78c4-139">Det segment som skapades tidigare uppdateras med uppdaterade data.</span><span class="sxs-lookup"><span data-stu-id="a78c4-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="a78c4-140">Om du vill redigera ett liknande segment markerar du det på sidan **Segment** och välj **redigera** i åtgärdsfältet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="a78c4-141">Tillämpa ändringarna och välj **kör** för att starta bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="a78c4-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="a78c4-142">Ta bort ett liknande segment</span><span class="sxs-lookup"><span data-stu-id="a78c4-142">Delete a similar segment</span></span>

<span data-ttu-id="a78c4-143">Välj segment på sidan **Segment** och välj **Ta bort** i åtgärdsfältet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="a78c4-144">Bekräfta sedan borttagningen.</span><span class="sxs-lookup"><span data-stu-id="a78c4-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="a78c4-145">Om likhetspoäng</span><span class="sxs-lookup"><span data-stu-id="a78c4-145">About similarity scores</span></span>

<span data-ttu-id="a78c4-146">Den binära klassificering maskininlärningsmodellen tilldelar en poäng till kunder i det liknande segmentet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="a78c4-147">Poängen baseras på likheten med kunder i källsegmentet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="a78c4-148">Likhetspoäng under 0,55 är kunderna systemet klassificerat som *inte liknande* till kunderna i källsegmentet</span><span class="sxs-lookup"><span data-stu-id="a78c4-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="a78c4-149">Likhetsresultat mellan 0,55 – 0,7 klassificeras som *något liknande*</span><span class="sxs-lookup"><span data-stu-id="a78c4-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="a78c4-150">Likhetsresultat mellan 0,7 – 0,85 klassificeras som *liknande*</span><span class="sxs-lookup"><span data-stu-id="a78c4-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="a78c4-151">Likhetsresultat mellan 0,85 – 1 är kunder systemet klassificerat lika *mycket likt*</span><span class="sxs-lookup"><span data-stu-id="a78c4-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="a78c4-152">Kunder med likhetspoäng under 0,4 ingår inte i modellens utdata.</span><span class="sxs-lookup"><span data-stu-id="a78c4-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="a78c4-153">Systemet anser inte att det är lika tillräckligt för källsegmentet.</span><span class="sxs-lookup"><span data-stu-id="a78c4-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]