---
title: Anslut en Azure Synapse-datakälla (förhandsversion)
description: Använda en databas i Azure Synapse som en datakälla i Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259820"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Anslut en Azure Synapse Analytics-datakälla (förhandsversion)

Azure Synapse Analytics är en företagsanalystjänst som skyndar på tiden till insikter i datalager och stordatasystem. Azure Synapse Analytics samlar de bästa SQL-teknikerna som används inom lagring av företagsdata, Spark-tekniker som används för stordata, Data Explorer för analyser av logg och tidsserier, Pipelines för dataintegrering och ETL/ELT samt djupintegrering med andra Azure-tjänster som Power BI, Cosmos DB och AzureML.

Mer information finns i [Azure Synapse översikt](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Förutsättningar

> [!NOTE]
> Synapse-arbetsytor som har [brandvägg aktiverat](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) stöds för närvarande inte.
> [!IMPORTANT]
> Se till att ange alla **rolltilldelningar** enligt beskrivningen.  

**I Customer Insights**:

* Du har rollen **Administratör** i Customer Insights.. Läs mer om [användarbehörigheter i Customer Insights](permissions.md#add-users).

**I Azure**:

- En aktiv Azure-prenumeration.

- Om du använder ett nytt Azure Data Lake Storage Gen2-konto måste *tjänsthuvudmannen för Customer Insights*, vilket är "Dynamics 365 AI for Customer Insights", ha behörigheter för **Storage Blob-datadeltagare**. Lär dig mer om [att ansluta till Azure Data Lake Storage med ett huvudkonto för Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **måste ha** [hierarkiskt namnutrymme](/azure/storage/blobs/data-lake-storage-namespace) aktiverat.

- I resursgruppen där Azure Synapse workspace finns måste *tjänstens huvudkonto*, vilket är "Dynamics 365 AI for Customer Insights", och *användare för Customer Insights* måste tilldelas behörigheter för **Läsare**. Mer information finns i [Tilldela Azure-roller med Azure-portalen](/azure/role-based-access-control/role-assignments-portal).

- *Användaren* behöver **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns kopplade till Azure Synapse arbetsytan. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse arbetsytan hanterad identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* behöver behörigheten **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns och kopplas till Azure Synapse arbetsytan. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- På Azure Synapse workspace måste *tjänstens huvudkonto för Customer Insights*, vilket är "Dynamics 365 AI for Customer Insights", ha behörighet för **Synapse-administratör** tilldelad. Mer information finns i [Konfigurera åtkomstkontroll för din Synapse-arbetsyta](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Om din Customer Insights-miljö lagrar data i din [egen Azure Data Lake Storage](own-data-lake-storage.md), måste användaren som konfigurerar anslutningen till Azure Synapse Analytics minst ha den inbyggda rollen **Läsare** på Data Lake Storage-kontot. Mer information finns i [Tilldela Azure-roller med Azure-portalen](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Anslut till Data Lake-databas i Azure Synapse Analytics

1. Gå till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Välj metoden **Azure Synapse Analytics (förhandsversion)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialogruta för att ansluta till Synapse Analytics-data":::
  
1. Ange ett **Namn** för datakällan och en valfri **Beskrivning**.

1. Välj en [tillgänglig anslutning](connections.md) till Azure Synapse Analytics eller [skapa en ny](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse)

1. Välj en **databas** från arbetsytan som är ansluten till vald Azure Synapse Analytics-anslutning och välj **Nästa**. För tillfället har vi bara stöd för databastypen *lake databas*.

1. Välj vilka entiteter som ska matas in från den anslutna databasen och välj **Nästa**.

1. Alternativt kan du välja vilka dataentiteter som dataprofilering ska tillåtas för.

1. Välj **Spara** om du vill tillämpa dina val och starta inmatningen av data från den nyligen skapade datakällan länkad till Lake-databastabellerna i Azure Synapse Analytics. Sidan **Datakällor** öppnas där den nya datakälla visas i status **uppdateras**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta lång tid att läsa in data. Efter en lyckad uppdatering kan hämtade data granskas från sidan [**Entiteter**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
