---
title: Exportera Customer Insights-data till Dynamics 365 Marketing
description: Lär dig hur du konfigurerar anslutningen och exporterar till Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759659"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="1598e-103">Använd segment i Dynamics 365 Marketing (förhandsvisning)</span><span class="sxs-lookup"><span data-stu-id="1598e-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1598e-104">Använd [segment](segments.md) för att generera kampanjer och kontakta specifika kundgrupper med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="1598e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="1598e-105">Mer information finns i [Använda segment från Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="1598e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="1598e-106">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="1598e-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="1598e-107">Kontaktposter måste finnas i Dynamics 365 Marketing innan du kan exportera ett segment från Customer Insights till Marketing.</span><span class="sxs-lookup"><span data-stu-id="1598e-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="1598e-108">Läs mer om hur du matar in kontakter i [Dynamics 365 Marketing med Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1598e-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="1598e-109">Om du exporterar segment från målgruppsinsikter till Marketing skapas inte nya kontaktposter i Marketing-instanserna.</span><span class="sxs-lookup"><span data-stu-id="1598e-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="1598e-110">Kontaktposterna från Marketing måste matas in i målgruppsinsikter och användas som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="1598e-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="1598e-111">De måste också finnas med i den enhetliga entiteten Kund för att mappa kund-ID till kontakt-ID innan segment kan exporteras.</span><span class="sxs-lookup"><span data-stu-id="1598e-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="1598e-112">Upprätta anslutningen till Marketing</span><span class="sxs-lookup"><span data-stu-id="1598e-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="1598e-113">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="1598e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1598e-114">Välj **Lägg till anslutning** och välj **Dynamics 365 Marketing** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1598e-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="1598e-115">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="1598e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1598e-116">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="1598e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1598e-117">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1598e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1598e-118">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1598e-118">Choose who can use this connection.</span></span> <span data-ttu-id="1598e-119">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="1598e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1598e-120">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1598e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1598e-121">Ange organisationens marknadsförings-URL i fältet **Serveradress**.</span><span class="sxs-lookup"><span data-stu-id="1598e-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="1598e-122">I avsnittet **Serveradministratörskonto** väljer du **Logga in** och väljer ett Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="1598e-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="1598e-123">Mappa ett kund-ID-fält till Dynamics 365 Contact ID.</span><span class="sxs-lookup"><span data-stu-id="1598e-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="1598e-124">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1598e-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1598e-125">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="1598e-125">Configure an export</span></span>

<span data-ttu-id="1598e-126">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="1598e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1598e-127">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1598e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1598e-128">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="1598e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1598e-129">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="1598e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1598e-130">I fältet **Anslutning för export**, välj en anslutning från avsnittet Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="1598e-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="1598e-131">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="1598e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1598e-132">Välj ett eller flera segment.</span><span class="sxs-lookup"><span data-stu-id="1598e-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="1598e-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1598e-133">Select **Save**.</span></span>

<span data-ttu-id="1598e-134">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="1598e-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1598e-135">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1598e-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1598e-136">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1598e-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
