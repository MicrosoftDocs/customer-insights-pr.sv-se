---
title: Berikning med anpassad SFTP-import
description: Allmän information om berikning med anpassad SFTP-import.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269628"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Berika kundprofiler med anpassade data (förhandsversion)

Anpassad SFTP-import (Secure File Transfer Protocol) gör det möjligt att importera data som inte behöver gå igenom dataförening. Det är ett flexibelt, säkert och enkelt sätt att ta med dina data. Anpassad SFTP-import kan användas i kombination med [SFTP-export](export-sftp.md), som gör att du kan exportera de kundprofildata som behövs för berikning. Data kan sedan bearbetas, berikas och med anpassad SFTP-import användas för att återställa berikade data till målgruppsinsiktskapaciteten i Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera anpassad SFTP-import:

- Du har användarautentiseringsuppgifter (användarnamn och löseord) för den SFTP-plats som data ska importeras från.
- Du har en URL och ett portnummer (vanligtvis 22) för STF-värden.
- Du har filnamn och plats för filen som ska importeras till SFTP-värden.
- Det finns en *model.json*-fil som anger schemat för de data som ska importeras. Filen måste finnas i samma katalog som filen som ska importeras.
- Du har [administratörs](permissions.md#administrator)behörighet.

## <a name="configuration"></a>Konfiguration

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. I panelen **Anpassad SFTP-import** väljer du **Berika mina data**.

   > [!div class="mx-imgBorder"]
   > ![Panelen Anpassad SFTP-import](media/SFTP_Custom_Import_tile.png "Panelen Anpassad SFTP-import")

1. Välj **Kom igång** och ange autentiseringsuppgifterna och adressen för SFTP-servern. Till exempel sftp://mysftpserver.com:22.

1. Ange namnet på den fil som innehåller data och sökvägen till filen på SFTP-servern om den inte finns i rotmappen.

1. Bekräfta alla indata genom att välja **Anslut till anpassad import**.

   > [!div class="mx-imgBorder"]
   > ![Utfällbar meny Konfiguration av anpassad SFTP-import](media/SFTP_Custom_Import_Configuration_flyout.png "Utfällbar meny Konfiguration av anpassad SFTP-import")

## <a name="defining-field-mappings"></a>Definiera fältmappningar 

Katalogen som innehåller den fil som ska importeras på SFTP-servern måste också innehålla en *model.json*-fil. Den här filen definierar schemat som ska användas för att importera data. Schemat måste använda [Common Data Model](https://docs.microsoft.com/common-data-model/) för att ange fältmappningen. Ett enkelt exempel på en model.json-fil ser ut så här:

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

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på de data som ska importeras och anslutningen till SFTP-servern.

När en berikningsprocess har slutförts kan du granska dina nyligen importerade anpassade berikningsdata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segmen](segments.md), [mått](measures.md) och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.




[!INCLUDE[footer-include](../includes/footer-banner.md)]