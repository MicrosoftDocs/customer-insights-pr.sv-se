---
title: Startsida i målgruppsinsikter
description: Börja utforska appen på startsidan.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597257"
---
# <a name="create-a-new-environment"></a>Skapa en ny miljö

## <a name="create-a-trial-environment"></a>Skapa en utvärderingsmiljö

Du kan registrera dig för en utvärderingsversion på [sidan för registrering av utvärderingsversion](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Utvärderingsversionen upphör att gälla efter 30 dagar.

1. Välj alternativet **Registrera dig för en kostnadsfri utvärderingsversion** och välj **Registrera nu**.

1. Ange din e-postadress för arbetet eller skolan, berätta mer om dig själv och välj **Nästa**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogruta för att registrera sig för en utvärderingsinstans":::

1. Ange ett **namn** för den nya miljön. 

1. Välj utvärderingstyp.

1. Välj en **Region** för din miljö.

1. Om det är en administratör av en Dynamics 365-organisation kan du välja **avancerade inställningar** och ange URL-adressen till din organisation om du vill använda prediktionsfunktioner som kundomsättning.

1. Välj **Skapa**. 

När miljön skapades ser du **Demo**-miljön som gör att du kan utforska appen med fiktiva data. Du kan ändra exempeldata så att de överensstämmer med din bransch. Välj ikonen **Inställningar** i rubriken och välj **Demoinställningar**. Dessutom kan du ändra det visuella temat. 

Du [växlar till den miljö](#switch-environments) du skapade under registreringsprocessen för att arbeta med dina egna data.

## <a name="create-a-new-production-or-sandbox-environment"></a>Skapa en ny produktions- eller sandbox-miljö

I din miljö väljer du **Miljö**-väljare i apphuvudet och välj **Ny**.

Följ anvisningarna på samma sätt som om du [skapar en utvärderingsmiljö](#create-a-trial-environment). Som standard lagras data i Customer Insights-hanterad datasjö. Du kan välja ett annat alternativ när du väljer **Avancerade inställningar** för att lagra dina data i din egen Azure Data Lake. Ange kontonamn och kontonyckel för att upprätta en anslutning till din Azure Data Lake. 

> [!IMPORTANT]
> Genom att spara data i Azure Data Lake Storage godkänner du att data överförs till och lagras på rätt geografiska plats för Azure Storage-kontot, som kan skilja sig från varifrån data lagras i Dynamics 365 Customer Insights. [Läs mer i Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Utforska startsidan

Du kan [få tillgång till målgruppsinsikter från Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) på följande URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Start** sidan visar en översikt över segment, mått och berikningsdata (om konfigurerat) efter slutförandet av faserna [mappa](map-entities.md), [matcha](match-entities.md) och [sammanslå](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Insikter på startsidan](media/home-page-insights.png "Insikter på startsidan")

Under **senaste segment** visas grupper med kunder utifrån demografiska, beteende- eller transaktionella attribut som du har definierat. [Genom att skapa segment](segments.md) kan du gruppera din kundbas och rikta dina affärsaktiviteter på ett bättre sätt.

**Senaste åtgärder** visar paneler med [nyckeltal (KPI:er)](measures.md) som du har definierats. Till exempel genomsnittlig sannolikhet för kundomsättning eller genomsnittlig omsättning online per kund.

I avsnittet **Senast använda** visas resultaten av de nya anriknings körningarna som har slutförts nyligen. [Berikningar](enrichment-hub.md) lägger till information om kundbasen. Du kan till exempel förstå de intressen och märken som de har tillhörighet för.

## <a name="switch-environments"></a>Växla miljö

Välj kontrollen **miljö** i det övre högra hörnet av sidan om du vill ändra miljöer.

> [!div class="mx-imgBorder"] 
> ![Växla miljö](media/home-page-environment-switcher.png "Växla miljö")

Administratörer kan skapa och hantera [flera miljöer](manage-environments.md). Det kan vara bra att upprätthålla mer än en miljö om din organisation exempelvis arbetar internationellt och du behöver åtskilja data och insikter på olika sätt.

## <a name="next-step"></a>Nästa steg

Om du vill visa dina egna insikter på startsidan måste du först [lägga till datakällor](data-sources.md) och [förena](data-unification.md) dina data för att skapa kundprofiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]