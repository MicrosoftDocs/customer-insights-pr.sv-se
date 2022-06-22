---
title: Uppdatera uppdateringar för Power Query och för Azure Data Lake datakällor
description: Uppdatera nya och uppdaterade data för stora datakällor baserat på Power Query eller Azure Data Lake datakällor.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012047"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Uppdatera uppdateringar för Power Query och för Azure Data Lake datakällor

I den här artikeln beskrivs hur du konfigurerar inkrementella uppdateringar datakällor som är baserade på Power Query eller Azure Data Lake.

Stegvis uppdatering för datakällor har följande fördelar:

- **Snabbare uppdateringar** – endast data som har ändrats uppdateras. Du kan till exempel endast uppdatera de fem senaste dagarna av en historisk datauppsättning.
- **Ökad pålitlighet** – med mindre uppdateringar behöver du inte upprätthålla anslutningar till temporärt källsystem så länge som minskar risken för anslutningsproblem.
- **Minskad resursförbrukning** – uppdatera endast en del av dina totala dataleads till en effektivare användning av datorresurser och minskar miljöutrymme.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfigurera inkrementell uppdatering för datakällor baserade på Power Query

Customer Insights gör det möjligt att göra inkrementella uppdateringar för datakällor som importeras genom Power Query som stöder inkrementell inmatning. Till exempel Azure SQL-databaser med datum- och tidsfält som anger när dataposter senast uppdaterades.

1. [Skapa en ny datakälla som är baserad på Power Query](connect-power-query.md).

1. Välj en datakälla som stöder inkrementell uppdatering, t.ex. [Azure SQL-databas.](/power-query/connectors/azuresqldatabase).

1. Välj de entiteter eller register som du vill samla in.

1. Slutför omvandlingsstegen och välj **nästa**.

1. I dialogrutan **Konfigurera inkrementell uppdatering** väljer du **konfigurera** för att öppna **inkrementella uppdateringsinställningar**. Om du väljer **hoppa över** kommer datakällan att uppdatera hela datauppsättningen.
   > [!TIP]
   > Du kan också tillämpa stegvis uppdatering senare genom att redigera en befintlig datakälla.

1. På **Inställningar för stegvis uppdatering**, konfigurerar du den inkrementella uppdateringen för alla entiteter du valde när du skapade datakälla.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurera inställningar för inkrementell uppdatering.":::

1. Välj en entitet och ange följande information:

   - **Definiera primär nyckeln**: Välj en primär nyckel för entiteten eller tabellen.
   - **Definiera senast uppdaterade fältet**: det här fältet visar endast attribut av typen datum eller tid. Välj ett attribut som anger när posterna senast uppdaterades. Den används för att identifiera poster som faller inom den inkrementella uppdateringens tidsram.
   - **sök efter uppdateringar varje**: anger hur länge du vill tidsram den inkrementella uppdateringen.

1. Klicka på **spara** för att slutföra skapandet av datakälla. Den ursprungliga datauppdateringen blir en fullständig uppdatering. Därefter sker inkrementella uppdateringen av data som har konfigurerats i föregående steg.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigurera inkrementell uppdatering för Azure Data Lake datakällor

Customer Insights tillåter inkrementell uppdatering för datakällor som är anslutna till Azure Data Lake Storage. För att använda inkrementell inmatning och uppdatering för en entitet, konfigurera den entiteten när du lägger till Azure Data Lake-datakällan eller senare när du redigerar datakällan. Entitetsdatamappen måste innehålla följande mappar:

- **FullData**: Mapp med datafiler som innehåller initiala poster
- **IncrementalData**: Mapp med datum/tidshierarki mappar i **åååå/mm/dd/hh** format som innehåller uppdateringar för uppdateringar. **hh** representerar UTC-timmen för uppdateringarna och innehåller mapparna **Upserts** och **Borttagningar**. **Upserts** innehåller datafiler med uppdateringar av befintliga poster eller nya poster. **Borttagningar** innehåller datafiler med poster som ska tas bort.

1. När du lägger till eller redigerar datakälla navigerar du till entitetens **attribut** fönster.

1. Granska attributen. Se till att ett skapat eller senast uppdaterat datumattribut är inställt med en *dateTime* **Dataformat** och *Calendar.Date* **Semantisk typ**. Redigera attributet om det behövs och välj **Klar**.

1. Från fönstret **Välj entiteter** redigera entiteten. Kryssrutan **Inkrementell inmatning** markeras.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurera entiteter i en datakälla för inkrementell uppdatering.":::

   1. Bläddra till rotmappen som innehåller .csv- eller .parquet-filerna för fullständig data, inkrementella data upserts och inkrementella dataraderingar.
   1. Ange filnamnstillägget för fullständiga data och båda filerna (\.csv or \.parquet).
   1. Välj **Spara**.

1. För **Senaste uppdatering** väljer du attributet datumtidsstämpel.

1. Om den **primära nyckeln** inte är markerad markerar du den primära nyckeln. Den primära nyckeln är ett attribut som är unikt för entiteten. För att ett attribut ska vara en giltig primär nyckel bör det inte innehålla dubblettvärden, saknade värden och null-värden. Sträng-, heltals- och GUID-datatypattribut stöds som primärnycklar.

1. Välj **Stäng** när du vill spara och stänga fönstret.

1. Fortsätt med att lägga till eller redigera datakälla.

[!INCLUDE [footer-include](includes/footer-banner.md)]
