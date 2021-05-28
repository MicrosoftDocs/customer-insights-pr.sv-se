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
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034034"
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

## <a name="get-insights-on-existing-segments"></a>Skaffa insikter om befintliga segment

Upptäck ytterligare information om dina befintliga segment med [segmentinsikter](segment-insights.md). Ta reda på vad som skiljer mellan två segment och vad de har gemensamt.

## <a name="find-similar-customers"></a>Sök efter liknande kunder

Hitta kunder som liknar medlemmarna i ett valt segment med hjälp av artificiell intelligens. Mer information finns i [Liknande kunder](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Hantera befintliga segment

Gå till sidan **Segment** om du vill visa alla sparade segment och hantera dem.

Varje segment representeras av en rad som innehåller ytterligare information om segmentet.

> [!div class="mx-imgBorder"]
> ![Alternativ för att hantera ett befintligt segment](media/segments-selected-segment.png "Alternativ för att hantera ett befintligt segment")

Följande åtgärd är tillgänglig när du väljer ett segment:

- **Visa** information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.
- **Redigera** segmentet om du vill ändra dess egenskaper.
- **Skapa dubblett** av ett segment. Du kan välja att redigera egenskaperna direkt eller bara spara dubbletten.
- **Uppdatera** segmentet så att det omfattar senaste data.
- **Aktivera** eller **Inaktivera** segmentet. Segment har två möjliga tillstånd - aktiva eller inaktiva. Dessa tillstånd har praktiskt taget när de redigerar ett segment. För inaktiva segment finns segmentdefinitionen, men den innehåller inga kunder ännu. När du aktiverar ett segment ändras dess status från "inaktivt" till "aktivt" och sökningen börjar söka efter kunder som matchar segmentdefinitionen. Om en [schemalagd uppdatering](system.md#schedule-tab) har konfigurerats har inaktiva segment **Status** anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats. När ett inaktivt segment aktiveras uppdateras och tas med i schemalagda uppdateringar.
  Du kan också använda funktionen **Schemalägg senare** i listrutan **Aktivera/inaktivera** för att ange ett framtida datum och tid för aktivering och inaktivering av ett visst segment.
- **Byt namn** på segment.
- **Hämta** listan över medlemmar som en .CSV-fil.
- Alternativet **Lägg till** skickar listan med kund-ID i segmentet för bearbetning i ett annat program.
- **Ta bort** segment.

## <a name="refresh-segments"></a>Uppdatera segment

Du kan uppdatera alla segment på en gång genom att markera **Uppdatera alla** på sidan **Segment**, eller också kan du uppdatera ett eller flera segment när du markerar dem och väljer **Uppdatera** bland alternativen. Du kan även konfigurera en återkommande uppdatering på **Administratör** > **System** > **Schemalägg**.

> [!TIP]
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies). Du kan välja status för en process om du vill visa information om förloppet för hela jobbet. När du har valt **Se detaljer** för en av jobbets uppgifter hittar du ytterligare information: bearbetningstid, det senaste behandlingsdatumet och alla fel och varningar som är kopplade till uppgiften.

## <a name="view-processing-history-and-segment-members"></a>Visa historik- och segmentmedlemmar för bearbetning

Du kan visa konsoliderade data om ett segment genom att granska dess detaljer.

På sidan **Segment**, välj det segment du vill granska.

Den övre delen av sidan innehåller ett trenddiagram som visualiserar ändringar i medlemsantal. Hovra över datapunkter om du vill visa antal medlemmar för ett visst datum.

Du kan uppdatera visualiseringens tidsram.

> [!div class="mx-imgBorder"]
> ![Tidsintervall för segment](media/segment-time-range.png "Tidsintervall för segment")

Den nedre delen innehåller en lista över segmentets medlemmar.

> [!NOTE]
> Fält som visas i listan bygger på attributen för segmentets entiteter.
>
>Listan är en förhandsgranskning av de matchande segmentmedlemmarna och visar de första 100 posterna för ditt segment så att du snabbt kan utvärdera den och granska dess definitioner om det behövs. Om du vill visa alla matchande poster måste du [exportera segmentet](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
