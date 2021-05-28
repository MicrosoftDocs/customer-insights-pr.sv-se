---
title: Föreslagna segment baserade på aktivitet.
description: Låt maskininlärning hjälpa dig att hitta nya segment som bygger på kundaktiviteter.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034119"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="dd445-103">Föreslagna segment baserade på aktivitetsdata (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="dd445-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="dd445-104">Upptäck kundsegment som är intressanta och baserade på kundaktivitetsdata som är baserade på Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dd445-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="dd445-105">Exempel på aktivitetsdata är transaktioner, varaktighet för supportsamtal, köp eller returer.</span><span class="sxs-lookup"><span data-stu-id="dd445-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="dd445-106">Om du vill föreslå segment analyseras aktivitetsdata efter recency, frekvens och monetärt värde (eller varaktighet).</span><span class="sxs-lookup"><span data-stu-id="dd445-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="dd445-107">Du kan också skapa [segment som föreslås för att förbättra ett mått eller förstå vad som påverkar ett attribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="dd445-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fliken Förslag på segment visar segmentförslag för aktivitetsbaserade och attributbaserade segment.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="dd445-109">Kategorisera kunder efter aktivitet</span><span class="sxs-lookup"><span data-stu-id="dd445-109">Categorize customers by activity</span></span>

<span data-ttu-id="dd445-110">Med [aktivitetsdata](activities.md) som är tillgängliga i Customer Insights kan vi generera förslag som representerar kundgrupper:</span><span class="sxs-lookup"><span data-stu-id="dd445-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="dd445-111">mes aktiva kunderna</span><span class="sxs-lookup"><span data-stu-id="dd445-111">most active customers</span></span> 
- <span data-ttu-id="dd445-112">kunder som har gjort flest inköp</span><span class="sxs-lookup"><span data-stu-id="dd445-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="dd445-113">kunder som genererat mest omsättning</span><span class="sxs-lookup"><span data-stu-id="dd445-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="dd445-114">kunder som inte har varit aktiva på sistone</span><span class="sxs-lookup"><span data-stu-id="dd445-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="dd445-115">kunder som ofta interagerar med ditt företag</span><span class="sxs-lookup"><span data-stu-id="dd445-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="dd445-116">Om du har ett återförsäljningsföretag kan du ta reda på vilka kunder som genererar mest intäkter och ge dem en rabatt.</span><span class="sxs-lookup"><span data-stu-id="dd445-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="dd445-117">Du kan även identifiera enstaka kunder och erbjuda dem att gå med i ett program för att besöka din verksamhet oftare.</span><span class="sxs-lookup"><span data-stu-id="dd445-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="dd445-118">Om du är i hälso- och sjukvårdsbranschen och erbjuder offentlig hälso- och sjukvård och ditt mål är att minimera utgifter för enskilda utgifter.</span><span class="sxs-lookup"><span data-stu-id="dd445-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="dd445-119">Ett sätt att göra detta kan vara att minska antalet återkommande besök genom att erbjuda bästa möjliga vård i så få besök som möjligt.</span><span class="sxs-lookup"><span data-stu-id="dd445-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="dd445-120">I det här fallet är målet att hålla besöksfrekvensen låg och minimera återkommande kostnader för besöket.</span><span class="sxs-lookup"><span data-stu-id="dd445-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="dd445-121">Du kan också identifiera grupper med personer som ofta har avtalade tider och stora återkommande kostnader, och analysera dessa ärenden för att förbättra den enskildes behov.</span><span class="sxs-lookup"><span data-stu-id="dd445-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="dd445-122">Obligatoriska data</span><span class="sxs-lookup"><span data-stu-id="dd445-122">Required data</span></span>

<span data-ttu-id="dd445-123">Förslag skapas utifrån valda indata.</span><span class="sxs-lookup"><span data-stu-id="dd445-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="dd445-124">Kundprofiler: Alla kunder eller medlemmar i ett visst segment.</span><span class="sxs-lookup"><span data-stu-id="dd445-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="dd445-125">Tidsperiod: Senaste månaden, förra året eller eventuella anpassade tidsram.</span><span class="sxs-lookup"><span data-stu-id="dd445-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="dd445-126">Aktivitetstyp: inköp, återförsäljningstransaktioner, onlinetransaktioner, kundsupportärenden, prenumerationer och så vidare.</span><span class="sxs-lookup"><span data-stu-id="dd445-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="dd445-127">Entitet i Customer Insights som innehåller aktivitetsdata: Entiteten UnifiedActivity eller entiteten för en viss aktivitet.</span><span class="sxs-lookup"><span data-stu-id="dd445-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="dd445-128">Mått som ska inkludera: Recency, frekvens eller monetärt, beroende på dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="dd445-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="dd445-129">Generera föreslagna segment</span><span class="sxs-lookup"><span data-stu-id="dd445-129">Generate suggested segments</span></span>

1. <span data-ttu-id="dd445-130">Gå till **Segment**.</span><span class="sxs-lookup"><span data-stu-id="dd445-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="dd445-131">Välj fliken **Förslag (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="dd445-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="dd445-132">Välj **Sök efter nya förslag** och välj **Visa eller förutse kundbeteende**.</span><span class="sxs-lookup"><span data-stu-id="dd445-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="dd445-133">Välj **Start** om du vill köra den guidade upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="dd445-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Första steget i konfigurationsguiden för ett föreslaget segment baserat på aktivitet.":::

1. <span data-ttu-id="dd445-135">Ange de indata som krävs och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="dd445-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="dd445-136">Välj kunder: Ta med alla kunder eller ett specifikt segment.</span><span class="sxs-lookup"><span data-stu-id="dd445-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="dd445-137">Välj aktivitet: Välj aktivitetstyp och de entiteter som beskriver aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="dd445-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="dd445-138">Inställningar: Ange den tidsperiod som ska beaktas, faktorerna för förslag och mappa attributen.</span><span class="sxs-lookup"><span data-stu-id="dd445-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="dd445-139">Granska indata och välj **Kör** för att köra modellen och generera förslag.</span><span class="sxs-lookup"><span data-stu-id="dd445-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="dd445-140">Beroende på antalet kundprofiler och valda aktiviteter kan det ta några minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="dd445-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="dd445-141">När du har genererat förslagen kan du filtrera dem efter det värde du är mest intresserad av.</span><span class="sxs-lookup"><span data-stu-id="dd445-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="dd445-142">Visa information om föreslaget segment</span><span class="sxs-lookup"><span data-stu-id="dd445-142">View details of a suggested segment</span></span>

<span data-ttu-id="dd445-143">När förslagen har genererats hittar du dem listade i **Segment** > **Förslag (förhandsversion)** i avsnittet **Aktivitetsbaserade förslag**.</span><span class="sxs-lookup"><span data-stu-id="dd445-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Den expanderade rutan på sidan visar detaljerade data för ett föreslaget segment.":::

<span data-ttu-id="dd445-145">Välj **Visa förslag** på ett föreslaget segment för att visa information om det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="dd445-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="dd445-146">I den vänstra rutan visas information om i vilken omfattning varje ruta visas i jämförelse med målgruppen.</span><span class="sxs-lookup"><span data-stu-id="dd445-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="dd445-147">Det visar också antalet potentiella medlemmar i segmenten och den motsvarande procentandelen av de totala kunderna.</span><span class="sxs-lookup"><span data-stu-id="dd445-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="dd445-148">Om du vill behålla förslaget som ett segment väljer du **Skapa segment**.</span><span class="sxs-lookup"><span data-stu-id="dd445-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="dd445-149">Spara ett förslag som ett segment</span><span class="sxs-lookup"><span data-stu-id="dd445-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="dd445-150">Gå till **Segment** > **Förslag (förhandsgranskning)**.</span><span class="sxs-lookup"><span data-stu-id="dd445-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="dd445-151">Välj det segment som du vill spara.</span><span class="sxs-lookup"><span data-stu-id="dd445-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="dd445-152">I den vänstra rutan, välj **Skapa segment**.</span><span class="sxs-lookup"><span data-stu-id="dd445-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="dd445-153">När du har sparat segmenten visas det i listan med segment på fliken **Alla segment**. Det kan nu [uppdateras eller tas bort på samma sätt som i andra segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dd445-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="dd445-154">Du kan inte redigera segmentinformationen.</span><span class="sxs-lookup"><span data-stu-id="dd445-154">You can't edit the segment details.</span></span> <span data-ttu-id="dd445-155">Du kan emellertid ändra indatavillkoren för förslagen och generera olika förslag.</span><span class="sxs-lookup"><span data-stu-id="dd445-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="dd445-156">Uppdatera eller redigera en uppsättning förslag</span><span class="sxs-lookup"><span data-stu-id="dd445-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="dd445-157">Gå till **Segment** > **Förslag (förhandsversion)** och leta upp avsnittet **Aktivitetsbaserade förslag**.</span><span class="sxs-lookup"><span data-stu-id="dd445-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="dd445-158">Välj **Uppdatera förslag** för att uppdatera förslagen samtidigt som du behåller konfigurerade attribut.</span><span class="sxs-lookup"><span data-stu-id="dd445-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="dd445-159">Eller välj **Redigera förslag** om du vill ändra de konfigurerade attributen.</span><span class="sxs-lookup"><span data-stu-id="dd445-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="dd445-160">Systemet kör processen på nytt, genererar segmentförslag utifrån senaste data och ersätter de aktuella förslagen.</span><span class="sxs-lookup"><span data-stu-id="dd445-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
