---
title: Exportera Customer Insights-data till SFTP-värdar
description: Lär dig hur du konfigurerar anslutningen till en SFTP-värd.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598407"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="1aac4-103">Koppling för SFTP (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="1aac4-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="1aac4-104">Du kan använda dina kunddata i program från tredje part genom att exportera dem till en SFTP-värd (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="1aac4-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1aac4-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="1aac4-105">Prerequisites</span></span>

- <span data-ttu-id="1aac4-106">Tillgänglighet för en STP-värd och motsvarande autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="1aac4-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="1aac4-107">Anslut till SFTP</span><span class="sxs-lookup"><span data-stu-id="1aac4-107">Connect to SFTP</span></span>

1. <span data-ttu-id="1aac4-108">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1aac4-109">Under **SFTP**, välj **Inställning**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="1aac4-110">Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1aac4-111">Tillhandahåll **Användarnamn**, **Lösenord**, **Värdnamn** och **Exportmapp** för ditt SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="1aac4-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="1aac4-112">Välj **Verifiera** för att testa anslutningen.</span><span class="sxs-lookup"><span data-stu-id="1aac4-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="1aac4-113">Efter verifieringen väljer du om du vill exportera dina data **g-zippade** eller **uppackade** och väljer **fältavgränsare** för de exporterade filerna.</span><span class="sxs-lookup"><span data-stu-id="1aac4-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="1aac4-114">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1aac4-115">Välj **Nästa** du vill börja konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="1aac4-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="1aac4-116">Konfigurera exporten</span><span class="sxs-lookup"><span data-stu-id="1aac4-116">Configure the export</span></span>

1. <span data-ttu-id="1aac4-117">Markera de entiteter, till exempel segment, som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="1aac4-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1aac4-118">Varje vald entitet kommer att vara upp till fem utdatafiler när de exporteras.</span><span class="sxs-lookup"><span data-stu-id="1aac4-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="1aac4-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1aac4-120">Exportera data</span><span class="sxs-lookup"><span data-stu-id="1aac4-120">Export the data</span></span>

<span data-ttu-id="1aac4-121">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1aac4-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1aac4-122">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1aac4-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1aac4-123">Kända begränsningar</span><span class="sxs-lookup"><span data-stu-id="1aac4-123">Known limitations</span></span>

- <span data-ttu-id="1aac4-124">Hur länge en export körs beror på systemprestanda.</span><span class="sxs-lookup"><span data-stu-id="1aac4-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="1aac4-125">Vi rekommenderar två processorkärnor och 1 Gb minne som minimal konfiguration av servern.</span><span class="sxs-lookup"><span data-stu-id="1aac4-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="1aac4-126">Det kan ta 90 minuter att exportera entiteter med upp till 100 miljoner kundprofiler om du använder den rekommenderade minimikonfigurationen på två processorkärnor och 1 Gb minne.</span><span class="sxs-lookup"><span data-stu-id="1aac4-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1aac4-127">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="1aac4-127">Data privacy and compliance</span></span>

<span data-ttu-id="1aac4-128">När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="1aac4-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1aac4-129">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="1aac4-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1aac4-130">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1aac4-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1aac4-131">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="1aac4-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]