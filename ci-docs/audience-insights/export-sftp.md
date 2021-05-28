---
title: Exportera Customer Insights-data till SFTP-värdar
description: Lär dig hur du konfigurerar anslutningen och exporterar till SFTP-plats.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976961"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="04e00-103">Exportera segmentlistor och annan data till SFTP (förhandsvisning)</span><span class="sxs-lookup"><span data-stu-id="04e00-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="04e00-104">Använd kunddata i program från tredje part genom att exportera dem till en SFTP-plats (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="04e00-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="04e00-105">Krav för anslutning</span><span class="sxs-lookup"><span data-stu-id="04e00-105">Prerequisites for connection</span></span>

- <span data-ttu-id="04e00-106">Tillgänglighet för en STP-värd och motsvarande autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="04e00-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="04e00-107">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="04e00-107">Known limitations</span></span>

- <span data-ttu-id="04e00-108">Hur länge en export körs beror på systemprestanda.</span><span class="sxs-lookup"><span data-stu-id="04e00-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="04e00-109">Vi rekommenderar två processorkärnor och 1 Gb minne som minimal konfiguration av servern.</span><span class="sxs-lookup"><span data-stu-id="04e00-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="04e00-110">Det kan ta 90 minuter att exportera entiteter med upp till 100 miljoner kundprofiler om du använder den rekommenderade minimikonfigurationen på två processorkärnor och 1 Gb minne.</span><span class="sxs-lookup"><span data-stu-id="04e00-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="04e00-111">Konfigurera anslutningar till SFTP</span><span class="sxs-lookup"><span data-stu-id="04e00-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="04e00-112">Gå till **Admin** > **Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="04e00-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="04e00-113">Välj **Lägg till anslutning** och välj **SFTP** för att konfigurera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="04e00-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="04e00-114">Ge anslutningen ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="04e00-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="04e00-115">Namn och typen av anslutning beskriver en anslutning.</span><span class="sxs-lookup"><span data-stu-id="04e00-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="04e00-116">Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.</span><span class="sxs-lookup"><span data-stu-id="04e00-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="04e00-117">Välj vem som kan använda anslutningen.</span><span class="sxs-lookup"><span data-stu-id="04e00-117">Choose who can use this connection.</span></span> <span data-ttu-id="04e00-118">Om du inte gör något blir standardvärdet Administratörer.</span><span class="sxs-lookup"><span data-stu-id="04e00-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="04e00-119">Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="04e00-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="04e00-120">Tillhandahåll **Användarnamn**, **Lösenord**, **Värdnamn** och **Exportmapp** för ditt SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="04e00-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="04e00-121">Välj **Verifiera** för att testa anslutningen.</span><span class="sxs-lookup"><span data-stu-id="04e00-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="04e00-122">Välj om du vill exportera dina data **Komprimerad** eller **Uppackad** och **fältavgränsaren** för de exporterade filerna.</span><span class="sxs-lookup"><span data-stu-id="04e00-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="04e00-123">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="04e00-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="04e00-124">Välj **Spara** för att slutföra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="04e00-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="04e00-125">Konfigurera en export</span><span class="sxs-lookup"><span data-stu-id="04e00-125">Configure an export</span></span>

<span data-ttu-id="04e00-126">Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="04e00-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="04e00-127">Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="04e00-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="04e00-128">Gå till **Data** > **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="04e00-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="04e00-129">Välj för att skapa en ny export **Lägg till destination**.</span><span class="sxs-lookup"><span data-stu-id="04e00-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="04e00-130">I fältet **Anslutning för export**, välj en anslutning från avsnittet SFTP.</span><span class="sxs-lookup"><span data-stu-id="04e00-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="04e00-131">Om avsnittets namn inte visas finns det inga tillgängliga anslutningar av den här typen.</span><span class="sxs-lookup"><span data-stu-id="04e00-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="04e00-132">Markera de entiteter, till exempel segment, som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="04e00-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="04e00-133">Varje vald entitet delas upp i upp till fem utdatafiler när de exporteras.</span><span class="sxs-lookup"><span data-stu-id="04e00-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="04e00-134">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="04e00-134">Select **Save**.</span></span>

<span data-ttu-id="04e00-135">När du sparar en export körs inte exporten omedelbart.</span><span class="sxs-lookup"><span data-stu-id="04e00-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="04e00-136">Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="04e00-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="04e00-137">Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="04e00-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="04e00-138">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="04e00-138">Data privacy and compliance</span></span>

<span data-ttu-id="04e00-139">När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="04e00-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="04e00-140">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="04e00-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="04e00-141">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="04e00-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="04e00-142">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="04e00-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
