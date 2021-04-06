---
title: Exportera Customer Insights-data till DotDigital
description: Lär dig hur du konfigurerar anslutningen till DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598039"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="69ca5-103">Anslutningsprogram för DotDigital (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="69ca5-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="69ca5-104">Exportera segment med enhetliga kundprofiler till DotDigital-adressböcker och använd dem för kampanjer, skicka marknadsföring via e-post och skapa kundsegment med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="69ca5-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="69ca5-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="69ca5-105">Prerequisites</span></span>

-   <span data-ttu-id="69ca5-106">Du har ett [DotDigital-konto](https://dotdigital.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="69ca5-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="69ca5-107">Det finns befintliga adressböcker i DotDigital och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="69ca5-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="69ca5-108">ID hittar du i URL-adressen när du väljer och öppnar en adressbok.</span><span class="sxs-lookup"><span data-stu-id="69ca5-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="69ca5-109">Mer information finns i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="69ca5-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="69ca5-110">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="69ca5-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="69ca5-111">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="69ca5-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="69ca5-112">Ansluta till DotDigital</span><span class="sxs-lookup"><span data-stu-id="69ca5-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="69ca5-113">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="69ca5-114">Under **DotDigita** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="69ca5-115">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurationsfönster för DotDigital-export.":::

1. <span data-ttu-id="69ca5-117">Ange ditt **användarnamn och lösenord för DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="69ca5-118">Ange ditt **[ID till DotDigital-adressboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="69ca5-119">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="69ca5-120">Välj **Anslut** om du vill initiera anslutningen till DotDigital.</span><span class="sxs-lookup"><span data-stu-id="69ca5-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="69ca5-121">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="69ca5-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="69ca5-122">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="69ca5-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="69ca5-123">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="69ca5-123">Configure the connector</span></span>

1. <span data-ttu-id="69ca5-124">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="69ca5-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="69ca5-125">Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Fullständigt namn**, **Kön** och **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="69ca5-126">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="69ca5-126">Select the segments you want to export.</span></span> <span data-ttu-id="69ca5-127">Du kan exportera upp till totalt 1 000 000 kundprofiler till DotDigital.</span><span class="sxs-lookup"><span data-stu-id="69ca5-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="69ca5-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="69ca5-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="69ca5-129">Exportera data</span><span class="sxs-lookup"><span data-stu-id="69ca5-129">Export the data</span></span>

<span data-ttu-id="69ca5-130">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="69ca5-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="69ca5-131">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="69ca5-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="69ca5-132">I DotDigital kan du nu hitta segment i [DotDigitals adressböcker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="69ca5-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="69ca5-133">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="69ca5-133">Known limitations</span></span>

- <span data-ttu-id="69ca5-134">Upp till 1 000 000 profiler per export till DotDigital.</span><span class="sxs-lookup"><span data-stu-id="69ca5-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="69ca5-135">Export till DotDigital är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="69ca5-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="69ca5-136">Export av segment med totalt 1 000 000 profiler kan ta upp till 3 timmar på grund av begränsningar på leverantörens sida.</span><span class="sxs-lookup"><span data-stu-id="69ca5-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="69ca5-137">Antalet profiler som du kan exportera till DotDigital är beroende av och begränsat enligt ditt kontrakt med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="69ca5-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="69ca5-138">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="69ca5-138">Data privacy and compliance</span></span>

<span data-ttu-id="69ca5-139">När du aktiverar Dynamics 365 Customer Insights för att överföra data till DotDigital tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="69ca5-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="69ca5-140">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att DotDigital uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="69ca5-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="69ca5-141">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="69ca5-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="69ca5-142">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="69ca5-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]