---
title: Exportera Customer Insights-data till Salesforce Marketing Cloud
description: Lär dig hur du konfigurerar anslutningen och exporterar till Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314681"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="b4e33-103">Exportera segment och andra data till Salesforce Marketing Cloud (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="b4e33-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="b4e33-104">Använd dina kunddata i Salesforce Marketing Cloud genom att exportera dem via en plats för säkert filöverföringsprotokoll (SFTP).</span><span class="sxs-lookup"><span data-stu-id="b4e33-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b4e33-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="b4e33-105">Prerequisites for connection</span></span>

- <span data-ttu-id="b4e33-106">Tillgängligheten för en SFTP-värd och motsvarande administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b4e33-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="b4e33-107">Så här konfigurerar su SFTP-platser för Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="b4e33-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="b4e33-108">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="b4e33-108">Known limitations</span></span>

- <span data-ttu-id="b4e33-109">Hur länge en export körs beror på systemprestanda.</span><span class="sxs-lookup"><span data-stu-id="b4e33-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="b4e33-110">Vi rekommenderar två processorkärnor och 1 Gb minne som minimal konfiguration av servern.</span><span class="sxs-lookup"><span data-stu-id="b4e33-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="b4e33-111">Det kan ta 90 minuter att exportera entiteter med upp till 100 miljoner kundprofiler om den rekommenderade minimikonfigurationen används.</span><span class="sxs-lookup"><span data-stu-id="b4e33-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="b4e33-112">Konfigurera anslutningen till Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="b4e33-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="b4e33-113">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="b4e33-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b4e33-114">Välj **Lägg till anslutning** och välj **Salesforce Marketing Cloud** om du vill konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="b4e33-115">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="b4e33-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b4e33-116">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="b4e33-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b4e33-117">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b4e33-118">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-118">Choose who can use this connection.</span></span> <span data-ttu-id="b4e33-119">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="b4e33-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b4e33-120">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b4e33-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b4e33-121">Tillhandahåll **Användarnamn**, **Lösenord**, **Värdnamn** och **Exportmapp** för ditt SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="b4e33-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="b4e33-122">Välj **Verifiera** för att testa anslutningen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="b4e33-123">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="b4e33-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b4e33-124">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b4e33-125">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="b4e33-125">Configure an export</span></span>

<span data-ttu-id="b4e33-126">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b4e33-127">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b4e33-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b4e33-128">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="b4e33-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b4e33-129">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="b4e33-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b4e33-130">I fältet **Anslutning för export**, välj en anslutning från avsnittet SFTP.</span><span class="sxs-lookup"><span data-stu-id="b4e33-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="b4e33-131">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b4e33-132">Välj om du vill exportera dina data **Komprimerad** eller **Uppackad** och **fältavgränsaren** för de exporterade filerna.</span><span class="sxs-lookup"><span data-stu-id="b4e33-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="b4e33-133">Markera de entiteter, till exempel segment, som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="b4e33-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b4e33-134">Varje vald entitet delas upp i upp till fem utdatafiler när de exporteras.</span><span class="sxs-lookup"><span data-stu-id="b4e33-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="b4e33-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b4e33-135">Select **Save**.</span></span>

<span data-ttu-id="b4e33-136">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="b4e33-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b4e33-137">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b4e33-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b4e33-138">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b4e33-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="b4e33-139">Importera Customer Insights-data från SFTP-plats till Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="b4e33-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="b4e33-140">Skapa [datatillägg i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) för att importera datafilen för Customer Insights från SFTP-platsen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="b4e33-141">[Importera data från SFTP-platsen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) till datatillägget för Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="b4e33-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="b4e33-142">Konfigurera automatiseringen för att importera data till datatilläggen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="b4e33-143">Läs mer om [automatisering via filsläpp och schemalagda automatiseringar](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="b4e33-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="b4e33-144">Definiera ett [automatisering via filsläpp](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [schemalagd automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="b4e33-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="b4e33-145">Här följer ett exempel på [en automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="b4e33-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b4e33-146">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="b4e33-146">Data privacy and compliance</span></span>

<span data-ttu-id="b4e33-147">När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b4e33-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b4e33-148">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="b4e33-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b4e33-149">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b4e33-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b4e33-150">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="b4e33-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
