---
title: Exportera Customer Insights-data till SendGrid
description: Lär dig hur du konfigurerar anslutningen och exporterar till SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976938"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="2207f-103">Exportera segment till SendGrid (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="2207f-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="2207f-104">Exportera segment med enhetliga kundprofiler till SendGrid-kontaktlistor och använd dem för kampanjer och e-postmarknadsföring i SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2207f-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2207f-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="2207f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2207f-106">Du har ett [SendGrid-konto](https://sendgrid.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="2207f-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2207f-107">Det finns befintliga kontaktlistor i SendGrid och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="2207f-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="2207f-108">Mer information finns i [SendGrid – Hantera kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="2207f-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="2207f-109">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="2207f-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2207f-110">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="2207f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2207f-111">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="2207f-111">Known limitations</span></span>

- <span data-ttu-id="2207f-112">Upp till 100 000 profiler totalt till SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2207f-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="2207f-113">Export till SendGrid är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="2207f-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="2207f-114">Att exportera upp till 100 000 profiler till SendGrid kan ta upp till några timmar att genomföra.</span><span class="sxs-lookup"><span data-stu-id="2207f-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="2207f-115">Antalet profiler som du kan exportera till SendGrid är beroende av och begränsat enligt ditt kontrakt med SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2207f-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="2207f-116">Konfigurera anslutningen SendGrid</span><span class="sxs-lookup"><span data-stu-id="2207f-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="2207f-117">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="2207f-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2207f-118">Välj **Lägg till anslutning** och välj **SendGrid** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="2207f-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="2207f-119">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="2207f-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2207f-120">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="2207f-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2207f-121">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="2207f-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2207f-122">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="2207f-122">Choose who can use this connection.</span></span> <span data-ttu-id="2207f-123">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="2207f-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2207f-124">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2207f-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2207f-125">Ange **SendGrids API-nyckel** [SendGrids API-nyckel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="2207f-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="2207f-126">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="2207f-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2207f-127">Välj **Anslut** om du vill initiera anslutningen till SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2207f-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="2207f-128">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2207f-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2207f-129">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="2207f-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2207f-130">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="2207f-130">Configure an export</span></span>

<span data-ttu-id="2207f-131">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="2207f-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2207f-132">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2207f-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2207f-133">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="2207f-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2207f-134">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="2207f-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2207f-135">I fältet **Anslutning för export**, välj en anslutning från avsnittet SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2207f-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="2207f-136">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="2207f-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2207f-137">Ange ditt **[ID för SendGrid-lista](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="2207f-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="2207f-138">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="2207f-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2207f-139">Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Land/region**, **Delstat**, **Stad** och **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="2207f-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="2207f-140">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="2207f-140">Select the segments you want to export.</span></span> <span data-ttu-id="2207f-141">Vi **rekommenderar starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2207f-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="2207f-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2207f-142">Select **Save**.</span></span>

<span data-ttu-id="2207f-143">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="2207f-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2207f-144">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2207f-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2207f-145">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2207f-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2207f-146">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="2207f-146">Data privacy and compliance</span></span>

<span data-ttu-id="2207f-147">När du aktiverar Dynamics 365 Customer Insights för att överföra data till SendGrid tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="2207f-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2207f-148">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att SendGrid uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="2207f-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2207f-149">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2207f-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2207f-150">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="2207f-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]