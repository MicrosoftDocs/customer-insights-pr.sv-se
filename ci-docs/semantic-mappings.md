---
title: Semantiska mappningar (förhandsgranskning)
description: Översikt över semantiska mappningar och hur man använder dem.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303899"
---
# <a name="semantic-mappings-preview"></a>Semantiska mappningar (förhandsgranskning)

> [!NOTE]
> Sidan **Semantiska mappningar** är endast tillgänglig för företagsmiljöer (B2B) där kontaktprofiler redan har skapats med den här sidan. Du kan fortsätta att skapa och hantera de enskilda kontaktprofilerna med hjälp av sidan **Semantiska mappningar**. Eller [förena dina kontaktdata](data-unification-contacts.md) för att ta bort dubbletter, identifiera matchningar mellan enheter och skapa en enhetlig kontaktprofil. Du kan sedan använda den enhetliga kontaktprofilen för att skapa aktiviteter på kontaktnivå.

Med hjälp av en semantisk mappning kan du mappa icke-aktivitetsdata till fördefinierade scheman. Med de här schemana kan Customer Insights för att få en bättre bild av dina dataattribut. En bildningsmappning och medföljande data möjliggör nya insikter och funktioner Customer Insights. Om du vill mappa dina aktivitetsdata till scheman kan du läsa [dokumentationen](activities.md) för aktiviteter.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definiera mappning av en ContactProfile-entitet

1. Gå till **Data** > **Semantiska mappningar (förhandsgranskning)**.

1. Välj **Lägg till semantisk mappning** för att starta den guidade upplevelsen.

1. I steget **Entitetsdata**, ange värdena för följande fält

   - **Mappningsnamn för semantisk entitet**: Namn för din semantiska mappning av entiteter.
   - **Källentitet**: enhet som innehåller kontaktdata.
   - **Primärnyckel**: fältet som används för unik identifiering av en kontaktpost. Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurera mappningen för entiteten med namn, källentitet och primärnyckel.":::

1. Välj **Nästa**.

1. I **Relationer**, konfigurera detaljerna för att ansluta dina kontaktuppgifter till motsvarande kontodata. Det här steget visualiserar anslutningen mellan entiteter.  

   Det finns två typer av relationssökvägar som kan implementeras: **Direkta relationer** och **Indirekta relationer**. Mer information finns i [direkta och indirekta relationssökvägar](relationships.md#relationship-paths). 

   1. Välj **Lägg till relation** och konfigurera relationen.
   1. Välj attributet från din källenhet som ansluter din kontaktenhet till en annan enhet.
   1. Välj den entitet som kontaktens entitet ska anslutas till. Välj entitet från avsnittet **Kontoentiteter** eller **Mellanliggande entitet**. Om du väljer en mellanliggande entitet måste du definiera en andra relation för att ansluta till målkontoentiteten.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Välj antingen en kontoentitet eller en mellanliggande entitet.":::

   1. Ange ett **regelnamn**. Om en relation mellan entiteterna redan finns är relationsnamnet skrivskyddet. Om det inte finns någon relation skapas en ny relation med det namn du anger.
   1. Välj **Tillämpa** när relationskonfigurationen ska slutföras.

   > [!NOTE]
   > Du kan konfigurera fler relationer mellan kontaktentiteten och andra kontoentiteter med mellanliggande entiteter.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisering av olika relationer ansluter kontaktpersoner till kontoentiteter.":::

1. Välj **Nästa**.

1. I steget **Ange semantiktyp**, välj en **Semantisk typ**. För tillfället finns det en **Semantisk typ** kallas *ContactProfile*.

1. Mappa ditt kontakt-id till *ContactProfile* semantisk typ **Kontakt-ID**. Om du vill kan du mappa andra fält som förnamn, efternamn, kön eller e-post.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mappa dina kontaktdataattribut till de obligatoriska och valfria fälten.":::

1. Välj **Nästa**.

1. I steget **granskning** tar du en titt på konfigurationen av semantiska mappningen. Välj **Redigera** för motsvarande avsnitt om du vill göra ändringar.

1. Välj **Spara**.

1. För att bearbeta den semantiska mappningen, välj **Kör**. Eller välj **Stäng** om du vill spara mappningen utan att bearbeta den. Om du vill köra den senare markerar du semantisk mappning och väljer **Uppdatera**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Hantera befintliga semantiska mappningar

Gå till **Data** > **Semantiska mappningar (förhandsgranskning)** för att visa dina sparade semantiska mappningar, deras källenhet, semantiska typ, mappningstyp och status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Alternativ för hantering av semantiska mappningar.":::

Välj den semantiska mappningen om du vill visa tillgängliga åtgärder.
- **Redigera** den aktuella konfigurationen. Välj **Spara** och **Kör** för att bearbeta ändringarna.
- **Uppdatera** den semantiska mappningen så att det omfattar senaste data. Om du uppdaterar en viss semantisk mappning uppdateras alla semantiska mappningar av samma typ.
- **Byt namn** på den semantiska mappningen. Välj **Spara**.
- **Ta bort** den semantiska mappningen. Du kan ta bort fler än en semantisk mappning på samma gång genom att välja de olika semantiska mappningarna och borttagningsikonen. Välj **Ta bort** för att borttagningen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
