---
title: Integrera webbdata från engagemangsinsikter med målgruppsinsikter
description: Hämta webbinformation om kunder från engagemangsinsikter till målgruppsinsikter.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267698"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="202b3-103">Integrera webbdata från engagemangsinsikter med målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="202b3-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="202b3-104">Kunderna gör ofta sina dagliga transaktioner online via webbplatser.</span><span class="sxs-lookup"><span data-stu-id="202b3-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="202b3-105">Funktionerna för engagemangsinsikter i Dynamics 365 Customer Insights är en praktisk lösning för att integrera webbdata som källa.</span><span class="sxs-lookup"><span data-stu-id="202b3-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="202b3-106">Förutom transaktionsinformation, demografisk information eller beteendeinformation kan vi se aktiviteter på webben i enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="202b3-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="202b3-107">Vi kan använda den här profilen för att få ytterligare insikter som segment, mått eller förutsägelser för målgruppsaktivering.</span><span class="sxs-lookup"><span data-stu-id="202b3-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="202b3-108">Den här artikeln beskriver stegen du tar för att ta dina kunders webbaktivitetsdata från engagemangsinsikter till din befintliga miljö för målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="202b3-109">I det här exemplet förutsätts det att miljön innehåller enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="202b3-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="202b3-110">Profilerna var enhetliga med källor från undersökningar, återförsäljning och ett ärendesystem.</span><span class="sxs-lookup"><span data-stu-id="202b3-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="202b3-111">Det visar också kundernas relaterade aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="202b3-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="202b3-112">Nu vill vi veta om en kund besöker våra webbegenskaper och förstår deras aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="202b3-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="202b3-113">Aktiviteterna omfattar till exempel besökta webbplatser eller visade produktsidor från en länk som tagits emot i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="202b3-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="202b3-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="202b3-114">Prerequisites</span></span>

<span data-ttu-id="202b3-115">För att integrera data från engagemangsinsikter måste några krav uppfyllas:</span><span class="sxs-lookup"><span data-stu-id="202b3-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="202b3-116">Integrera SDK för engagemangsinsikter med din webbplats.</span><span class="sxs-lookup"><span data-stu-id="202b3-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="202b3-117">Mer information finns i [Kom igång med webb-SDK](../engagement-insights/instrument-website.md).</span><span class="sxs-lookup"><span data-stu-id="202b3-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="202b3-118">För att exportera webbhändelser från engagemangsinsikter krävs åtkomst till ett ADLS Gen 2-lagringskonto som används för att mata in webbhändelsers data i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="202b3-119">Mer information finns i [Exportera händelser](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="202b3-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="202b3-120">Konfigurera förfinade händelser i engagemangsinsikter</span><span class="sxs-lookup"><span data-stu-id="202b3-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="202b3-121">När en administratör har instrumenterat en webbplats med SDK för engagemangsinsikter, samlas *grundhändelser* när en användare visar en webbsida eller klickar någonstans.</span><span class="sxs-lookup"><span data-stu-id="202b3-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="202b3-122">Grundhändelser innehåller mängder av detaljer.</span><span class="sxs-lookup"><span data-stu-id="202b3-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="202b3-123">Beroende på hur du använder ett ärende behöver du bara en delmängd data i en grundhändelse.</span><span class="sxs-lookup"><span data-stu-id="202b3-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="202b3-124">Med engagemangsinsikter kan du skapa *förfinade händelser* som endast innehåller egenskaperna för en grundhändelse som du har valt.</span><span class="sxs-lookup"><span data-stu-id="202b3-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="202b3-125">Mer information finns i [Skapa och ändra förfinade händelser](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="202b3-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="202b3-126">Att tänka på när man skapar förfinade händelser:</span><span class="sxs-lookup"><span data-stu-id="202b3-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="202b3-127">Ge ett meningsfullt namn för den förfinade händelsen.</span><span class="sxs-lookup"><span data-stu-id="202b3-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="202b3-128">Det används som ett aktivitetsnamn i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="202b3-129">Välj åtminstone följande egenskaper för att skapa en aktivitet i målgruppsinsikter:</span><span class="sxs-lookup"><span data-stu-id="202b3-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="202b3-130">Signal.Action.Name – ange aktivitetsinformationen</span><span class="sxs-lookup"><span data-stu-id="202b3-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="202b3-131">Signal.User.Id – används för att mappa med kund-ID</span><span class="sxs-lookup"><span data-stu-id="202b3-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="202b3-132">Signal.View.Uri – används som webbadress som bas för segment eller mått</span><span class="sxs-lookup"><span data-stu-id="202b3-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="202b3-133">Signal.Export.Id – att använda som primärnyckel för händelser</span><span class="sxs-lookup"><span data-stu-id="202b3-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="202b3-134">Signal.Timestamp – för att fastställa datum och tid för aktiviteten</span><span class="sxs-lookup"><span data-stu-id="202b3-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="202b3-135">Välj vilka filter som ska fokusera på de händelser och sidor som är viktiga för ditt användningsområde.</span><span class="sxs-lookup"><span data-stu-id="202b3-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="202b3-136">I det här exemplet använder vi åtgärdsnamnet "E-postkampanj".</span><span class="sxs-lookup"><span data-stu-id="202b3-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="202b3-137">Exportera förfinade webbhändelser</span><span class="sxs-lookup"><span data-stu-id="202b3-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="202b3-138">När du har definierat en förfinad händelse måste du konfigurera exporten av händelsedata till Azure Data Lake Storage, som kan anges som datakälla för insamling i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="202b3-139">Exporten sker kontinuerligt när händelserna flödar från webbegenskapen.</span><span class="sxs-lookup"><span data-stu-id="202b3-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="202b3-140">Mer information finns i [Exportera händelser](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="202b3-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="202b3-141">Mata in händelsedata i målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="202b3-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="202b3-142">Nu när du har definierat den förfinade händelsen och konfigurerat exporten går vi vidare till att mata in data i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="202b3-143">Du måste skapa en ny datakälla baserat på mappen Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="202b3-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="202b3-144">Ange information för lagringskontot som du exporterar händelserna till.</span><span class="sxs-lookup"><span data-stu-id="202b3-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="202b3-145">I filen *default.cdm.json* väljer du den förfinade händelsen som ska matas in och skapar entiteten i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="202b3-146">Mer information finns i [Ansluta till en Common Data Model-mapp med ett Azure Data Lake-konto](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="202b3-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="202b3-147">Relatera data om förfinade händelser som en aktivitet i en kundprofil</span><span class="sxs-lookup"><span data-stu-id="202b3-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="202b3-148">När du har slutfört entitetsinmatningen kan du konfigurera aktiviteten för kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="202b3-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="202b3-149">Mer information finns i [Kundaktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="202b3-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="Sidan Aktiviteter med expanderad redigeringsaktivitetsruta och ifyllda fält.":::

<span data-ttu-id="202b3-151">Konfigurera den nya aktiviteten med följande mappning:</span><span class="sxs-lookup"><span data-stu-id="202b3-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="202b3-152">**Primärnyckel:** Signal.Export.Id, ett unikt ID som är tillgängligt för varje händelsepost i engagemangsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="202b3-153">Egenskapen genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="202b3-153">This property is automatically generated.</span></span>

- <span data-ttu-id="202b3-154">**Tidsstämpel:** Signal.Timestamp i händelseegenskapen.</span><span class="sxs-lookup"><span data-stu-id="202b3-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="202b3-155">**Händelse:** Signal.Name, det händelsenamn du vill spåra.</span><span class="sxs-lookup"><span data-stu-id="202b3-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="202b3-156">**Webbadress:** Signal.View.Uri hänvisar till uri på sidan som skapade händelsen.</span><span class="sxs-lookup"><span data-stu-id="202b3-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="202b3-157">**Information:** Signal.Action.Name som representerar den information som ska associeras med händelsen.</span><span class="sxs-lookup"><span data-stu-id="202b3-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="202b3-158">Den valda egenskapen i det här ärendet anger att händelsen gäller e-postkampanj.</span><span class="sxs-lookup"><span data-stu-id="202b3-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="202b3-159">**Aktivitetstyp:** I det här exemplet väljer vi den befintliga aktivitetstypen WebLog.</span><span class="sxs-lookup"><span data-stu-id="202b3-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="202b3-160">Det här alternativet är ett användbart filteralternativ för att köra förutsägelsemodeller eller skapa segment baserat på denna aktivitetstyp.</span><span class="sxs-lookup"><span data-stu-id="202b3-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="202b3-161">**Skapa relation:** Den här viktiga inställningen gör att aktiviteten kan knytas till befintliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="202b3-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="202b3-162">**Signal.User.Id** är identifieraren som konfigurerats i SDK som ska samlas in och som relaterar till användar-ID i andra datakällor som har konfigurerats i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="202b3-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="202b3-163">I det här exemplet konfigurerar vi relationen mellan Signal.User.Id och RetailCustomers:CustomerRetailId, som är den primära nyckel som identifierades i mappningssteget av dataföreningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="202b3-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="202b3-164">När du har bearbetat aktiviteterna kan du granska kundposter och öppna ett kundkort för att se aktiviteter från engagemangsinsikter i tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="202b3-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="202b3-165">Om du vill hitta ett kund-ID som har en engagemangsinsiktsaktivitet går du till **Entiteter** och förhandsgranskar data för entiteten UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="202b3-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="202b3-166">ActivityTypeDisplay = WebLog innehåller den engagemangsinsiktsaktivitet som konfigurerats i exemplet ovan.</span><span class="sxs-lookup"><span data-stu-id="202b3-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="202b3-167">Kopiera kund-ID för en av dessa poster och för ID på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="202b3-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="202b3-168">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="202b3-168">Next Steps</span></span>

<span data-ttu-id="202b3-169">Du kan nu skapa [segment](segments.md), [mått](measures.md) och [förutsägelse](predictions.md) för att skapa en meningsfull kontakt med dina kunder.</span><span class="sxs-lookup"><span data-stu-id="202b3-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]