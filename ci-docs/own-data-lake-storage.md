---
title: Använd ditt eget Azure Data Lake Storage Gen2-konto
author: mukeshpo
description: Lär dig mer om kraven fär att använda ditt eget Azure Data Lake Storage-konto för att lagra Customer Insights-data.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833932"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Använd ditt eget Azure Data Lake Storage Gen2-konto

Med Dynamics 365 Customer Insights får du möjlighet att lagra alla dina data i [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Genom att spara data till Data Lake Storage- godkänner du att data överförs till och lagras på rätt geografisk plats för det Azure-lagringskontot. För mer information, se [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Administratörer i Customer Insights kan [skapa miljöer](create-environment.md) och [ange alternativet för datalagring](create-environment.md#step-2-configure-data-storage) i processen.

## <a name="prerequisites-to-use-your-storage-account"></a>Villkor för att använda ditt lagringskonto

- Azure Data Lake Storage-konton måste finnas i samma Azure-region som du valde när du skapade Customer Insights-miljön. Du kan kontrollera regionen för Customer Insights-miljön under **Administratör** > **System** > **Om**.
- Data Lake Storage måste vara Gen2 och ha [hierarkisk namnrymd aktiverad](/azure/storage/blobs/create-data-lake-storage-account). Gen1-lagringskonton stöds inte.
- En behållare med namnet `customerinsights` måste finnas på lagringskontot. Du måste skapa detn innan du kan använda din egen Data Lake Storage i Customer Insights. Den administratör som konfigurerar Customer Insights-miljön kräver rollen Storage Blob Data-deltagare eller Storage Blob Data-ägare på lagringskontot eller behållaren `customerinsights`. Mer information om hur du tilldelar behörighet i ett lagringskonto finns i [Skapa ett lagringskonto](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Anslut Customer Insights till ditt lagringskonto

När du skapar en ny miljö ska du se till att Data Lake Storage-kontot finns och att alla krav uppfylls.

1. I steget **Datalagring** när miljön skapas ska **Spara utdata** som **Azure Data Lake Storage Gen2**.
1. Välj hur du vill **ansluta ditt lagringsutrymme**. Du kan välja mellan ett resursbaserat och ett prenumerationsbaserat autentiseringsalternativ. Mer information finns i [Ansluta till ett Azure Data Lake Storage-konto med hjälp av ett huvudkonto för Azure-tjänster](connect-service-principal.md).
   - För **Azure-prenumeration** väljer du den **prenumeration**, den **resursgrupp** och det **lagringskonto** som innehåller behållaren `customerinsights`.
   - För **Kontonyckel** anger du **kontonamn** och **kontonyckel** för Data Lake Storage-kontot. Om du använder denna autentiseringsmetod antyder det att du känner till huruvida din organisation roterar nycklarna. Du måste [uppdatera miljökonfigurationen](manage-environments.md#edit-an-existing-environment) med den nya nyckeln när denna roteras.

När systemprocesser såsom datainmatning är slutförd skapar systemet motsvarande kataloger på lagringskontot. Datafiler och *model.json*-filer skapas och läggs till i mappar baserat på processnamn.

Om du skapar flera miljöer med Customer Insights och väljer att spara utdataentiteterna från dessa miljöer till ditt lagringskonto skapar Customer Insights separata mappar för varje miljö med `ci_environmentID` i behållare.
