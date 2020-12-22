---
title: Exportera Customer Insights-data till Facebook Ads Manager
description: Lär dig hur du konfigurerar anslutningen till Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643705"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="f8f18-103">Koppling för Facebook Ads Manager (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="f8f18-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="f8f18-104">Exportera segment med enhetliga kundprofiler till Facebook Ads Manager för att skapa kampanjer på Facebook och Instagram.</span><span class="sxs-lookup"><span data-stu-id="f8f18-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8f18-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f8f18-105">Prerequisites</span></span>

- <span data-ttu-id="f8f18-106">Du måste ha ett [**Facebook Ad-konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) med ett [**Facebook Business-konto**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="f8f18-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="f8f18-107">Du måste vara en administratör på [**Facebook Ad-kontot**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="f8f18-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="f8f18-108">Ansluta till Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="f8f18-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="f8f18-109">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="f8f18-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f8f18-110">Under **Facebook Ads Manager**, välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="f8f18-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="f8f18-111">Ange ditt exportmål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="f8f18-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f8f18-112">Välj **Fortsätt med Facebook** för att logga in på ditt Facebook annonskonto.</span><span class="sxs-lookup"><span data-stu-id="f8f18-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="f8f18-113">Bevilja **ads_management**-behörighet efter autentisering med Facebook.</span><span class="sxs-lookup"><span data-stu-id="f8f18-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="f8f18-114">Välj det **Facebook Ads-konto** som du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="f8f18-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="f8f18-115">Välj en **befintlig anpassad publik** i listrutan eller skapa en **ny anpassad publik**.</span><span class="sxs-lookup"><span data-stu-id="f8f18-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="f8f18-116">Mer information finns i [**målgrupper i Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="f8f18-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="f8f18-117">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="f8f18-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f8f18-118">Välj **Nästa** du vill konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="f8f18-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f8f18-119">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="f8f18-119">Configure the connector</span></span>

1. <span data-ttu-id="f8f18-120">I fältet **Välj din nyckelidentifierare**, välj **E-post**, **Namn och adress** eller **Telefon** som ska skickas till Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="f8f18-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="f8f18-121">Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.</span><span class="sxs-lookup"><span data-stu-id="f8f18-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="f8f18-122">[TIPS] De bästa chanserna för en matchning uppstår om du väljer **E-post** som nyckelidentifierare.</span><span class="sxs-lookup"><span data-stu-id="f8f18-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="f8f18-123">Om du lägger till ytterligare identifierare kan matchningen förbättras.</span><span class="sxs-lookup"><span data-stu-id="f8f18-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="f8f18-124">Välj **Lägg till** om du vill mappa ytterligare attribut att skicka till Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="f8f18-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="f8f18-125">Attribut från Facebook Ads Manager mappar till följande användarvänliga namn: **FN** = **förnamn**, **LN** = **efternamn**, **FI** = **första initial**, **PHONE** = **telefon**, **GEN** = **kön**, **DOB** = **födelsedatum**, **ST** = **ort**, **CT** = **City**, **ZIP** = **postnummer**, **COUNTRY** = **land/region**</span><span class="sxs-lookup"><span data-stu-id="f8f18-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="f8f18-126">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="f8f18-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="f8f18-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f8f18-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f8f18-128">Exportera data</span><span class="sxs-lookup"><span data-stu-id="f8f18-128">Export the data</span></span>

<span data-ttu-id="f8f18-129">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f8f18-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f8f18-130">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f8f18-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f8f18-131">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="f8f18-131">Data privacy and compliance</span></span>

<span data-ttu-id="f8f18-132">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Facebook Ads Manager tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="f8f18-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f8f18-133">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Facebook Ads uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="f8f18-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f8f18-134">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f8f18-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f8f18-135">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="f8f18-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
