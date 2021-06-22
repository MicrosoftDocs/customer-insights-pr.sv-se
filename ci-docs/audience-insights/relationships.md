---
title: Relationer mellan entiteter och entiteters sökvägar
description: Skapa och hantera relationer mellan entiteter från flera datakällor.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171186"
---
# <a name="relationships-between-entities"></a>Relationer mellan entiteter

Relationer ansluter entiteter och definierar ett diagram över dina data när entiteter delar en gemensam identifierare, en utländsk nyckel. Den här utländska nyckeln kan refereras från en entitet till en annan. Med anslutna entiteter kan du definiera segment och mått baserat på flera datakällor.

Det finns tre typer av relationer: 
- Icke-redigerbara systemrelationer, skapat av systemet som en del av datasammansättningsprocessen
- Icke-redigerbara relationer, som skapas automatiskt från att mata in datakällor 
- Redigerbara anpassade relationer, skapad och konfigurerad av användare

## <a name="non-editable-system-relationships"></a>Icke-redigerbara systemrelationer

Under dataenandet skapas systemrelationer automatiskt baserat på intelligent matchning. Med hjälp av dessa relationer kan kundprofilposterna relateras till motsvarande entiteter. Följande diagram illustrerar skapandet av tre systembaserade relationer. Kundentiteten matchas med andra entiteter för att producera den enhetliga *kundentiteten*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram med relationsvägar för kundentiteten med tre 1-n-relationer.":::

- ***CustomerToContact*-relation** skapades mellan entiteten *Kund* och entiteten *Kontakt*. Entiteten *Kund* får nyckelfältet **Contact_contactID** att relatera till entiteten *Kontakt* s nyckelfält **contactID**.
- ***CustomerToAccount*-relation** skapades mellan entiteten *Kund* och entiteten *Konto*. Entiteten *Kund* hämtar nyckelfält **Account_accountID** som relaterar till entiteten *Konto* s nyckelfält **accountID**.
- ***CustomerToWebAccount*-relation** skapades mellan entiteten *Kund* och entiteten *WebAccount*. Entiteten *Kund* hämtar nyckelfältet **WebAccount_webaccountID** för att relatera till entiteten *WebAccount* s nyckelfält **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Icke-redigerbara ärvda relationer

Under datainmatningsprocessen kontrollerar systemet datakällor för befintliga relationer. Om det inte finns någon relation skapas de automatiskt. Dessa relationer används också i nedströmsprocesser.

## <a name="create-a-custom-relationship"></a>Skapa en anpassad relation

Relationen består av en *källentitet* som innehåller den utländska nyckeln och en *målentitet* som källentitetens utländska nyckel pekar mot. 

1. I målgruppsinsikter går du till **Data** > **Relationer**.

2. Välj **Ny relation**.

3. I fönstret **Ny relation** anger du följande information:

   :::image type="content" source="media/relationship-add.png" alt-text="Nytt relationsfönster med tomma inmatningsfält.":::

   - **Relationsnamn**: Namn som återspeglar relationens syfte. Exempel: CustomerToSupportCase.
   - **Beskrivning**: Beskrivning av relationsrollen.
   - **Källentitet**: Entitet som används som källa i relationen. Exempel: SupportCase.
   - **Målentitet**: Entitet som används som mål i relationen. Exempel: Kund.
   - **Källkardinalitet**: Ange källentitetens kardinalitet. Kardinalitet beskriver antalet möjliga element i en uppsättning. Det har alltid att göra med målkardinaliteten. Du kan välja mellan **En** och **Många**. Det går bara att använda många till en-relationer och en till en-relationer.  
     - Många till en: Flera källposter kan relatera till en målpost. Exempel: Flera supportärenden från en enskild kund.
     - En-till-en: En enda källpost relaterar till en målpost. Exempel: Ett lojalitets-ID för en enskild kund.

     > [!NOTE]
     > Många till många-relationer kan skapas med två många-till-en-relationer och en länkande entitet, som förbinder källentiteten och målentiteten.

   - **Målets kardinalitet**: Välj kardinalitet för målentitetsposterna. 
   - **Källnyckelfält**: Fältet för främmande nyckel i källentiteten. Exempel: SupportCase kan använda CaseID som ett fält med främmande nyckel.
   - **Fältet Målnyckel**: nyckelfältet för målentiteten. Exempel: Kund kan använda nyckelfältet **CustomerID**.

4. Välj **Spara** för att skapa den anpassade relationen.

## <a name="view-relationships"></a>Visa relationer

På Relationer-sidan visas alla relationer som har skapats. Varje rad representerar en relation, som också innehåller information om källentiteten, målentiteten och kardinaliteten. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista över relationer och alternativ i åtgärdsfältet på Relationer-sidan.":::

Den här sidan innehåller en uppsättning alternativ för befintliga och nya relationer: 
- **Ny relation**: [Skapa en anpassad relation](#create-a-custom-relationship).
- **Visualiserare**: [Utforska relationsvisualiseraren](#explore-the-relationship-visualizer) för att se ett nätverksdiagram över befintliga relationer och deras kardinalitet.
- **Filtrera efter**: Välj vilken typ av relationer som ska visas i listan.
- **Sök relationer**: Använd en textbaserad sökning efter egenskaper för relationer.

### <a name="explore-the-relationship-visualizer"></a>Utforska relationsvisualiseraren

Relationsvisualiseraren visar ett nätverksdiagram över befintliga relationer mellan anslutna entiteter och deras kardinalitet.

Om du vill anpassa vyn kan du ändra rutornas placering genom att dra dem på arbetsytan.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skärmbild av relationsvisualiseringsnätverksdiagrammet med anslutningar mellan relaterade entiteter.":::

Tillgängliga alternativ: 
- **Exportera som bild**: Spara den aktuella vyn som en bildfil.
- **Ändra till vågrät/lodrät layout**: Ändra justeringen för entiteterna och relationer.
- **Redigera**: Uppdatera egenskaper för anpassade relationer i redigeringsfönstret och spara ändringar.

## <a name="manage-existing-relationships"></a>Hantera befintliga relationer 

På sidan Relationer representeras varje relation av en rad. 

Välj en relation och välj något av följande alternativ: 
 
- **Redigera**: Uppdatera egenskaper för anpassade relationer i redigeringsfönstret och spara ändringar.
- **Ta bort**: Ta bort anpassade relationer.
- **Visa**: Visa systemskapade och ärvda relationer. 

## <a name="next-step"></a>Nästa steg

System och anpassade relationer används för att [skapa segment](segments.md) utifrån flera datakällor som inte längre är silor.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
