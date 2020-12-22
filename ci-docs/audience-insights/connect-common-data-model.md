---
title: Anslut Common Data Model till ett Azure Data Lake-konto
description: Arbeta med Common Data Model-data med hjälp av Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643480"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Anslut till en Common Data Model-mapp som använder Azure Data Lake-konto

Den här artikeln innehåller information om hur du matar in data från en Common Data Model-mapp med hjälp av ditt Azure Data Lake Storage Gen2-konto.

## <a name="important-considerations"></a>Viktigt!

- Data i Azure Data Lake måste följa standarden Common Data Model. Andra format stöds inte för tillfället.

- Datainmatning stöder Azure Data Lake *Gen2*-lagringskonton exklusivt. Du kan inte använda Azure Data Lake Gen1-lagringskonton för att mata in data.

- Om du vill autentisera med Azure-tjänstens huvudkonto, se till att det är konfigurerat i din klientorganisation. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md).

- Den Azure Data Lake du vill ansluta och mata in data från måste vara i samma Azure-region som Dynamics 365 Customer Insights-miljön. Anslutningar till en Common Data Model-mapp från en datasjö i en annan Azure-region stöds inte. Om du vill veta Azure-regionen i miljön, gå till **Admin** > **System** > **Om** i målgruppsinsikter.

- Data som lagras i onlinetjänster kan lagras på en annan plats än där data behandlas eller lagras i Dynamics 365 Customer Insights.Genom att importera eller ansluta till data som lagras på en onlinetjänst, t.ex. godkänner du att data kan överföras till och lagras med Dynamics 365 Customer Insights. [Läs mer i Microsoft säkerhetscenter.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Anslut till en Common Data Model-mapp

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Välj **Anslut till en Common Data Model-mapp**, ange ett **Namn** på datakällan och välj **Nästa**.

1. Du kan välja mellan att använda ett resursbaserat alternativ och ett prenumerationsbaserat alternativ för autentisering. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md). Ange informationen **Behållare** och välj **Nästa**.
   > [!div class="mx-imgBorder"]
   > ![Dialogruta där du kan ange anslutningsinformation för Azure Data Lake](media/enter-new-storage-details.png)

1. I dialogrutan **Välj en Common Data Model-mapp** väljer du den model.json-fil som data ska importeras från och väljer sedan **Nästa**.
   > [!NOTE]
   > Inga model.json-filer som är associerade med en annan datakälla i miljön visas.

1. Du får en lista över tillgängliga entiteter i den valda model.json-filen. Du kan granska och välja i listan bland tillgängliga entiteter och välja **Spara**. Alla de valda entiteterna matas in från den nya datakällan.
   > [!div class="mx-imgBorder"]
   > ![Dialogruta med en lista över entiteter från en modell.json-fil](media/review-entities.png)

8. Ange vilka dataentiteter du vill aktivera dataprofilering för och välj **Spara**. Med dataprofilering kan du använda analyser och andra funktioner. Du kan välja hela entiteten, som väljer alla attribut från entiteten, eller välja vissa valfria attribut. Som standard är ingen entitet aktiverad för dataprofilering.
   > [!div class="mx-imgBorder"]
   > ![Dialogruta som visar en dataprofilering](media/dataprofiling-entities.png)

9. När du har sparat dina val öppnas sidan **datakällor**. Nu bör du se anslutningen för Common Data Model-mappen som en datakälla.

> [!NOTE]
> En model.json-fil kan bara associera med en datakälla i samma miljö. Samma model.json-fil kan dock användas för datakällor i flera miljöer.

## <a name="edit-a-common-data-model-folder-data-source"></a>Redigera en datakälla för en Common Data Model-mapp

Du kan uppdatera åtkomstnyckeln för det lagringskonto som innehåller Common Data Model-mappen. Du kan också ändra model.json-filen. Om du vill ansluta till en annan behållare från lagringskontot eller ändra kontonamnet måste du [skapa en ny datakällaanslutning](#connect-to-a-common-data-model-folder).

1. I målgruppsinsikter går du till **Data** > **Datakällor**.

2. Markera tre punkter bredvid datakälla som du vill uppdatera.

3. Välj alternativet **Redigera** från listan.

4. Om du vill kan du uppdatera **åtkomst nyckeln** och välja **nästa**.

   ![Dialogruta för att redigera och uppdatera en snabb tangent för en befintlig datakälla](media/edit-access-key.png)

5. Eventuellt kan du uppdatera från en kontonyckelanslutning till en resursbaserad eller en prenumerationsbaserad anslutning. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md). Du kan inte ändra informationen **Behållare** när anslutningen uppdateras.
   > [!div class="mx-imgBorder"]
   > ![Dialogruta där du kan ange anslutningsinformation för Azure Data Lake](media/enter-existing-storage-details.png)

6. Alternativt kan du välja en annan model.json-fil med en annan uppsättning entiteter från behållaren.

7. Eventuellt kan du välja ytterligare entiteter att mata in. Du kan också ta bort alla entiteter som redan är markerade om det inte finns några beroenden.

   > [!IMPORTANT]
   > Om det finns beroenden på den befintliga model.json-filen och uppsättningen med entiteter visas ett felmeddelande och det går inte att välja en annan model.json-fil. Ta bort beroendena innan du ändrar model.json-filen eller skapa en ny datakälla med model.json-filen som du vill använda för att undvika att ta bort beroendena.

8. Eventuellt kan du välja ytterligare attribut eller entiteter för att aktivera dataprofilering på eller inaktivera redan valda.   
