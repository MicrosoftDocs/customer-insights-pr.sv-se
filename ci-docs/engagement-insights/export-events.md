---
title: Exportera förfinade händelser
description: Exportera förfinade händelser och bashändelser.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032407"
---
# <a name="export-events"></a>Exportera händelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En händelse representerar användarbeteende. Den registrerar när en användare visar en sida (visa händelse) eller interagerar med innehåll (åtgärdshändelse). När du kan bestämma vilka egenskaper för data som du vill visa i en rapport kallas denna virtuella vy av data a *förfinad händelse*. 

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

Det finns två sätt att exportera händelser: 
- Gå till **Data** > **Exporter** och välj **Ny export**.
- Gå till **Data** > **Händelser**, välj **Fler [...]** bredvid den händelse du vill exportera, och välj **Exportera** i listrutan. 

Här får du instruktioner om hur du skapar en export:

1. Ange ett **Exportnamn**.

1. I listrutan **Händelseval** väljer du de bashändelser och förfinade händelser som ska inkluderas i exporten. 

1. Under **Filstruktur** väljer du takt för att skapa nya filer i mållagringsplatsen. Händelser exporteras kontinuerligt när de inträffar.

1. Välj format för exporten. Du kan välja mellan formaten **Common Data Model**, **CSV** och **JSON**. Om du vill använda exporten med andra Dynamics 365-program rekommenderar vi att du använder formatet Common Data Model.

1. I steget **Välj destination**, ange Azure Data Lake Storage Gen 2 plats.
    1. **ADLS Gen 2 kontonamn** är namnet på det lagringskonto som du vill spara exporten till. 
    1. **Mappsökvägen** definierar var exporten ska lagras i lagringskontots filsystem och katalogstruktur.
    1. **Delad nyckel** är tillgänglig från Azure-portalen för lagringskontot.

1. Granska och bekräfta dina val.

## <a name="view-and-manage-exports"></a>Visa och hantera exporter

När du har ställt in en export går du till **Data** > **Exporter** för att visa den. Välj **Mer [...]** för en befintlig export om du vill redigera eller ta bort den.


[!INCLUDE[footer-include](../includes/footer-banner.md)]