---
title: Anslut till data i en Microsoft Dataverse hanterad data lake
description: Importera data från en Microsoft Dataverse hanterad data lake.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206975"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Anslut till data i en Microsoft Dataverse hanterad data lake

Microsoft Dataverse-användare kan snabbt ansluta till analysentiteter i en Microsoft Dataverse hanterad enhet. Endast en datakälla av en miljö kan samtidigt använda samma Dataverse-hanterade sjö.

> [!NOTE]
> Du måste vara administratör i Dataverse organisationen för att kunna fortsätta och visa listan över entiteter som är tillgängliga i den hanterade organisationen.

## <a name="prerequisites"></a>Förutsättningar

- Data som lagras i en onlinetjänster, t.ex. Azure Data Lake Storage kan lagras på en annan plats än där data bearbetas eller lagras i Dynamics 365 Customer Insights. Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter](https://www.microsoft.com/trust-center).

- Endast Dataverse-entiteter med aktiverad [ändringsspårning](/power-platform/admin/enable-change-tracking-control-data-synchronization) visas. Dessa entiteter kan exporteras till den Dataverse-hanterade data laken och användas i Customer Insights. Färdiga Dataverse-tabeller har ändringsspårning aktiverad som standard. Du måste aktivera ändringsspårning för anpassade tabeller. Om du vill kontrollera om en Dataverse-tabell har aktiverats för ändringsspårning går du till [Power Apps](https://make.powerapps.com) > **Data** > **Tabeller**. Leta upp tabellen av intresse och välj den. Gå till **Inställningar** > **Avancerade alternativ** och granska inställningen **Spåra ändringar**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Ansluta till en Dataverse hanterad sjö

1. Gå till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Markera **Microsoft Dataverse**.

1. Ange ett **Namn** för datakällan och en valfri **Beskrivning**.

1. Ange **serveradressen** för Dataverse-organisationen och välj sedan **Logga in**.

1. Välj de tabeller du vill ange som entiteter i Customer Insights i den tillgängliga listan.

   > [!NOTE]
   > Om vissa tabeller redan är valda kan dessa komma att användas av andra Dynamics 365-program (till exempel Dynamics 365 Sales Insights elller Customer Service Insights). Det går inte att ändra det här valet. Dessa tabeller blir tillgängliga som entiteter när datakällan har skapats.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogruta med en lista över entiteter i Dataverse-miljön.":::

1. Spara dina val om du vill börja synkronisera de valda tabellerna från Dataverse. Den nyligen tillagda anslutningen finns på sidan **datakällor**. Dina val placeras i kö och anger entitetsantalet som 0 tills alla markerade tabeller har synkroniserats.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan [**Entiteter**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigera en Dataverse hanterad sjö datakälla

Du redigerar endast enhetsurvalet när du har skapat datakälla. Exempel: om fler entiteter har lagts till Dataverse och du vill importera dem också.
Om du vill skapa en ny Dataverse-data lake [skapar du en ny datakälla](#connect-to-a-dataverse-managed-lake).

1. Gå till **Data** > **Datakällor**.

1. Välj bredvid datakällan du vill uppdatera **Redigera**.

1. Välj ytterligare entiteter från listan med tillgängliga entiteter.

1. Klicka på **Spara** om du vill tillämpa ändringarna och återgå till sidan **Datakällor**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
