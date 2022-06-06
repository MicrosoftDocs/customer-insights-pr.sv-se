---
title: Segment i Customer Insights
description: Översikt över segment och hur du skapar och hanterar dem.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800764"
---
# <a name="segments-overview"></a>Segment – översikt

Med segment kan du gruppera dina kunder baserat på demografiska attribut, transaktionella eller beteendemässiga attribut. Du kan använda segment för att rikta reklamkampanjer, säljaktiviteter och kundsupport för att uppnå dina affärsmål.

Kundprofiler som överensstämmer med filter för en segmentdefinition kallas *medlemmar* i ett segment. Vissa [servicegränser](/dynamics365/customer-insights/service-limits) gäller.

## <a name="create-a-new-segment"></a>Skapa ett nytt segment

Du kan skapa ett nytt segment på flera sätt: 

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

- Komplext segment med segmentverktyget: [Bygga ett eget](segment-builder.md#create-a-new-segment) 
- Enkla segment med en operator: [Snabbsegment](segment-builder.md#quick-segments) 
- AI-drivet sätt att hitta liknande kunder: [Liknande kunder](find-similar-customer-segments.md) 
- AI-drivna förslag baserade på mått eller attribut: [Förslag på segment för att förbättra åtgärder](suggested-segments.md) 
- Förslag utifrån aktiviteter: [Förslag på segment utifrån kundaktivitet](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

- Komplext segment med segmentverktyget: [Bygga ett eget](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Hantera befintliga segment

Gå till sidan **Segment** om du vill visa alla sparade segment och hantera dem.

Varje segment representeras av en rad som innehåller ytterligare information om segmentet.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valt segment med alternativlistrutan och tillgängliga alternativ." lightbox="media/segments-selected-segment.png":::

Följande åtgärder är tillgängliga när du väljer ett segment:

- **Visa** information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.
- **Hämta** listan över medlemmar som en .CSV-fil.
- **Redigera** segmentet om du vill ändra dess egenskaper.
- **Skapa dubblett** av ett segment. Du kan välja att redigera egenskaperna på en gång eller spara dubbletten.
- **Uppdatera** segmentet så att det omfattar senaste data.
- **Aktivera** eller **Inaktivera** segmentet. För inaktiva segment finns segmentdefinitionen, men den innehåller inga kunder ännu. Ett aktivt segment söker efter kunder som matchar segmentdefinitionen. Om en [schemalagd uppdatering](system.md#schedule-tab) har konfigurerats har inaktiva segment **Status** anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats. När ett inaktivt segment aktiveras uppdateras och tas med i schemalagda uppdateringar.
  Du kan också använda funktionen **Schemalägg senare** i listrutan **Aktivera/inaktivera** för att ange ett framtida datum och tid för aktivering och inaktivering av ett visst segment.
- **[Hitta liknande kunder](find-similar-customer-segments.md)** från segmenten.
- **Byt namn** på segment.
- **Tagg** för att [hantera taggar](work-with-tags-columns.md#manage-tags) för segmentet.
- **Hämta** listan över medlemmar som en .CSV-fil.
- **Hantera export** för att se exportrelaterade segment och hantera dem. [Läs mer om exporter.](export-destinations.md)
- **Ta bort** segment.
- **Kolumner** för att [anpassa vilka kolumner](work-with-tags-columns.md#customize-columns) som visas.
- **Filtrera** om du vill [filtrera på taggar](work-with-tags-columns.md#filter-on-tags).
- **Söknamn** för att söka efter segmentnamn.

## <a name="refresh-segments"></a>Uppdatera segment

Du kan uppdatera alla segment på en gång genom att markera **Uppdatera alla** på sidan **Segment**, eller också kan du uppdatera ett eller flera segment när du markerar dem och väljer **Uppdatera** bland alternativen. Du kan även konfigurera en återkommande uppdatering på **Administratör** > **System** > **Schemalägg**. När en återkommande uppdatering konfigureras gäller följande regler:

- Alla segment med typen **Dynamisk** eller **Expansion** uppdateras automatiskt med angiven takt. När uppdateringen väl är slutförd anger **Status** om det fanns några problem med att uppdatera segmentet. **Senast uppdaterade** visar en tidsstämpel för den senaste lyckade uppdateringen. Om ett fel inträffar markerar du felet för att visa information om vad som har hänt.
- Segment med typen **Statisk** kommer *inte* att uppdateras automatiskt. **Senast uppdaterade** visar en tidsstämpel för sista gången de statiska segmenten kördes eller uppdaterades manuellt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportera segment

Du kan exportera ett segment från segmentsidan eller [exportsidan](export-destinations.md). 

1. Gå till sidan **Segment**.

1. Markera den vertikala ellipsen (&vellip;) för det segment du vill exportera.

1. Välj **Hantera exporter** i listrutan Åtgärder.

1. Sidan **Exporter (förhandsversion) för segment** öppnas. Alla konfigurerade exporter visas grupperade efter om de innehåller det aktuella avsnittet eller inte.

   1. Om du vill lägga till det valda segmentet i en export **redigerar** du respektive export så att motsvarande segment markeras och sparar sedan. I miljöer för enskilda kunder kan du istället markera exporten i listan och välja **Lägg till segment** för att få samma resultat.

   1. Om du vill skapa en ny export med det markerade segmentet väljer du **Lägg till export**. Mer information om hur du skapar export finns i [Konfigurera en ny export](export-destinations.md#set-up-a-new-export).

1. Välj **Tillbaka** för att gå tillbaka till huvudsidan för segment.

## <a name="track-usage-of-a-segment"></a>Spåra användning av ett segment

Om du använder segment i appar, som bygger på samma Microsoft Dataverse-organisation som är kopplad till Customer Insights, kan du spåra användningen av ett segment. För [Customer Insights-segment som används i kundens färd inom Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) informerar systemet dig om hur detta segment används.

När du redigerar ett segment som används i Customer Insights-miljön, eller i en kundens färd i Marknadsföring, informerar en banderoll i [segmentverktyget](segment-builder.md) dig om beroendena. Du kan kontrollera beroendeinformationen direkt från banderollen eller genom att välja **Användning** i segmentverktyget.

I fönstret **Segmentanvändning** visas information om användningen av detta segment i Dataverse-baserade appar. För segment som används i kundens färd hittar du en länk som hjälper dig att kontrollera färden i Marknadsföring där detta segment används. Om du har behörighet för att få åtkomst till appen Marknadsföring kan du få tillgång till mer information där.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Sidofönster med information om segmentanvändningen i segmentverktyget.":::

Systemet informerar dig rörande användningen av ett spårat segment används när du försöker ta bort det. Om det segment du håller på att ta bort används i en kundens färd i Marknadsföring stoppas den färden för alla användare i segmentet. Om resan ingår i en marknadsföringskampanj kommer borttagningen att påverka själva kampanjen. Du kan emellertid fortfarande ta bort segmenten trots de varningar som har utfärdats.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogruta för att bekräfta segmentborttagning när ett segment används i ett Dataverse-program.":::

### <a name="supported-apps"></a>Program som stöds

Användning spåras för närvarande i följande Dataverse-baserade appar:

- [Kundfärder i Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
