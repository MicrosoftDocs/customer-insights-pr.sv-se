---
title: Relationer mellan entiteter och entiteters sökvägar
description: Skapa och hantera relationer mellan entiteter från flera datakällor.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: 5477798a8b9e0771d390e403379b7447eb7baddd
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081856"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Relationer mellan entiteter och entiteters sökvägar

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

1. Gå till **Data** > **Relationer**.

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

## <a name="set-up-account-hierarchies"></a>Ange kontohierarkier

Miljöer som är konfigurerade att använda affärskonton som primär målgrupp kan konfigurera kontohierarkier för relaterade affärskonton. Till exempel ett företag som har separata affärsenheter. 

Organisationer skapar kontohierarkier för att bättre hantera konton och deras relationer med varandra. Customer Insights stöder hierarkier för överordnade och underordnade konton som redan finns i hämtade kunddata. Exempelvis konton från Dynamics 365 Sales. De här hierarkierna kan konfigureras på **Relationer** sidan.

1. Gå till **Data** > **Relationer**.
1. Välj fliken **kontohierarki**.
1. Välj **Ny kontohierarki**. 
1. Ange ett namn på hierarkin i rutan **Kontohierarki**. Systemet skapar ett namn på utdataentiteten. Du kan ändra namnet på entiteten för utdatanamnet.
1. Välj den entitet som innehåller kontohierarkin. Vanligtvis finns den i samma entitet som innehåller kontona.
1. Välj **Konto-ID** och **ID för överordnat konto** från den valda entiteten 
1. Välj **Spara** om du vill tillämpa inställningarna och slutföra kontohierarkin.

## <a name="view-relationships"></a>Visa relationer

På Relationer-sidan visas alla relationer som har skapats. Varje rad representerar en relation, som också innehåller information om källentiteten, målentiteten och kardinaliteten. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista över relationer och alternativ i åtgärdsfältet på Relationer-sidan.":::

Den här sidan innehåller en uppsättning alternativ för befintliga och nya relationer: 
- **Ny relation**: [Skapa en anpassad relation](#create-a-custom-relationship).
- **Visualiserare**: [Utforska relationsvisualiseraren](#explore-the-relationship-visualizer) för att se ett nätverksdiagram över befintliga relationer och deras kardinalitet.
- **Filtrera efter**: Välj vilken typ av relationer som ska visas i listan.
- **Sök relationer**: Använd en textbaserad sökning efter egenskaper för relationer.

### <a name="explore-the-relationship-visualizer"></a>Utforska relationsvisualiseraren

Relationsvisualiseraren visar ett nätverksdiagram över befintliga relationer mellan anslutna entiteter och deras kardinalitet. Det visualiserar också relationssökvägen.

Om du vill anpassa vyn kan du ändra rutornas placering genom att dra dem på arbetsytan.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skärmbild av relationsvisualiseringsnätverksdiagrammet med anslutningar mellan relaterade entiteter.":::

Tillgängliga alternativ: 
- **Exportera som bild**: Spara den aktuella vyn som en bildfil.
- **Ändra till vågrät/lodrät layout**: Ändra justeringen för entiteterna och relationer.
- **Redigera**: Uppdatera egenskaper för anpassade relationer i redigeringsfönstret och spara ändringar.

## <a name="relationship-paths"></a>Relationsvägar

En relationsväg beskriver de entiteter som är kopplade genom relationer mellan en källentitet och en målentitet. Den används när du skapar ett segment eller ett mått som innehåller andra entiteter än entiteten för en enhetlig profil och det finns flera alternativ för att nå entiteten för en enhetlig profil. 

En relationsväg informerar systemet om vilka relationer som har åtkomst till den sammanslagna profilentiteten. Olika relationssökvägar kan ge olika resultat.

Entiteten har till exempel *eCommerce_eCommercePurchases* har följande information för enhetliga profil *Kund*:

- eCommerce_eCommercePurchases > kund
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > kund
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > kund 

En relationsväg avgör vilka entiteter du kan använda när du skapar regler för åtgärder eller segment. Om du väljer alternativet med den längsta relationssökvägen ger det troligen färre resultat eftersom matchande poster måste vara en del av alla entiteter. I det här exemplet måste en kund ha köpt varor via e-handeln (eCommerce_eCommercePurchases), vid en försäljningsställe(POS_posPurchases) och delta i vårt lojalitetsprogram (loyaltyScheme_loyCustomers). När du väljer det första alternativet får du förmodligen fler resultat eftersom kunderna bara behöver finnas i en ytterligare entitet.

### <a name="direct-relationship"></a>Direkt relation

En relation klassificeras som en **direkt relation** då en källentitet relaterar till en målentitet med endast en relation.

Om exempelvis en aktivitetsentitet med namnet *eCommerce_eCommercePurchases* ansluter till en målentitet *eCommerce_eCommerceContacts* enbart via *ContactId* är det en direkt relation.

:::image type="content" source="media/direct_Relationship.png" alt-text="Källentiteten ansluter direkt till målentiteten.":::

#### <a name="multi-path-relationship"></a>Relation med flera vägar

En **relation med flera vägar** är en speciell typ av direkt relation som ansluter en källentitet till flera målentiteter.

Om exempelvis en aktivitetsentitet med namnet *eCommerce_eCommercePurchases* ansluter till två målentiteter, både *eCommerce_eCommerceContacts* och *loyaltyScheme_loyCustomers*, är det en relation med flera vägar.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Källentiteten ansluter direkt till flera målentiteter via en multi-hop-relation.":::

### <a name="indirect-relationship"></a>Indirekt relation

En relation klassificeras som en **indirekt relation** då en källentitet relaterar till en eller flera ytterligare entiteter före den ansluter till en målentitet.

#### <a name="multi-hop-relationship"></a>Multi-hop-relation

En *multi-hop-relation* är en *indirekt relation* som gör att du kan ansluta en källentitet till en målentitet via en eller flera andra mellanliggande entiteter.

Om exempelvis en aktivitetsentitet med namnet *eCommerce_eCommercePurchasesWest* ansluter till en mellanliggande entitet med namnet *eCommerce_eCommercePurchasesEast* och sedan ansluter till en målentitet med namnet *eCommerce_eCommerceContacts* är det multi-hop-relation.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Källentiteten ansluter direkt till en målentitet med en mellanliggande entitet.":::

### <a name="multi-hop-multi-path-relationship"></a>Multi-hop-relation med flera vägar

Multi-hop-relationer och relationer med flera vägar kan användas tillsammans och skapa en **multi-hop-relation med flera vägar**. Den här specialtypen kombinerar funktionerna för **multi-hop-relationer** och **relationer med flera vägar**. Du kan ansluta till fler än en målentitet med hjälp av mellanliggande entiteter.

Om exempelvis en aktivitetsentitet med namnet *eCommerce_eCommercePurchasesWest* ansluter till en mellanliggande entitet med namnet *eCommerce_eCommercePurchasesEast* och sedan ansluter till två målentiteter, både *eCommerce_eCommerceContacts* och *loyaltyScheme_loyCustomers*, är det multi-hop-relation med flera vägar.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Källentiteten ansluter direkt till en målentitet och ansluter till en annan målentitet via en mellanliggande entitet.":::

## <a name="manage-existing-relationships"></a>Hantera befintliga relationer 

På sidan Relationer representeras varje relation av en rad. 

Välj en relation och välj något av följande alternativ: 
 
- **Redigera**: Uppdatera egenskaper för anpassade relationer i redigeringsfönstret och spara ändringar.
- **Ta bort**: Ta bort anpassade relationer.
- **Visa**: Visa systemskapade och ärvda relationer. 

## <a name="next-step"></a>Nästa steg

System och anpassade relationer används för att [skapa segment](segments.md) och [mått](measures.md) baserade på flera datakällor som inte längre är silo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
