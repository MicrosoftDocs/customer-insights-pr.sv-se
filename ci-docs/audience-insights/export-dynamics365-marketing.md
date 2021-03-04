---
title: Exportera Customer Insights-data till Dynamics 365 Marketing
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269076"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="b0e63-103">Koppling för Dynamics 365 Marketing (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="b0e63-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b0e63-104">Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="b0e63-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="b0e63-105">Mer information finns i [Använda segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="b0e63-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b0e63-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b0e63-106">Prerequisite</span></span>

- <span data-ttu-id="b0e63-107">Kontaktposter måste finnas i Dynamics 365 Marketing innan du kan exportera ett segment från Customer Insights till Marketing.</span><span class="sxs-lookup"><span data-stu-id="b0e63-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="b0e63-108">Läs mer om hur du matar in kontakter i [Dynamics 365 Marketing med Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b0e63-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b0e63-109">Om du exporterar segment från målgruppsinsikter till Marketing skapas inte nya kontaktposter i Marketing-instanserna.</span><span class="sxs-lookup"><span data-stu-id="b0e63-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="b0e63-110">Kontaktposterna från Marketing måste matas in i målgruppsinsikter och användas som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="b0e63-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b0e63-111">De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.</span><span class="sxs-lookup"><span data-stu-id="b0e63-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="b0e63-112">Konfigurera koppling för marknadsföring</span><span class="sxs-lookup"><span data-stu-id="b0e63-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="b0e63-113">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="b0e63-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b0e63-114">Under **Dynamics 365 Marketing**, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="b0e63-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="b0e63-115">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="b0e63-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b0e63-116">Ange organisationens marknadsförings-URL i fältet **Serveradress**.</span><span class="sxs-lookup"><span data-stu-id="b0e63-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b0e63-117">I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="b0e63-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="b0e63-118">Mappa ett kund-ID-fält till Dynamics 365 Contact ID.</span><span class="sxs-lookup"><span data-stu-id="b0e63-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b0e63-119">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b0e63-119">Select **Next**.</span></span>

1. <span data-ttu-id="b0e63-120">Välj ett eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="b0e63-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="b0e63-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b0e63-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b0e63-122">Exportera data</span><span class="sxs-lookup"><span data-stu-id="b0e63-122">Export the data</span></span>

<span data-ttu-id="b0e63-123">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b0e63-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b0e63-124">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b0e63-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]