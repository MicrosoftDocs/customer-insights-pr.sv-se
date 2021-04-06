---
title: Exportera Customer Insights-data till Dynamics 365 Marketing
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597625"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a7006-103">Koppling för Dynamics 365 Marketing (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="a7006-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a7006-104">Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a7006-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a7006-105">Mer information finns i [Använda segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a7006-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a7006-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="a7006-106">Prerequisite</span></span>

- <span data-ttu-id="a7006-107">Kontaktposter måste finnas i Dynamics 365 Marketing innan du kan exportera ett segment från Customer Insights till Marketing.</span><span class="sxs-lookup"><span data-stu-id="a7006-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="a7006-108">Läs mer om hur du matar in kontakter i [Dynamics 365 Marketing med Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a7006-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a7006-109">Om du exporterar segment från målgruppsinsikter till Marketing skapas inte nya kontaktposter i Marketing-instanserna.</span><span class="sxs-lookup"><span data-stu-id="a7006-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="a7006-110">Kontaktposterna från Marketing måste matas in i målgruppsinsikter och användas som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="a7006-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a7006-111">De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.</span><span class="sxs-lookup"><span data-stu-id="a7006-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a7006-112">Konfigurera koppling för marknadsföring</span><span class="sxs-lookup"><span data-stu-id="a7006-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a7006-113">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="a7006-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a7006-114">Under **Dynamics 365 Marketing**, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="a7006-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a7006-115">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="a7006-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a7006-116">Ange organisationens marknadsförings-URL i fältet **Serveradress**.</span><span class="sxs-lookup"><span data-stu-id="a7006-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a7006-117">I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="a7006-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a7006-118">Mappa ett kund-ID-fält till Dynamics 365 Contact ID.</span><span class="sxs-lookup"><span data-stu-id="a7006-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a7006-119">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7006-119">Select **Next**.</span></span>

1. <span data-ttu-id="a7006-120">Välj ett eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="a7006-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="a7006-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a7006-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a7006-122">Exportera data</span><span class="sxs-lookup"><span data-stu-id="a7006-122">Export the data</span></span>

<span data-ttu-id="a7006-123">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a7006-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a7006-124">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a7006-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]