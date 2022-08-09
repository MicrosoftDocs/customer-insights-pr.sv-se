---
title: Exportera till Azure Synapse Analytics (förhandsversion)
description: Lär dig att konfigurera anslutningen till Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196416"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportera till Azure Synapse Analytics (förhandsversion)

Azure Synapse är en analystjänst som snabbare kan få överblick över datalager och stora datasystem. Du kan skapa och använda dina Customer Insights-data i [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Förutsättningar

> [!NOTE]
> Se till att ange alla **rolltilldelningar** enligt beskrivningen.

- I Customer Insights måste Azure Active Directory (AD) användarkonto ha rollen [Administratörsroll](permissions.md#assign-roles-and-permissions).

i Azure:

- En aktiv Azure-prenumeration.

- Om du använder ett nytt Azure Data Lake Storage Gen2-konto måste [tjänsthuvudmannen för Customer Insights](connect-service-principal.md) ha behörigheter för **Storage Blob-datadeltagare**. Data Lake Storage Gen2 **måste ha** [hierarkiskt namnutrymme](/azure/storage/blobs/data-lake-storage-namespace) aktiverat.

- I resursgruppen där Azure Synapse workspace finns måste *tjänstens huvudkonto* och *Azure AD användare med administratörsbehörighet i Customer Insights* tilldelas behörigheter för **Läsare** [behörigheter](/azure/role-based-access-control/role-assignments-portal).

- *Azure AD-användaren med administratörsbehörigheter i Customer Insights* måste har behörigheter för **Storage Blob-datadeltagare** för det Azure Data Lake Storage-Gen2 kontot där data finns och länkade till Azure Synapse workspace. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse workspace hanterad identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* behöver behörigheten **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns och kopplas till Azure Synapse arbetsytan. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- På Azure Synapse workspace, *tjänstens huvudkonto för Customer Insights* har **Synapse-administratör** [roll tilldelad](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Konfigurera anslutningar till Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Azure Synapse Analytics**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Välj eller sök efter prenumerationen som du vill använda Customer Insights data i. Så fort en prenumeration har valts kan du också välja **Arbetsyta**, **Lagringskonto** och **Behållare**.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

## <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)] Om du vill konfigurera exporten med en delad anslutning måste du minst ha behörighet **deltagare** i Customer Insights.

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export**, välj en anslutning från avsnittet Azure Synapse Analytics. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett igenkännande **Visningsnamn** för exporten och ett **Databasnamn** . Vid exporten skapas en ny [Azure Synapse lake databas](/azure/synapse-analytics/database-designer/concepts-lake-database) i arbetsytan som definieras i anslutningen.

1. Välj vilka entiteter du vill exportera till Azure Synapse Analytics.
   > [!NOTE]
   > Datakällor som bygger på en [Common Data Model-mapp](connect-common-data-model.md) stöds inte.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Om du vill fråga efter data som har exporterats till Synapse Analytics måste du ha åtkomsten **Storage Blob Data-läsare** till destinationslagringen på exportarbetsytan.

## <a name="update-an-export"></a>Uppdatera en export

1. Gå till **Data** > **Exporter**.

1. Välj **Redigera** för exporten du vill uppdatera.

   - **Lägga till** eller **Ta bort** entiteter från urvalet. Om entiteter tas bort från urvalet tas de inte bort från Synapse Analytics-databasen. Framtida datauppdateringar uppdaterar emellertid inte de borttagna entiteterna i databasen.

   - **Om du ändrar databasnamnet** skapas en ny Synapse Analytics-databas. Databasen med namnet som konfigurerats tidigare får inga uppdateringar i framtida uppdateringar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
