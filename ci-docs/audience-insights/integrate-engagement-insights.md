---
title: Integrera webbdata från engagemangsinsikter med målgruppsinsikter
description: Hämta webbinformation om kunder från engagemangsinsikter till målgruppsinsikter.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a4cb77bb4c6ef0d88b3f00802f66baab5520a07
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896441"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrera webbdata från engagemangsinsikter med målgruppsinsikter

Kunderna gör ofta sina dagliga transaktioner online via webbplatser. Funktionerna för engagemangsinsikter i Dynamics 365 Customer Insights är en praktisk lösning för att integrera webbdata som källa. Förutom transaktionsinformation, demografisk information eller beteendeinformation kan vi se aktiviteter på webben i enhetliga kundprofiler. Vi kan använda den här profilen för att få ytterligare insikter som segment, mått eller förutsägelser för målgruppsaktivering.

Den här artikeln beskriver stegen du tar för att ta dina kunders webbaktivitetsdata från engagemangsinsikter till din befintliga miljö för målgruppsinsikter.

I det här exemplet förutsätts det att miljön innehåller enhetliga kundprofiler. Profilerna var enhetliga med källor från undersökningar, återförsäljning och ett ärendesystem. Det visar också kundernas relaterade aktiviteter. 

Nu vill vi veta om en kund besöker våra webbegenskaper och förstår deras aktiviteter. Aktiviteterna omfattar till exempel besökta webbplatser eller visade produktsidor från en länk som tagits emot i ett e-postmeddelande.

## <a name="prerequisites"></a>Förutsättningar

För att integrera data från engagemangsinsikter måste några krav uppfyllas: 

- Integrera SDK för engagemangsinsikter med din webbplats. Mer information finns i [Kom igång med webb-SDK](../engagement-insights/instrument-website.md).
- För att exportera webbhändelser från engagemangsinsikter krävs åtkomst till ett ADLS Gen 2-lagringskonto som används för att mata in webbhändelsers data i målgruppsinsikter. Mer information finns i [Exportera händelser](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurera förfinade händelser i engagemangsinsikter

När en administratör har instrumenterat en webbplats med SDK för engagemangsinsikter, samlas *grundhändelser* när en användare visar en webbsida eller klickar någonstans. Grundhändelser innehåller mängder av detaljer. Beroende på hur du använder ett ärende behöver du bara en delmängd data i en grundhändelse. Med engagemangsinsikter kan du skapa *förfinade händelser* som endast innehåller egenskaperna för en grundhändelse som du har valt.     

Mer information finns i [Skapa och ändra förfinade händelser](../engagement-insights/refined-events.md).

Att tänka på när man skapar förfinade händelser: 

- Ge ett meningsfullt namn för den förfinade händelsen. Det används som ett aktivitetsnamn i målgruppsinsikter.
- Välj åtminstone följande egenskaper för att skapa en aktivitet i målgruppsinsikter: 
    - Signal.Action.Name – ange aktivitetsinformationen
    - Signal.User.Id – används för att mappa med kund-ID
    - Signal.View.Uri – används som webbadress som bas för segment eller mått
    - Signal.Export.Id – att använda som primärnyckel för händelser
    - Signal.Timestamp – för att fastställa datum och tid för aktiviteten

Välj vilka filter som ska fokusera på de händelser och sidor som är viktiga för ditt användningsområde. I det här exemplet använder vi åtgärdsnamnet "E-postkampanj".

## <a name="export-the-refined-web-events"></a>Exportera förfinade webbhändelser 

När du har definierat en förfinad händelse måste du konfigurera exporten av händelsedata till Azure Data Lake Storage, som kan anges som datakälla för insamling i målgruppsinsikter. Exporten sker kontinuerligt när händelserna flödar från webbegenskapen.

Mer information finns i [Exportera händelser](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Mata in händelsedata i målgruppsinsikter

Nu när du har definierat den förfinade händelsen och konfigurerat exporten går vi vidare till att mata in data i målgruppsinsikter. Du måste skapa en ny datakälla baserat på mappen Common Data Model. Ange information för lagringskontot som du exporterar händelserna till. I filen *default.cdm.json* väljer du den förfinade händelsen som ska matas in och skapar entiteten i målgruppsinsikter.

Mer information finns i [Ansluta till en Common Data Model-mapp med ett Azure Data Lake-konto](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relatera data om förfinade händelser som en aktivitet i en kundprofil

När du har slutfört entitetsinmatningen kan du konfigurera aktiviteten för kundprofilen.

Mer information finns i [Kundaktiviteter](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Sidan Aktiviteter med expanderad redigeringsaktivitetsruta och ifyllda fält.":::

Konfigurera den nya aktiviteten med följande mappning: 

- **Primärnyckel:** Signal.Export.Id, ett unikt ID som är tillgängligt för varje händelsepost i engagemangsinsikter. Egenskapen genereras automatiskt.

- **Tidsstämpel:** Signal.Timestamp i händelseegenskapen.

- **Händelse:** Signal.Name, det händelsenamn du vill spåra.

- **Webbadress:** Signal.View.Uri hänvisar till uri på sidan som skapade händelsen.

- **Information:** Signal.Action.Name som representerar den information som ska associeras med händelsen. Den valda egenskapen i det här ärendet anger att händelsen gäller e-postkampanj.

- **Aktivitetstyp:** I det här exemplet väljer vi den befintliga aktivitetstypen WebLog. Det här alternativet är ett användbart filteralternativ för att köra förutsägelsemodeller eller skapa segment baserat på denna aktivitetstyp.

- **Skapa relation:** Den här viktiga inställningen gör att aktiviteten kan knytas till befintliga kundprofiler. **Signal.User.Id** är identifieraren som konfigurerats i SDK som ska samlas in och som relaterar till användar-ID i andra datakällor som har konfigurerats i målgruppsinsikter. I det här exemplet konfigurerar vi relationen mellan Signal.User.Id och RetailCustomers:CustomerRetailId, som är den primära nyckel som identifierades i mappningssteget av dataföreningsprocessen.


När du har bearbetat aktiviteterna kan du granska kundposter och öppna ett kundkort för att se aktiviteter från engagemangsinsikter i tidslinjen. 

> [!TIP]
> Om du vill hitta ett kund-ID som har en engagemangsinsiktsaktivitet går du till **Entiteter** och förhandsgranskar data för entiteten UnifiedActivity. ActivityTypeDisplay = WebLog innehåller den engagemangsinsiktsaktivitet som konfigurerats i exemplet ovan. Kopiera kund-ID för en av dessa poster och för ID på sidan **Kunder**.

## <a name="next-steps"></a>Nästa steg

Du kan nu skapa [segment](segments.md), [mått](measures.md) och [förutsägelse](predictions.md) för att skapa en meningsfull kontakt med dina kunder.


[!INCLUDE[footer-include](../includes/footer-banner.md)]