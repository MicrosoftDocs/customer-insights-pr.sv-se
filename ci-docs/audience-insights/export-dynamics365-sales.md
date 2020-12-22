---
title: Exportera Customer Insights-data till Dynamics 365 Sales
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643840"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="15086-103">Koppling för Dynamics 365 Sales (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="15086-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="15086-104">Använd dina kunddata för att skapa marknadsföringslistor, följa upp arbetsflöden och skicka ut reklamkampanjer med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="15086-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="15086-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="15086-105">Prerequisite</span></span>

<span data-ttu-id="15086-106">Kontaktposter [från Dynamics 365 Sales matade in med Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="15086-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="15086-107">Konfigurera koppling för Sales</span><span class="sxs-lookup"><span data-stu-id="15086-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="15086-108">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="15086-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="15086-109">Under **Dynamics 365 Sales**, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="15086-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="15086-110">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="15086-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="15086-111">Ange organisationens Sales-URL i fältet **Serveradress**.</span><span class="sxs-lookup"><span data-stu-id="15086-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="15086-112">I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="15086-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="15086-113">Mappa ett kund-ID-fält till Dynamics 365 Contact ID.</span><span class="sxs-lookup"><span data-stu-id="15086-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="15086-114">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="15086-114">Select **Next**.</span></span>

1. <span data-ttu-id="15086-115">Välj ett eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="15086-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="15086-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="15086-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="15086-117">Exportera data</span><span class="sxs-lookup"><span data-stu-id="15086-117">Export the data</span></span>

<span data-ttu-id="15086-118">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="15086-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="15086-119">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="15086-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
