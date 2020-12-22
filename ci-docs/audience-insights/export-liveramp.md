---
title: LiveRamp anslutning
description: Lär dig hur du exporterar data till LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667206"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="8c29f-103">LiveRamp&reg; kontakt (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="8c29f-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="8c29f-104">Aktivera dina data i LiveRamp om du vill ansluta med över 500 plattformar över digitala, sociala och TV-ekosystem.</span><span class="sxs-lookup"><span data-stu-id="8c29f-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="8c29f-105">Arbeta med dina data i LiveRamp om du vill rikta, undertrycka och anpassa AD-kampanjer.</span><span class="sxs-lookup"><span data-stu-id="8c29f-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c29f-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="8c29f-106">Prerequisites</span></span>

- <span data-ttu-id="8c29f-107">Du måste ha en LiveRamp-prenumeration om du vill använda den här anslutningen.</span><span class="sxs-lookup"><span data-stu-id="8c29f-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="8c29f-108">Om du vill få en prenumeration [kontaktar du LiveRamp](https://liveramp.com/contact/) direkt.</span><span class="sxs-lookup"><span data-stu-id="8c29f-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="8c29f-109">[Läs mer om LiveRamp-registrering](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="8c29f-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="8c29f-110">Anslut till LiveRamp</span><span class="sxs-lookup"><span data-stu-id="8c29f-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="8c29f-111">I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="8c29f-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8c29f-112">I panelen **LiveRamp** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="8c29f-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="8c29f-113">Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="8c29f-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8c29f-114">Ange ett **användarnamn** och **lösenord** för ditt LiveRamp-skyddade FTP-konto (SFTP).</span><span class="sxs-lookup"><span data-stu-id="8c29f-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="8c29f-115">Autentiseringsuppgifterna kan skilja sig från dina autentiseringsuppgifter för LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="8c29f-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="8c29f-116">Välj **kontrollera** för att testa anslutningen till LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="8c29f-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="8c29f-117">När du har verifierat klart anger du ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="8c29f-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="8c29f-118">Välj **Nästa** om du vill konfigurera LiveRamp-kopplingen.</span><span class="sxs-lookup"><span data-stu-id="8c29f-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8c29f-119">Konfigurera kopplingen</span><span class="sxs-lookup"><span data-stu-id="8c29f-119">Configure the connector</span></span>

1. <span data-ttu-id="8c29f-120">I fältet **Välj din nyckelidentifierare** välj **E-post**,  **Namn och adress** eller **Telefon** att skicka till LiveRamp för identitetsmatchning.</span><span class="sxs-lookup"><span data-stu-id="8c29f-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="8c29f-121">Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.</span><span class="sxs-lookup"><span data-stu-id="8c29f-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="8c29f-122">Välj **Lägg till attribut** om du vill mappa ytterligare attribut att skicka till LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="8c29f-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="8c29f-123">Om du skickar fler attribut för nyckelidentifierare till LiveRamp får du troligen en högre matchningsfrekvens.</span><span class="sxs-lookup"><span data-stu-id="8c29f-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="8c29f-124">Markera de segment du vill exportera till LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="8c29f-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="8c29f-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c29f-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8c29f-126">![LiveRamp-koppling med attributmappning](media/export-liveramp-segments.png "LiveRamp-koppling med attributmappning")</span><span class="sxs-lookup"><span data-stu-id="8c29f-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8c29f-127">Exportera data</span><span class="sxs-lookup"><span data-stu-id="8c29f-127">Export the data</span></span>

<span data-ttu-id="8c29f-128">Exporten startar kort om alla nödvändiga förutsättningar för exporten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="8c29f-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="8c29f-129">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8c29f-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="8c29f-130">När exporten har slutförts kan du logga in på LiveRamp-registrering för att aktivera och distribuera dina data.</span><span class="sxs-lookup"><span data-stu-id="8c29f-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8c29f-131">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="8c29f-131">Data privacy and compliance</span></span>

<span data-ttu-id="8c29f-132">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Liveramp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="8c29f-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8c29f-133">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Liveramp uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="8c29f-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8c29f-134">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8c29f-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8c29f-135">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="8c29f-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>