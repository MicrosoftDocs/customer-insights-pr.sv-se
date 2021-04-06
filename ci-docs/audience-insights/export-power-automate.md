---
title: Power Automate anslutningsprogram | Microsoft Docs
description: Skapa flöden i Microsoft Power Automate från Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597947"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="c417c-103">Power Automate anslutningsprogram (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="c417c-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="c417c-104">Utlös specifika händelser automatiskt när data ändras och hantera mer komplicerade flöden direkt i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c417c-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="c417c-105">Power Automate-utlösare</span><span class="sxs-lookup"><span data-stu-id="c417c-105">Power Automate triggers</span></span>

<span data-ttu-id="c417c-106">Med utlösare kan du skapa molnflöden och automatisera repetitiva uppgifter, till exempel meddelanden eller mer avancerade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c417c-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="c417c-107">Utlöses när en uppdatering av en datakälla misslyckas.</span><span class="sxs-lookup"><span data-stu-id="c417c-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="c417c-108">Utlöses när en uppdatering av en datakälla lyckas.</span><span class="sxs-lookup"><span data-stu-id="c417c-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="c417c-109">Utlöses när ett tröskelvärde passeras i ett segment.</span><span class="sxs-lookup"><span data-stu-id="c417c-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="c417c-110">Utlösaren begränsas till att passera över tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="c417c-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c417c-111">Utlöses när ett tröskelvärde passeras i ett affärsmått.</span><span class="sxs-lookup"><span data-stu-id="c417c-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="c417c-112">Utlösaren begränsas till att passera över tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="c417c-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="c417c-113">Utlösa när en fullständig uppdatering av (datakällor, segment, mått ...) är slutförd.</span><span class="sxs-lookup"><span data-stu-id="c417c-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="c417c-114">Utlöses när en uppdatering av föreningsprocessen (mappning, matchning, sammanslagning) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="c417c-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="c417c-115">[Konfigurera utlösarna i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="c417c-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="c417c-116">Power Automate-åtgärder</span><span class="sxs-lookup"><span data-stu-id="c417c-116">Power Automate actions</span></span>
<span data-ttu-id="c417c-117">Power Automate-anslutaren tillhandahåller andra åtgärder än de tillgängliga utlösarna.</span><span class="sxs-lookup"><span data-stu-id="c417c-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="c417c-118">Mer information finns i [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="c417c-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="c417c-119">Skapa ett Power Automate-flöde</span><span class="sxs-lookup"><span data-stu-id="c417c-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="c417c-120">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="c417c-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c417c-121">I panelen **Power Automate**, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="c417c-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="c417c-122">Customer Insights-anslutningsprogrammet (förhandsversion) i Power Automate öppnas.</span><span class="sxs-lookup"><span data-stu-id="c417c-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="c417c-123">**Logga in på** till Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c417c-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="c417c-124">Välj en av de tillgängliga utlösarna och lägg till fler steg i det nya flödet.</span><span class="sxs-lookup"><span data-stu-id="c417c-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="c417c-125">Mer information finns i [Skapa ett molnflöde i Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="c417c-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="c417c-126">Exempel på hur flöden används:</span><span class="sxs-lookup"><span data-stu-id="c417c-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="c417c-127">Publicera ett meddelande till en Microsoft Teams-kanal om en datakälla inte går att uppdatera.</span><span class="sxs-lookup"><span data-stu-id="c417c-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="c417c-128">Skicka ett e-postmeddelande till dataägarna när en tröskel för ett segment överskrids.</span><span class="sxs-lookup"><span data-stu-id="c417c-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]