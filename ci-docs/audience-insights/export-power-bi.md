---
title: Anslutningsapp för Power BI
description: Läs mer om hur du använder Dynamics 365 Customer Insights anslutningsprogram i Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: faeb95bd7d2fe3cb220308cdee559b3347c5af54
ms.sourcegitcommit: f98b6b2058f384365f222d1f9ba0cc9ce801f09d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2021
ms.locfileid: "6661124"
---
# <a name="connector-for-power-bi-preview"></a>Koppling för Power BI (förhandsversion)

Skapa visualiseringar för dina data med Power BI Desktop. Skapa ytterligare insikter och skapa rapporter med dina enhetliga kunddata.

## <a name="prerequisites"></a>Förutsättningar

- Du har enhetliga kundprofiler.
- Den senaste versionen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) är installerad på datorn. [Läs mer om Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurera koppling för Power BI

1. I Power BI Desktop, välj **Fil** > **Hämta data**.

1. Välj **Se fler** och sök efter **Dynamics 365 Customer Insights**

1. Välj **Anslut**.

1. **Logga in** med samma organisationskonto som du använder för Customer Insights och välj **Anslut**.
   > [!NOTE]
   > Det konto du anger i det här steget används för att hämta data från Customer Insights som inte behöver vara samma som du är inloggad på Power BI. Om du vill återställa kontot som används för datahämtning öppnar du Power BI och går **Fil** > **Alternativ** > **Inställningar** > **Inställningar för datakälla**. Välj inloggning i listan över datakällor välj **Dynamics 365 Customer Insights inloggning** och välj **Rensa behörigheter**.  

1. Klicka på dialogrutan **Navigering**. du ser listan över alla miljöer som du har åtkomst till. Expandera en miljö och öppna någon av mapparna (entiteter, mått, segment, berikningar). Öppna till exempel mappen **entiteter** om du vill visa alla entiteter som du kan importera.

   ![Power BI-navigator för anslutningsprogram.](media/power-bi-navigator.png "Power BI kopplingsnavigering")

1. Markera kryssrutorna bredvid de entiteter som ska tas med och **läsas in**. Du kan välja flera entiteter från flera miljöer.

1. En dialogruta för inläsning visas medan entiteterna har lästs in. När alla dina valda entiteter har lästs in kan du använda funktionerna i Power BI för att visualisera data.

## <a name="large-data-sets"></a>Stora datauppsättningar

Customer Insights-anslutningen för Power BI har utformats för att fungera för data uppsättningar som innehåller upp till 1 miljon kundprofiler. Det kan ta en stund att importera större datauppsättningar, men det tar lång tid. Dessutom kan processen köra på en tidsgräns på grund av Power BI begränsningar. Mer information finns i [Power BI rekommendationerna för stora datauppsättningar](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Arbeta med en delmängd av data.

Överväg att arbeta med en delmängd av dina data. Du kan till exempel skapa [segment](segments.md) i stället för att exportera alla kundposter till Power BI.

## <a name="troubleshooting"></a>Felsökning

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-miljön visas inte i Power BI

Miljöer som har fler än en [relation](relationships.md) som har definierats mellan två identiska entiteter målgruppsinsikter kommer inte att vara tillgängliga i Power BI-anslutningsprogrammet.

Du kan identifiera och ta bort de duplicerade relationerna.

1. I målgruppsinsikter går du till **Data** > **Relationer** i den miljö du saknar i Power BI.
2. Identifiera dubblettrelationer:
   - Kontrollera om det finns fler än en relation som har definierats mellan samma två entiteter.
   - Kontrollera om det finns en relation som har skapats mellan två entiteter som båda ingår i föreningsprocessen. Det finns en implicit relation mellan alla entiteter som ingår i föreningsprocessen.
3. Ta bort eventuella dubblettrelationer som har identifierats.

När du har tagit bort dubblettrelationer försöker du konfigurera Power BI-anslutningsprogrammet igen. Miljön ska vara tillgänglig nu.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Fel i datumfält när entiteter läses in i Power BI Desktop

När du läser in entiteter som innehåller fält med datumformat som MM/DD/ÅÅÅÅ kan du stöta på fel på grund av felaktiga språkformat. Denna felmatchning inträffar om din Power BI Desktop-fil har angetts till en annan språktyp än engelska (USA), detta eftersom datumfälten i målgruppsinsikter sparas i amerikanskt format.

Filen Power BI Desktop har en enda språkinställning som används när data hämtas. Se till att dessa datumfält fungerar som de ska, och ange språkinställningen för .BPI-filen som engelska (USA). [Lär dig hur du ändrar språkversionen för en stationär Power BI-fil](/power-bi/fundamentals/supported-languages-countries-regions.md#choose-the-locale-for-importing-data-into-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
