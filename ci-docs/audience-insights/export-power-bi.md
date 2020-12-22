---
title: Anslutningsapp för Power BI
description: Läs mer om hur du använder Dynamics 365 Customer Insights anslutningsprogram i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407066"
---
# <a name="connector-for-power-bi-preview"></a>Koppling för Power BI (förhandsversion)

Skapa visualiseringar för dina data med Power BI Desktop. Skapa ytterligare insikter och skapa rapporter med dina enhetliga kunddata.

## <a name="prerequisites"></a>Förutsättningar

- Du har enhetliga kundprofiler.
- Den senaste versionen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) är installerad på datorn. [Läs mer om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurera koppling för Power BI

1. I Power BI Desktop, välj **Fil** > **Hämta data**.

1. Välj **Se fler** och sök efter **Dynamics 365 Customer Insights**

1. Markera resultatet och välj **Anslut**.

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
