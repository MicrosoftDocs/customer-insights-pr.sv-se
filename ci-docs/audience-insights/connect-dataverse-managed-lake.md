---
title: Anslut till tabeller i Microsoft Dataverse
description: Importera data från en Microsoft Dataverse hanterad datasjö.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 8e11b60295fa5c187b1ac4877fb347e2d9bb41a1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354164"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Anslut till data i en Microsoft Dataverse hanterad datasjö



Den här artikeln innehåller information om hur Dataverse användare snabbt kan ansluta till analysentiteter i en Microsoft Dataverse hanterad sjö. 

> [!NOTE]
> Du måste vara administratör i Dataverse organisationen för att kunna fortsätta och visa listan över entiteter som är tillgängliga i den hanterade organisationen.

## <a name="important-considerations"></a>Viktigt!

Data som lagras i en onlinetjänster, t.ex. Azure Data Lake Storage kan lagras på en annan plats än där data bearbetas eller lagras i Dynamics 365 Customer Insights.Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Ansluta till en Dataverse hanterad sjö

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Välj **Lägg till datakälla**.

3. Välj **Microsoft Dataverse** och välj **Nästa**.

4. Ange ett **namn** för datakällan och välj sedan **Nästa**. 

5. Ange **serveradressen** för Dataverse-organisationen och välj sedan **Logga in**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Skärmen i datainmatningssteget där en användare kan ange webbadressen (URL) till Dataverse-miljön.":::

6. Välj de tabeller du vill mata in som entiteter för målgruppsinsikter från den tillgängliga listan.    

   > [!NOTE]
   > Om vissa tabeller redan är valda kan dessa komma att användas av andra Dynamics 365-program (till exempel Dynamics 365 Sales Insights elller Customer Service Insights). Det går inte att ändra det här valet. Dessa tabeller blir tillgängliga som entiteter när datakällan har skapats.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogruta med en lista över entiteter i Dataverse-miljön.":::

7. Spara dina val om du vill börja synkronisera de valda tabellerna från Dataverse. Den nyligen tillagda anslutningen finns på sidan **datakällor**. Dina val placeras i kö och anger entitetsantalet som 0 tills alla markerade tabeller har synkroniserats.

Endast en datakälla av en miljö kan samtidigt använda samma Dataverse-hanterade sjö.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigera en Dataverse hanterad sjö datakälla

Du redigerar endast enhetsurvalet när du har skapat datakälla. Exempel: om fler entiteter har lagts till Dataverse och du vill importera dem också.    
Om du vill skapa en ny Dataverse-datasjö [skapar du en ny datakälla](#connect-to-a-dataverse-managed-lake).

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Markera tre punkter bredvid datakälla som du vill uppdatera.

3. Välj alternativet **Redigera** från listan.

4. Välj ytterligare entiteter från listan med tillgängliga entiteter och välj **Spara**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
