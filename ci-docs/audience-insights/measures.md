---
title: Skapa och redigera åtgärder
description: Definiera kundrelaterade åtgärder för att analysera och avspegla resultat för vissa affärsområden.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407104"
---
# <a name="define-and-manage-measures"></a>Definiera och hantera mått

**Mått** representerar KPI:er som avspeglar prestanda och hälsa för specifika affärsområden. Målgruppsinsikter ger en intuitiv upplevelse för att bygga olika typer av åtgärder, med hjälp av en frågebyggare som inte kräver att du kodar eller validerar dina åtgärder manuellt. **Du kan spåra dina affärsmått på startsidan**, visa mått för specifika kunder på **kundkortet** och använda mått för att definiera kundsegment på sidan **segment**.

## <a name="create-a-measure"></a>Skapa ett mått

Det här avsnittet innehåller stegvisa anvisningar om hur du skapar ett mått från grunden. Du kan skapa mått med data från flera datakällor som är anslutna via entiteten kund. Vissa [servicegränser](service-limits.md) gäller.

1. I målgruppsinsikter går du till **Åtgärder**.

2. Välj **nytt mått**.

3. Välj en mått **typ**:

   - **Kundattribut**: ett enskilt fält per kund som visar poäng, värde eller tillstånd för kunden. Kundattribut skapas som attribut i en ny systemgenererad entitet som kallas **Customer_Measure**.

   - **Kundmått**: insikt för kundbeteende med uppdelning efter valda dimensioner. En ny entitet skapas för varje mått, eventuellt med flera poster per kund.

   - **Affärsmått**: spårar företagets affärsprestanda och hälsa. Affärsmått kan ha två olika utgångar: ett numeriskt resultat som visas på **startsidan** eller en ny entitet som du hittar på sidan **entiteter**.

4. Ange ett **namn** och ett valfritt **visningsnamn** och välj sedan **nästa**.

5. I avsnittet **Entiteter**, markera den första entiteten från listrutan. I det här skedet bör du bestämma om ytterligare entiteter behövs som en del av måttdefinitionen.

   > [!div class="mx-imgBorder"]
   > ![Måttdefinition](media/measure-definition.png "Måttdefinition")

   Om du vill lägga till fler entiteter väljer du **Lägg till entitet** och markerar de entiteter du vill använda för måttet.

   > [!NOTE]
   > Du kan bara välja entiteter som har förhållanden till din utgångsenhet. För mer information om hur du definierar relationer, se [relationer](relationships.md).

6. Du kan även konfigurera variabler. I avsnittet **Variabler**, välj **Ny variabel**.

   Variabler är beräkningar som görs för varje markerad post. Exempel: summering av kassa (POS) och försäljning online för varje kunds post.

7. Ange ett **Namn** för variabeln.

8. I området **Uttryck** area, välj ett fält att börja din beräkning med.

9. Skriv ett uttryck i området **uttryck** och välj fler fält som ska ingå i beräkningen.

   > [!NOTE]
   > För närvarande stöds endast aritmetiska uttryck. Variabla beräkningar stöds inte för entiteter från olika [entitetssökvägar](relationships.md).

10. Markera **Klart**.

11. I avsnittet **måttdefinition** anger du hur valda entiteter och beräknade variabler ska slås samman i en ny måttentitet eller ett nytt attribut.

12. Välj **Ny dimension**. Du kan betrakta som en dimension som en funktion *gruppera efter*. Utdata för måttenheten eller attributet grupperas efter alla definierade dimensioner.

    > [!div class="mx-imgBorder"]
    > ![Välj aggregeringscykel](media/measures-businessreport-measure-definition2.png "Välj aggregeringscykel")

    Välj eller ange följande information som en del av dimensionens definition:

    - **Entitet**: om du definierar en måttentitet ska den innehålla minst ett attribut. Om du definierar ett måttattribut tas endast ett attribut med som standard. Det här alternativet är att välja entiteten som innehåller attributet.
    - **Fält**: Välj det specifika attribut som ska ingå antingen i måttentiteten eller attributet.
    - **Bucket**: Välj om du vill samla in data per dag, månad eller år. Det är endast ett obligatoriskt val om du har valt attribut av datumtyp.
    - **Som**: anger namnet på det nya fältet.
    - **Visningsnamn**: definierar fältets visningsnamn.

    > [!NOTE]
    > Ditt affärsmått sparas som en entitet med en siffra och visas på **Startsidan** såvida du inte lägger till fler dimensioner i ditt mått. När du har lagt till fler dimensioner visas *inte* måttet på **Startsidan**.

13. Alternativt kan du lägga till aggregeringsfunktioner. En aggregering som du skapar resulterar i ett nytt värde inom måttentiteten eller attributet. Aggregeringsfunktioner som stöds är: **Min**, **Max**, **Genomsnitt**, **Median**, **Summa**, **Antal unika**, **Först** (tar den första posten i ett dimensionsvärde) och **Sista** (tar den sista posten till ett dimensionsvärde).

14. Välj **Spara** för att spara ändringarna till måttet.

## <a name="manage-your-measures"></a>Hantera dina mått

När du har skapat minst en åtgärd visas en lista med åtgärder på sidan **Åtgärder**.

Du hittar information om måttypen, skaparen, datumet och tiden för att skapa datum och tid, senast redigerad, status (om måttet är aktivt, inaktivt eller misslyckat) och datum och tid för senaste uppdatering. När du väljer ett mått i listan kan du visa en förhandsgranskning av resultatet.

Om du vill uppdatera alla dina åtgärder samtidigt markerar du **Uppdatera allt** utan att välja ett specifikt mått.

> [!div class="mx-imgBorder"]
> ![Åtgärder för att hantera enskilda mått](media/measure-actions.png "Åtgärder för att hantera enskilda mått")

Du kan också välja ett mått i listan och utföra någon av följande åtgärder:

- Markera måttets namn om du vill se detaljerna.
- **Redigera** måttets konfiguration.
- **Byt namn** på mått.
- **Ta bort** måttet.
- Välj tre punkter (...) och sedan **uppdatera** för att starta uppdateringsprocessen för måttet.
- Välj tre punkter (...) och **Hämta** för att hämta en .CSV-fil av måttet.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="next-step"></a>Nästa steg

Du använder befintliga mått för att skapa ditt första kundsegment på sidan **segment**. Mer information finns [Segment](segments.md).
