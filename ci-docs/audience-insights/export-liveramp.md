---
title: LiveRamp anslutning
description: Lär dig hur du konfigurerar anslutningen och exporterar till LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760349"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="dbe9e-103">Exportera segment till LiveRamp&reg; (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="dbe9e-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="dbe9e-104">Aktivera dina data i LiveRamp för att ansluta till över 500 plattformar på digitala, sociala och TV.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="dbe9e-105">Arbeta med dina data i LiveRamp om du vill rikta, undertrycka och anpassa AD-kampanjer.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="dbe9e-106">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="dbe9e-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="dbe9e-107">Du måste ha en LiveRamp-prenumeration om du vill använda den här anslutningen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="dbe9e-108">Om du vill få en prenumeration [kontaktar du LiveRamp](https://liveramp.com/contact/) direkt.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="dbe9e-109">[Läs mer om LiveRamp-registrering](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="dbe9e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="dbe9e-110">Konfigurera anslutningen LiveRamp</span><span class="sxs-lookup"><span data-stu-id="dbe9e-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="dbe9e-111">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dbe9e-112">Välj **Lägg till anslutning** och välj **LiveRamp** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="dbe9e-113">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dbe9e-114">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dbe9e-115">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dbe9e-116">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-116">Choose who can use this connection.</span></span> <span data-ttu-id="dbe9e-117">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dbe9e-118">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dbe9e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dbe9e-119">Ange ett **användarnamn** och **lösenord** för ditt LiveRamp-skyddade FTP-konto (SFTP).</span><span class="sxs-lookup"><span data-stu-id="dbe9e-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="dbe9e-120">Autentiseringsuppgifterna kan skilja sig från dina autentiseringsuppgifter för LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="dbe9e-121">Välj **kontrollera** för att testa anslutningen till LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="dbe9e-122">När du har verifierat klart anger du ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dbe9e-123">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dbe9e-124">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="dbe9e-124">Configure an export</span></span>

<span data-ttu-id="dbe9e-125">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dbe9e-126">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dbe9e-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dbe9e-127">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dbe9e-128">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dbe9e-129">I fältet **Anslutning för export**, välj en anslutning från avsnittet LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="dbe9e-130">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dbe9e-131">I fältet **Välj din nyckelidentifierare** välj **E-post**,  **Namn och adress** eller **Telefon** att skicka till LiveRamp för identitetsmatchning.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbe9e-132">![LiveRamp-koppling med attributmappning](media/export-liveramp-segments.png "LiveRamp-koppling med attributmappning")</span><span class="sxs-lookup"><span data-stu-id="dbe9e-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="dbe9e-133">Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="dbe9e-134">Välj **Lägg till attribut** för att mappa fler attribut som ska skickas till LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="dbe9e-135">Om du skickar fler attribut för nyckelidentifierare till LiveRamp får du troligen en högre matchningsfrekvens.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="dbe9e-136">Markera de segment du vill exportera till LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="dbe9e-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-137">Select **Save**.</span></span>

<span data-ttu-id="dbe9e-138">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dbe9e-139">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dbe9e-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dbe9e-140">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dbe9e-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dbe9e-141">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="dbe9e-141">Data privacy and compliance</span></span>

<span data-ttu-id="dbe9e-142">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Liveramp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dbe9e-143">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Liveramp uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dbe9e-144">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dbe9e-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dbe9e-145">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="dbe9e-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
