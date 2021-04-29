---
title: Exportera Customer Insights-data till Dynamics 365 Sales
description: Lär dig hur du konfigurerar anslutningen och exporterar till Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759626"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="ccd4a-103">Använd segment i Dynamics 365 Sales (förhandsvisning)</span><span class="sxs-lookup"><span data-stu-id="ccd4a-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ccd4a-104">Använd dina kunddata för att skapa marknadsföringslistor, följa upp arbetsflöden och skicka ut reklamkampanjer med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="ccd4a-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="ccd4a-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="ccd4a-106">Kontaktposter måste finnas i Dynamics 365 Sales innan du kan exportera ett segment från Customer Insights till Sales.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="ccd4a-107">Läs mer om hur du matar in kontakter i [Dynamics 365 Sales med Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ccd4a-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ccd4a-108">Om du exporterar segment från målgruppsinsikter till Sales skapas inte nya kontaktposter i Sales-instanserna.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="ccd4a-109">Kontaktposterna från Sales måste matas in i målgruppsinsikter och användas som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ccd4a-110">De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="ccd4a-111">Upprätta anslutningen till Sales</span><span class="sxs-lookup"><span data-stu-id="ccd4a-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="ccd4a-112">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ccd4a-113">Välj **Lägg till anslutning** och välj **Dynamics 365 Sales** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="ccd4a-114">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ccd4a-115">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ccd4a-116">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ccd4a-117">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-117">Choose who can use this connection.</span></span> <span data-ttu-id="ccd4a-118">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ccd4a-119">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ccd4a-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ccd4a-120">Ange organisationens Sales-URL i fältet **Serveradress**.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ccd4a-121">I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="ccd4a-122">Mappa ett kund-ID-fält till Dynamics 365 Contact ID.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ccd4a-123">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ccd4a-124">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="ccd4a-124">Configure an export</span></span>

<span data-ttu-id="ccd4a-125">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ccd4a-126">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ccd4a-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ccd4a-127">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ccd4a-128">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ccd4a-129">I fältet **Anslutning för export**, välj en anslutning från avsnittet Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="ccd4a-130">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ccd4a-131">Välj ett eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="ccd4a-132">Välj **Spara**</span><span class="sxs-lookup"><span data-stu-id="ccd4a-132">Select **Save**</span></span>

<span data-ttu-id="ccd4a-133">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="ccd4a-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ccd4a-134">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ccd4a-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ccd4a-135">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ccd4a-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
