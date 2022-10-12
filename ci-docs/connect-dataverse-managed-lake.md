---
title: Anslut till data i en Microsoft Dataverse hanterad data lake
description: Importera data från en Microsoft Dataverse hanterad data lake.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609873"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Anslut till data i en Microsoft Dataverse hanterad data lake

Microsoft Dataverse-användare kan snabbt ansluta till analysentiteter i en Microsoft Dataverse hanterad enhet. Endast en datakälla av en miljö kan samtidigt använda samma Dataverse-hanterade sjö.

> [!NOTE]
> Du måste vara administratör i Dataverse organisationen för att kunna fortsätta och visa listan över entiteter som är tillgängliga i den hanterade organisationen.

## <a name="prerequisites"></a>Förutsättningar

- Data som lagras i en onlinetjänster, t.ex. Azure Data Lake Storage kan lagras på en annan plats än där data bearbetas eller lagras i Dynamics 365 Customer Insights. Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter](https://www.microsoft.com/trust-center).

- Endast Dataverse-entiteter med aktiverad [ändringsspårning](/power-platform/admin/enable-change-tracking-control-data-synchronization) visas. Dessa entiteter kan exporteras till den Dataverse-hanterade data laken och användas i Customer Insights. Färdiga Dataverse-tabeller har ändringsspårning aktiverad som standard. Du måste aktivera ändringsspårning för anpassade tabeller. Om du vill kontrollera om en Dataverse-tabell har aktiverats för ändringsspårning går du till [Power Apps](https://make.powerapps.com) > **Data** > **Tabeller**. Leta upp tabellen av intresse och välj den. Gå till **Inställningar** > **Avancerade alternativ** och granska inställningen **Spåra ändringar**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Ansluta till en Dataverse hanterad sjö

1. Gå till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Markera **Microsoft Dataverse**.

1. Ange ett **Namn** för datakällan och en valfri **Beskrivning**.

1. Ange **serveradressen** för Dataverse-organisationen och välj sedan **Logga in**.

1. Välj de tabeller du vill ange som entiteter i Customer Insights i den tillgängliga listan.

   > [!NOTE]
   > Om vissa tabeller redan är valda kan dessa komma att användas av andra Dynamics 365-program (till exempel Dynamics 365 Sales Insights elller Customer Service Insights). Det går inte att ändra det här valet. Dessa tabeller blir tillgängliga som entiteter när datakällan har skapats.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogruta med en lista över entiteter i Dataverse-miljön.":::

1. Spara dina val om du vill börja synkronisera de valda tabellerna från Dataverse. Den nyligen tillagda anslutningen finns på sidan **datakällor**. Dina val placeras i kö och anger entitetsantalet som 0 tills alla markerade tabeller har synkroniserats.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan [**Entiteter**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigera en Dataverse hanterad sjö datakälla

Du redigerar endast enhetsurvalet när du har skapat datakälla. Exempel: om fler entiteter har lagts till Dataverse och du vill importera dem också.
Om du vill skapa en ny Dataverse-data lake [skapar du en ny datakälla](#connect-to-a-dataverse-managed-lake).

1. Gå till **Data** > **Datakällor**.

1. Välj bredvid datakällan du vill uppdatera **Redigera**.

1. Välj ytterligare entiteter från listan med tillgängliga entiteter.

1. Klicka på **Spara** om du vill tillämpa ändringarna och återgå till sidan **Datakällor**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Vanliga orsaker till inkökningsfel eller skadade data

Följande kontroller körs på inmatade data för att visa skadade poster:

- Värdet för ett fält stämmer inte överens med datatypen för kolumnen.
- Fält innehåller tecken som gör att kolumnerna inte matchar det förväntade schemat. Till exempel: felaktigt formaterade offerter, icke-förfallna offerter eller nyradstecken.
- Om det finns kolumner med datetime/date/datetimeoffset måste formatet anges i modellen om det inte följer standard ISO-formatet.

### <a name="schema-or-data-type-mismatch"></a>Schema eller datatypsmatchning

Om informationen inte överensstämmer med schemat blir posterna skadade. Korrigera antingen källdata eller schemat och mata in data på ett annat sätt.

### <a name="datetime-fields-in-the-wrong-format"></a>Datetime-fält i fel format

Datum- och tidsfälten i entiteten är inte i ISO- eller en-US-format. Standardformatet för datetime i Customer Insights är en-US-format. Alla datetime-fält i en entitet ska vara i samma format. Customer Insights stöder andra format förutsatt att anteckningar eller drag görs på käll- eller entitetsnivå i modellen eller manifest.json. Till exempel: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  I ett manifest.json kan datetime-formatet anges på entitetsnivå eller på attributnivå. På entitetsnivå använder du "exhibitsTraits" i entiteten i *.manifest.cdm.json för att definiera datatime-formatet. På attributnivån använder du "appliedTraits" i attributet i entityname.cdm.json.

**Manifest.json på entitetsnivå**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json på attributnivå**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
