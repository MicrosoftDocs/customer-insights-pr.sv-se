---
title: Skapa och hantera miljöer
description: Läs om hur du registrerar dig för tjänsten och hur du hanterar miljöer.
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5888008"
---
# <a name="manage-environments"></a><span data-ttu-id="505a8-103">Hantera miljöer</span><span class="sxs-lookup"><span data-stu-id="505a8-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="505a8-104">I den här artikeln beskriver vi hur du skapar en ny organisation och hur du etablerar en miljö.</span><span class="sxs-lookup"><span data-stu-id="505a8-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="505a8-105">Registrera dig och skapa en organisation</span><span class="sxs-lookup"><span data-stu-id="505a8-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="505a8-106">Gå till [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="505a8-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="505a8-107">Välj **Komma igång**.</span><span class="sxs-lookup"><span data-stu-id="505a8-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="505a8-108">Välj önskat inloggningsscenario och välj motsvarande länk.</span><span class="sxs-lookup"><span data-stu-id="505a8-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="505a8-109">Godkänn villkoren och välj **Fortsätt** när du vill börja skapa organisationen.</span><span class="sxs-lookup"><span data-stu-id="505a8-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="505a8-110">När miljön har skapats omdirigeras du till [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="505a8-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="505a8-111">Använd demonstrationsmiljön för att utforska appen eller skapa en ny miljö genom att följa stegen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="505a8-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="505a8-112">När du har angett miljöinställningarna väljer du **skapa**.</span><span class="sxs-lookup"><span data-stu-id="505a8-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="505a8-113">Du kommer att vara inloggad efter att miljön har skapats.</span><span class="sxs-lookup"><span data-stu-id="505a8-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="505a8-114">Skapa en miljö i en befintlig organisation</span><span class="sxs-lookup"><span data-stu-id="505a8-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="505a8-115">En ny miljö kan skapas på två olika sätt.</span><span class="sxs-lookup"><span data-stu-id="505a8-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="505a8-116">Du kan antingen ange en helt ny konfiguration, eller också kan du kopiera vissa konfigurationsinställningar från en befintlig miljö.</span><span class="sxs-lookup"><span data-stu-id="505a8-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="505a8-117">Organisationer kan skapa *två* miljöer för varje Customer Insights-licens.</span><span class="sxs-lookup"><span data-stu-id="505a8-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="505a8-118">Om din organisation köper mer än en gång licens [kontakta vårt supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) för att öka antalet tillgängliga miljöer.</span><span class="sxs-lookup"><span data-stu-id="505a8-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="505a8-119">Mer information om kapacitet och kapacitet för tillägg finns i [Dynamics 365 licensguiden](https://go.microsoft.com/fwlink/?LinkId=866544).</span><span class="sxs-lookup"><span data-stu-id="505a8-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="505a8-120">För att skapa en miljö i:</span><span class="sxs-lookup"><span data-stu-id="505a8-120">To create an environment:</span></span>

1. <span data-ttu-id="505a8-121">Välj **Miljö**-väljaren i apphuvudet.</span><span class="sxs-lookup"><span data-stu-id="505a8-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="505a8-122">Välj **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="505a8-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="505a8-123">![Miljöinställningar](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="505a8-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="505a8-124">I dialogrutan **Skapa ny miljö** välj **Ny miljö**.</span><span class="sxs-lookup"><span data-stu-id="505a8-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="505a8-125">Om du vill [Kopiera data från den aktuella miljön](#considerations-for-copy-configuration-preview) väljer du **Kopiera från befintlig miljö**.</span><span class="sxs-lookup"><span data-stu-id="505a8-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="505a8-126">Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.</span><span class="sxs-lookup"><span data-stu-id="505a8-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="505a8-127">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="505a8-127">Provide the following details:</span></span>
   - <span data-ttu-id="505a8-128">**Namn**: Namnet på miljön.</span><span class="sxs-lookup"><span data-stu-id="505a8-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="505a8-129">Detta fält är redan ifyllt om du har kopierat en befintlig miljö, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="505a8-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="505a8-130">**Region**: Den region där tjänsten disribueras och förvaras</span><span class="sxs-lookup"><span data-stu-id="505a8-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="505a8-131">**Typ**: Välj om du vill skapa en produktions- eller sandbox-miljö.</span><span class="sxs-lookup"><span data-stu-id="505a8-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="505a8-132">Alternativt kan du välja **Avancerade inställningar**:</span><span class="sxs-lookup"><span data-stu-id="505a8-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="505a8-133">**Spara alla data till**: anger var du vill lagra de utflödesdata som genererades från Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="505a8-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="505a8-134">Du har två alternativ: **Customer Insights-lagring** (en Azure Data Lake som hanteras av Customer Insights-teamet) och **Azure Data Lake Storage Gen2** (din egen Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="505a8-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="505a8-135">Som standard är alternativet för Customer Insights-lagring markerat.</span><span class="sxs-lookup"><span data-stu-id="505a8-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="505a8-136">Genom att spara data i Azure Data Lake Storage godkänner du att data överförs till och lagras på rätt geografiska plats för Azure Storage-kontot, som kan skilja sig från varifrån data lagras i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="505a8-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="505a8-137">Läs mer i Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="505a8-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="505a8-138">För närvarande lagras hämtade entiteter alltid i Customer Insights hanterade Data Lake.</span><span class="sxs-lookup"><span data-stu-id="505a8-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="505a8-139">Vi stöder endast Azure Data Lake Gen2-lagringskonton från samma Azure-region som du valde när du skapade miljön.</span><span class="sxs-lookup"><span data-stu-id="505a8-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="505a8-140">Vi stöder endast Azure Data Lake Gen2 hierarkiska namnrymd (HNS) lagringskonton.</span><span class="sxs-lookup"><span data-stu-id="505a8-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="505a8-141">För alternativet Azure Data Lake Storage Gen2 kan du välja mellan ett resursbaserat alternativ och ett prenumerationsbaserat alternativ för autentisering.</span><span class="sxs-lookup"><span data-stu-id="505a8-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="505a8-142">Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="505a8-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="505a8-143">Namnet på **behållare** går inte att ändra, utan kommer att vara "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="505a8-143">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="505a8-144">Om du vill använda [prediktioner](predictions.md), konfigurerar du datadelning med program och lösningar baserat på Microsoft Dataverse eller aktiverar datainmatning från lokala datakällor tillhandahåller du Microsoft Dataverse miljö-URL under **Konfigurera datadelning med Microsoft Dataverse och aktiverar ytterligare funktioner**.</span><span class="sxs-lookup"><span data-stu-id="505a8-144">If you want to use [predictions](predictions.md), configure data sharing with applications and solutions based on Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="505a8-145">Välj **Aktivera datadelning** för att dela Customer Insights-utdata med en Microsoft Dataverse-hanterad Data Lake.</span><span class="sxs-lookup"><span data-stu-id="505a8-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="505a8-146">Datadelning med Microsoft Dataverse-hanterad Data Lake stöds för närvarande inte när du sparar alla data i din egen Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="505a8-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="505a8-147">[Förutsägelse av saknade värden i en entitet](predictions.md) stöds för närvarande inte när du aktiverar datadelning med Microsoft Dataverse-hanterad Data Lake.</span><span class="sxs-lookup"><span data-stu-id="505a8-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="505a8-148">![Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="505a8-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="505a8-149">När du kör processer, till exempel datainmatning eller skapande av segment, kommer motsvarande mappar att skapas i det lagringskonto du angav ovan.</span><span class="sxs-lookup"><span data-stu-id="505a8-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="505a8-150">Datafiler och model.json-filer skapas och läggs till i motsvarande undermappar baserat på den process du kör.</span><span class="sxs-lookup"><span data-stu-id="505a8-150">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="505a8-151">Om du skapar flera miljöer av Customer Insights och väljer att spara utdataentiteterna från dessa miljöer i ditt lagringskonto, kommer separata mappar att skapas för varje miljö med ci_<environmentid> i behållaren.</span><span class="sxs-lookup"><span data-stu-id="505a8-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="505a8-152">Att tänka på vid kopieringskonfiguration (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="505a8-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="505a8-153">Följande konfigurationsinställningar kan kopieras:</span><span class="sxs-lookup"><span data-stu-id="505a8-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="505a8-154">Funktionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="505a8-154">Feature configurations</span></span>
- <span data-ttu-id="505a8-155">Inmatade/importerade datakällor</span><span class="sxs-lookup"><span data-stu-id="505a8-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="505a8-156">Dataföreningskonfiguration (mappning, matchning, sammanslagning)</span><span class="sxs-lookup"><span data-stu-id="505a8-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="505a8-157">Segments</span><span class="sxs-lookup"><span data-stu-id="505a8-157">Segments</span></span>
- <span data-ttu-id="505a8-158">Mått</span><span class="sxs-lookup"><span data-stu-id="505a8-158">Measures</span></span>
- <span data-ttu-id="505a8-159">Relationer</span><span class="sxs-lookup"><span data-stu-id="505a8-159">Relationships</span></span>
- <span data-ttu-id="505a8-160">Aktiviteter</span><span class="sxs-lookup"><span data-stu-id="505a8-160">Activities</span></span>
- <span data-ttu-id="505a8-161">Sök och filtrera index</span><span class="sxs-lookup"><span data-stu-id="505a8-161">Search & filter Index</span></span>
- <span data-ttu-id="505a8-162">Exportmål</span><span class="sxs-lookup"><span data-stu-id="505a8-162">Export destinations</span></span>
- <span data-ttu-id="505a8-163">Schemalagd uppdatering</span><span class="sxs-lookup"><span data-stu-id="505a8-163">Scheduled refresh</span></span>
- <span data-ttu-id="505a8-164">Berikning</span><span class="sxs-lookup"><span data-stu-id="505a8-164">Enrichments</span></span>
- <span data-ttu-id="505a8-165">Modellhantering</span><span class="sxs-lookup"><span data-stu-id="505a8-165">Model management</span></span>
- <span data-ttu-id="505a8-166">Rolltilldelningar</span><span class="sxs-lookup"><span data-stu-id="505a8-166">Role assignments</span></span>

<span data-ttu-id="505a8-167">Följande konfigurationsinställningar kan *inte* kopieras:</span><span class="sxs-lookup"><span data-stu-id="505a8-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="505a8-168">Kundprofiler.</span><span class="sxs-lookup"><span data-stu-id="505a8-168">Customer profiles.</span></span>
- <span data-ttu-id="505a8-169">Autentiseringsuppgifter för datakälla.</span><span class="sxs-lookup"><span data-stu-id="505a8-169">Data source credentials.</span></span> <span data-ttu-id="505a8-170">Du måste ange autentiseringsuppgifterna för varje datakälla och uppdatera datakällorna manuellt.</span><span class="sxs-lookup"><span data-stu-id="505a8-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="505a8-171">Datakällor från Common Data Model-mappen och den Common Data Service-hanterade sjön.</span><span class="sxs-lookup"><span data-stu-id="505a8-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="505a8-172">Du måste skapa dessa datakällor manuellt med samma namn som i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="505a8-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="505a8-173">När du kopierar en miljö visas ett bekräftelsemeddelande om att den nya miljön har skapats.</span><span class="sxs-lookup"><span data-stu-id="505a8-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="505a8-174">Välj **gå till datakällor** om du vill visa listan över datakällor.</span><span class="sxs-lookup"><span data-stu-id="505a8-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="505a8-175">I alla data källor visas statusen **Autentiseringsuppgifter krävs**.</span><span class="sxs-lookup"><span data-stu-id="505a8-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="505a8-176">Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem.</span><span class="sxs-lookup"><span data-stu-id="505a8-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="505a8-177">![Datakällor som kopierats](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="505a8-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="505a8-178">När datakällorna har uppdaterats går du till **Data** > **Förena**.</span><span class="sxs-lookup"><span data-stu-id="505a8-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="505a8-179">Här hittar du inställningar från källmiljön.</span><span class="sxs-lookup"><span data-stu-id="505a8-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="505a8-180">Redigera dem efter behov eller välj **kör** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.</span><span class="sxs-lookup"><span data-stu-id="505a8-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="505a8-181">När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.</span><span class="sxs-lookup"><span data-stu-id="505a8-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="505a8-182">Redigera en befintlig miljö</span><span class="sxs-lookup"><span data-stu-id="505a8-182">Edit an existing environment</span></span>

<span data-ttu-id="505a8-183">Du kan redigera vissa av detaljerna i befintliga miljöer.</span><span class="sxs-lookup"><span data-stu-id="505a8-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="505a8-184">Välj **Miljö**-väljaren i apphuvudet.</span><span class="sxs-lookup"><span data-stu-id="505a8-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="505a8-185">Välj ikonen **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="505a8-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="505a8-186">I rutan **Redigera miljö** kan du uppdatera miljöns **visningsnamn**, men du kan inte ändra **Region** eller **Typ**.</span><span class="sxs-lookup"><span data-stu-id="505a8-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="505a8-187">Om en miljö är konfigurerad att lagra data i Azure Data Lake Storage Gen2 kan du uppdatera **kontonyckeln**.</span><span class="sxs-lookup"><span data-stu-id="505a8-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="505a8-188">Du kan emellertid inte ändra **Kontonam** eller namnet för **Behållare**.</span><span class="sxs-lookup"><span data-stu-id="505a8-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="505a8-189">Alternativt kan du uppdatera från en kontonyckelbaserad anslutning till en resursbaserad eller prenumerationsbaserad anslutning.</span><span class="sxs-lookup"><span data-stu-id="505a8-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="505a8-190">När du har uppgraderat kan du inte återgå till kontonyckeln efter uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="505a8-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="505a8-191">Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="505a8-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="505a8-192">Du kan inte ändra informationen **Behållare** när anslutningen uppdateras.</span><span class="sxs-lookup"><span data-stu-id="505a8-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="505a8-193">Du kan även ange en Microsoft Dataverse miljö-URL under **Konfigurera datadelning med Microsoft Dataverse och aktivera ytterligare funktioner**.</span><span class="sxs-lookup"><span data-stu-id="505a8-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="505a8-194">Dessa funktioner för datadelning med program och lösningar som bygger på Microsoft Dataverse, datainsamling som lokala datakällor eller användning av [prediktioner](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="505a8-194">These capabilities inlcude data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="505a8-195">Välj **Aktivera datadelning** för att dela Customer Insights-utdata med en Microsoft Dataverse-hanterad Data Lake.</span><span class="sxs-lookup"><span data-stu-id="505a8-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="505a8-196">Datadelning med Microsoft Dataverse-hanterad Data Lake stöds för närvarande inte när du sparar alla data i din egen Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="505a8-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="505a8-197">[Prediktion av värden som saknas i en entitet](predictions.md) stöds för närvarande inte när du aktiverar datadelning med Microsoft Dataverse-hanterad Data Lake.</span><span class="sxs-lookup"><span data-stu-id="505a8-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="505a8-198">När du har aktiverat datadelning med Microsoft Dataverse, en fullständig uppdatering av dina datakällor och andra processer kommer att utlösas.</span><span class="sxs-lookup"><span data-stu-id="505a8-198">Once you enable data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes will be triggered.</span></span> <span data-ttu-id="505a8-199">Om processer körs och köas för tillfället visas inte alternativet att aktivera datadelning med Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="505a8-199">If processes are currently running and queued, you will not see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="505a8-200">Du kan vänta tills processerna har slutförts eller avbrutits om du vill aktivera datadelning.</span><span class="sxs-lookup"><span data-stu-id="505a8-200">You can wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse.":::
   
   <span data-ttu-id="505a8-202">När du kör processer, till exempel datainmatning eller skapande av segment, kommer motsvarande mappar att skapas i det lagringskonto du angav ovan.</span><span class="sxs-lookup"><span data-stu-id="505a8-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="505a8-203">Datafiler och model.json-filer skapas och läggs till i respektive undermappar, beroende på vilken process du kör.</span><span class="sxs-lookup"><span data-stu-id="505a8-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="505a8-204">Återställa en befintlig miljö</span><span class="sxs-lookup"><span data-stu-id="505a8-204">Reset an existing environment</span></span>

<span data-ttu-id="505a8-205">Som en administratör kan du återställa en miljö till ett tomt tillstånd om du vill ta bort alla konfigurationer och ta bort de inmatade data.</span><span class="sxs-lookup"><span data-stu-id="505a8-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="505a8-206">Välj **Miljö**-väljaren i apphuvudet.</span><span class="sxs-lookup"><span data-stu-id="505a8-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="505a8-207">Välj den miljö du vill återställa och välj ellipsen **...**.</span><span class="sxs-lookup"><span data-stu-id="505a8-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="505a8-208">Välj alternativet **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="505a8-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="505a8-209">Bekräfta borttagningen genom att ange miljönamnet och välj **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="505a8-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="505a8-210">Ta bort en befintlig miljö (finns endast för administratörer)</span><span class="sxs-lookup"><span data-stu-id="505a8-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="505a8-211">Som en administratör kan du ta bort en miljö som du administrerar.</span><span class="sxs-lookup"><span data-stu-id="505a8-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="505a8-212">Välj **Miljö**-väljaren i apphuvudet.</span><span class="sxs-lookup"><span data-stu-id="505a8-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="505a8-213">Välj den miljö du vill återställa och välj ellipsen **...**.</span><span class="sxs-lookup"><span data-stu-id="505a8-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="505a8-214">Välj alternativet **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="505a8-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="505a8-215">Bekräfta borttagningen genom att ange miljö namnet och välja **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="505a8-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
