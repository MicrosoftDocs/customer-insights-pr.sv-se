---
title: Mata in data från Azure Synapse Analytics
description: Använda en databas i Azure Synapse som en datakälla i Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647697"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Anslut en Azure Synapse-datakälla (förhandsversion)

Azure Synapse Analytics är en företagsanalystjänst som skyndar på tiden till insikter i datalager och stordatasystem. Azure Synapse Analytics samlar de bästa SQL-teknikerna som används inom lagring av företagsdata, Spark-tekniker som används för stordata, Data Explorer för analyser av logg och tidsserier, Pipelines för dataintegrering och ETL/ELT samt djupintegrering med andra Azure-tjänster som Power BI, Cosmos DB och AzureML.

Mer information finns i [Azure Synapse översikt](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas för att konfigurera anslutningen från Dynamics 365 Customer Insights till Azure Synapse.

> [!IMPORTANT]
> Se till att ange alla **rolltilldelningar** enligt beskrivningen.  

## <a name="prerequisites-in-customer-insights"></a>Förkrav i Customer Insights

* Du har rollen **Administratör** i Customer Insights.. Läs mer om [användarbehörigheter i Customer Insights](permissions.md#assign-roles-and-permissions).

i Azure: 

- En aktiv Azure-prenumeration.

- Om du använder ett nytt Azure Data Lake Storage Gen2-konto måste *tjänsthuvudmannen för Customer Insights* ha behörigheter för **Storage Blob-datadeltagare**. Lär dig mer om [att ansluta till Azure Data Lake Storage med ett huvudkonto för Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **måste ha** [hierarkiskt namnutrymme](/azure/storage/blobs/data-lake-storage-namespace) aktiverat.

- I resursgruppen där Azure Synapse workspace finns måste *tjänstens huvudkonto* och *användare för Customer Insights* måste tilldelas behörigheter för **Läsare**. Mer information finns i [Tilldela Azure-roller med Azure-portalen](/azure/role-based-access-control/role-assignments-portal).

- *Användaren* behöver **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns kopplade till Azure Synapse arbetsytan. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse arbetsytan hanterad identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* behöver behörigheten **Storage Blob-datadeltagare** i kontot Azure Data Lake Storage Gen2 där data finns och kopplas till Azure Synapse arbetsytan. Läs mer om hur du [använder Azure-portalen för att tilldela en Azure-roll för åtkomst till blobb och ködata](/azure/storage/common/storage-auth-aad-rbac-portal) och [behörigheter för Storage Blob-datadeltagare](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- På Azure Synapse workspace måste *tjänstens huvudkonto för Customer Insights* ha behörighet för **Synapse-administratör** tilldelad. Mer information finns i [Konfigurera åtkomstkontroll för din Synapse-arbetsyta](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Anslut till Data Lake-databaser i Azure Synapse Analytics

1. Gå till **Data** > **Datakällor**.

1. Välj **Lägg till datakälla**.

1. Välj metoden **Azure Synapse Analytics (förhandsversion)**.

1. Ange ett **namn** på datakälla och välj **nästa** om du vill skapa datakälla. 

1. Välj en [tillgänglig anslutning](connections.md) till Azure Synapse Analytics eller skapa en ny.

1. Välj en **Lake-databas** från arbetsytan som är ansluten till vald Azure Synapse Analytics-anslutning och välj **Nästa**.

1. Välj vilka entiteter som ska matas in från den anslutna databasen. 

1. Alternativt kan du välja vilka dataentiteter som dataprofilering ska tillåtas för. 

1. Välj **Spara** om du vill tillämpa dina val och starta inmatningen av data från den nyligen skapade datakällan länkad till Lake-databastabellerna i Azure Synapse Analytics.
