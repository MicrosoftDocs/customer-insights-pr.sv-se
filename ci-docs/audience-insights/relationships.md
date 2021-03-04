---
title: Relationer mellan entiteter och entiteters sökvägar
description: Skapa och hantera relationer mellan entiteter från flera datakällor.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269903"
---
# <a name="relationships-between-entities"></a>Relationer mellan entiteter

Relationer hjälper dig att ansluta entiteter och skapa ett diagram över dina data när entiteter delar en gemensam identifierare (sekundär nyckel) som kan refereras från en entitet till en annan. Med anslutna entiteter kan du definiera segment och mått baserat på flera datakällor.

Det finns två typer av relationer. Systemrelationer som inte kan redigeras, som skapas automatiskt och anpassade relationer skapas och konfigureras av användare.

Under matchnings- och sammanslagningsprocesserna skapas systemrelationer i bakgrunden, baserat på intelligent matchning. Med hjälp av dessa relationer kan kund profilposterna relateras till andra motsvarande entiteter. Följande diagram illustrerar skapandet av tre systemrelationer när entiteten kund matchas med ytterligare entiteter för att producera den slutliga entiteten för kundprofilen.

> [!div class="mx-imgBorder"]
> ![Skapar relation](media/relationships-entities-merge.png "Skapar relation")

- ***CustomerToContact* relationen** skapades mellan entiteten kund och entiteten kontakt. Entiteten Kund hämtar nyckelfält **Contact_contactId** som relaterar till nyckelfältet kontaktentitet **contactId**.
- ***CustomerToAccount* relationen** skapades mellan entiteten kund och entiteten konto. Entiteten Kund hämtar nyckelfält **Account_accountId** som relaterar till nyckelfältet kontoentitet **accountId**.
- ***CustomerToWebAccount* relationen** skapades mellan entiteten kund och entiteten WebAccount. Entiteten Kund hämtar nyckelfält **WebAccount_webaccountId** som relaterar till nyckelfältet WebAccount-entitet **webaccountId**.

## <a name="create-a-relationship"></a>Skapa en relation

Definiera anpassade relationer på sidan **Relationer**. Varje relation består av en källentitet (entiteten som innehåller sekundär nyckeln) och en målentitet (den entitet som källentitetens externa nyckel refererar till).

1. I målgruppsinsikter går du till **Data** > **Relationer**.

2. Välj **Ny relation**.

3. I fönstret **Lägg till relationer** anger du följande information:

   > [!div class="mx-imgBorder"]
   > ![Ange relationsdetaljer](media/relationships-add.png "Ange relationsdetaljer")

   - **Relationsnamn**: namn som återspeglar syftet med relationen (t.ex. **AccountWebLogs**).
   - **Beskrivning**: Beskrivning av relationsrollen.
   - **Källentiteten**: Välj den entitet som används som källa i relationen (t.ex. WebLog).
   - **Kardinalitet**: Välj kardinalitet för källentitetsposterna. Exempelvis betyder "många" att flera bloggposter är relaterade till ett enda WebAccount.
   - **Fältet Källnyckel**: Detta representerar det externa nyckel fältet källentiteten. Till exempel WebLog har **accountId** externa nyckelfältet.
   - **Målentiteten**: Välj den entitet som används som mål i relationen (t.ex. WebAccount).
   - **Målets kardinalitet**: Välj kardinalitet för målentitetsposterna. Exempelvis betyder "en" att flera bloggposter är relaterade till ett enda WebAccount.
   - **Fältet Målnyckel**: det här fältet representerar nyckelfältet för målentiteten. Till exempel WebAccount har **accountId** nyckelfältet.

> [!NOTE]
> Det går bara att använda många till en-relationer och en till en-relationer. Många till många-relationer kan skapas med två många till en-relationer och en länkentitet (en entitet som används för att ansluta källentiteten och målentiteten).

## <a name="delete-a-relationship"></a>Ta bort en relation

1. I målgruppsinsikter går du till **Data** > **Relationer**.

2. Markera kryssrutan för de relationer du väljer att radera.

3. Välj **Radera** längst upp i tabellen **Relationer**.

4. Bekräfta borttagningen.

## <a name="next-step"></a>Nästa steg

System och anpassade relationer används för att skapa segment utifrån flera datakällor som inte längre är silor. Mer information finns [Segment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]