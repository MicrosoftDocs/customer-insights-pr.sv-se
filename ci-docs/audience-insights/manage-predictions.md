---
title: Delade uppgifter för prediktionsscenarier
description: Lär dig hur du hanterar, felsöker och förfinar förutsägelser.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315900"
---
# <a name="manage-predictions"></a><span data-ttu-id="33753-103">Hantera förutsägelser</span><span class="sxs-lookup"><span data-stu-id="33753-103">Manage predictions</span></span>

<span data-ttu-id="33753-104">I den här artikeln beskrivs några uppgifter som de flesta prediktionsscenarier delar.</span><span class="sxs-lookup"><span data-stu-id="33753-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="33753-105">Felsöka en misslyckad förutsägelse</span><span class="sxs-lookup"><span data-stu-id="33753-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="33753-106">Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="33753-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="33753-107">Välj de lodräta ellipserna bredvid den förutsägelse som du vill visa felloggarna för.</span><span class="sxs-lookup"><span data-stu-id="33753-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="33753-108">Välj **Loggar**.</span><span class="sxs-lookup"><span data-stu-id="33753-108">Select **Logs**.</span></span>

1. <span data-ttu-id="33753-109">Granska alla fel.</span><span class="sxs-lookup"><span data-stu-id="33753-109">Review all the errors.</span></span> <span data-ttu-id="33753-110">Det finns flera typer av fel som kan inträffa, och dessa beskriver vilket villkor som orsakat problemet.</span><span class="sxs-lookup"><span data-stu-id="33753-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="33753-111">Ett fel som till exempel innebär att det inte finns tillräckligt med data för att förutsäga problemet korrekt löses vanligtvis genom att ytterligare data läses in i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="33753-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="33753-112">Användbarhetsrapport över inmatning av data</span><span class="sxs-lookup"><span data-stu-id="33753-112">Input data usability report</span></span>

<span data-ttu-id="33753-113">Rapporten om användbarhet av indata ger en konsoliderad vy över de fel och varningar som dina färdiga förutsägelser kan generera.</span><span class="sxs-lookup"><span data-stu-id="33753-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="33753-114">Det ger också rekommendationer om hur man förbättrar modellens prestanda.</span><span class="sxs-lookup"><span data-stu-id="33753-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="33753-115">Rapporten är tillgänglig när en modell har slutfört sin utbildningsprocess.</span><span class="sxs-lookup"><span data-stu-id="33753-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="33753-116">Den skapas för varje modell separat, oavsett om den har slutförts eller inte.</span><span class="sxs-lookup"><span data-stu-id="33753-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="33753-117">Se användbarhetsrapport över inmatning av data</span><span class="sxs-lookup"><span data-stu-id="33753-117">View the input data usability report</span></span>

<span data-ttu-id="33753-118">När en färdig modell har slutfört utbildningssteget, visa rapporten:</span><span class="sxs-lookup"><span data-stu-id="33753-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="33753-119">Välj ellipserna bredvid modellnamnet och välj rapporten **Användbarhetsrapport för indata**.</span><span class="sxs-lookup"><span data-stu-id="33753-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="33753-120">Välj status för en modell välj **Se användbarhetsrapporten för indata** i sidorutan.</span><span class="sxs-lookup"><span data-stu-id="33753-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="33753-121">Välj en av modellerna i listan och välj rapporten **Användbarhetsrapport för indata** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="33753-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="33753-122">Öppna modellresultatsidan och välj rapporten **Användbarhetsrapport för indata** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="33753-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="33753-123">Information i användbarhetsrapport över inmatning av data</span><span class="sxs-lookup"><span data-stu-id="33753-123">Information in the input data usability report</span></span>

<span data-ttu-id="33753-124">Följande kolumner i rapporten innehåller användbar information för att förbättra data för modellen.</span><span class="sxs-lookup"><span data-stu-id="33753-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exempel på en användbarhetsrapport för indata som visar en tabell med fel, varningar och rekommendationer.":::

- <span data-ttu-id="33753-126">Namn: Beskrivande namn på felet, varningen eller rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="33753-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="33753-127">Steg: Modellfas, tåg eller poäng, som informationen refererar till.</span><span class="sxs-lookup"><span data-stu-id="33753-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="33753-128">Tillstånd: Informationens allvarlighetsgrad (fel, varning, rekommendation).</span><span class="sxs-lookup"><span data-stu-id="33753-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="33753-129">Kolumnnamn: Kolumn i en entitet som måste ändras för att förbättra modellens prestanda.</span><span class="sxs-lookup"><span data-stu-id="33753-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="33753-130">Entitetsnamn: Namn på en entitet som måste ändras för att förbättra modellens prestanda.</span><span class="sxs-lookup"><span data-stu-id="33753-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="33753-131">Information: Information om fel, varning eller rekommendation.</span><span class="sxs-lookup"><span data-stu-id="33753-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="33753-132">Uppdatera en förutsägelse</span><span class="sxs-lookup"><span data-stu-id="33753-132">Refresh a prediction</span></span>

<span data-ttu-id="33753-133">Förutsägelser uppdateras automatiskt i samma [schema som dina data uppdaterar](system.md#schedule-tab) enligt konfigurationen i inställningarna.</span><span class="sxs-lookup"><span data-stu-id="33753-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="33753-134">Du kan uppdatera dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="33753-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="33753-135">Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="33753-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="33753-136">Markera de lodräta punkterna bredvid den förutsägelse du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="33753-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="33753-137">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="33753-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="33753-138">Ta bort en förutsägelse</span><span class="sxs-lookup"><span data-stu-id="33753-138">Delete a prediction</span></span>

<span data-ttu-id="33753-139">Om du tar bort en förutsägelse tas även dess utdataentitet bort.</span><span class="sxs-lookup"><span data-stu-id="33753-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="33753-140">Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.</span><span class="sxs-lookup"><span data-stu-id="33753-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="33753-141">Markera de lodräta punkterna bredvid den förutsägelse du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="33753-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="33753-142">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="33753-142">Select **Delete**.</span></span>
