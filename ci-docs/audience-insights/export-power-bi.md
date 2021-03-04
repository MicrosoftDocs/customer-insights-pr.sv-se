---
title: Anslutningsapp för Power BI
description: Läs mer om hur du använder Dynamics 365 Customer Insights anslutningsprogram i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477110"
---
# <a name="connector-for-power-bi-preview"></a>Koppling för Power BI (förhandsversion)

Skapa visualiseringar för dina data med Power BI Desktop. Skapa ytterligare insikter och skapa rapporter med dina enhetliga kunddata.

## <a name="prerequisites"></a>Förutsättningar

- Du har enhetliga kundprofiler.
- Den senaste versionen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) är installerad på datorn. [Läs mer om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurera koppling för Power BI

1. I Power BI Desktop, välj **Fil** > **Hämta data**.

1. Välj **Se fler** och sök efter **Dynamics 365 Customer Insights**

1. Välj **Anslut**.

1. **Logga in** med samma organisationskonto som du använder för Customer Insights och välj **Anslut**.
   > [!NOTE]
   > Det konto du anger i det här steget används för att hämta data från Customer Insights som inte behöver vara samma som du är inloggad på Power BI. Om du vill återställa kontot som används för datahämtning öppnar du Power BI och går **Fil** > **Alternativ** > **Inställningar** > **Inställningar för datakälla**. Välj inloggning i listan över datakällor välj **Dynamics 365 Customer Insights inloggning** och välj **Rensa behörigheter**.  

1. Klicka på dialogrutan **Navigering**. du ser listan över alla miljöer som du har åtkomst till. Expandera en miljö och öppna någon av mapparna (entiteter, mått, segment, berikningar). Öppna till exempel mappen **entiteter** om du vill visa alla entiteter som du kan importera.

   ![Power BI kopplingsnavigering](media/power-bi-navigator.png "Power BI kopplingsnavigering")

1. Markera kryssrutorna bredvid de entiteter som ska tas med och **läsas in**. Du kan välja flera entiteter från flera miljöer.

1. En dialogruta för inläsning visas medan entiteterna har lästs in. När alla dina valda entiteter har lästs in kan du använda funktionerna i Power BI för att visualisera data.

## <a name="large-data-sets"></a>Stora datauppsättningar

Customer Insights-anslutningen för Power BI har utformats för att fungera för data uppsättningar som innehåller upp till 1 miljon kundprofiler. Det kan ta en stund att importera större datauppsättningar, men det tar lång tid. Dessutom kan processen köra på en tidsgräns på grund av Power BI begränsningar. Mer information finns i [Power BI rekommendationerna för stora datauppsättningar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]

