---
title: Anslut till tabeller i Microsoft Dataverse
description: Importera data från en Microsoft Dataverse hanterad datasjö.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033102"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Anslut till data i en Microsoft Dataverse hanterad datasjö

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Denna artikel innehåller information om hur Dataverse-användare snabbt kan ansluta till sina analysentiteter i en Dataverse-hanterad datasjö. Du måste vara administratör i Dataverse organisationen för att kunna fortsätta och visa en lista över tillgängliga entiteter i den hanterade sjän.

## <a name="important-considerations"></a>Viktigt!

Data som lagras i en onlinetjänster, t.ex. Azure Data Lake Storage kan lagras på en annan plats än där data bearbetas eller lagras i Dynamics 365 Customer Insights.Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Ansluta till en Dataverse hanterad sjö

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Välj **Lägg till datakälla**.

3. Välj **Anslut till Microsoft Dataverse-hanterad datasjö** och välj **Nästa**.

4. Ange ett **namn** för datakällan och välj sedan **Nästa**. Namnge riktlinjer: 
   - Inled med en bokstav.
   - Använd endast bokstäver och siffror. Specialtecken och blanksteg är inte tillåtna.
   - Använd mellan 3 och 64 tecken.

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