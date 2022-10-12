---
title: Anslut till en Common Data Model-mapp som använder Azure Data Lake-konto
description: Arbeta med Common Data Model-data med hjälp av Azure Data Lake Storage.
ms.date: 09/29/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: c12603b9ed8a814356a0f8d0137e97afc749b87c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609970"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Ansluta till data i Azure Data Lake Storage

Hämta data till Dynamics 365 Customer Insights med ditt Azure Data Lake Storage Gen2-konto. Datainmatning kan göras fullständig eller vara inkrementell.

## <a name="prerequisites"></a>Förutsättningar

- Datainmatning stöder endast Azure Data Lake Storage *Gen2*-konton. Du kan inte använda Data Lake Storage Gen1-lagringskonton för att mata in data.

- Azure Data Lake Storage-konton måste ha [hierarkiskt namnutrymme aktiverat](/azure/storage/blobs/data-lake-storage-namespace). Data måste lagras i ett hierarkiskt mappformat som definierar rotmappen och som har undermappar för varje entitet. Undermapparna kan ha fullständiga data eller mappar med indata.

- Om du vill autentisera med Azure-tjänstens huvudkonto, se till att det är konfigurerat i din klientorganisation. Mer information finns i [Ansluta till ett Azure Data Lake Storage Gen2-konto med ett Azure-tjänsthuvudkonto](connect-service-principal.md).

- Den Azure Data Lake Storage som du vill ansluta och hämta data från måste finnas i samma Azure-region som Dynamics 365 Customer Insights-miljön. Anslutningar till en Common Data Model-mapp från en datasjö i en annan Azure-region stöds inte. För att känna till Azure-regionen i miljön, gå till **Admin** > **System** > **Om** i Customer Insights.

- Data som lagras i onlinetjänster kan lagras på en annan plats än där data behandlas eller lagras i Dynamics 365 Customer Insights. Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter](https://www.microsoft.com/trust-center).

- Tjänsten Customer Insights måste finnas i en av följande roller för att få åtkomst till lagringskontot. Mer information finns i [Bevilja behörigheter till tjänstens huvudnamn för åtkomst till lagringskontot](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Storage Blob-dataläsare
  - Storage Blob-dataägare
  - Storage Blob-datadeltagare

- Användaren som upprättar datakällsanslutningen måste ha minst behörigheten Storage Blob-datadeltagare för lagringskontot.

- Data i din Data Lake Storage bör följa standarden för Common Data Model för lagring av dina data och ha en Common Data Model som representerar schemat för datafilerna (*.csv eller *.parquet). Manifestet måste innehålla information om entiteterna, t.ex. entitetskolumner och datatyper, samt datafilsplatsen och filtypen. Mer information om finns i [Common Data Model manifest](/common-data-model/sdk/manifest). Om manifestet inte finns kan administratörsanvändare med åtkomst till Storage Blob-dataägare eller Storage Blob-datadeltagare deltagare definiera schemat när de öppnar data.

## <a name="recommendations"></a>Rekommendationer

För optimala prestanda rekommenderar Customer Insights att en partitions storlek är 1 GB eller mindre och att antalet partitionsfiler i en mapp inte får överskrida 1000.

## <a name="connect-to-azure-data-lake-storage"></a>Ansluta till Azure Data Lake Storage

1. Gå till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Välj **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialogruta där du kan ange anslutningsinformation för Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Ange ett **Namn** för datakällan och en valfri **Beskrivning**. Namnet identifierar unikt datakälla refereras i processer nedströms och kan inte ändras.

1. Välj ett av följande alternativ för **Anslut lagringsutrymmet med**. Mer information finns i [Ansluta Customer Insights till ett Azure Data Lake Storage Gen2-konto med ett Azure-tjänsthuvudkonto](connect-service-principal.md).

   - **Azure-resurs**: Ange **resurs-ID**. Om du vill hämta data från ett lagringskonto via en Azure Private Link väljer du **Aktivera Private Link**. Mer information finns i den här [Private Link](security-overview.md#set-up-an-azure-private-link).
   - **Azure-prenumeration**: Välj **prenumeration** och sedan **resursgruppen** och **lagringskontot**. Om du vill hämta data från ett lagringskonto via en Azure Private Link väljer du **Aktivera Private Link**. Mer information finns i den här [Private Link](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Du behöver en av följande roller för antingen behållaren eller lagringskontot om du vill skapa datakällan:
   >
   >  - Storage Blob Data-läsare räcker för att läsa från ett lagringskonto och mata in datan i Customer Insights.
   >  - Deltagare i eller ägare av Storage Blob Data krävs om du vill redigera manifestfilerna direkt i Customer Insights.  
  
1. Välj namnet på den **behållare** som innehåller data och schema (filen model.json eller manifest.json) om du vill importera data från och välj **Nästa**.
   > [!NOTE]
   > Inga model.json- eller manifest.json-filer som är associerade med en annan datakälla i miljön visas. Samma model.json- eller manifest.json-fil kan dock användas för datakällor i flera miljöer.

1. Om du vill skapa ett nytt schema går du till [Skapa en ny schemafil](#create-a-new-schema-file).

1. Om du vill använda ett befintligt schema navigerar du till mappen som innehåller filen model.json eller manifest.cdm.json. Du kan söka i en katalog för att hitta filen.

1. Välj json-fil och välj **Nästa**. En lista över tillgängliga entiteter visas.

   :::image type="content" source="media/review-entities.png" alt-text="Dialogrutan för en lista över entiteter som ska väljas":::

1. Välj de enheter du vill inkludera.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogruta som visar Obligatoriskt för primärnyckel":::

   > [!TIP]
   > Om du vill redigera en entitet i ett JSON-redigeringsgränssnitt väljer entiteten och sedan **Redigera schemafil**. Gör ändringar och välj **Spara**.

1. För valda entiteter som kräver inkrementell inmatning visas **obligatoriska** skärmar under **inkrementell uppdatering**. För var och en av dessa entiteter se [Konfigurera en inkrementell uppdatering för Azure Data Lake datakällor](incremental-refresh-data-sources.md).

1. För valda entiteter där en primärnyckel inte har definierats visas **Obligatoriska** under **Primärnyckel**. För var och en av dessa entiteter:
   1. Välj **Obligatorisk**. Panelen **Redigera entitet** visas.
   1. Välj **primärnyckel**. Den primära nyckeln är ett attribut som är unikt för entiteten. För att ett attribut ska vara en giltig primär nyckel bör det inte innehålla dubblettvärden, saknade värden och null-värden. Sträng-, heltals- och GUID-datatypattribut stöds som primärnycklar.
   1. Alternativt kan du ändra partitionsmönstret.
   1. Välj **Stäng** när du vill spara och stänga panelen.

1. Välj antalet **attribut** för varje inkluderad entitet. Sidan **Hantera attribut** visas.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogruta för att välja dataprofilering.":::

   1. Skapa nya attribut, redigera eller ta bort befintliga attribut. Du kan ändra namn, dataformat eller lägga till en semantiktyp.
   1. Om du vill aktivera analyser och andra funktioner väljer du **Dataprofilering** för hela entiteten eller för specifika attribut. Som standard är ingen entitet aktiverad för dataprofilering.
   1. Välj **Utfört**.

1. Välj **Spara**. Sidan **Datakällor** öppnas där den nya datakälla visas i status **uppdateras**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan [**Entiteter**](entities.md).

### <a name="create-a-new-schema-file"></a>Skapa en ny schemafil

1. Välj **Ny schemafil**.

1. Ange ett namn för filen och välj **Spara**.

1. Välj **ny entitet**. Panelen **Ny entitet** visas.

1. Ange enhetens namn och välj **Datafilers sökväg**.
   - **Flera .csv eller .parquet filer**: Bläddra till rotmappen, välj mönstertyp och ange uttrycket.
   - **Enskilda .csv eller .parquet filer**: Bläddra till .csv- eller .parquet-filen och välj den.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialogruta för att skapa en ny entitet med plats för datafiler.":::

1. Välj **Spara**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialogruta för att definiera eller skapa attribut automatiskt.":::

1. Välj **definiera attributen** och lägg till attributen manuellt, eller välj **generera dem automatiskt**. Ange ett namn, välj dataformat och valfri typ av attribut om du vill definiera attributen. För automatiskt genererade attribut:

   1. När attributen har skapats automatiskt väljer du **Granska attribut**. Sidan **Hantera attribut** visas.

   1. Kontrollera att dataformatet är korrekt för varje attribut.

   1. Om du vill aktivera analyser och andra funktioner väljer du **Dataprofilering** för hela entiteten eller för specifika attribut. Som standard är ingen entitet aktiverad för dataprofilering.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogruta för att välja dataprofilering.":::

   1. Välj **Utfört**. Sidan **Välj entiteter** visas.

1. Fortsätt att lägga till entiteter och attribut om tillämpligt.

1. När alla entiteter har lagts till väljer du **Inkludera** och ta med entiteterna i datakällsinsamlingen.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogruta som visar Obligatoriskt för primärnyckel":::

1. För valda entiteter som kräver inkrementell inmatning visas **obligatoriska** skärmar under **inkrementell uppdatering**. För var och en av dessa entiteter se [Konfigurera en inkrementell uppdatering för Azure Data Lake datakällor](incremental-refresh-data-sources.md).

1. För valda entiteter där en primärnyckel inte har definierats visas **Obligatoriska** under **Primärnyckel**. För var och en av dessa entiteter:
   1. Välj **Obligatorisk**. Panelen **Redigera entitet** visas.
   1. Välj **primärnyckel**. Den primära nyckeln är ett attribut som är unikt för entiteten. För att ett attribut ska vara en giltig primär nyckel bör det inte innehålla dubblettvärden, saknade värden och null-värden. Sträng-, heltals- och GUID-datatypattribut stöds som primärnycklar.
   1. Alternativt kan du ändra partitionsmönstret.
   1. Välj **Stäng** när du vill spara och stänga panelen.

1. Välj **Spara**. Sidan **Datakällor** öppnas där den nya datakälla visas i status **uppdateras**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan [**Entiteter**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Redigera en Azure Data Lake Storage datakälla

Du kan uppdatera alternativet *Anslut till ett lagringskonto med*. Mer information finns i [Ansluta Customer Insights till ett Azure Data Lake Storage Gen2-konto med ett Azure-tjänsthuvudkonto](connect-service-principal.md). Om du vill ansluta till en annan behållare från lagringskontot eller ändra kontonamnet måste du [skapa en ny datakällaanslutning](#connect-to-azure-data-lake-storage).

1. Gå till **Data** > **Datakällor**.

1. Välj bredvid datakällan du vill uppdatera **Redigera**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialogrutan för att redigera Azure Data Lake datakälla.":::

1. Ändra någon av följande information:

   - **Beskrivning**
   - **Anslut ditt lagringsutrymme med** och information om anslutningen. Du kan inte ändra informationen **Behållare** när anslutningen uppdateras.
      > [!NOTE]
      > En av följande roller måste tilldelas till lagringskontot eller -behållare:
        > - Storage Blob-dataläsare
        > - Storage Blob-dataägare
        > - Storage Blob-datadeltagare

   - **Aktivera Private Link** Om du vill hämta data från ett lagringskonto via en Azure Private Link. Mer information finns i den här [Private Link](security-overview.md#set-up-an-azure-private-link).

1. Välj **Nästa**.
1. Ändra någon av följande:
   - Navigera till en annan model.json- eller manifest.json-fil med en annan uppsättning entiteter från behållare.
   - Om du vill lägga till ytterligare entiteter att mata in markerar du **Ny entitet**.
   - Om du vill ta bort alla markerade entiteter som redan finns utan beroende markerar du entiteten och **Ta bort**.
      > [!IMPORTANT]
      > Om det finns beroenden på den befintliga filen model.json eller manifest.json och entitetsuppsättningen visas ett felmeddelande och det går inte att välja en annan model.json- eller manifest.json-fil. Ta bort dessa beroenden innan du ändrar filen model.json eller manifest.json, eller skapa en ny datakälla med den model.json- eller manifest.json-fil som du vill använda för att undvika att ta bort beroendena.
   - Om du vill ändra platsen för datafilen eller den primära nyckeln väljer du **Redigera**.
   - Information om inkrementell uppdatering av data finns i [Konfigurera en inkrementell uppdatering för Azure Data Lake datakällor](incremental-refresh-data-sources.md).
   - Ändra endast entitetsnamnet så att det matchar entitetsnamnet i .json-filen.

     > [!NOTE]
     > Behåll alltid enhetsnamnet i Customer Insights samma som enhetsnamnet i filen model.json eller manifest.json efter inmatning. Customer Insights verifierar alla entitetsnamn med model.json eller manifest.json vid varje systemuppdatering. Om ett entitetsnamn ändras antingen i Customer Insights eller utanför, uppstår ett fel eftersom Customer Insights inte kan hitta det nya entitetsnamnet i .json-filen. Om ett inmatade entitetsnamn har ändrats av misstag redigerar du entitetsnamnet i Customer Insights så att det matchar namnet i .json-filen.

1. Välj **Attribut** om du vill lägga till eller ändra attribut eller för att aktivera dataprofilering. Markera sedan **Klar**.

1. Klicka på **Spara** om du vill tillämpa ändringarna och återgå till sidan **Datakällor**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Vanliga orsaker till inkökningsfel eller skadade data

Under datainmatningen kan några av de vanligaste orsakerna till att en post betraktas som skadad:

- Datatyperna och fältvärdena matchar inte mellan källfilen och schemat
- Antalet kolumner i källfilen matchar inte schemat
- Fält innehåller tecken som gör att kolumnerna inte avviker jämfört med det förväntade schemat. Till exempel: felaktigt formaterade offerter, icke-förfallna offerter, nyradstecken eller fliktecken.
- Partitionsfiler saknas
- Om det finns kolumner med datetime/date/datetimeoffset måste formatet anges i schema om det inte följer standardformatet.

### <a name="schema-or-data-type-mismatch"></a>Schema eller datatypsmatchning

Om data inte överensstämmer med schemat intagsprocessen slutförs med fel. Korrigera antingen källdata eller schemat och mata in data på ett annat sätt.

### <a name="partition-files-are-missing"></a>Partitionsfiler saknas

- Om det gick utan skadade poster, men inga data visas, redigerar du filen model.json eller manifest.json och kontrollerar att partitioner har angetts. Sedan [uppdatera datakällan](data-sources.md#refresh-data-sources).

- Om dataindelning sker samtidigt som datakällor uppdateras vid en automatisk uppdatering av schemat, kan partitionsfilerna vara tomma eller inte tillgängliga för Customer Insights att bearbeta. För att anpassa sig till uppströmsuppdateringsschemat, ändra [systemets uppdateringsschema](schedule-refresh.md) eller uppdateringsschemat för datakällan. Justera tiden så att alla uppdateringar inte sker samtidigt och ger de senaste data som ska bearbetas i Customer Insights.

### <a name="datetime-fields-in-the-wrong-format"></a>Datetime-fält i fel format

Datum- och tidsfälten i entiteten är inte i ISO 8601- eller en-US-format. Standardformatet för datetime i Customer Insights är en-US-format. Alla datetime-fält i en entitet ska vara i samma format. Customer Insights stöder andra format förutsatt att anteckningar eller drag görs på käll- eller entitetsnivå i modellen eller manifest.json. Till exempel: 

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

  I ett manifest.json kan datetime-formatet anges på entitetsnivå eller på attributnivå. På entitetsnivå använder du "exhibitsTraits" i entiteten i *.manifest.cdm.json för att definiera datetime-formatet. På attributnivån använder du "appliedTraits" i attributet i entityname.cdm.json.

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
