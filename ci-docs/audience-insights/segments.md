---
title: Segments i målgruppsinsikter
description: Översikt över segment och hur du skapar och hanterar dem.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6e2080b4ad19f6f57f60da591345e80ce9083e8a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554089"
---
# <a name="segments-overview"></a>Segment – översikt

Med segment kan du gruppera dina kunder baserat på demografiska attribut, transaktionella eller beteendemässiga attribut. Du kan använda segment för att rikta reklamkampanjer, säljaktiviteter och kundsupport för att uppnå dina affärsmål.

Kundprofiler som överensstämmer med filter för en segmentdefinition kallas *medlemmar* i ett segment. Vissa [servicegränser](service-limits.md) gäller.

## <a name="create-a-new-segment"></a>Skapa ett nytt segment

Du kan skapa ett nytt segment på flera sätt: 

- Komplext segment med segmentverktyget: [Tomt segment](segment-builder.md#create-a-new-segment)
- Enkla segment med en operator: [Snabbsegment](segment-builder.md#quick-segments)
- AI-drivet sätt att hitta liknande kunder: [Liknande kunder](find-similar-customer-segments.md)
- AI-drivna förslag baserade på mått eller attribut: [Förslag på segment för att förbättra åtgärder](suggested-segments.md)
- Förslag utifrån aktiviteter: [Förslag på segment utifrån kundaktivitet](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Hantera befintliga segment

Gå till sidan **Segment** om du vill visa alla sparade segment och hantera dem.

Varje segment representeras av en rad som innehåller ytterligare information om segmentet.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valt segment med alternativlistrutan och tillgängliga alternativ.":::

Följande åtgärd är tillgänglig när du väljer ett segment:

- **Visa** information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.
- **Redigera** segmentet om du vill ändra dess egenskaper.
- **Skapa dubblett** av ett segment. Du kan välja att redigera egenskaperna direkt eller bara spara dubbletten.
- **Uppdatera** segmentet så att det omfattar senaste data.
- **Aktivera** eller **Inaktivera** segmentet. Segment har två möjliga tillstånd - aktiva eller inaktiva. Dessa tillstånd har praktiskt taget när de redigerar ett segment. För inaktiva segment finns segmentdefinitionen, men den innehåller inga kunder ännu. När du aktiverar ett segment ändras dess status från "inaktivt" till "aktivt" och sökningen börjar söka efter kunder som matchar segmentdefinitionen. Om en [schemalagd uppdatering](system.md#schedule-tab) har konfigurerats har inaktiva segment **Status** anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats. När ett inaktivt segment aktiveras uppdateras och tas med i schemalagda uppdateringar.
  Du kan också använda funktionen **Schemalägg senare** i listrutan **Aktivera/inaktivera** för att ange ett framtida datum och tid för aktivering och inaktivering av ett visst segment.
- **Byt namn** på segment.
- **Hämta** listan över medlemmar som en .CSV-fil.
- **Hantera export** för att se exportrelaterade segment och hantera dem. [Läs mer om exporter.](export-destinations.md)
- **Ta bort** segment.

## <a name="refresh-segments"></a>Uppdatera segment

Du kan uppdatera alla segment på en gång genom att markera **Uppdatera alla** på sidan **Segment**, eller också kan du uppdatera ett eller flera segment när du markerar dem och väljer **Uppdatera** bland alternativen. Du kan även konfigurera en återkommande uppdatering på **Administratör** > **System** > **Schemalägg**.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="export-segments"></a>Exportera segment

Du kan exportera ett segment från segmentsidan eller [exportsidan](export-destinations.md). 

1. Gå till sidan **Segment**.

1. Välj **Visa mer [...]** för det segment som du vill exportera.

1. Välj **Hantera exporter** i listrutan Åtgärder.

1. Sidan **Exporter (förhandsversion) för segment** öppnas. Du kan se alla konfigurerade exporter grupperade efter export som innehåller det aktuella segmentet eller inte innehåller det.

   1. Om du vill lägga till det valda segmentet i en export markerar du exporten i listan och väljer **Lägg till segment**.

   1. Om du vill skapa en ny export med det markerade segmentet väljer du **Lägg till export**. Mer information om hur du skapar export finns i [Konfigurera en ny export](export-destinations.md#set-up-a-new-export).

1. Välj **Tillbaka** för att gå tillbaka till huvudsidan för segment.

## <a name="view-processing-history-and-segment-members"></a>Visa historik- och segmentmedlemmar för bearbetning

Du kan visa konsoliderade data om ett segment genom att granska dess detaljer.

På sidan **Segment**, välj det segment du vill granska.

Den övre delen av sidan innehåller ett trenddiagram som visualiserar ändringar i medlemsantal. Hovra över datapunkter om du vill visa antal medlemmar för ett visst datum.

Du kan uppdatera visualiseringens tidsram.

> [!div class="mx-imgBorder"]
> ![Tidsintervall för segment.](media/segment-time-range.png "Tidsintervall för segment")

Den nedre delen innehåller en lista över segmentets medlemmar.

> [!NOTE]
> Fält som visas i listan bygger på attributen för segmentets entiteter.
>
>Listan är en förhandsgranskning av de matchande segmentmedlemmarna och visar de första 100 posterna för ditt segment så att du snabbt kan utvärdera den och granska dess definitioner om det behövs. Om du vill visa alla matchande poster måste du [exportera segmentet](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
