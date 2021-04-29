---
title: Exportera Customer Insights-data till DotDigital
description: Lär dig hur du konfigurerar anslutningen och exporterar till DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759981"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="fa1c5-103">Exportera segmentlistor till DotDigital (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="fa1c5-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="fa1c5-104">Exportera segment med enhetliga kundprofiler till DotDigital-adressböcker och använd dem för kampanjer, skicka marknadsföring via e-post och skapa kundsegment med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="fa1c5-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="fa1c5-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="fa1c5-106">Du har ett [DotDigital-konto](https://dotdigital.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fa1c5-107">Det finns befintliga adressböcker i DotDigital och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="fa1c5-108">ID hittar du i URL-adressen när du väljer och öppnar en adressbok.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="fa1c5-109">Mer information finns i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="fa1c5-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="fa1c5-110">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fa1c5-111">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fa1c5-112">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="fa1c5-112">Known limitations</span></span>

- <span data-ttu-id="fa1c5-113">Upp till 1 000 000 profiler per export till DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="fa1c5-114">Export till DotDigital är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="fa1c5-115">Export av segment med totalt 1 000 000 profiler kan ta upp till 3 timmar på grund av begränsningar på leverantörens sida.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="fa1c5-116">Antalet profiler som du kan exportera till DotDigital är beroende av och begränsat enligt ditt kontrakt med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="fa1c5-117">Konfigurera anslutningen DotDigital</span><span class="sxs-lookup"><span data-stu-id="fa1c5-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="fa1c5-118">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fa1c5-119">Välj **Lägg till anslutning** och välj **DotDigital** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="fa1c5-120">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fa1c5-121">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fa1c5-122">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fa1c5-123">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-123">Choose who can use this connection.</span></span> <span data-ttu-id="fa1c5-124">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fa1c5-125">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fa1c5-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fa1c5-126">Ange ditt **användarnamn och lösenord för DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="fa1c5-127">Ange ditt **[ID till DotDigital-adressboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="fa1c5-128">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fa1c5-129">Välj **Anslut** om du vill initiera anslutningen till DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="fa1c5-130">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fa1c5-131">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="fa1c5-132">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="fa1c5-132">Configure an export</span></span>

<span data-ttu-id="fa1c5-133">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fa1c5-134">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fa1c5-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fa1c5-135">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fa1c5-136">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fa1c5-137">I fältet **Anslutning för export**, välj en anslutning från avsnittet DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="fa1c5-138">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="fa1c5-139">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fa1c5-140">Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Fullständigt namn**, **Kön** och **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="fa1c5-141">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-141">Select the segments you want to export.</span></span> <span data-ttu-id="fa1c5-142">Du kan exportera upp till totalt 1 000 000 kundprofiler till DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="fa1c5-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-143">Select **Save**.</span></span>

<span data-ttu-id="fa1c5-144">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fa1c5-145">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fa1c5-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fa1c5-146">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fa1c5-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="fa1c5-147">I DotDigital kan du nu hitta segment i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="fa1c5-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fa1c5-148">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="fa1c5-148">Data privacy and compliance</span></span>

<span data-ttu-id="fa1c5-149">När du aktiverar Dynamics 365 Customer Insights för att överföra data till DotDigital tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fa1c5-150">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att DotDigital uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fa1c5-151">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fa1c5-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fa1c5-152">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="fa1c5-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
