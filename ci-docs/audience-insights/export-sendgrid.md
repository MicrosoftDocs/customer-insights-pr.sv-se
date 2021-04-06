---
title: Exportera Customer Insights-data till SendGrid
description: Lär dig hur du konfigurerar anslutningen till SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597303"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="0329c-103">Anslutningsprogram för SendGrid (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0329c-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="0329c-104">Exportera segment med enhetliga kundprofiler till SendGrid-kontaktlistor och använd dem för kampanjer och e-postmarknadsföring i SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0329c-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0329c-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="0329c-105">Prerequisites</span></span>

-   <span data-ttu-id="0329c-106">Du har ett [SendGrid-konto](https://sendgrid.com/) och motsvarande administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="0329c-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0329c-107">Det finns befintliga kontaktlistor i SendGrid och motsvarande ID.</span><span class="sxs-lookup"><span data-stu-id="0329c-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="0329c-108">Mer information finns i [SendGrid – Hantera kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="0329c-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="0329c-109">Du har [konfigurerade segment](segments.md) i målgruppsinsikter.</span><span class="sxs-lookup"><span data-stu-id="0329c-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0329c-110">Enhetliga kundprofiler i de exporterade segmenten innehåller ett fält som representerar en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="0329c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="0329c-111">Ansluta till SendGrid</span><span class="sxs-lookup"><span data-stu-id="0329c-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="0329c-112">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="0329c-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0329c-113">Under **SendGrid** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="0329c-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="0329c-114">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="0329c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Konfigurationsfönstret för export av SendGrid.":::

1. <span data-ttu-id="0329c-116">Ange **SendGrids API-nyckel** [SendGrids API-nyckel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="0329c-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="0329c-117">Ange ditt **[ID för SendGrid-lista](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="0329c-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="0329c-118">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="0329c-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0329c-119">Välj **Anslut** om du vill initiera anslutningen till SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0329c-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="0329c-120">Välj **Lägg till dig själv som exportanvändare** och ange dina autentiseringsuppgifter för Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0329c-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0329c-121">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="0329c-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0329c-122">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="0329c-122">Configure the connector</span></span>

1. <span data-ttu-id="0329c-123">I avsnittet **Datamatchning**, i fältet **E-post**, väljer du det fält i din enhetliga kundprofil som representerar en kunds e-postadress.</span><span class="sxs-lookup"><span data-stu-id="0329c-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0329c-124">Upprepa samma steg för andra valfria fält, t.ex. **Förnamn**, **Efternamn**, **Land/region**, **Delstat**, **Stad** och **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="0329c-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="0329c-125">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="0329c-125">Select the segments you want to export.</span></span> <span data-ttu-id="0329c-126">Vi **rekommenderar starkt att du inte exporterar fler än 100 000 kundprofiler totalt** till SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0329c-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="0329c-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0329c-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0329c-128">Exportera data</span><span class="sxs-lookup"><span data-stu-id="0329c-128">Export the data</span></span>

<span data-ttu-id="0329c-129">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0329c-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0329c-130">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0329c-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0329c-131">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="0329c-131">Known limitations</span></span>

- <span data-ttu-id="0329c-132">Upp till 100 000 profiler totalt till SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0329c-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="0329c-133">Export till SendGrid är begränsad till segment.</span><span class="sxs-lookup"><span data-stu-id="0329c-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="0329c-134">Att exportera upp till 100 000 profiler till SendGrid kan ta upp till några timmar att genomföra.</span><span class="sxs-lookup"><span data-stu-id="0329c-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0329c-135">Antalet profiler som du kan exportera till SendGrid är beroende av och begränsat enligt ditt kontrakt med SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0329c-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0329c-136">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="0329c-136">Data privacy and compliance</span></span>

<span data-ttu-id="0329c-137">När du aktiverar Dynamics 365 Customer Insights för att överföra data till SendGrid tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="0329c-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0329c-138">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att SendGrid uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="0329c-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0329c-139">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0329c-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0329c-140">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="0329c-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]