---
title: Exportera Customer Insights-data till Sendinblue
description: Lär dig hur du konfigurerar anslutningen och exporterar till Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314682"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="79db9-103">Exportera segment till Sendinblue (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="79db9-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="79db9-104">Exportera segment från enhetliga kundprofiler i syfte att generera kampanjer, skapa e-postmarknadsföring och använda specifika kundgrupper med Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="79db9-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="79db9-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="79db9-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="79db9-106">Du har ett [Sendinblue-konto](https://www.sendinblue.com/) och motsvarande autentiseringsuppgifter för administratör.</span><span class="sxs-lookup"><span data-stu-id="79db9-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="79db9-107">Det finns befintliga listor i Sendinblue och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="79db9-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="79db9-108">Du har [konfigurerat segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="79db9-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="79db9-109">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="79db9-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="79db9-110">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="79db9-110">Known limitations</span></span>

- <span data-ttu-id="79db9-111">Upp till 1 miljoner profiler per export till Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="79db9-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="79db9-112">Exporten till Sendinblue är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="79db9-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="79db9-113">Det kan ta upp till 90 minuter att exportera segment med totalt 1 miljoner profiler.</span><span class="sxs-lookup"><span data-stu-id="79db9-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="79db9-114">Antalet profiler du kan exportera till Sendinblue beror på och begränsas efter ditt kontrakt med Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="79db9-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="79db9-115">Konfigurera anslutning till Sendinblue</span><span class="sxs-lookup"><span data-stu-id="79db9-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="79db9-116">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="79db9-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="79db9-117">Välj **Lägg till anslutning** och välj **Sendinblue** om du vill konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="79db9-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="79db9-118">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="79db9-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="79db9-119">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="79db9-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="79db9-120">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="79db9-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="79db9-121">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="79db9-121">Choose who can use this connection.</span></span> <span data-ttu-id="79db9-122">Som standard är det bara administratörer.</span><span class="sxs-lookup"><span data-stu-id="79db9-122">By default it's only administrators.</span></span> <span data-ttu-id="79db9-123">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="79db9-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="79db9-124">Ange din **[SendinBlue API-nyckel](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="79db9-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="79db9-125">Välj **Jag godkänner** för att bekräfta **Datasekretess och efterlevnad** och välj **Anslut** för att initiera anslutningen till Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="79db9-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="79db9-126">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="79db9-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="79db9-127">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="79db9-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="79db9-128">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="79db9-128">Configure an export</span></span>

<span data-ttu-id="79db9-129">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="79db9-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="79db9-130">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="79db9-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="79db9-131">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="79db9-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="79db9-132">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="79db9-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="79db9-133">I fältet **Anslutning för export** väljer du en anslutning från avsnittet Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="79db9-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="79db9-134">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="79db9-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="79db9-135">Ange ditt **List-ID för Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="79db9-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="79db9-136">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="79db9-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="79db9-137">Alternativt kan du exportera **Förnamn**, **Efternamn** och **Telefonnummer** om du vill skapa mer anpassade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="79db9-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="79db9-138">Välj **Lägg till attribut** för att mappa dessa fält.</span><span class="sxs-lookup"><span data-stu-id="79db9-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="79db9-139">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="79db9-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="79db9-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="79db9-140">Select **Save**.</span></span>

<span data-ttu-id="79db9-141">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="79db9-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="79db9-142">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="79db9-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="79db9-143">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="79db9-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79db9-144">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="79db9-144">Data privacy and compliance</span></span>

<span data-ttu-id="79db9-145">När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till Sendinblue tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="79db9-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79db9-146">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Sendinblue uppfyller dina eventuella sekretess- och säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="79db9-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="79db9-147">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="79db9-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="79db9-148">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="79db9-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
