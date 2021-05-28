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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896303"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Berika kundprofiler med anpassade data (förhandsversion)

Anpassad import av Secure File Transfer Protocol (SFTP) gör att du kan importera data som inte behöver gå igenom processen för datasamordning. Det är ett flexibelt, säkert och enkelt sätt att ta med dina data. Anpassad SFTP-import kan användas i kombination med [SFTP-export](export-sftp.md), som gör att du kan exportera de kundprofildata som behövs för berikning. Data kan sedan bearbetas, berikas och med anpassad SFTP-import användas för att återställa berikade data till målgruppsinsiktskapaciteten i Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera anpassad SFTP-import:

- Du har filnamnet och sökvägen (sökvägen) för den fil som ska importeras på SFTP-värd.
- Det finns en *model.json*-fil som anger schemat för [Common Data Model-schema](/common-data-model/) för data att importeras. Filen måste finnas i samma katalog som filen som ska importeras.
- En SFTP-anslutning har redan konfigurerats av en administratör *eller* eller så har du [administratör](permissions.md#administrator) behörigheter. Du behöver autentiseringsuppgifterna, URL:en och portnumret för den SFTP-plats där du vill importera data från.


## <a name="configure-the-import"></a>Konfigurera importen

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. På **Anpassad SFTP-importpanel**, välj **Utöka mina data** och välj **Kom igång**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Anpassad SFTP-importpanelen.":::

1. Välj en [anslutning](connections.md) från listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja **Anpassad SFTP-import** från listrutan.

1. Välj **Anslut till anpassad import** för att bekräfta anslutningen.

1.  Välj **Nästa** och ange **filnamnet** och **sökvägen** till den datafil du vill importera.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skärmbild när dataplats matas in.":::

1. Välj **Nästa** och ange ett namn på utdataenheten och ett namn för utdataenheten. 

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurera anslutningen för anpassad SFTP-import 

Du måste vara en administratör för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på panelen för anpassad import.

1. Ange ett namn för anslutningen i rutan **visningsnamn**.

1. Ange ett giltigt användarnamn, lösenord och en värd-URL för STFP-servern som de data som ska importeras finns på.

1. Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. När verifieringen är klar går det att spara anslutningen genom att klicka på **Spara**.

> [!div class="mx-imgBorder"]
   > ![Konfigurationssida för Experian-anslutning](media/enrichment-SFTP-connection.png "Konfigurationssida för Experian-anslutning")


## <a name="defining-field-mappings"></a>Definiera fältmappningar 

Katalogen som innehåller den fil som ska importeras på SFTP-servern måste också innehålla en *model.json*-fil. Den här filen definierar schemat som ska användas för att importera data. Schemat måste använda [Common Data Model](/common-data-model/) för att ange fältmappningen. Ett enkelt exempel på en model.json-fil ser ut så här:

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