---
title: Exportera Customer Insights-data till Constant Contact
description: Lär dig hur du konfigurerar anslutningen och exporterar till Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760646"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="a9a11-103">Exportera segmentlistor till Constant Contact (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="a9a11-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="a9a11-104">Exportera segment med enhetliga kundprofiler till Constant Contact och använd dem för marknadsföringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="a9a11-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a9a11-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="a9a11-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a9a11-106">Du har ett [Constant Contact-konto](https://www.constantcontact.com/account-home) och motsvarande autentiseringsuppgifter för administratör.</span><span class="sxs-lookup"><span data-stu-id="a9a11-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a9a11-107">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="a9a11-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a9a11-108">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="a9a11-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a9a11-109">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="a9a11-109">Known limitations</span></span>

- <span data-ttu-id="a9a11-110">Du kan exportera upp till en miljoner profiler per export till Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a9a11-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="a9a11-111">Export till Constant Contact är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="a9a11-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="a9a11-112">Det kan ta upp till 1 timme att exportera upp till 1 miljon profiler till Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a9a11-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="a9a11-113">Hur många profiler du kan exportera till Constant Contact beror på och begränsas av ditt kontrakt med Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a9a11-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="a9a11-114">Konfigurera anslutning till Constant Contact</span><span class="sxs-lookup"><span data-stu-id="a9a11-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="a9a11-115">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="a9a11-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a9a11-116">Välj **Lägg till anslutning** och välj **Constant Contact** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a9a11-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="a9a11-117">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="a9a11-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a9a11-118">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="a9a11-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a9a11-119">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a9a11-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a9a11-120">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a9a11-120">Choose who can use this connection.</span></span> <span data-ttu-id="a9a11-121">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="a9a11-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a9a11-122">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a9a11-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a9a11-123">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="a9a11-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a9a11-124">Välj **Anslut** om du vill initiera anslutningen till Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a9a11-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="a9a11-125">Välj **Autentisera med AdRoll** och ange dina administratörsuppgifter för Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a9a11-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="a9a11-126">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a9a11-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a9a11-127">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a9a11-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a9a11-128">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="a9a11-128">Configure an export</span></span>

<span data-ttu-id="a9a11-129">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="a9a11-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a9a11-130">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a9a11-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a9a11-131">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a9a11-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a9a11-132">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="a9a11-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a9a11-133">I fältet **Anslutning för export**, välj en anslutning från avsnittet Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a9a11-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="a9a11-134">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="a9a11-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a9a11-135">Ange din [**Constant Contact list-ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="a9a11-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="a9a11-136">Öppna en lista i Constant Contact för att hitta list-ID:t i URL:en.</span><span class="sxs-lookup"><span data-stu-id="a9a11-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="a9a11-137">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="a9a11-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a9a11-138">Det krävs att exportera segment till Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a9a11-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="a9a11-139">Alternativt kan du exportera Förnamn och Efternamn som ytterligare fält för att skapa mer personligt anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a9a11-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="a9a11-140">Välj **Lägg till attribut** för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="a9a11-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a9a11-141">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="a9a11-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="a9a11-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a9a11-142">Select **Save**.</span></span>

<span data-ttu-id="a9a11-143">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="a9a11-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a9a11-144">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9a11-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a9a11-145">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a9a11-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a9a11-146">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="a9a11-146">Data privacy and compliance</span></span>

<span data-ttu-id="a9a11-147">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Constant Contact, du tillåter överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a9a11-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a9a11-148">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Constant Contact uppfyller alla eventuella sekretess- eller säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="a9a11-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a9a11-149">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a9a11-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a9a11-150">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="a9a11-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
