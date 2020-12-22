---
title: Robot for Microsoft Teams
description: Slå upp enhetliga kundprofiler i Microsoft Teams med hjälp av en robot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407094"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="28290-103">Teamrobot för Dynamics 365 Customer Insights (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="28290-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="28290-104">Anslut med Microsoft Teams för att låta en robot slå upp enhetliga kundprofiler i Teams-kanaler.</span><span class="sxs-lookup"><span data-stu-id="28290-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="28290-105">![Teams-robot som visar en kundpost](media/teams-bot.png "Teams-robot som visar en kundpost")</span><span class="sxs-lookup"><span data-stu-id="28290-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28290-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="28290-106">Prerequisites</span></span>

<span data-ttu-id="28290-107">Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera och konfigurera robotprogrammet:</span><span class="sxs-lookup"><span data-stu-id="28290-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="28290-108">Minst en [datakälla har lagts till](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="28290-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="28290-109">[Föreningsprocessen](data-unification.md) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="28290-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="28290-110">Fält läggs till i [Sök- och filterindex](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="28290-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="28290-111">Customer Insights och Teams finns i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="28290-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="28290-112">Konfigurera roboten</span><span class="sxs-lookup"><span data-stu-id="28290-112">Configure the bot</span></span>

1. <span data-ttu-id="28290-113">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="28290-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="28290-114">I panelen Microsoft Teams, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="28290-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="28290-115">Du omdirigeras då till området **appar** i Teams.</span><span class="sxs-lookup"><span data-stu-id="28290-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="28290-116">Du kan också öppna Teams och välja **appar** längst ned till vänster eller [Hämta den direkt från AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="28290-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="28290-117">Sök efter **Customer Insights** och välj appen.</span><span class="sxs-lookup"><span data-stu-id="28290-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="28290-118">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="28290-118">Select **Add**.</span></span>
1. <span data-ttu-id="28290-119">När du har loggat in på Customer Insights i Teams ser du ett välkomstmeddelande och kan komma igång.</span><span class="sxs-lookup"><span data-stu-id="28290-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="28290-120">Saker du kan göra med roboten</span><span class="sxs-lookup"><span data-stu-id="28290-120">Things you can do with the bot</span></span>

<span data-ttu-id="28290-121">Roboten har uppslagsfunktioner för enhetliga kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="28290-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="28290-122">Ange **sökning** följt av ett namn, en e-postadress eller ett annat fält i den enhetliga kundprofilen som läggs till i sök- och filterindexet.</span><span class="sxs-lookup"><span data-stu-id="28290-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="28290-123">Du får ett kort med upp till 15 fält från den resulterande kundprofilen.</span><span class="sxs-lookup"><span data-stu-id="28290-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="28290-124">Flera matchningar returnerar en resultatlista där du kan välja en profil.</span><span class="sxs-lookup"><span data-stu-id="28290-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="28290-125">Du kan lägga till sökterm i dubbla citattecken för att slå upp en exakt matchning.</span><span class="sxs-lookup"><span data-stu-id="28290-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="28290-126">Om organisationen underhåller flera Customer Insights-miljöer i samma organisation kan du ange **switchinstance** för att välja vilken miljö du vill ansluta roboten till.</span><span class="sxs-lookup"><span data-stu-id="28290-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="28290-127">Ange **Hjälp** för att visa en lista över tillgängliga kommandon för robot.</span><span class="sxs-lookup"><span data-stu-id="28290-127">Enter **help** to see a list of available commands for the bot.</span></span>  
