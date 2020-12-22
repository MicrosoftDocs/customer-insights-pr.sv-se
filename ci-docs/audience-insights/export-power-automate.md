---
title: Power Automate anslutningsprogram | Microsoft Docs
description: Skapa flöden i Microsoft Power Automate från Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407061"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="60989-103">Power Automate anslutningsprogram (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="60989-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="60989-104">Utlös specifika händelser automatiskt när data ändras och hantera mer komplicerade flöden direkt i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="60989-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="60989-105">Power Automate-utlösare</span><span class="sxs-lookup"><span data-stu-id="60989-105">Power Automate triggers</span></span>

<span data-ttu-id="60989-106">Du kan använda en mängd olika utlösare som gör det möjligt att skapa flöden för att automatisera återkommande uppgifter, till exempel aviseringar eller mer avancerade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="60989-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="60989-107">Utlöses när en uppdatering av en datakälla misslyckas.</span><span class="sxs-lookup"><span data-stu-id="60989-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="60989-108">Utlöses när en uppdatering av en datakälla lyckas.</span><span class="sxs-lookup"><span data-stu-id="60989-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="60989-109">Utlöses när ett tröskelvärde passeras i ett segment.</span><span class="sxs-lookup"><span data-stu-id="60989-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="60989-110">Utlösaren begränsas till att passera över tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="60989-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="60989-111">Utlöses när ett tröskelvärde passeras i ett affärsmått.</span><span class="sxs-lookup"><span data-stu-id="60989-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="60989-112">Utlösaren begränsas till att passera över tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="60989-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="60989-113">Utlösa när en fullständig uppdatering av (datakällor, segment, mått ...) är slutförd.</span><span class="sxs-lookup"><span data-stu-id="60989-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="60989-114">Utlöses när en uppdatering av föreningsprocessen (mappning, matchning, sammanslagning) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="60989-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="60989-115">[Konfigurera utlösarna i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="60989-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="60989-116">Power Automate-åtgärder</span><span class="sxs-lookup"><span data-stu-id="60989-116">Power Automate actions</span></span>
<span data-ttu-id="60989-117">Power Automate-anslutaren tillhandahåller andra åtgärder än de tillgängliga utlösarna.</span><span class="sxs-lookup"><span data-stu-id="60989-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="60989-118">Mer information finns i [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="60989-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="60989-119">Skapa ett Power Automate-flöde i målgruppsinsikter</span><span class="sxs-lookup"><span data-stu-id="60989-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="60989-120">I målgruppsinsikter går du till **Admin** > **System**.</span><span class="sxs-lookup"><span data-stu-id="60989-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="60989-121">På sidan **System**, välj fliken **Status**.</span><span class="sxs-lookup"><span data-stu-id="60989-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="60989-122">I avsnittet **Datakällor**, välj **Flöden** och välj **Skapa ett flöde** i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="60989-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60989-123">![Power Automate anslutningsprogram med skapa en flödesåtgärd](media/power-automate-connector-create-flow.png "Power Automate anslutningsprogram med skapa en flödesåtgärd")</span><span class="sxs-lookup"><span data-stu-id="60989-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="60989-124">I Power Automate väljer du en av de tillgängliga utlösarna för att skapa det önskade flödet.</span><span class="sxs-lookup"><span data-stu-id="60989-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="60989-125">Om du skapar ditt första flöde måste du först autentisera med Power Automate-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="60989-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
