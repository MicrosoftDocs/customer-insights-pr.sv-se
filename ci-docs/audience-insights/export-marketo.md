---
title: Exportera Customer Insights-data till Marketo
description: Lär dig hur du konfigurerar anslutningen och exporterar till Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059338"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="d9108-103">Exportera segment till Marketo (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="d9108-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="d9108-104">Exportera segment av enhetliga kundprofiler för att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Marketo.</span><span class="sxs-lookup"><span data-stu-id="d9108-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d9108-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="d9108-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="d9108-106">Du har ett [Marketo-konto](https://login.marketo.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d9108-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d9108-107">Det finns befintliga listor i Marketo och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="d9108-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="d9108-108">Mer information finns på [Marketo-listor](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="d9108-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="d9108-109">Du har [konfigurerat segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d9108-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="d9108-110">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d9108-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d9108-111">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="d9108-111">Known limitations</span></span>

- <span data-ttu-id="d9108-112">Upp till 1 000 000 profiler per export till Marketo.</span><span class="sxs-lookup"><span data-stu-id="d9108-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="d9108-113">Export till Marketo är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="d9108-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="d9108-114">Det kan ta upp till 3 timmar att exportera segment med totalt 1 000 000 profiler.</span><span class="sxs-lookup"><span data-stu-id="d9108-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="d9108-115">Antalet profiler som du kan exportera till Marketo är beroende av och begränsat enligt ditt kontrakt med Marketo.</span><span class="sxs-lookup"><span data-stu-id="d9108-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="d9108-116">Upprätta anslutningen till Marketo</span><span class="sxs-lookup"><span data-stu-id="d9108-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="d9108-117">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="d9108-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d9108-118">Välj **Lägg till anslutning** och välj **Marketo** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9108-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="d9108-119">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="d9108-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d9108-120">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="d9108-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d9108-121">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9108-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d9108-122">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9108-122">Choose who can use this connection.</span></span> <span data-ttu-id="d9108-123">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="d9108-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d9108-124">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d9108-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d9108-125">Ange ditt **[klient-ID för Marketo, din klienthemlighet och slutpunktsvärdnamnet för REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="d9108-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="d9108-126">Endast slutpunktsvärdnamn för REST utan `https://`.</span><span class="sxs-lookup"><span data-stu-id="d9108-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="d9108-127">Exempel: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="d9108-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="d9108-128">Välj **Jag godkänner** för att bekräfta **datasekretess och regelefterlevnad** och välj **Anslut** för att initiera anslutningen till Marketo.</span><span class="sxs-lookup"><span data-stu-id="d9108-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="d9108-129">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d9108-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d9108-130">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="d9108-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d9108-131">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="d9108-131">Configure an export</span></span>

<span data-ttu-id="d9108-132">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="d9108-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d9108-133">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d9108-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d9108-134">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="d9108-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d9108-135">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="d9108-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d9108-136">I fältet **Anslutning för export**, välj en anslutning från avsnittet Marketo.</span><span class="sxs-lookup"><span data-stu-id="d9108-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="d9108-137">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="d9108-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d9108-138">Ange ditt **[ID för Marketo-lista](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="d9108-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="d9108-139">List-ID:t är ett endast numeriskt värde.</span><span class="sxs-lookup"><span data-stu-id="d9108-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="d9108-140">Om ditt Marketo-list-ID är ST12345A7 tar du bort tecknet före och efter numeriska tecken och anger `12345`.</span><span class="sxs-lookup"><span data-stu-id="d9108-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="d9108-141">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d9108-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d9108-142">Alternativt kan du exportera **Förnamn**, **Efternamn**, **Ort**, **Delstat** och **Land/Region** för att skapa mer anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="d9108-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="d9108-143">Välj **Lägg till attribut** för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="d9108-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d9108-144">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="d9108-144">Select the segments you want to export.</span></span> <span data-ttu-id="d9108-145">Du kan exportera upp till totalt 1 000 000 kundprofiler till Marketo.</span><span class="sxs-lookup"><span data-stu-id="d9108-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="d9108-146">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d9108-146">Select **Save**.</span></span>

<span data-ttu-id="d9108-147">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="d9108-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d9108-148">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d9108-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d9108-149">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d9108-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="d9108-150">I Marketo kan du nu hitta dina segment under [Marketo-listor](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="d9108-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d9108-151">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="d9108-151">Data privacy and compliance</span></span>

<span data-ttu-id="d9108-152">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Marketo tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d9108-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d9108-153">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Marketo uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="d9108-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d9108-154">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d9108-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d9108-155">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="d9108-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
