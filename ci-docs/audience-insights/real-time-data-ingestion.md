---
title: Datainmatning och begränsningar i realtid
description: Allmän information om realtidsfunktioner i målgruppsinsikter.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270302"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="47b35-103">Datainmatning i realtid (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="47b35-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="47b35-104">Med funktionen nästan i realtid kan du se inom några sekunder de senaste interaktionerna som dina kunder har gjort med dina produkter eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="47b35-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="47b35-105">[Schemalagda uppdateringar](system.md#schedule-tab) omfattar ett stort antal poster och flera komplexa operationer.</span><span class="sxs-lookup"><span data-stu-id="47b35-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="47b35-106">Först hämtas data från datakällan.</span><span class="sxs-lookup"><span data-stu-id="47b35-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="47b35-107">Därefter är informationen enhetlig och sedan utökad med ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="47b35-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="47b35-108">Alla körningar av den här processen kan ta minuter till timmar.</span><span class="sxs-lookup"><span data-stu-id="47b35-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="47b35-109">Realtidsfunktionen ger data omedelbart för förbrukning, tills den efterföljande schemalagda uppdateringen hämtar dessa data från datakällan.</span><span class="sxs-lookup"><span data-stu-id="47b35-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="47b35-110">Uppdateringar i realtid har en förfallotid efter att de inte längre ersätter värdet från datakälla:</span><span class="sxs-lookup"><span data-stu-id="47b35-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="47b35-111">Profiluppdateringar sparas i 4 timmar</span><span class="sxs-lookup"><span data-stu-id="47b35-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="47b35-112">Aktiviteter sparas i 30 dagar</span><span class="sxs-lookup"><span data-stu-id="47b35-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="47b35-113">Dessa värden är parametrar för API-anrop som du kan ändra.</span><span class="sxs-lookup"><span data-stu-id="47b35-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="47b35-114">De syftar till att se till att dina källdata förblir källan för sanningen.</span><span class="sxs-lookup"><span data-stu-id="47b35-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="47b35-115">Om du vill att uppdateringar i realtid ska ingå längre, måste du lägga till dem i en datakälla så att de hämtas under nästa schemalagda uppdatering.</span><span class="sxs-lookup"><span data-stu-id="47b35-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="47b35-116">Uppdatering i realtid av fälten för en enhetlig kundprofil</span><span class="sxs-lookup"><span data-stu-id="47b35-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="47b35-117">Uppdaterade profiler kommer att visas i kundkortsvyn, eller någon annan visualisering, inom några sekunder.</span><span class="sxs-lookup"><span data-stu-id="47b35-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="47b35-118">Eftersom realtidsåtgärder utförs efter att dataföreningen har inträffat gäller de bara för enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="47b35-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="47b35-119">Ändringar i realtidsprofilen uppdaterar därför inte åtgärder, segmentmedlemskap och berikningar.</span><span class="sxs-lookup"><span data-stu-id="47b35-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="47b35-120">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="47b35-120">Limitations</span></span>

- <span data-ttu-id="47b35-121">Kundprofiler kan uppdateras men inte skapas eller tas bort.</span><span class="sxs-lookup"><span data-stu-id="47b35-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="47b35-122">Det är inte möjligt att exportera uppdateringar i realtid till externa system Power BI just nu.</span><span class="sxs-lookup"><span data-stu-id="47b35-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="47b35-123">Skapande av aktiviteter i realtid</span><span class="sxs-lookup"><span data-stu-id="47b35-123">Real-time creation of activities</span></span>

<span data-ttu-id="47b35-124">Med realtids-API kan du publicera en ny aktivitet från ditt källsystem (en enskild källpost) till en enhetlig kundprofil.</span><span class="sxs-lookup"><span data-stu-id="47b35-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="47b35-125">Den nya aktiviteten blir tillgänglig som en enhetlig aktivitet i den enhetliga kundprofilens tidslinje inom några sekunder.</span><span class="sxs-lookup"><span data-stu-id="47b35-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="47b35-126">Du kan se tidslinjen i kundkortsvyn eller någon annan tidslinjeintegrering som du konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="47b35-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="47b35-127">Aktiviteter är oföränderliga.</span><span class="sxs-lookup"><span data-stu-id="47b35-127">Activities are immutable.</span></span> <span data-ttu-id="47b35-128">De ändras inte när de har skapats.</span><span class="sxs-lookup"><span data-stu-id="47b35-128">They don't change once created.</span></span>
> - <span data-ttu-id="47b35-129">För närvarande uppdateras inte segment och mått baserat på den nya aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="47b35-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="47b35-130">Aktiviteter som endast lagts till via API i realtid ingår inte i exporten och visas inte i PowerBI.</span><span class="sxs-lookup"><span data-stu-id="47b35-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="47b35-131">Du kan ansluta till realtids-API:et på två sätt:</span><span class="sxs-lookup"><span data-stu-id="47b35-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="47b35-132">[indirekt](#connect-via-the-dynamics-365-customer-insights-connector) med hjälp av [Dynamics 365 Customer Insights koppling](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="47b35-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="47b35-133">[direkt](#connect-directly-to-the-real-time-api), med kod</span><span class="sxs-lookup"><span data-stu-id="47b35-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="47b35-134">Båda sätten delar följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="47b35-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="47b35-135">En Customer Insights-miljö</span><span class="sxs-lookup"><span data-stu-id="47b35-135">A Customer Insights environment</span></span>
- <span data-ttu-id="47b35-136">Enhetliga kundprofiler</span><span class="sxs-lookup"><span data-stu-id="47b35-136">Unified customer profiles</span></span>
- <span data-ttu-id="47b35-137">Aktiviteter som har konfigurerats och körs</span><span class="sxs-lookup"><span data-stu-id="47b35-137">Activities configured and run</span></span>
- <span data-ttu-id="47b35-138">Verifiera ditt konto genom att deltagare eller administratörsbehörigheter</span><span class="sxs-lookup"><span data-stu-id="47b35-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="47b35-139">Anslut via Dynamics 365 Customer Insights kopplingen</span><span class="sxs-lookup"><span data-stu-id="47b35-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="47b35-140">API i realtid kan hämta data från en dedikerad Power Platform-koppling, [Dynamics 365 Customer Insights-koppling](https://docs.microsoft.com/connectors/customerinsights/) utan att någon kod behöver skrivas och distribueras.</span><span class="sxs-lookup"><span data-stu-id="47b35-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="47b35-141">Kopplingen kan utföra samma realtidsåtgärder som API.</span><span class="sxs-lookup"><span data-stu-id="47b35-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="47b35-142">Du behöver en giltig licens för Premium-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="47b35-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="47b35-143">Mer information finns i [Vanliga frågor om licensiering för Power Apps och Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="47b35-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="47b35-144">Power Platform [Power Apps och/eller Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="47b35-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="47b35-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="47b35-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="47b35-146">Mer information om hur du skapar flöden finns i [Power Automate-dokumentationen](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="47b35-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="47b35-147">Anslut direkt till API i realtid</span><span class="sxs-lookup"><span data-stu-id="47b35-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="47b35-148">Du kan använda realtidsfunktionerna genom att bygga en egen pipeline och ansluta direkt till realtids-API:et.</span><span class="sxs-lookup"><span data-stu-id="47b35-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="47b35-149">Du kan publicera en aktivitet i formatet för ditt källsystem eller i UnifiedActivity-format.</span><span class="sxs-lookup"><span data-stu-id="47b35-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="47b35-150">Visa formatet genom att göra ett API-anrop till /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="47b35-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="47b35-151">Detaljer om detta API, inklusive parametrar och svar, finns i avsnittet **EntityData** på [referensen Customer Insights-API:er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="47b35-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="47b35-152">Mer information finns i [Arbeta med Customer Insights-API:er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="47b35-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="47b35-153">Förstå din realtidsförbrukning med telemetri</span><span class="sxs-lookup"><span data-stu-id="47b35-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="47b35-154">Få en översikt över volymen av begäranden till realtids-API och information om problem som systemet kan stöta på.</span><span class="sxs-lookup"><span data-stu-id="47b35-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="47b35-155">Du kan [komma åt telemetri i realtid](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="47b35-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]