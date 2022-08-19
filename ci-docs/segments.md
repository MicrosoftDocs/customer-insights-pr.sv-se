---
title: Segment – översikt
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
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246315"
---
# <a name="segments-overview"></a>Segment – översikt

Med segment kan du gruppera dina kunder baserat på demografiska attribut, transaktionella eller beteendemässiga attribut. Du kan använda segment för att rikta reklamkampanjer, säljaktiviteter och kundsupport för att uppnå dina affärsmål.

Kundprofiler som överensstämmer med filter för en segmentdefinition kallas *medlemmar* i ett segment. Vissa [servicegränser](/dynamics365/customer-insights/service-limits) gäller.

## <a name="create-a-segment"></a>Skapa ett segment

Välj hur du vill skapa ett segment utifrån din målgrupp.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

- Komplext segment med segmentverktyget: [Bygga ditt eget](segment-builder.md)
- Enkla segment med en operator: [Snabbsegment](segment-quick.md)
- AI-drivet sätt att hitta liknande kunder: [Liknande kunder](find-similar-customer-segments.md)
- AI-drivna förslag baserade på mått eller attribut: [Förslag på segment baserade på mått](suggested-segments.md)
- Förslag utifrån aktiviteter: [Förslag på segment utifrån kundaktivitet](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

- Enkla eller komplexa segment med segmentverktyget: [Bygga ditt eget](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Hantera befintliga segment

Gå till sidan **Segment** om du vill visa de segment du skapade, deras status och status, antalet medlemmar och sista gången data uppdaterades. Du kan sortera listan med segment efter valfri kolumn eller använda sökrutan för att hitta det segment du vill hantera.

Välj segment om du vill visa tillgängliga åtgärder.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valt segment med alternativlistrutan och tillgängliga alternativ." lightbox="media/segments-selected-segment.png":::

- [**Visa**](#view-segment-details) information om segmentet, inklusive trend för antal medlemmar en förhandsgranskning av segmentmedlemmar.
- **Hämta** listan över medlemmar som en .CSV-fil.
- **Redigera** segmentet om du vill ändra dess egenskaper.
- **Skapa dubblett** av ett segment. Du kan välja att redigera egenskaperna på en gång eller spara dubbletten.
- [**Uppdatera**](#refresh-segments) segmentet så att det omfattar senaste data.
- **Aktivera** eller **Inaktivera** segmentet. Inaktiva segment kommer inte att uppdateras under en [schemalagd uppdatering](schedule-refresh.md) och ha **Status** som anges som **Överhoppad**, vilket tyder på att en uppdatering inte ens provats. Aktiva segment uppdateras baserat på typen statiska eller dynamiska.
- **Gör statisk** eller **Gör dynamisk** segmenttypen. Du måste uppdatera statiska segment manuellt. Dynamiska segment uppdateras automatiskt under en systemuppdatering
- [**Hitta liknande kunder**](find-similar-customer-segments.md) från segmenten.
- **Byt namn** på segment.
- **Tagg** för att [hantera taggar](work-with-tags-columns.md#manage-tags) för segmentet.
- [**Hantera export**](#export-segments) för att se exportrelaterade segment och hantera dem. [Läs mer om exporter.](export-destinations.md)
- **Ta bort** segment.
- **Kolumner** för att [anpassa vilka kolumner](work-with-tags-columns.md#customize-columns) som visas.
- **Filtrera** om du vill [filtrera på taggar](work-with-tags-columns.md#filter-on-tags).
- **Söknamn** för att söka efter segmentnamn.

## <a name="view-segment-details"></a>Visa segmentinformation

På sidan **Segment** väljer du ett segment om du vill visa bearbetningshistorik och segmentmedlemmar.

Den övre delen av sidan innehåller ett trenddiagram som visualiserar ändringar i medlemsantal. Hovra över datapunkter om du vill visa antal medlemmar för ett visst datum. Ändra visualiseringens tidsram.

:::image type="content" source="media/segment-time-range.png" alt-text="Tidsintervall för segment.":::

Den nedre delen innehåller en lista över segmentets medlemmar.

> [!NOTE]
> Fält som visas i listan bygger på attributen för segmentets entiteter.
>
>Listan är en förhandsgranskning av de matchande segmentmedlemmarna och visar de första 100 posterna för ditt segment så att du snabbt kan utvärdera den och granska dess definitioner om det behövs. Om du vill visa alla matchande poster [exportera segmentet](export-destinations.md).

## <a name="refresh-segments"></a>Uppdatera segment

Segment kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran. Om du vill uppdatera en eller flera segment manuellt markerar du dem och väljer **Uppdatera**.

Om du vill [schemalägga en automatisk uppdatering](schedule-refresh.md) går du till **Admin** > **System** > **Schemalägg**. Följande regler gäller:

- Alla segment med typen **Dynamisk** eller **Expansion** uppdateras automatiskt med angiven takt. När uppdateringen väl är slutförd anger **Status** om det fanns några problem med att uppdatera segmentet. **Senast uppdaterade** visar en tidsstämpel för den senaste lyckade uppdateringen. Om ett fel inträffar markerar du felet för att visa information om vad som har hänt.
- Segment med typen **Statisk** kommer *inte* att uppdateras automatiskt. **Senast uppdaterade** visar en tidsstämpel för sista gången de statiska segmenten kördes eller uppdaterades manuellt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportera segment

Exportera segment till andra appar för att ytterligare använda data. Exportera ett segment från segmentsidan eller [exportsidan](export-destinations.md).

1. På sidan **Segment**, välj det segment du vill exportera.

1. Välj **Hantera exporter**. Sidan **Exporter (förhandsversion) för segment** öppnas. Visa alla konfigurerade exporter grupperade efter om de innehåller det aktuella avsnittet eller inte.

   1. Om du vill lägga till det valda segmentet i en export **redigerar** du respektive export så att motsvarande segment markeras och sparar sedan. I miljöer för enskilda kunder kan du markera exporten i listan och välja **Lägg till segment** för att få samma resultat.

   1. Om du vill skapa en ny export med det markerade segmentet väljer du **Lägg till export**. Mer information om hur du skapar export finns i [Konfigurera en ny export](export-destinations.md#set-up-a-new-export).

1. Välj **Tillbaka** för att gå tillbaka till huvudsidan för segment.

## <a name="track-usage-of-a-segment"></a>Spåra användning av ett segment

Om du använder segment i appar, som bygger på samma Microsoft Dataverse-organisation som är kopplad till Customer Insights, kan du spåra användningen av ett segment. För [Customer Insights-segment som används i kundens färd inom Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) informerar systemet dig om hur detta segment används.

När du redigerar ett segment som används i Customer Insights-miljön, eller i en kundens färd i Marknadsföring, informerar en banderoll i [segmentverktyget](segment-builder.md) dig om beroendena. Kontrollera beroendeinformationen direkt från banderollen eller genom att välja **Användning** i segmentverktyget.

I fönstret **Segmentanvändning** visas information om användningen av detta segment i Dataverse-baserade appar. För segment som används i kundens färd hittar du en länk som hjälper dig att kontrollera färden i Marknadsföring där detta segment används. Om du har behörighet för att få åtkomst till appen Marknadsföring kan du se mer information där.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Sidofönster med information om segmentanvändningen i segmentverktyget.":::

Systemet informerar dig rörande användningen av ett spårat segment används när du försöker ta bort det. Om det segment du håller på att ta bort används i en kundens färd i Marknadsföring stoppas den färden för alla användare i segmentet. Om resan ingår i en marknadsföringskampanj kommer borttagningen att påverka själva kampanjen. Du kan emellertid fortfarande ta bort segmenten trots de varningar som har utfärdats.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogruta för att bekräfta segmentborttagning när ett segment används i ett Dataverse-program.":::

### <a name="supported-apps"></a>Program som stöds

Användning spåras för närvarande i följande Dataverse-baserade appar:

- [Kundfärder i Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
