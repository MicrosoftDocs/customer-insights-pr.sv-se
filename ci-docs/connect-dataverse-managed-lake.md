---
title: Anslut till tabeller i Microsoft Dataverse
description: Importera data från en Microsoft Dataverse hanterad data lake.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 7140e9254108bc6f0d518b3ccf4b10fc33cde115
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800199"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Anslut till data i en Microsoft Dataverse hanterad data lake

Den här artikeln innehåller information om hur Dataverse användare snabbt kan ansluta till analysentiteter i en Microsoft Dataverse hanterad sjö. 

> [!NOTE]
> Du måste vara administratör i Dataverse organisationen för att kunna fortsätta och visa listan över entiteter som är tillgängliga i den hanterade organisationen.

## <a name="important-considerations"></a>Viktigt!

1. Data som lagras i en onlinetjänster, t.ex. Azure Data Lake Storage kan lagras på en annan plats än där data bearbetas eller lagras i Dynamics 365 Customer Insights. Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter](https://www.microsoft.com/trust-center).
2. Endast Dataverse-entiteter med aktiverad [ändringsspårning](/power-platform/admin/enable-change-tracking-control-data-synchronization) visas. Dessa entiteter kan exporteras till den Dataverse-hanterade data laken och användas i Customer Insights. Färdiga Dataverse-tabeller har ändringsspårning aktiverad som standard. Du måste aktivera ändringsspårning för anpassade tabeller. Om du vill kontrollera om en Dataverse-tabell har aktiverats för ändringsspårning går du till [Power Apps](https://make.powerapps.com) > **Data** > **Tabeller**. Leta upp tabellen av intresse och välj den. Gå till **Inställningar** > **Avancerade alternativ** och granska inställningen **Spåra ändringar**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Ansluta till en Dataverse hanterad sjö

1. I Customer Insights, gå till **Data** > **Datakällor**.

2. Välj **Lägg till datakälla**.

3. Välj **Microsoft Dataverse** och välj **Nästa**.

4. Ange ett **namn** för datakällan och välj sedan **Nästa**. 

5. Ange **serveradressen** för Dataverse-organisationen och välj sedan **Logga in**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Skärmen i datainmatningssteget där en användare kan ange webbadressen (URL) till Dataverse-miljön.":::

6. Välj de tabeller du vill ange som entiteter i Customer Insights i den tillgängliga listan.    

   > [!NOTE]
   > Om vissa tabeller redan är valda kan dessa komma att användas av andra Dynamics 365-program (till exempel Dynamics 365 Sales Insights elller Customer Service Insights). Det går inte att ändra det här valet. Dessa tabeller blir tillgängliga som entiteter när datakällan har skapats.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogruta med en lista över entiteter i Dataverse-miljön.":::

7. Spara dina val om du vill börja synkronisera de valda tabellerna från Dataverse. Den nyligen tillagda anslutningen finns på sidan **datakällor**. Dina val placeras i kö och anger entitetsantalet som 0 tills alla markerade tabeller har synkroniserats.

Endast en datakälla av en miljö kan samtidigt använda samma Dataverse-hanterade sjö.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigera en Dataverse hanterad sjö datakälla

Du redigerar endast enhetsurvalet när du har skapat datakälla. Exempel: om fler entiteter har lagts till Dataverse och du vill importera dem också.    
Om du vill skapa en ny Dataverse-data lake [skapar du en ny datakälla](#connect-to-a-dataverse-managed-lake).

1. Gå till **Data** > **Datakällor**.

2. Markera den stående ellipsen (&vellip;) bredvid den datakälla du vill uppdatera.

3. Välj alternativet **Redigera** från listan.

4. Välj ytterligare entiteter från listan med tillgängliga entiteter och välj **Spara**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
