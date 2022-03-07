---
title: Semantiska mappningar (förhandsgranskning)
description: Översikt över semantiska mappningar och hur man använder dem.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731965"
---
# <a name="semantic-mappings"></a>Semantiska mappningar

Med hjälp av en semantisk mappning kan du mappa icke-aktivitetsdata till fördefinierade scheman. Med de här schemana kan målgruppsinsikter för att få en bättre bild av dina dataattribut. En bildningsmappning och medföljande data möjliggör nya insikter och funktioner målgruppsinsikter. Om du vill mappa dina aktivitetsdata till scheman kan du läsa [dokumentationen](activities.md) för aktiviteter.

**Semantiska mappningar är för närvarande aktiverade för miljöer baserade på företagskonton**. *ContactProfile* är den enda typen av semantisk kartläggning som för närvarande finns tillgänglig i målgruppsinsikter.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definiera mappning av en ContactProfile-entitet

1. I målgruppsinsikter, gå till **Data** > **Semantiska mappningar (förhandsversion)**.

1. Välj **Lägg till semantisk mappning** för att starta den guidade upplevelsen.

1. I steget **Entitetsdata**, ange värdena för följande fält

   - **Mappningsnamn för semantisk entitet**: Ange ett namn för din semantiska mappning av entiteter.
   - **Källentitet**: Välj en enhet som innehåller kontaktdata.
   - **Primärnyckel**: Välj fältet som används för unik identifiering av en kontaktpost. Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurera mappningen för entiteten med namn, källentitet och primärnyckel.":::

1. Fortsätt genom att klicka på **Nästa**.

1. I **Relationer**, konfigurera detaljerna för att ansluta dina kontaktuppgifter till motsvarande kontodata. Det här steget visualiserar anslutningen mellan entiteter.  

   Det finns två typer av relationssökvägar som kan implementeras: **Direkta relationer** och **Indirekta relationer**. Mer information finns i [direkta och indirekta relationssökvägar](relationships.md#relationship-paths). 

   1. Välj **Lägg till relation** och konfigurera relationen.
   1. Välj attributet från din källenhet som ansluter din kontaktenhet till en annan enhet.
   1. Välj den entitet som kontaktens entitet ska anslutas till. Du kan välja en entitet från avsnittet **Kontoentiteter** eller **Mellanliggande entitet**. Om du väljer en mellanliggande entitet måste du definiera en andra relation för att ansluta till målkontoentiteten.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Välj antingen en kontoentitet eller en mellanliggande entitet.":::

   1. Ange ett **regelnamn**. Om en relation mellan entiteterna redan finns är relationsnamnet skrivskyddet. Om det inte finns någon relation skapas en ny relation med det namn du anger.
   1. Välj **Tillämpa** när relationskonfigurationen ska slutföras.

   > [!NOTE]
   > Du kan konfigurera fler relationer mellan kontaktentiteten och andra kontoentiteter med mellanliggande entiteter.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisering av olika relationer ansluter kontaktpersoner till kontoentiteter.":::

1. Välj **Nästa** när du är klar med relationskonfigurationen.

1. I steget **Ange semantiktyp**, välj en **Semantisk typ**. För tillfället finns det en **Semantisk typ** kallas *ContactProfile*.

1. Mappa dina data till *ContactProfile* **Semantisk typ** för fälten som visas.
   - Obligatoriskt fält: kontakt-ID
   - Valfria fält: Förnamn, Efternamn, Födelsedatum, Kön, Primär e-postadress och Primär telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mappa dina kontaktdataattribut till de obligatoriska och valfria fälten.":::

1. Fortsätt genom att klicka på **Nästa**.

1. I steget **granskning** tar du en titt på konfigurationen av sematiska mappningen. Välj **Redigera** för motsvarande avsnitt om du vill göra ändringar.

1. Välj **Spara** om du vill spara den nya **Semantiska mappningen**.

1. När du har sparat kan du välja **Kör** processen semantisk mappning eller du kan välja **Stäng** för att spara din semantiska mappning utan att bearbeta den.

1. Om du vill köra en mappning senare markerar du semantisk mappning och väljer **Uppdatera**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Hantera befintliga semantiska mappningar

I **Data** > **semantisk mappning (förhandsversion)**, kan du se alla dina sparade semantiska mappningar och hantera dem. Varje semantisk mappning representeras av en separat rad. Här finns information om källentiteten, typ av språk, mappningstyp och dess status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Alternativ för hantering av semantiska mappningar.":::

- **Redigera**: Öppnar konfigurationen av den semantiska mappningsinställningen i granskningssteget. Du kan ändra den aktuella konfigurationen. Välj **Spara** och **Kör** för att bearbeta ändringarna.

- **Uppdatera**: Uppdaterar den valda semantiska mappningen med den mest uppdaterade data från de enheter som ingår i dess konfiguration. Om du uppdaterar en viss semantisk mappning uppdateras alla semantiska mappningar av samma typ.

- **Byt namn**: Öppnar en dialogruta där du kan ange ett annat namn för den valda semantiska mappningen. Välj **Spara** för att införa ändringarna.

- **Ta bort**: Öppnar en dialog för att bekräfta borttagningen av den valda semantiska mappningen. Du kan också ta bort fler än en semantisk mappning på samma gång genom att välja de olika semantiska mappningarna och borttagningsikonen. Välj **Ta bort** för att borttagningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
