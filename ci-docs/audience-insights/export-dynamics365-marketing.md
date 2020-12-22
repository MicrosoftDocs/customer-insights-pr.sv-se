---
title: Exportera Customer Insights-data till Dynamics 365 Marketing
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643795"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="e4729-103">Koppling för Dynamics 365 Marketing (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="e4729-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e4729-104">Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e4729-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="e4729-105">Mer information finns i [Använda segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="e4729-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="e4729-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e4729-106">Prerequisite</span></span>

<span data-ttu-id="e4729-107">Kontaktposter [från Dynamics 365 Marketing matade in Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e4729-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="e4729-108">Konfigurera koppling för marknadsföring</span><span class="sxs-lookup"><span data-stu-id="e4729-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="e4729-109">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="e4729-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e4729-110">Under **Dynamics 365 Marketing**, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="e4729-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="e4729-111">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="e4729-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e4729-112">Ange organisationens marknadsförings-URL i fältet **Serveradress**.</span><span class="sxs-lookup"><span data-stu-id="e4729-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e4729-113">I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="e4729-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="e4729-114">Mappa ett kund-ID-fält till Dynamics 365 Contact ID.</span><span class="sxs-lookup"><span data-stu-id="e4729-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e4729-115">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e4729-115">Select **Next**.</span></span>

1. <span data-ttu-id="e4729-116">Välj ett eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="e4729-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="e4729-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e4729-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e4729-118">Exportera data</span><span class="sxs-lookup"><span data-stu-id="e4729-118">Export the data</span></span>

<span data-ttu-id="e4729-119">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e4729-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e4729-120">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4729-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
