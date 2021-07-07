---
title: Berikning med anpassad SFTP-import
description: Allmän information om berikning med anpassad SFTP-import.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304672"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="bafe4-103">Berika kundprofiler med anpassade data (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="bafe4-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="bafe4-104">Anpassad SFTP-import (Secure File Transfer Protocol) gör det möjligt att importera data som inte behöver gå igenom dataförening.</span><span class="sxs-lookup"><span data-stu-id="bafe4-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="bafe4-105">Det är ett flexibelt, säkert och enkelt sätt att ta med dina data.</span><span class="sxs-lookup"><span data-stu-id="bafe4-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="bafe4-106">Anpassad SFTP-import kan användas i kombination med [SFTP-export](export-sftp.md), som gör att du kan exportera de kundprofildata som behövs för berikning.</span><span class="sxs-lookup"><span data-stu-id="bafe4-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="bafe4-107">Datan kan sedan bearbetas och berikas, och SFTP-anpassad import kan användas för att återföra berikade data till målgruppsinsiktsfunktionen i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bafe4-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bafe4-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="bafe4-108">Prerequisites</span></span>

<span data-ttu-id="bafe4-109">Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera anpassad SFTP-import:</span><span class="sxs-lookup"><span data-stu-id="bafe4-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bafe4-110">Du har filnamn och sökväg för den fil som ska importeras på SFTP-värddatorn.</span><span class="sxs-lookup"><span data-stu-id="bafe4-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="bafe4-111">Det finns en *model.json*-fil som anger schemat för [Common Data Model-schema](/common-data-model/) för data att importeras.</span><span class="sxs-lookup"><span data-stu-id="bafe4-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="bafe4-112">Filen måste finnas i samma katalog som filen som ska importeras.</span><span class="sxs-lookup"><span data-stu-id="bafe4-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="bafe4-113">En SFTP-anslutning har redan konfigurerats av en administratör *eller* eller så har du [administratör](permissions.md#administrator) behörigheter.</span><span class="sxs-lookup"><span data-stu-id="bafe4-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="bafe4-114">Du behöver autentiseringsuppgifterna, URL:en och portnumret för den SFTP-plats där du vill importera data från.</span><span class="sxs-lookup"><span data-stu-id="bafe4-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="bafe4-115">Konfigurera importen</span><span class="sxs-lookup"><span data-stu-id="bafe4-115">Configure the import</span></span>

1. <span data-ttu-id="bafe4-116">Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.</span><span class="sxs-lookup"><span data-stu-id="bafe4-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="bafe4-117">På **Anpassad SFTP-importpanel**, välj **Utöka mina data** och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="bafe4-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Anpassad SFTP-importpanelen.":::

1. <span data-ttu-id="bafe4-119">Välj en [anslutning](connections.md) i listrutan.</span><span class="sxs-lookup"><span data-stu-id="bafe4-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="bafe4-120">Kontakta en administratör om det inte finns någon anslutning.</span><span class="sxs-lookup"><span data-stu-id="bafe4-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="bafe4-121">Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja **Anpassad SFTP-import** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="bafe4-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="bafe4-122">Välj **Anslut till anpassad import** för att bekräfta anslutningen.</span><span class="sxs-lookup"><span data-stu-id="bafe4-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="bafe4-123">Välj **Nästa** och ange **Sökväg** och **Filnamn** för den datafil som du vill importera.</span><span class="sxs-lookup"><span data-stu-id="bafe4-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skärmbild när dataplats matas in.":::

1. <span data-ttu-id="bafe4-125">Välj **Nästa** och ange ett namn på utdataenheten och ett namn för utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="bafe4-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="bafe4-126">Välj **Spara berikning** när du har granskat dina val.</span><span class="sxs-lookup"><span data-stu-id="bafe4-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="bafe4-127">Konfigurera anslutningen för anpassad SFTP-import</span><span class="sxs-lookup"><span data-stu-id="bafe4-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="bafe4-128">Du måste vara en administratör för att konfigurera anslutningar.</span><span class="sxs-lookup"><span data-stu-id="bafe4-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="bafe4-129">Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på panelen för anpassad import.</span><span class="sxs-lookup"><span data-stu-id="bafe4-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="bafe4-130">Ange ett namn för anslutningen i rutan **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="bafe4-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="bafe4-131">Ange ett giltigt användarnamn, lösenord och en värd-URL för den SFTP-server där den data som ska importeras finns.</span><span class="sxs-lookup"><span data-stu-id="bafe4-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="bafe4-132">Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.</span><span class="sxs-lookup"><span data-stu-id="bafe4-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="bafe4-133">Välj **Verifiera** om konfigurationen ska verifieras.</span><span class="sxs-lookup"><span data-stu-id="bafe4-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="bafe4-134">När verifieringen är klar går det att spara anslutningen genom att välja **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bafe4-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bafe4-135">![Konfigurationssida för Experian-anslutning](media/enrichment-SFTP-connection.png "Konfigurationssida för Experian-anslutning")</span><span class="sxs-lookup"><span data-stu-id="bafe4-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="bafe4-136">Definiera fältmappningar</span><span class="sxs-lookup"><span data-stu-id="bafe4-136">Defining field mappings</span></span> 

<span data-ttu-id="bafe4-137">Katalogen som innehåller den fil som ska importeras på SFTP-servern måste också innehålla en *model.json*-fil.</span><span class="sxs-lookup"><span data-stu-id="bafe4-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="bafe4-138">Den här filen definierar schemat som ska användas för att importera data.</span><span class="sxs-lookup"><span data-stu-id="bafe4-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="bafe4-139">Schemat måste använda [Common Data Model](/common-data-model/) för att ange fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="bafe4-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="bafe4-140">Ett enkelt exempel på en model.json-fil ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="bafe4-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="bafe4-141">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="bafe4-141">Enrichment results</span></span>

<span data-ttu-id="bafe4-142">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="bafe4-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bafe4-143">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bafe4-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bafe4-144">Bearbetningstiden beror på storleken på de data som ska importeras och anslutningen till SFTP-servern.</span><span class="sxs-lookup"><span data-stu-id="bafe4-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="bafe4-145">När en berikningsprocess har slutförts kan du granska dina nyligen importerade anpassade berikningsdata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="bafe4-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="bafe4-146">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="bafe4-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bafe4-147">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="bafe4-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bafe4-148">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bafe4-148">Next steps</span></span>

<span data-ttu-id="bafe4-149">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="bafe4-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bafe4-150">Skapa [segment](segments.md) och [mått](measures.md) och [exportera datan](export-destinations.md) för att leverera anpassade upplevelser till dina kunder.</span><span class="sxs-lookup"><span data-stu-id="bafe4-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
