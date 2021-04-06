---
title: Anslut till entiteter i den Common Data Service-hanterade sjön
description: Importera data från en Common Data Service hanterad datasjö.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596981"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Anslut till data i en Common Data Service hanterad datasjö

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Den här artikeln innehåller information om hur befintliga Dynamics 365-kunder snabbt kan ansluta till deras analysenheter i en Common Data Service hanterad sjö. Du måste vara administratör i Common Data Service organisationen för att kunna fortsätta och visa en lista över tillgängliga entiteter i den hanterade sjän.

## <a name="important-considerations"></a>Viktigt!

Data som lagras i en onlinetjänster, t.ex. Azure Data Lake Storage kan lagras på en annan plats än där data bearbetas eller lagras i Dynamics 365 Customer Insights.Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Ansluta till en Common Data Service hanterad sjö

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Välj **Lägg till datakälla**.

3. Välj **Anslut till Common Data Service** och välj **Nästa**.

4. Ange ett **namn** för datakällan och välj sedan **Nästa**. Namnge riktlinjer: 
   - Inled med en bokstav.
   - Använd endast bokstäver och siffror. Specialtecken och blanksteg är inte tillåtna.
   - Använd mellan 3 och 64 tecken.

5. Ange **Serveradressen** för din Common Data Service organisation och välj **Logga in**.

   > [!div class="mx-imgBorder"]
   > ![Dialogruta där du anger Common Data Service serveradressen](media/enter-CDS-org-details.png)

6. Markera de entiteter som du vill mata in från den tillgängliga listan.    

   > [!NOTE]
   > Om några entiteter redan valts kan de användas av andra Dynamics 365-program (t.ex. Dynamics 365 Sales Insights eller Customer Service Insights). Det går inte att ändra det här valet. Entiteterna blir tillgängliga när datakälla skapas.

   > [!div class="mx-imgBorder"]
   > ![Dialogruta med en lista över entiteter i Common Data Service organisationen](media/select-analytical-entities.png)

7. Spara ditt val om du vill synkronisera de valda enheterna med den Common Data Service hanterade sjö. Den nyligen tillagda anslutningen finns på sidan **datakällor**. Den placeras i kö för uppdatering och visar antalet entiteter som 0 tills alla entiteter har synkroniserats.

Endast en datakälla av en miljö kan samtidigt använda samma Common Data Service-hanterade sjö.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Redigera en Common Data Service hanterad sjö datakälla

Du redigerar endast enhetsurvalet när du har skapat datakälla. Exempel: om fler entiteter har lagts till Common Data Service och du vill importera dem också.    
För att ansluta till en annan Common Data Service, [skapa en ny datakälla](#connect-to-a-common-data-service-managed-lake).

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Markera tre punkter bredvid datakälla som du vill uppdatera.

3. Välj alternativet **Redigera** från listan.

4. Välj ytterligare entiteter från listan med tillgängliga entiteter och välj **Spara**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]