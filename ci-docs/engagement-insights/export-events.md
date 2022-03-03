---
title: Exportera förfinade händelser
description: Exportera förfinade händelser och bashändelser.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232910"
---
# <a name="export-events"></a>Exportera händelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En händelse representerar användarbeteende. Den registrerar när en användare visar en sida (visa händelse) eller interagerar med innehåll (åtgärdshändelse). När du kan bestämma vilka egenskaper för data som du vill visa i en rapport kallas denna virtuella vy av data a *förfinad händelse*. Mer information finns i [Skapa och ändra händelser](refined-events.md).

- Du kan exportera händelser och förfinade händelser till extern lagring. 
- Exporterna är ett dataflöde för vidarebefordran. Du kan inte fylla på strömmen. 
- Exporten har fasta scheman. Om du lägger till anpassade egenskaper för en händelse inkluderas de inte. Du måste skapa en ny export.

## <a name="prerequisites"></a>Förutsättningar

Innan du upprättar en export måste du ha åtkomst till och en aktiv prenumeration på Azure-portalen. Du behöver information om lagringskontot under exportprocessen. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Skapa ett Azure Data Lake Storage Gen 2-konto

1. Logga in på Azure-portalen och [skapa ett nytt lagringskonto](/azure/storage/common/storage-account-create). 

1. Kontrollera att du aktiverar **Hierarkiskt namnutrymme** på fliken **Avancerat**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Aktivera hierarkisk namnrymd på fliken Avancerat.":::

1. När den har distribuerats går du till det nyligen skapade lagringskontot. I navigeringsfönstret, välj **Inställningar** > **Åtkomstnycklar**. 

1. Kopiera **Kontonamn** och **Nyckel** för att använda dem när du skapar en ny rapport.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Åtkomstnycklar på ett lagringskonto.":::

## <a name="export-events"></a>Exportera händelser

Du kan visa dialogrutan **Exportera händelser** på två sätt: 
- Gå till **Data** > **Exporter** och välj **Ny export**.
- Gå till **Data** > **Händelser**, välj **Fler [...]** bredvid den händelse du vill exportera, och välj **Exportera** i listrutan. 

:::image type="content" source="media/new-export.png" alt-text="Skapa en ny export.":::

Här får du instruktioner om hur du skapar en export:

1. Ange ett **exportnamn** och välj sedan **Nästa**.

1. I listrutan **Händelseval** väljer du de bashändelser och förfinade händelser som ska inkluderas i exporten. 

1. I avsnittet **Filstruktur** väljer du takt (timme eller dag) för att skapa nya filer i mållagringsplatsen och väljer **Nästa**. Händelser exporteras kontinuerligt när de inträffar.

1. I dialogrutan **Välj format** välj formatet för din export. Välj mellan formaten **Common Data Model**, **CSV** och **JSON**. Om du vill använda exporten med andra Dynamics 365-program rekommenderar vi formatet **Common Data Model**.

1. I dialogrutan **Välj destination** ange Azure Data Lake Storage Gen 2 plats.
    1. **ADLS Gen 2 kontonamn** är namnet på det lagringskonto som du vill spara exporten till. 
    1. **Mappsökvägen** definierar var exporten ska lagras i lagringskontots filsystem och katalogstruktur.
    1. **Delad nyckel** är tillgänglig från Azure-portalen för lagringskontot.

1. Granska och bekräfta dina val för att slutföra.

## <a name="view-and-manage-exports"></a>Visa och hantera exporter

När du har ställt in en export går du till **Data** > **Exporter** för att visa den. Välj **Mer [...]** för en befintlig export om du vill redigera eller ta bort den.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
