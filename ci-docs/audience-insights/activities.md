---
title: Kundaktiviteter
description: Definiera kundaktiviteter och visa dem på tidslinjen för kunden.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596751"
---
# <a name="customer-activities"></a>Kundaktiviteter

Kombinera kundaktiviteter från [olika datakällor](data-sources.md) i Dynamics 365 Customer Insights och skapa en kundtidslinje som visar aktiviteterna i kronologisk ordning. Du kan lägga till tidslinjen i appar för kundengagemang i Dynamics 365 via [tillägget kundkort](customer-card-add-in.md) eller på en Power BI-instrumentpanel.

## <a name="define-an-activity"></a>Definiera en aktivitet

Dina datakällor innehåller entiteter med transaktions- och aktivitetsdata från flera datakällor. Identifiera entiteterna och välj de aktiviteter du vill visa på kundens tidslinje. Välj den entitet som innehåller målaktiviteten eller aktiviteterna.

1. I målgruppsinsikter går du till **Data** > **Aktiviteter**.

1. Välj **Lägg till aktivitet**.

   > [!NOTE]
   > En entitet måste ha minst ett attribut av typen **Datum** för att kunna tas med i en kundtidslinje och du kan inte lägga till entiteter utan **datum**-fält. Kontrollen **Lägg till aktivitet** är inaktiverad om ingen sådan entitet hittas.

1. I rutan **Lägg till aktivitet** ställa in värdena för följande fält:

   - **Entitet**: Välj en entitet som innehåller transaktions- eller aktivitetsdata.
   - **Primärnyckeln**: Välj fältet som används för unik identifiering av en post. Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.
   - **Tidsstämpel**: Välj det fält som representerar starttiden för aktiviteten.
   - **Händelse**: Välj det fält som utgör händelsen för aktiviteten.
   - **Webbadress**: Markera fältet som representerar en URL som tillhandahåller ytterligare information om aktiviteten. Det kan till exempel vara det transaktionssystem som visar aktiviteten. URL:en kan vara vilket fält som helst från datakällan, eller också kan den skapas som ett nytt fält med hjälp av en Power Query-omvandling. URL-data kommer att lagras i entiteten för enhetliga aktiviteter och kan konsumeras längre fram med hjälp av API:er.
   - **Detaljer**: Alternativt kan du välja det fält som du vill lägga till ytterligare information.
   - **Ikon**: om du vill kan du markera den ikon som representerar aktiviteten.
   - **Aktivitetstyp**: Definiera den referens till Common Data Model för aktivitetstypen som bäst beskriver den semantiska definitionen av aktiviteten.

1. I avsnittet **Konfigurera relation** konfigurerar du detaljerna för att koppla dina aktivitets data till den motsvarande kunden.

    - **Fältet aktivitetsentitet**: Välj det fält i aktivitetsentiteten som ska användas för att skapa en relation med en annan entitet.
    - **Kundentitet**: Välj den motsvarande källkundentitet som du vill att aktivitetsentiteten ska finnas i relation till. Du kan bara relatera till de kundentiteter för kunder som används i föreningsprocessen för data.
    - **Fältet kundentitet**: i det här fältet visas primärnyckeln för källkundentiteten enligt vad som valts i mappningsprocessen. Det här primära nyckelfältet i entiteten för källkund används för att upprätta en relation med entiteten aktivitet.
    - **Namn**: om det redan finns en relation mellan den här aktivitetsentiteten och den valda källkundentiteten är relationsnamnet i skrivskyddat läge. Om det inte finns någon sådan relation skapas en ny relation med det namn som visas här.
   
   > [!div class="mx-imgBorder"]
   > ![Definiera entitetsrelation](media/activities-entities-define.png "Definiera entitetsrelation")

1. Välj **Spara** för att införa ändringarna.

1. På sidan **Aktiviteter**, välj **Kör**.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="edit-an-activity"></a>Redigera en aktivitet

1. I målgruppsinsikter går du till **Data** > **Aktiviteter**.

2. Välj den aktivitetsenhet du vill redigera och välj **Redigera**. Du kan också hovra över entitetens rad och välja ikonen **Redigera**.

3. Klicka på ikonen **Redigera**.

4. Uppdatera värdena i fönstret **redigera aktivitet** och välj **spara**.

5. På sidan **Aktiviteter**, välj **Kör**.

## <a name="delete-an-activity"></a>Ta bort en aktivitet

1. I målgruppsinsikter går du till **Data** > **Aktiviteter**.

2. Välj den aktivitetsenhet du vill ta bort och välj **Ta bort**. Du kan också hovra över entitetens rad och välja ikonen **Ta bort**. Dessutom kan du välja att flera aktivitetsentiteter ska tas bort samtidigt.
   > [!div class="mx-imgBorder"]
   > ![Redigera eller ta bort entitetsrelationerna](media/activities-entities-edit-delete.png "Redigera eller ta bort entitetsrelationerna")

3. Välj ikonen **Ta bort**.

4. Bekräfta borttagningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]