---
title: Exportera Customer Insights-data till Azure Synapse Analytics
description: Lär dig hur du konfigurerar anslutningen och exporterar till Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f206043298bdbf8a84b0ef37b47a43290653beba7d3d0e8b807ec74513614aa8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031955"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportera data till Azure Synapse Analytics (förhandsversion)

Azure Synapse är en analystjänst som snabbare kan få överblick över datalager och stora datasystem. Du kan skapa och använda dina Customer Insights-data i [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Förutsättningar

Följande krav måste uppfyllas för att konfigurera anslutningen från Customer Insights till Azure Synapse.

> [!NOTE]
> Se till att ange alla **rolltilldelningar** enligt beskrivningen.  

## <a name="prerequisites-in-customer-insights"></a>Förkrav i Customer Insights

* Du har rollen **Administratör** i målgruppinsikter. Läs mer om hur du anger [användarbehörigheter i målinsikter](permissions.md#assign-roles-and-permissions)

i Azure: 

- En aktiv Azure-prenumeration.

- Om du använder ett nytt Azure Data Lake Storage Gen2-konto behöver *huvudkonto för tjänsten för målgruppinsikter* behöver behörigheter **Storage Blob-datadeltagare**. Läs mer om att [ansluta till ett Azure Data Lake Storage Gen2-konto med Azure-huvudkonto för tjänsten för målinsikter](connect-service-principal.md). Data Lake Storage Gen2 **måste ha** [hierarkiskt namnutrymme](/azure/storage/blobs/data-lake-storage-namespace) aktiverat.

- I resursgruppen som Azure Synapse arbetsytan finns, måste *huvudkonto för tjänsten* och *användare för målinsikter* måste tilldelas minst behörigheten **Läsare**. Mer information finns i [Tilldela Azure-roller med Azure-portalen](/azure/role-based-access-control/role-assignments-portal).

- *Användaren* behöver **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns kopplade till Azure Synapse arbetsytan. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse arbetsytan hanterad identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* behöver behörigheten **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns och kopplas till Azure Synapse arbetsytan. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- På Azure Synapse arbetsytan behöver *huvudkonto för tjänsten för målinsikter* rollen **Administratör för Synapse** tilldelas. Mer information finns i [Konfigurera åtkomstkontroll för din Synapse-arbetsyta](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Upprätta anslutningen och exportera till Azure Synapse

### <a name="configure-a-connection"></a>Konfigurera en anslutning

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Azure Synapse Analytics** eller välj **Konfigurera** på panelen **Azure Synapse Analytics** för att konfigurera anslutningen.

1. Ge anslutningen ett beskrivande namn i fältet visningsnamn. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj eller sök efter prenumerationen som du vill använda Customer Insights data i. Så fort en prenumeration har valts kan du också välja **Arbetsyta**, **Lagringskonto** och **Behållare**.

1. Välj **Spara** för att spara anslutningen.

### <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till export**.

1. I fältet **Anslutning för export** välj en anslutning från avsnittet **Azure Synapse Analytics**. Om avsnittets namn inte visas finns det inga tillgängliga [anslutningar](connections.md) av den här typen.

1. Ange ett igenkännande **Visningsnamn** för exporten och ett **Databasnamn** .

1. Välj vilka entiteter du vill exportera till Azure Synapse Analytics.
   > [!NOTE]
   > Datakällor som bygger på en [Common Data Model-mapp](connect-common-data-model.md) stöds inte.

2. Välj **Spara**.

När du sparar en export körs inte exporten omedelbart.

Exporten körs med alla [schemalagda uppdateringar](system.md#schedule-tab). Du kan också [exportera data på begäran](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Uppdatera en export

1. Gå till **Data** > **Exporter**.

1. Välj **Redigera** för exporten du vill uppdatera.

   - **Lägga till** eller **Ta bort** entiteter från urvalet. Om entiteter tas bort från urvalet tas de inte bort från Synapse Analytics-databasen. Framtida datauppdateringar uppdaterar emellertid inte de borttagna entiteterna i databasen.

   - **Om du ändrar databasnamnet** skapas en ny Synapse Analytics-databas. Databasen med namnet som konfigurerats tidigare får inga uppdateringar i framtida uppdateringar.
