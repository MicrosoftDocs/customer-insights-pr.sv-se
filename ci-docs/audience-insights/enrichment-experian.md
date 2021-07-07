---
title: Berikande med tredjepartsberikande Experian
description: Allmän information om tredjepartsberikande Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309842"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="5c32f-103">Berika kundprofiler med demografisk information från Experian (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="5c32f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="5c32f-104">Experian är en global ledare inom rapporterings- och marknadsföringstjänster för konsument- och affärskreditföretag.</span><span class="sxs-lookup"><span data-stu-id="5c32f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="5c32f-105">Med hjälp av tjänsterna för datatillägg från Experian kan du öka förståelsen för dina kunder genom att berika dina kundprofiler med demografisk information, t.ex. storlek, inkomst och mycket annat.</span><span class="sxs-lookup"><span data-stu-id="5c32f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5c32f-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="5c32f-106">Prerequisites</span></span>

<span data-ttu-id="5c32f-107">För att konfigurera Experian måste följande villkor vara uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="5c32f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5c32f-108">Du måste ha en aktiv prenumeration på Experian.</span><span class="sxs-lookup"><span data-stu-id="5c32f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="5c32f-109">Om du vill få en prenumeration [kontaktar du Experian](https://www.experian.com/marketing-services/contact) direkt.</span><span class="sxs-lookup"><span data-stu-id="5c32f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="5c32f-110">[Läs mer om Experian-databerikande](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="5c32f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="5c32f-111">En Experian-anslutning har redan konfigurerats av en administratör, *eller* också har du [administratärs](permissions.md#administrator)behörighet.</span><span class="sxs-lookup"><span data-stu-id="5c32f-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="5c32f-112">Du behöver också användar-ID, part-ID och modellnummer för ditt SSH-aktiverade ST-konto (Secure Transport) som Experian skapat åt dig.</span><span class="sxs-lookup"><span data-stu-id="5c32f-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="5c32f-113">Länder/regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="5c32f-113">Supported countries/regions</span></span>

<span data-ttu-id="5c32f-114">Vi stöder för närvarande endast berikande av kundprofiler i USA.</span><span class="sxs-lookup"><span data-stu-id="5c32f-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="5c32f-115">Konfiguration av berikning</span><span class="sxs-lookup"><span data-stu-id="5c32f-115">Configure the enrichment</span></span>

1. <span data-ttu-id="5c32f-116">Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="5c32f-117">Välj **Berika mina data** i Experian-panelen.</span><span class="sxs-lookup"><span data-stu-id="5c32f-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c32f-118">![Experian panel](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="5c32f-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="5c32f-119">Välj en [anslutning](connections.md) i listrutan.</span><span class="sxs-lookup"><span data-stu-id="5c32f-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="5c32f-120">Kontakta en administratör om det inte finns någon anslutning.</span><span class="sxs-lookup"><span data-stu-id="5c32f-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="5c32f-121">Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja Experian i listrutan.</span><span class="sxs-lookup"><span data-stu-id="5c32f-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="5c32f-122">Bekräfta **Anslut till Experian** genom att bekräfta anslutningsvalet.</span><span class="sxs-lookup"><span data-stu-id="5c32f-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="5c32f-123">Välj **Nästa** och välj **kunddatauppsättning** som du vill berika med demografisk information från Experian.</span><span class="sxs-lookup"><span data-stu-id="5c32f-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="5c32f-124">Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="5c32f-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. <span data-ttu-id="5c32f-126">Välj **Nästa** och definiera vilken typ av fält från dina enhetliga profiler som ska användas för att söka efter matchande data från Experian.</span><span class="sxs-lookup"><span data-stu-id="5c32f-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="5c32f-127">Minst ett av fälten **Namn och adress**, **Telefon** eller **E-post** krävs.</span><span class="sxs-lookup"><span data-stu-id="5c32f-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="5c32f-128">För en bättre matchning kan du lägga till upp till två andra fält.</span><span class="sxs-lookup"><span data-stu-id="5c32f-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="5c32f-129">Det här valet påverkar mappningsfälten du har åtkomst till i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="5c32f-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="5c32f-130">Fler attribut för nyckelidentifierare som skickas till Experian leder troligen till en högre matchningskvot.</span><span class="sxs-lookup"><span data-stu-id="5c32f-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="5c32f-131">Välj **Nästa** för att starta fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="5c32f-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="5c32f-132">Definiera vilka fält i dina enhetliga profiler som ska användas för att söka efter matchande demografiska data från Experian.</span><span class="sxs-lookup"><span data-stu-id="5c32f-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="5c32f-133">Behövliga fält är markerade.</span><span class="sxs-lookup"><span data-stu-id="5c32f-133">Required fields are marked.</span></span>

1. <span data-ttu-id="5c32f-134">Ange ett namn för berikningen och ett namn för den utgående enheten.</span><span class="sxs-lookup"><span data-stu-id="5c32f-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="5c32f-135">Välj **Spara berikning** när du har granskat dina val.</span><span class="sxs-lookup"><span data-stu-id="5c32f-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="5c32f-136">Konfigurera anslutningen för Experian</span><span class="sxs-lookup"><span data-stu-id="5c32f-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="5c32f-137">Du måste vara en administratör för att konfigurera anslutningar.</span><span class="sxs-lookup"><span data-stu-id="5c32f-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="5c32f-138">Välj **Lägg till anslutning** när du konfigurerar ett berikande *eller* gå till **Administratör** > **Anslutningar** och välj **Konfigurera** i Experian-panelen.</span><span class="sxs-lookup"><span data-stu-id="5c32f-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="5c32f-139">Välj **Komma igång**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="5c32f-140">Ange ett namn för anslutningen i rutan **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="5c32f-141">Ange giltigt användar-ID, part-ID och modellnummer för ditt Experian-konto för säker transport.</span><span class="sxs-lookup"><span data-stu-id="5c32f-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="5c32f-142">Granska och ge ditt samtycke till **Data sekretess och efterlevnad** genom att välja **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="5c32f-143">Välj **Verifiera** om konfigurationen ska verifieras.</span><span class="sxs-lookup"><span data-stu-id="5c32f-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="5c32f-144">Välj **Spara** när verifieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="5c32f-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Konfigurationsruta för Experian-anslutning.":::

## <a name="enrichment-results"></a><span data-ttu-id="5c32f-146">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="5c32f-146">Enrichment results</span></span>

<span data-ttu-id="5c32f-147">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="5c32f-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="5c32f-148">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5c32f-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5c32f-149">Bearbetningstiden beror på storleken på dina kunddata och de berikningsprocesser som konfigurerats för ditt konto av Experian.</span><span class="sxs-lookup"><span data-stu-id="5c32f-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="5c32f-150">När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="5c32f-151">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="5c32f-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5c32f-152">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c32f-153">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5c32f-153">Next steps</span></span>

<span data-ttu-id="5c32f-154">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="5c32f-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5c32f-155">Skapa [segment](segments.md) och [mått](measures.md) och till och med [exportera datan](export-destinations.md) för att leverera anpassade upplevelser till dina kunder.</span><span class="sxs-lookup"><span data-stu-id="5c32f-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5c32f-156">Datasekretess och regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="5c32f-156">Data privacy and compliance</span></span>

<span data-ttu-id="5c32f-157">När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till Experian tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="5c32f-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5c32f-158">Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Experian uppfyller dina eventuella sekretess- och säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="5c32f-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5c32f-159">Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5c32f-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5c32f-160">Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="5c32f-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
