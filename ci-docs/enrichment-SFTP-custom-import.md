---
title: Berikning med anpassad SFTP-import
description: Allmän information om berikning med anpassad SFTP-import.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953741"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Berika kundprofiler med anpassade data (förhandsversion)

Anpassad SFTP-import (Secure File Transfer Protocol) gör det möjligt att importera data som inte behöver gå igenom dataförening. Det är ett flexibelt, säkert och enkelt sätt att ta med dina data. Anpassad SFTP-import kan användas i kombination med [SFTP-export](export-sftp.md), som gör att du kan exportera de kundprofildata som behövs för berikning. Data kan sedan bearbetas och berikas, och SFTP-anpassad import kan användas för att föra tillbaka utökade data till Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Förutsättningar

- Filnamn och plats (sökväg) för filen som ska importeras till SFTP-värden är kända.

- En *model.json*-fil som anger schemat för Common Data Model för data som ska importeras är tillgänglig. Filen måste finnas i samma katalog som filen som ska importeras.

- En SFTP [anslutning](connections.md) är [konfigurerad](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exempel på filschema

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurera anslutningen för anpassad SFTP-import

Du måste vara en [administratör](permissions.md#admin) i Customer Insights och ha användaruppgifter, URL och portnummer för den SFTP-plats som du vill importera data från.

1. Välj **Lägg till anslutning** när du konfigurerar ett tillägg eller gå till **Admin**  > **Anslutningar** och välj **Konfigurera** på panelen för anpassad import.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Anpassad importanslutning konfigurationssidan.":::

1. Ange ett namn på anslutningen.

1. Ange ett giltigt användarnamn, lösenord och en värd-URL för den SFTP-server där den data som ska importeras finns.

1. Granska och ge ditt samtycke till [Data sekretess och efterlevnad](#data-privacy-and-compliance) genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras och välj sedan **Spara**.

### <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data med anpassad import tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att data uppfyller eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.

## <a name="configure-the-import"></a>Konfigurera importen

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **SFTP anpassad import**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Anpassad SFTP-importpanelen.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj anslutning. Kontakta en administratör om ingen är tillgänglig.

1. Välj **Kunddatauppsättning** och välj den profil eller det segment du vill berika. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Välj **Nästa**.

1. Ange **sökväg** och **filnamn** för den datafil du vill importera.

1. Välj **Nästa**.

1. Ange ett **Namn** för berikningen och **utgående enhetsnamn**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="enrichment-results"></a>Berikningsresultat

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
