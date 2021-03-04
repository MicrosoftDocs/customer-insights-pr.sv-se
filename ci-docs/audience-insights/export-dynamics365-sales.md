---
title: Exportera Customer Insights-data till Dynamics 365 Sales
description: Lär dig hur du konfigurerar anslutningen till Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269030"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="24405-103">Koppling för Dynamics 365 Sales (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="24405-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="24405-104">Använd dina kunddata för att skapa marknadsföringslistor, följa upp arbetsflöden och skicka ut reklamkampanjer med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="24405-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="24405-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="24405-105">Prerequisite</span></span>

1. <span data-ttu-id="24405-106">Kontaktposter måste finnas i Dynamics 365 Sales innan du kan exportera ett segment från Customer Insights till Sales.</span><span class="sxs-lookup"><span data-stu-id="24405-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="24405-107">Läs mer om hur du matar in kontakter i [Dynamics 365 Sales med Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="24405-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="24405-108">Om du exporterar segment från målgruppsinsikter till Sales skapas inte nya kontaktposter i Sales-instanserna.</span><span class="sxs-lookup"><span data-stu-id="24405-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="24405-109">Kontaktposterna från Sales måste matas in i målgruppsinsikter och användas som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="24405-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="24405-110">De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.</span><span class="sxs-lookup"><span data-stu-id="24405-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="24405-111">Konfigurera koppling för Sales</span><span class="sxs-lookup"><span data-stu-id="24405-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="24405-112">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="24405-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="24405-113">Under **Dynamics 365 Sales**, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="24405-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="24405-114">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="24405-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="24405-115">Ange organisationens Sales-URL i fältet **Serveradress**.</span><span class="sxs-lookup"><span data-stu-id="24405-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="24405-116">I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="24405-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="24405-117">Mappa ett kund-ID-fält till Dynamics 365 Contact ID.</span><span class="sxs-lookup"><span data-stu-id="24405-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="24405-118">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="24405-118">Select **Next**.</span></span>

1. <span data-ttu-id="24405-119">Välj ett eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="24405-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="24405-120">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="24405-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="24405-121">Exportera data</span><span class="sxs-lookup"><span data-stu-id="24405-121">Export the data</span></span>

<span data-ttu-id="24405-122">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="24405-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="24405-123">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24405-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]