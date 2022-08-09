---
title: Power BI anslutningsprogram (förhandsversion)
description: Läs mer om hur du använder Dynamics 365 Customer Insights anslutningsprogram i Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196692"
---
# <a name="power-bi-connector-preview"></a>Power BI anslutningsprogram (förhandsversion)

Skapa visualiseringar för dina data med Microsoft Power BI Desktop. Skapa ytterligare insikter och skapa rapporter med dina enhetliga kunddata.

## <a name="prerequisites"></a>Förutsättningar

- Enhetliga kundprofiler.
- Den senaste versionen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) är installerad på datorn. [Läs mer om Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurera koppling för Power BI

1. I Power BI Desktop, välj **Fil** > **Hämta data**.

1. Välj **Se fler** och sök efter **Dynamics 365 Customer Insights**

1. Välj **Anslut**.

1. **Logga in** med samma organisationskonto som du använder för Customer Insights och välj **Anslut**.
   > [!NOTE]
   > Det konto du anger i det här steget används för att hämta data från Customer Insights som inte behöver vara samma som du är inloggad på Power BI. Om du vill återställa kontot som används för datahämtning öppnar du Power BI och går **Fil** > **Alternativ** > **Inställningar** > **Inställningar för datakälla**. Välj inloggning i listan över datakällor välj **Dynamics 365 Customer Insights inloggning** och välj **Rensa behörigheter**.  

1. Visa listan över alla miljöer du har åtkomst till i dialogrutan **Navigering**. Expandera en miljö och öppna någon av mapparna (entiteter, mått, segment, berikningar). Öppna till exempel mappen **entiteter** om du vill visa alla entiteter som du kan importera.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI-navigator för anslutningsprogram.":::

1. Markera kryssrutorna bredvid de entiteter som ska tas med och **läsas in**. Du kan välja flera entiteter från flera miljöer.

   En dialogruta för inläsning visas medan entiteterna har lästs in. När alla dina valda entiteter har lästs in kan du använda funktionerna i Power BI för att visualisera data.

## <a name="large-data-sets"></a>Stora datauppsättningar

Customer Insights-anslutningen för Power BI har utformats för att fungera för data uppsättningar som innehåller upp till 1 miljon kundprofiler. Import av större datauppsättningar kan fungera, men tar lång tid och kan ta time-out på grund av Power BI begränsningar. Mer information finns i [Power BI rekommendationerna för stora datauppsättningar](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Arbeta med en delmängd av data.

Överväg att arbeta med en delmängd av dina data. Du kan till exempel skapa [segment](segments.md) i stället för att exportera alla kundposter till Power BI.

## <a name="troubleshooting"></a>Felsökning

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-miljön visas inte i Power BI

Miljöer med fler än en [relation](relationships.md) som har definierats mellan två identiska entiteter i Customer Insights kommer inte att vara tillgängliga i Power BI-kopplingen.

Identifiera och ta bort de duplicerade relationerna.

1. Gå till **Data** > **Relationer** i den miljö som du saknar i Power BI.
1. Identifiera dubblettrelationer:
   - Kontrollera om det finns fler än en relation som har definierats mellan samma två entiteter.
   - Kontrollera om det finns en relation som har skapats mellan två entiteter som båda ingår i föreningsprocessen. Det finns en implicit relation mellan alla entiteter som ingår i föreningsprocessen.
1. Ta bort eventuella dubblettrelationer som har identifierats.

När du har tagit bort dubblettrelationer försöker du konfigurera Power BI-anslutningsprogrammet igen.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Fel i datumfält när entiteter läses in i Power BI Desktop

När du läser in entiteter som innehåller fält med datumformat som MM/DD/ÅÅÅÅ kan du stöta på fel på grund av felaktiga språkformat. Den här matchningen inträffar om Power BI Desktop-filen har angetts till en annan språkrelation än engelska (USA), eftersom datumfält i Customer Insights sparas i amerikanskt format.

Filen Power BI Desktop har en enda språkinställning som används när data hämtas. För att åtgärda datumfelen, [ställ in lokalen för .BPI-filen](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) till engelska (USA).

[!INCLUDE [footer-include](includes/footer-banner.md)]
