---
title: Exporter (förhandsversion) översikt
description: 'Hantera dataexport för att dela data. '
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460212"
---
# <a name="exports-preview-overview"></a>Exporter (förhandsversion) översikt

 Med exporter kan du dela specifika data med olika program. De kan innehålla kundprofiler, entiteter, scheman och mappningsdetaljer. För varje export krävs en [anslutning, konfigurerad av en administratör, för att hantera autentisering och åtkomst](connections.md). På sidan **Exporter** visas alla konfigurerade exporter.

## <a name="export-types"></a>Exporttyper

Det finns två huvudtyper av export:  

- **Export av utdata** låter dig exportera alla typer av entiteter som är Customer Insights. De entiteter du väljer för export exporteras med alla datafält, metadata, scheman och mappningsdetaljer.
- Med **segmentexport** kan du exportera segmententiteter från Customer Insights. Segment som är för enskilda kunder (B2C) representerar en lista över kundprofiler. För företag (B2B) kan [segment motsvara en lista med konton eller kontakter](segment-builder.md#create-a-new-segment-with-segment-builder). När du konfigurerar exporten väljer du de datafält som ingår, beroende på vilket målsystem du exporterar data till.

### <a name="export-segments"></a>Exportera segment

**Exportera segment i miljöer för affärskonton (B2B) eller enskilda konsumenter (B2C)**  
De flesta exportalternativ har stöd för båda typerna av miljöer. Det finns särskilda krav för att exportera segment till olika målsystem. 

**Segmentexport i miljöer för enskilda konsumenter (B2C)**  
- Segment i samband med miljöer för individuella kunder bygger på entiteten *Unified Customer Profile*. Alla segment som uppfyller målsystemens krav (till exempel en e-postadress) kan exporteras.

**Segmentexport i miljöer för affärskonton (B2B)**  
- Segment i samband med miljöer för affärskonton bygger på entiteten *konto* eller *kontakt*. För att kunna exportera kontosegment i sin form måste målsystemet ha stöd för kontosegment. Detta gäller för [LinkedIn](export-linkedin-ads.md) när du väljer alternativet **företag** när du definierar exporten.
- Alla andra målsystem kräver fält från kontaktentiteten.
- Med två segmenttyper (kontakter och konton) identifierar Customer Insights automatiskt vilken typ av segment som kan exporteras baserat på målsystemet. Till exempel, för ett kontaktfokuserat målsystem som Mailchimp, låter Customer Insights dig bara välja kontaktsegment att exportera.

**Begränsningar för segmentexport**  
- Målsystem från tredje part kan begränsa antalet kundprofiler som du kan exportera. 
- För enskilda kunder visas det faktiska antalet segmentmedlemmar när du väljer ett segment för export. Du får en varning om ett segment är för stort. 
- För affärskonton visas antalet konton eller kontaktpersoner beroende på segment. Du får en varning om ett segment är för stort. Att överskrida gränserna för målsystemresultaten kommer att hoppa över exporten.

## <a name="set-up-a-new-export"></a>Ställ in en ny export

Om du vill konfigurera eller redigera en export måste anslutningarna vara tillgängliga för dig. Anslutningarna beror på din [användarroll](permissions.md):
- **Administratörer** har åtkomst till alla anslutningar. De kan också skapa nya anslutningar när de upprättar en export.
- **Deltagare** kan ha åtkomst till specifika anslutningar. De är beroende av administratörer för att konfigurera och dela anslutningar. I exportlistan visas deltagare om de kan redigera eller bara visa en export i kolumnen **Dina behörigheter**. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Visningsprogram** kan bara visa befintlig export - inte skapa dem.

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export** för att skapa en ny export.

1. I rutan **Ställ in export** väljer du vilken [anslutning](connections.md) som ska användas.

1. Ange den information som krävs och välj **Spara** för att skapa exporten. Den information som krävs finns i dokumentationen för Customer Insights för den specifika exporten.

## <a name="manage-existing-exports"></a>Hantera befintliga exporter

Gå till **Data** > **Exporter** för att visa exporterna, deras anslutningsnamn, anslutningstyp och status. Alla användarroller kan visa konfigurerade exporter. Du kan sortera listan med exporter efter valfri kolumn eller använda sökrutan för att hitta den export du vill hantera.

Välj export om du vill visa tillgängliga åtgärder.

:::image type="content" source="media/exports_showmore.png" alt-text="Sidan exporter.":::

- **Visa** eller **Redigera** exporten. Användare utan redigeringsbehörigheter väljer du **Visa** istället för **Redigera** för att visa exportinformationen.
- **Kör** exporten för att exportera de senaste data.
- **Skapa dubblett** av en export.
- **[Schemalägg](#schedule-and-run-exports)** exporten.
- **Koppla från anslutning** för att ta bort anslutningen för den här exporten. Koppla bort tar inte bort anslutningen, men inaktiverar exporten. Kolumnen **Anslutning som används** visar Ingen anslutning.
- **Ta bort** export

## <a name="schedule-and-run-exports"></a>Schemalägg och kör exporter

Varje export som du konfigurerar har ett uppdateringsschema. Vid en uppdatering söker systemet efter nya eller uppdaterade data som ska ingå i en export. Som standard körs exporter som en del av alla [schemalagda systemuppdateringar](schedule-refresh.md). Du kan anpassa uppdateringsschemat eller inaktivera det om du vill köra exporten manuellt.

> [!TIP]
> Minimera bearbetningstiden för segmentexporten med hjälp av följande metodtips:
> - Distribuera segmententiteter över flera exporter.
> - Undvik att schemalägga alla exporter samtidigt. Låt det ta 30 minuter eller en timme mellan den schemalagda tiden för varje export.

Exportscheman beror på tillståndet för miljön. Om det pågår uppdateringar för [beroenden](system.md#refresh-processes) när en schemalagd export ska starta, slutför systemet först uppdateringarna och kör sedan exporten. Kolumnen **Uppdaterad** visar när en export senast uppdaterades.

### <a name="schedule-exports"></a>Schemalägg exporter

Definiera anpassade uppdateringsscheman för enskilda exporter eller flera exporter samtidigt. Det för närvarande definierade schemat visas i kolumnen **Schema** i exportlistan. Du kan ändra schemat på samma sätt som när du [redigerar och definierar exporter](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj den export som du vill schemalägga.

1. Välj **Schema**.

1. I fönstret **Schemalägg export** ställer du in **Schemalägg körning** på **På** för att köra exporten automatiskt. Ställ in på **Av** för att uppdatera manuellt.

1. För automatiskt uppdaterade exporter väljer du ett värde för **Upprepning** och anger detaljer för det. Den angivna tiden gäller för alla förekomster av en upprepning. Det är den tid då en export ska börja uppdateras.

1. Välj **Spara**.

När du redigerar schemat för flera exporter måste du välja under **Behåll eller åsidosätt scheman**:

- **Behåll enskilda scheman**: Bevara det tidigare definierade schemat för den valda exporten och inaktivera eller aktivera dem endast.
- **Ange ett nytt schema för alla valda exporter**: Åsidosätta befintliga scheman för de valda exporterna.

### <a name="run-exports-on-demand"></a>Kör exporter på begäran

För att exportera data utan att vänta på en schemalagd uppdatering, gå till **Data** > **Exporter**.

- Om du vill köra alla exporter väljer du **Kör alla** i kommandofältet. Endast exporter som har ett aktivt schema körs. Om du vill köra en export som inte är aktiv kör du en enda export.
- Om du vill köra en enskild export markerar du den i listan och väljer **Kör** i kommandofältet.

## <a name="troubleshooting"></a>Felsökning

### <a name="segment-not-eligible-for-export"></a>Segment som inte är berättigande till export

**Problem** I en miljö med företagskonton misslyckas exporten med felmeddelandet: "Följande segment är inte kvalificerat för den här exportmålet: "{Namn på segment}". Välj endast segment av typen ContactProfile och försök igen."

**Lösning** Customer Insights-miljöer för affärskonton har uppdaterats för att stödja kontaktsegment förutom kontosegment. På grund av den förändringen fungerar export som behöver kontaktinformation endast med segment baserade på kontakter.

1. [Skapa ett segment utifrån kontakter som överensstämmer](segment-builder.md) med ditt tidigare använda segment.

1. När kontaktsegmentet har körts redigerar du respektive export och markerar det nya segmentet.

1. Välj **Spara** om du vill spara konfigurationen eller **Spara och kör** för att testa exporten på en gång.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
