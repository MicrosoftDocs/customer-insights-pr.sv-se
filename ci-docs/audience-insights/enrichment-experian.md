---
title: Berikning med tredjepartsberikningen Experian
description: Allmän information om tredjepartsberikningen Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896395"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="10beb-103">Berika kundprofiler med demografisk information från Experian (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="10beb-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="10beb-104">Experian är en global ledare inom konsument- och affärskreditrapportering och marknadsföringstjänster.</span><span class="sxs-lookup"><span data-stu-id="10beb-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="10beb-105">Med Experians databerikningstjänster kan du skapa en djupare förståelse för dina kunder genom att berika dina kundprofiler med demografiska uppgifter som hushållsstorlek, inkomst och mer.</span><span class="sxs-lookup"><span data-stu-id="10beb-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10beb-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="10beb-106">Prerequisites</span></span>

<span data-ttu-id="10beb-107">För att konfigurera Experian måste följande villkor vara uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="10beb-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="10beb-108">Du har en aktiv Experian-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="10beb-108">You have an active Experian subscription.</span></span> <span data-ttu-id="10beb-109">Om du vill få en prenumeration [kontaktar du Experian](https://www.experian.com/marketing-services/contact) direkt.</span><span class="sxs-lookup"><span data-stu-id="10beb-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="10beb-110">[Läs mer om Experian databerikande](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="10beb-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="10beb-111">En Experian-anslutning har redan konfigurerats av en administratör *eller* eller så har du [administratör](permissions.md#administrator) behörigheter.</span><span class="sxs-lookup"><span data-stu-id="10beb-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="10beb-112">Du behöver också användar-ID, part-ID och modellnummer för ditt SSH-konto (Secure Transport) som Experian har skapat åt dig.</span><span class="sxs-lookup"><span data-stu-id="10beb-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="10beb-113">Konfiguration av berikning</span><span class="sxs-lookup"><span data-stu-id="10beb-113">Configure the enrichment</span></span>

1. <span data-ttu-id="10beb-114">Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.</span><span class="sxs-lookup"><span data-stu-id="10beb-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="10beb-115">Välj **Berika mina data** på Experian-panelen.</span><span class="sxs-lookup"><span data-stu-id="10beb-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10beb-116">![Experian-panel](media/experian-tile.png "Experian-panel")</span><span class="sxs-lookup"><span data-stu-id="10beb-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="10beb-117">Välj en [anslutning](connections.md) från listrutan.</span><span class="sxs-lookup"><span data-stu-id="10beb-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="10beb-118">Kontakta en administratör om det inte finns någon anslutning.</span><span class="sxs-lookup"><span data-stu-id="10beb-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="10beb-119">Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja Experian från listrutan.</span><span class="sxs-lookup"><span data-stu-id="10beb-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="10beb-120">Välj **Anslut till Experian** för att bekräfta anslutningsvalet.</span><span class="sxs-lookup"><span data-stu-id="10beb-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="10beb-121">Välj **Nästa** och välj den **kunddatauppsättning** du vill utöka med demografi från Experian.</span><span class="sxs-lookup"><span data-stu-id="10beb-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="10beb-122">Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="10beb-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. <span data-ttu-id="10beb-124">Välj **Nästa** och definiera vilken typ av fält från dina enhetliga profiler som ska användas för att söka efter matchande demografi från Experian.</span><span class="sxs-lookup"><span data-stu-id="10beb-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="10beb-125">Minst ett av fälten **Namn och adress**, **Telefon** eller **E-post** krävs.</span><span class="sxs-lookup"><span data-stu-id="10beb-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="10beb-126">För en bättre matchning kan du lägga till upp till två andra fält.</span><span class="sxs-lookup"><span data-stu-id="10beb-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="10beb-127">Det här valet påverkar mappningsfälten du har åtkomst till i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="10beb-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="10beb-128">Fler nyckel-ID-attribut som skickas till Experian ger troligen en högre matchningsfrekvens.</span><span class="sxs-lookup"><span data-stu-id="10beb-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="10beb-129">Välj **Nästa** för att starta fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="10beb-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="10beb-130">Definiera vilka fält från dina enhetliga profiler som ska användas för att leta efter matchande demografiska data från Experian.</span><span class="sxs-lookup"><span data-stu-id="10beb-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="10beb-131">Behövliga fält är markerade.</span><span class="sxs-lookup"><span data-stu-id="10beb-131">Required fields are marked.</span></span>

1. <span data-ttu-id="10beb-132">Ange ett namn för berikningen och ett namn för den utgående enheten.</span><span class="sxs-lookup"><span data-stu-id="10beb-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="10beb-133">Välj **Spara berikning** när du har granskat dina val.</span><span class="sxs-lookup"><span data-stu-id="10beb-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="10beb-134">Konfigurera anslutningen för Experian</span><span class="sxs-lookup"><span data-stu-id="10beb-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="10beb-135">Du måste vara en administratör för att konfigurera anslutningar.</span><span class="sxs-lookup"><span data-stu-id="10beb-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="10beb-136">Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på Experian-panelen.</span><span class="sxs-lookup"><span data-stu-id="10beb-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="10beb-137">Välj **Komma igång**.</span><span class="sxs-lookup"><span data-stu-id="10beb-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="10beb-138">Ange ett namn för anslutningen i rutan **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="10beb-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="10beb-139">Ange giltigt användar-ID, parti-ID och modellnummer för ditt Experian Secure Transport-konto.</span><span class="sxs-lookup"><span data-stu-id="10beb-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="10beb-140">Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**</span><span class="sxs-lookup"><span data-stu-id="10beb-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="10beb-141">Välj **Verifiera** om konfigurationen ska verifieras.</span><span class="sxs-lookup"><span data-stu-id="10beb-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="10beb-142">Välj **Spara** när verifieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="10beb-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Konfigurationsfönster för Experian-anslutning":::

## <a name="enrichment-results"></a><span data-ttu-id="10beb-144">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="10beb-144">Enrichment results</span></span>

<span data-ttu-id="10beb-145">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="10beb-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="10beb-146">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="10beb-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="10beb-147">Bearbetningstiden beror på storleken på kundens data och de eventuella processer som har konfigurerats för ditt konto av Experian.</span><span class="sxs-lookup"><span data-stu-id="10beb-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="10beb-148">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="10beb-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="10beb-149">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="10beb-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="10beb-150">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="10beb-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10beb-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="10beb-151">Next steps</span></span>

<span data-ttu-id="10beb-152">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="10beb-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="10beb-153">Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="10beb-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="10beb-154">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="10beb-154">Data privacy and compliance</span></span>

<span data-ttu-id="10beb-155">När du aktiverar Dynamics 365 Customer Insights för att överföra data till Experian tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="10beb-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="10beb-156">Microsoft kommer att överföra dessa data i din instruktion, men du ansvarar för att Experian uppfyller de sekretess- eller säkerhetskrav som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="10beb-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="10beb-157">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="10beb-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="10beb-158">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="10beb-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
