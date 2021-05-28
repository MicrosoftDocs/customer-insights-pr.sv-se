---
title: Exportera Customer Insights-data till Mailchimp
description: Lär dig hur du konfigurerar anslutningen och exporterar till Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976177"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="ba03f-103">Exportera segmentlistor till Mailchimp (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="ba03f-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="ba03f-104">Exportera segment av enhetliga kundprofiler till Mailchimp för att skapa nyhetsbrev och e-postkampanjer.</span><span class="sxs-lookup"><span data-stu-id="ba03f-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ba03f-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="ba03f-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ba03f-106">Du har ett [Mailchimp-konto](https://mailchimp.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ba03f-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ba03f-107">Det finns befintliga målgrupper i Mailchimp och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="ba03f-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="ba03f-108">Mer information finns i [Målgrupper för Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="ba03f-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="ba03f-109">Du har [konfigurerat segment](segments.md)</span><span class="sxs-lookup"><span data-stu-id="ba03f-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="ba03f-110">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ba03f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ba03f-111">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="ba03f-111">Known limitations</span></span>

- <span data-ttu-id="ba03f-112">Upp till 1 000 000 profiler per export till Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ba03f-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="ba03f-113">Export till Mailchimp är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="ba03f-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="ba03f-114">Det kan ta upp till tre timmar att exportera segment med en miljon profiler.</span><span class="sxs-lookup"><span data-stu-id="ba03f-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="ba03f-115">Antalet profiler som du kan exportera till Mailchimp är beroende av och begränsat enligt ditt kontrakt med Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ba03f-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="ba03f-116">Konfigurera anslutningen Mailchimp</span><span class="sxs-lookup"><span data-stu-id="ba03f-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="ba03f-117">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="ba03f-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ba03f-118">Välj **Lägg till anslutning** och välj **Autopilot** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ba03f-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="ba03f-119">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="ba03f-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ba03f-120">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="ba03f-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ba03f-121">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ba03f-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ba03f-122">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ba03f-122">Choose who can use this connection.</span></span> <span data-ttu-id="ba03f-123">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="ba03f-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ba03f-124">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ba03f-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ba03f-125">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="ba03f-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ba03f-126">Välj **Anslut** om du vill initiera anslutningen till Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ba03f-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="ba03f-127">Välj **Autentisera med Mailchimp** och ange dina Mailchimp-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ba03f-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="ba03f-128">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba03f-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ba03f-129">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="ba03f-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="ba03f-130">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="ba03f-130">Configure the connector</span></span>

<span data-ttu-id="ba03f-131">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="ba03f-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ba03f-132">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ba03f-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ba03f-133">Gå till **Data**> **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="ba03f-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="ba03f-134">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="ba03f-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ba03f-135">I fältet **Anslutning för export**, välj en anslutning från avsnittet Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ba03f-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="ba03f-136">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="ba03f-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ba03f-137">Ange din **[Målgrupps-ID för Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="ba03f-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="ba03f-138">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ba03f-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ba03f-139">Alternativt kan du exportera **Förnamn** och **Efternamn** för att skapa mer anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ba03f-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="ba03f-140">Välj **Lägg till attribut** för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="ba03f-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ba03f-141">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="ba03f-141">Select the segments you want to export.</span></span> <span data-ttu-id="ba03f-142">Du kan exportera upp till totalt 1 000 000 kundprofiler till Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ba03f-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="ba03f-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba03f-143">Select **Save**.</span></span>

<span data-ttu-id="ba03f-144">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="ba03f-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ba03f-145">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ba03f-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ba03f-146">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ba03f-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ba03f-147">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="ba03f-147">Data privacy and compliance</span></span>

<span data-ttu-id="ba03f-148">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Mailchimp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ba03f-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ba03f-149">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Mailchimp uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="ba03f-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ba03f-150">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ba03f-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ba03f-151">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="ba03f-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
