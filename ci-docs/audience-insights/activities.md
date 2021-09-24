---
title: Kundaktiviteter
description: Definiera kundaktiviteter och visa dessa på en tidslinje för kundprofiler.
ms.date: 09/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c5697df8a7d011c70384c8bc5e4773d7fcc25a62
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494433"
---
# <a name="customer-activities"></a>Kundaktiviteter

Kombinera kundaktiviteter från [olika datakällor](data-sources.md) i Dynamics 365 Customer Insights för att skapa en tidslinje som visar aktiviteterna kronologiskt. Ta med tidslinjen i Dynamics 365-appar med [tillägget kundkort](customer-card-add-in.md) eller på en Power BI instrumentpanel.

## <a name="define-an-activity"></a>Definiera en aktivitet

Dina datakällor innehåller entiteter med transaktions- och aktivitetsdata från flera datakällor. Identifiera entiteterna och välj de aktiviteter du vill visa på kundens tidslinje. Välj den entitet som innehåller målaktiviteten eller aktiviteterna.

> [!NOTE]
> En entitet måste ha minst ett attribut av typen **Datum** för att kunna tas med i en kundtidslinje och du kan inte lägga till entiteter utan **datum**-fält. Kontrollen **Lägg till aktivitet** är inaktiverad om ingen sådan entitet hittas.

1. I målgruppsinsikter går du till **Data** > **Aktiviteter**.

1. Välj **Lägg till aktivitet** för att starta den guidade upplevelsen för aktivitetens installationsprocessen.

1. I steget **Aktivitetsdata**, ställ in värdena för följande fält:

   - **Aktivitetsnamn**: Välj ett namn för aktiviteten.
   - **Entitet**: Välj en entitet som innehåller transaktions- eller aktivitetsdata.
   - **Primärnyckeln**: Välj fältet som används för unik identifiering av en post. Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurera aktivitetsdata med namn, entitet och primärnyckel.":::

1. Gå vidare till nästa steg genom att välja **Nästa**.

1. I steget **Relation** konfigurerar du informationen så att dina aktivitetsdata kan kopplas till motsvarande kund. Det här steget visualiserar anslutningen mellan entiteter.  

   - **Först**: Fält för externa fält i aktivitetsentiteten som används för att upprätta en relation med en annan entitet.
   - **Andra**: Motsvarande källkundentitet som din aktivitetsentitet ska vara i relation till. Du kan endast relatera till källkundentiteter som används i datakällprocessen.
   - **Tredje**: Om en relation mellan den här aktivitetsentiteten och den valda källkundentiteten redan finns kommer relationsnamnet att vara skrivskyddat läge. Om det inte finns någon sådan relation skapas en ny relation med det namn du anger i rutan.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiera entitetsrelation.":::

1. Gå vidare till nästa steg genom att välja **Nästa**. 

1. I steget **Samordning av aktiviteter** välj aktivitetshändelsen och starttiden för din aktivitet. 
   - **Obligatoriska fält**
      - **Händelseaktivitet**: Fält som är händelsen för aktiviteten.
      - **Tidsstämpel**: Fält som representerar aktivitetens starttid.

   - **Valfria fält**
      - **Ytterligare information**: Fält med relevant information för aktiviteten.
      - **Ikon**: Ikon som bäst representerar den här aktivitetstypen.
      - **Webbadress**: Fält som innehåller en URL med information om aktiviteten. Det kan till exempel vara det transaktionssystem som visar aktiviteten. URL:en kan vara vilket fält som helst från datakällan, eller också kan den skapas som ett nytt fält med hjälp av en Power Query-omvandling. URL-data lagras i entiteten *Enhetlig aktivitet*, som kan användas nedströms med [API:er](apis.md). 

   - **Visa på tidslinje**
      - Välj om du vill visa denna aktivitet i tidslinjevyn för dina kundprofiler. Välj **Ja** om du vill visa aktiviteten på tidslinjen eller **Nej** för att dölja den.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Ange kundaktivitetsdata i en entitet för enhetlig aktivitet.":::

1. Klicka på **Nästa** för att gå till nästa steg. Du kan välja **Slutför och granska** om du vill spara aktiviteten nu med aktivitetstypen **Annat**. 

1. Välj aktivitetstyp i steget **Aktivitetstyp** och välj om du vill mappa några av aktivitetstyperna så att de kan användas i andra områden av Customer Insights. I nuläget kan aktivitetstyperna *Feedback*, *Lojalitet*, *SalesOrder*, *SalesOrderLine* samt *Prenumeration* mappas semantiskt efter godkännande att fälten mappas. Om en aktivitetstyp inte är relevant för den nya aktiviteten kan du välja *Annat* eller *Skapa ny* för en anpassad aktivitetstyp.

1. Klicka på **Nästa** för att gå till nästa steg. 

1. I steget **Granska**, kontrollera dina val. Gå tillbaka till valfritt föregående steg och uppdatera informationen vid behov.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Granska de angivna fälten för en aktivitet.":::
   
1. Välj **Spara aktivitet** om du vill tillämpa ändringarna och välj **Klar** för att gå tillbaka till **Data**  > **Aktiviteter**. Här ser du vilka aktiviteter som ska visas på tidslinjen. 

1. På sidan **Aktiviteter**, välj **Kör** för att bearbeta aktiviteten. 

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.


## <a name="manage-existing-activities"></a>Hantera befintliga aktiviteter

På **Data** > **Aktiviteter**, kan du visa alla sparade aktiviteter och hantera dem. Varje aktivitet representeras av en rad som även innehåller information om källan, entiteten och aktivitetstypen.

Följande åtgärder är tillgängliga när du väljer en aktivitet. 

- **Redigera**: Öppnar aktivitetskonfigurationen i granskningssteget. Du kan ändra vilken som helst av eller hela den aktuella konfigurationen från det här steget. När du har ändrat konfigurationen väljer du **Spara aktivitet** och väljer **Kör** för att bearbeta ändringarna.

- **Byt namn**: Öppnar en dialog där du kan ange ett annat namn för den valda aktiviteten. Välj **Spara** för att införa ändringarna.

- **Ta bort**: Öppnar en dialog för att bekräfta borttagningen av den markerade aktiviteten. Du kan också ta bort mer än en aktivitet samtidigt genom att markera aktiviteterna och sedan markera ikonen för borttagning. Välj **Ta bort** för att borttagningen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
