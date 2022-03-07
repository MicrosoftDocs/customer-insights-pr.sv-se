---
title: Exportera data från Customer Insights
description: 'Hantera dataexport för att dela data. '
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 47bdcc5bb38587063e4414377568943f868107a3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539365"
---
# <a name="exports-preview-overview"></a>Exporter (förhandsversion) översikt

På sidan **Exporter** visas alla konfigurerade exporter. Med exporter delar du specifika data med olika program. De kan inkludera kundprofiler eller entiteter, scheman och mappningsdetaljer. För varje export krävs en [anslutning, konfigurerad av en administratör, för att hantera autentisering och åtkomst](connections.md).

Gå till **Data** > **Exporter** om du vill visa exportsidan. Alla användarroller kan visa konfigurerade exporter. Använd sökfältet i kommandofältet om du vill söka efter exporter efter namn, anslutningsnamn eller anslutningstyp.

## <a name="set-up-a-new-export"></a>Ställ in en ny export

Om du vill konfigurera eller redigera en export måste anslutningarna vara tillgängliga för dig. Anslutningarna beror på din [användarroll](permissions.md):
- Administratörer har åtkomst till alla anslutningar. De kan också skapa nya anslutningar när de upprättar en export.
- Deltagare kan ha åtkomst till specifika anslutningar. De är beroende av administratörer för att konfigurera och dela anslutningar. I exportlistan visas deltagare om de kan redigera eller bara visa en export i kolumnen **Dina behörigheter**. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Det går bara att visa befintlig export men inte skapa den.

### <a name="define-a-new-export"></a>Definiera en ny export

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export** för att skapa en ny export.

1. I rutan **Ställ in export** väljer du vilken anslutning som ska användas. [Anslutningarna ](connections.md) hanteras av administratörer. 

1. Ange den information som krävs och välj **Spara** för att skapa exporten.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definiera en ny export utifrån en befintlig export

1. Gå till **Data** > **Exporter**.

1. I listan över exporter väljer du den export som du vill duplicera.

1. Välj **Skapa dubblett** i kommandofältet om du vill öppna fönstret **Konfigurera export** med informationen för den valda exporten.

1. Granska och anpassa exporten och välj **Spara** för att skapa en ny export.

### <a name="edit-an-export"></a>Redigera export

1. Gå till **Data** > **Exporter**.

1. I listan över exporter väljer du den export som du vill redigera.

1. Välj **Redigera** i kommandofältet.

1. Ändra de värden du vill uppdatera och välj **Spara**.

## <a name="view-exports-and-export-details"></a>Visa exporter och exportinformation

Efter att ha skapat exportdestinationer listas de på **Data** > **Exporter**. Alla användare kan se vilka data som delas och dess senaste status.

1. Gå till **Data** > **Exporter**.

1. Användare utan redigeringsbehörigheter väljer du **Visa** istället för **Redigera** för att visa exportinformationen.

1. I sidrutan visas konfigurationen av en export. Du kan inte ändra värden utan att redigera behörigheter. Välj **Stäng** om du vill återgå till exportsidan.

## <a name="schedule-and-run-exports"></a>Schemalägg och kör exporter

Varje export som du konfigurerar har ett uppdateringsschema. Vid en uppdatering söker systemet efter nya eller uppdaterade data som ska ingå i en export. Som standard körs exporter som en del av alla [schemalagda systemuppdateringar](system.md#schedule-tab). Du kan anpassa uppdateringsschemat eller inaktivera det om du vill köra exporten manuellt.

Exportscheman beror på tillståndet för miljön. Om det pågår uppdateringar för [beroenden](system.md#refresh-policies) när en schemalagd export ska starta, slutför systemet först uppdateringarna och kör sedan exporten. Du kan se när en export senast uppdaterades i kolumnen **Uppdaterad**.

### <a name="schedule-exports"></a>Schemalägg exporter

Du kan definiera anpassade uppdateringsscheman för enskilda exporter eller flera exporter samtidigt. Det för närvarande definierade schemat visas i kolumnen **Schema** i exportlistan. Du kan ändra schemat på samma sätt som när du [redigerar och definierar exporter](export-destinations.md#set-up-a-new-export). 

1. Gå till **Data** > **Exporter**.

1. Välj den export som du vill schemalägga.

1. Välj **Schemalägg** i kommandofältet.

1. I fönstret **Schemalägg export** ställer du in **Schemalägg körning** på **På** för att köra exporten automatiskt. Ställ in på **Av** för att uppdatera manuellt.

1. För automatiskt uppdaterade exporter väljer du ett värde för **Upprepning** och anger detaljer för det. Den angivna tiden gäller för alla förekomster av en upprepning. Det är den tid då en export ska börja uppdateras.

1. Tillämpa och aktivera ändringarna genom att välja **Spara**.

När du redigerar schemat för flera exporter måste du välja under **Behåll eller åsidosätt scheman**:
- **Behåll enskilda scheman**: Bevara det tidigare definierade schemat för den valda exporten och inaktivera eller aktivera dem endast.
- **Ange ett nytt schema för alla valda exporter**: Åsidosätta befintliga scheman för de valda exporterna.

### <a name="run-exports-on-demand"></a>Kör exporter på begäran

För att exportera data utan att vänta på en schemalagd uppdatering, gå till **Data** > **Exporter**.

- Om du vill köra alla exporter väljer du **Kör alla** i kommandofältet. Den här åtgärden kör endast exporter med ett aktivt schema.
- Om du vill köra en enskild export markerar du den i listan och väljer **Kör** i kommandofältet. På det här viset kör du exporter utan något aktivt schema. 

## <a name="remove-an-export"></a>Ta bort en export

1. Gå till **Data** > **Exporter**.

1. Markera den export du vill ta bort.

1. Välj **Ta bort** i kommandofältet.

1. Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
