---
title: Semantiska mappningar (förhandsgranskning)
description: Översikt över semantiska mappningar och hur man använder dem.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: b3a0643ab71c98ce212f4e4581a584d8382c67eb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081995"
---
# <a name="semantic-mappings-preview"></a>Semantiska mappningar (förhandsgranskning)

Med hjälp av en semantisk mappning kan du mappa icke-aktivitetsdata till fördefinierade scheman. Med de här schemana kan Customer Insights för att få en bättre bild av dina dataattribut. En bildningsmappning och medföljande data möjliggör nya insikter och funktioner Customer Insights. Om du vill mappa dina aktivitetsdata till scheman kan du läsa [dokumentationen](activities.md) för aktiviteter.

**Semantiska mappningar är för närvarande aktiverade för miljöer baserade på företagskonton**. *ContactProfile* är den enda typen av semantisk kartläggning som för närvarande finns tillgänglig i Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definiera mappning av en ContactProfile-entitet

1. Gå till **Data** > **Semantiska mappningar (förhandsgranskning)**.

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Hantera befintliga semantiska mappningar

I **Data** > **semantisk mappning (förhandsversion)**, kan du se alla dina sparade semantiska mappningar och hantera dem. Varje semantisk mappning representeras av en separat rad. Här finns information om källentiteten, typ av språk, mappningstyp och dess status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Alternativ för hantering av semantiska mappningar.":::

- **Redigera**: Öppnar konfigurationen av den semantiska mappningsinställningen i granskningssteget. Du kan ändra den aktuella konfigurationen. Välj **Spara** och **Kör** för att bearbeta ändringarna.

- **Uppdatera**: Uppdaterar den valda semantiska mappningen med den mest uppdaterade data från de enheter som ingår i dess konfiguration. Om du uppdaterar en viss semantisk mappning uppdateras alla semantiska mappningar av samma typ.

- **Byt namn**: Öppnar en dialogruta där du kan ange ett annat namn för den valda semantiska mappningen. Välj **Spara** för att införa ändringarna.

- **Ta bort**: Öppnar en dialog för att bekräfta borttagningen av den valda semantiska mappningen. Du kan också ta bort fler än en semantisk mappning på samma gång genom att välja de olika semantiska mappningarna och borttagningsikonen. Välj **Ta bort** för att borttagningen.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Skapa aktiviteter på kontaktnivå med hjälp av en ContactProfile-mappning för entitetsbildning

När du har skapat en *ContactProfile*-mappning för entiteter kan du samla in kontakters aktiviteter. Det gör att du kan se i aktivitetstidslinjen för ett konto vilken kontakt som ansvarade för varje aktivitet. De flesta steg följer den typiska aktivitetsmappningskonfigurationen.

   > [!NOTE]
   > För att kontaktnivåaktiviteter ska fungera måste du ha både **AccountID**- och **ContactID**-attribut för varje post i dina aktivitetsdata.

1. [Definiera en *ContactProfile* semantisk entitetsmappning.](#define-a-contactprofile-semantic-entity-mapping) och kör semantiska mappningen.

1. Gå till **Data** > **Aktiviteter**.

1. Välj **Lägg till aktivitet** för att skapa en ny aktivitet.

1. Ge aktiviteten ett namn, välj entiteten för källaktiviteten och välj den primära nyckeln för aktivitetsentiteten.

1. I steget **Relationer**, skapa en indirekt relation mellan din aktivitetskällas data till konton, genom att använda din kontaktdata som en mellanliggande enhet. Mer information finns i [direkta och indirekta relationssökvägar](relationships.md#relationship-paths). 
   - Exempelrelation för en aktivitet med namnet *Inköp*:
      - **Aktivitetsdata för inköpskälla** > **Kontaktdata** på attributet **ContactID**
      - **Kontaktdata** > **Kontodata** i attributet **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Inställning av exempelrelation.":::

1. När du har Relationer väljer du **Nästa** och slutför konfiguration av aktivitetsmappning. Detaljerade steg när du skapar en aktivitet finns i [definiera en aktivitet](activities.md).

1. Kör dina aktivitetsmappningar.

1. Dina aktiviteter på kontaktnivå visas nu på din kundtidslinje.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Slutresultat efter konfigurering av kontaktaktiviteter":::

### <a name="contact-level-activity-timeline-filtering"></a>Tidslinjefiltrering på kontaktnivå

När du har konfigurerat en aktivitetsmappning på kontaktnivå och kör den uppdateras aktivitetstidslinjen för dina kunder. Det inkluderar deras ID eller namn, beroende på ditt *ContactProfile* konfiguration, för de aktiviteter de agerat på. Du kan filtrera aktiviteter efter kontakter i tidslinjen om du vill se specifika kontakter som du är intresserad av. Dessutom kan du visa alla aktiviteter som inte har tilldelats en viss kontakt genom att välja **Aktiviteter som inte är mappade till en kontakt**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Tillgängliga filtreringsalternativ för aktiviteter på kontaktnivå.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
