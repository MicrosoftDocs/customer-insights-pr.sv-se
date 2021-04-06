---
title: Berikning med anpassad SFTP-import
description: Allmän information om berikning med anpassad SFTP-import.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595877"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="45873-103">Berika kundprofiler med anpassade data (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="45873-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="45873-104">Anpassad SFTP-import (Secure File Transfer Protocol) gör det möjligt att importera data som inte behöver gå igenom dataförening.</span><span class="sxs-lookup"><span data-stu-id="45873-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="45873-105">Det är ett flexibelt, säkert och enkelt sätt att ta med dina data.</span><span class="sxs-lookup"><span data-stu-id="45873-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="45873-106">Anpassad SFTP-import kan användas i kombination med [SFTP-export](export-sftp.md), som gör att du kan exportera de kundprofildata som behövs för berikning.</span><span class="sxs-lookup"><span data-stu-id="45873-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="45873-107">Data kan sedan bearbetas, berikas och med anpassad SFTP-import användas för att återställa berikade data till målgruppsinsiktskapaciteten i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="45873-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="45873-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="45873-108">Prerequisites</span></span>

<span data-ttu-id="45873-109">Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera anpassad SFTP-import:</span><span class="sxs-lookup"><span data-stu-id="45873-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="45873-110">Du har användarautentiseringsuppgifter (användarnamn och löseord) för den SFTP-plats som data ska importeras från.</span><span class="sxs-lookup"><span data-stu-id="45873-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="45873-111">Du har en URL och ett portnummer (vanligtvis 22) för STF-värden.</span><span class="sxs-lookup"><span data-stu-id="45873-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="45873-112">Du har filnamn och plats för filen som ska importeras till SFTP-värden.</span><span class="sxs-lookup"><span data-stu-id="45873-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="45873-113">Det finns en *model.json*-fil som anger schemat för de data som ska importeras.</span><span class="sxs-lookup"><span data-stu-id="45873-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="45873-114">Filen måste finnas i samma katalog som filen som ska importeras.</span><span class="sxs-lookup"><span data-stu-id="45873-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="45873-115">Du har [administratörs](permissions.md#administrator)behörighet.</span><span class="sxs-lookup"><span data-stu-id="45873-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="45873-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="45873-116">Configuration</span></span>

1. <span data-ttu-id="45873-117">Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.</span><span class="sxs-lookup"><span data-stu-id="45873-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="45873-118">I panelen **Anpassad SFTP-import** väljer du **Berika mina data**.</span><span class="sxs-lookup"><span data-stu-id="45873-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45873-119">![Panelen Anpassad SFTP-import](media/SFTP_Custom_Import_tile.png "Panelen Anpassad SFTP-import")</span><span class="sxs-lookup"><span data-stu-id="45873-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="45873-120">Välj **Kom igång** och ange autentiseringsuppgifterna och adressen för SFTP-servern.</span><span class="sxs-lookup"><span data-stu-id="45873-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="45873-121">Till exempel sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="45873-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="45873-122">Ange namnet på den fil som innehåller data och sökvägen till filen på SFTP-servern om den inte finns i rotmappen.</span><span class="sxs-lookup"><span data-stu-id="45873-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="45873-123">Bekräfta alla indata genom att välja **Anslut till anpassad import**.</span><span class="sxs-lookup"><span data-stu-id="45873-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45873-124">![Utfällbar meny Konfiguration av anpassad SFTP-import](media/SFTP_Custom_Import_Configuration_flyout.png "Utfällbar meny Konfiguration av anpassad SFTP-import")</span><span class="sxs-lookup"><span data-stu-id="45873-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="45873-125">Definiera fältmappningar</span><span class="sxs-lookup"><span data-stu-id="45873-125">Defining field mappings</span></span> 

<span data-ttu-id="45873-126">Katalogen som innehåller den fil som ska importeras på SFTP-servern måste också innehålla en *model.json*-fil.</span><span class="sxs-lookup"><span data-stu-id="45873-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="45873-127">Den här filen definierar schemat som ska användas för att importera data.</span><span class="sxs-lookup"><span data-stu-id="45873-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="45873-128">Schemat måste använda [Common Data Model](/common-data-model/) för att ange fältmappningen.</span><span class="sxs-lookup"><span data-stu-id="45873-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="45873-129">Ett enkelt exempel på en model.json-fil ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="45873-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="45873-130">Berikningsresultat</span><span class="sxs-lookup"><span data-stu-id="45873-130">Enrichment results</span></span>

<span data-ttu-id="45873-131">Starta berikningsprocessen genom att välja **kör** från kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="45873-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="45873-132">Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="45873-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="45873-133">Bearbetningstiden beror på storleken på de data som ska importeras och anslutningen till SFTP-servern.</span><span class="sxs-lookup"><span data-stu-id="45873-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="45873-134">När en berikningsprocess har slutförts kan du granska dina nyligen importerade anpassade berikningsdata under **Mina berikningar**.</span><span class="sxs-lookup"><span data-stu-id="45873-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="45873-135">Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.</span><span class="sxs-lookup"><span data-stu-id="45873-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="45873-136">Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.</span><span class="sxs-lookup"><span data-stu-id="45873-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="45873-137">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="45873-137">Next steps</span></span>

<span data-ttu-id="45873-138">Skapa ovanpå dina berikade kunddata.</span><span class="sxs-lookup"><span data-stu-id="45873-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="45873-139">Skapa [segmen](segments.md), [mått](measures.md) och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.</span><span class="sxs-lookup"><span data-stu-id="45873-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]