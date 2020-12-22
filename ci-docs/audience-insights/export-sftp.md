---
title: Exportera Customer Insights-data till SFTP-värdar
description: Lär dig hur du konfigurerar anslutningen till en SFTP-värd.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643525"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="fb7ac-103">Koppling för SFTP (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="fb7ac-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="fb7ac-104">Du kan använda dina kunddata i program från tredje part genom att exportera dem till en SFTP-värd (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="fb7ac-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb7ac-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="fb7ac-105">Prerequisites</span></span>

- <span data-ttu-id="fb7ac-106">En SFTP-värd och motsvarande autentiseringsuppgifter är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="fb7ac-107">Anslut till SFTP</span><span class="sxs-lookup"><span data-stu-id="fb7ac-107">Connect to SFTP</span></span>

1. <span data-ttu-id="fb7ac-108">Gå till **Administratör** > **Exportera mål**.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fb7ac-109">Under **SFTP**, välj **Inställning**.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="fb7ac-110">Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fb7ac-111">Ange **Användarnamn**, **Lösenord** och **Värdnamn** för ditt SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="fb7ac-112">Exempel: Om din SFTP-servers rotmapp är /root/folder och du vill att data ska exporteras till /root/folder/ci_export_destination_folder bör värden vara sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="fb7ac-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="fb7ac-113">Välj **Verifiera** för att testa anslutningen.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="fb7ac-114">När du har verifierat den kan du välja om du vill exportera dina data som **komprimerad** eller **uppackad** och välja **fältavgränsare** för de exporterade filerna.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="fb7ac-115">Välj **Jag accepterar** för att bekräfta **datasekretess och kompatibilitet**.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fb7ac-116">Välj **Nästa** du vill börja konfigurera exporten.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="fb7ac-117">Konfigurera anslutningen</span><span class="sxs-lookup"><span data-stu-id="fb7ac-117">Configure the connection</span></span>

1. <span data-ttu-id="fb7ac-118">Välj **kundattributen** som ska exporteras.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="fb7ac-119">Du kan exportera ett eller flera attribut.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="fb7ac-120">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-120">Select **Next**.</span></span>

1. <span data-ttu-id="fb7ac-121">Välj de segment som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="fb7ac-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fb7ac-123">Exportera data</span><span class="sxs-lookup"><span data-stu-id="fb7ac-123">Export the data</span></span>

<span data-ttu-id="fb7ac-124">Du kan [Exportera data på begäran](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fb7ac-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fb7ac-125">Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fb7ac-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fb7ac-126">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="fb7ac-126">Data privacy and compliance</span></span>

<span data-ttu-id="fb7ac-127">När du aktiverar Dynamics 365 Customer Insights för att överföra data via SFTP tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fb7ac-128">Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att exportdestinationen uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fb7ac-129">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fb7ac-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fb7ac-130">Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="fb7ac-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
