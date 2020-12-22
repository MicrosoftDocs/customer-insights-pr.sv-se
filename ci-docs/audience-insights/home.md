---
title: Startsida i målgruppsinsikter
description: Börja utforska appen på startsidan.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407091"
---
# <a name="create-a-new-environment"></a>Skapa en ny miljö

## <a name="create-a-trial-environment"></a>Skapa en utvärderingsmiljö

Du kan registrera dig för en utvärderingsversion på [sidan för registrering av utvärderingsversion](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Utvärderingsversionen upphör att gälla efter 30 dagar.

1. Välj alternativet **Registrera dig för en kostnadsfri utvärderingsversion** och välj **Registrera nu**.

1. Ange din e-postadress för arbetet eller skolan, berätta mer om dig själv och välj **Nästa**.

1. Ange ett **namn** för den nya miljön. 

1. Välj utvärderingstyp.

1. Välj en **Region** för din miljö.

1. Om det är en administratör av en Dynamics 365-organisation kan du välja **avancerade inställningar** och ange URL-adressen till din organisation om du vill använda prediktionsfunktioner som kundomsättning.

1. Välj **Skapa**. 

När miljön skapades ser du **Demo**-miljön som gör att du kan utforska appen med fiktiva data. Du kan ändra exempeldata så att de överensstämmer med din bransch. Välj ikonen **Inställningar** i rubriken och välj **Demoinställningar**. Dessutom kan du ändra det visuella temat. 

Du [växlar till den miljö](#change-between-environments) du skapade under registreringsprocessen för att arbeta med dina egna data.

## <a name="create-a-new-production-or-sandbox-environment"></a>Skapa en ny produktions- eller sandbox-miljö

I din miljö, väljer du ikonen **Inställningar** i rubriken och välj **Ny miljö**.

Följ anvisningarna på samma sätt som om du [skapar en utvärderingsmiljö](#create-a-trial-environment). Du kan välja ett annat alternativ när du väljer **Avancerade inställningar** för att lagra dina data i din egen Azure Data Lake. Ange kontonamn och kontonyckel för att upprätta en anslutning till din Azure Data Lake. Som standard lagras data i Customer Insights-hanterad datasjö.

> [!IMPORTANT]
> Genom att spara data i Azure Data Lake Storage godkänner du att data överförs till och lagras på rätt geografiska plats för Azure Storage-kontot, som kan skilja sig från varifrån data lagras i Dynamics 365 Customer Insights. [Läs mer i Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Utforska startsidan

Du kan [komma åt din Customer Insights-miljö](https://home.ci.ai.dynamics.com/) på följande webbadress: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Sidan **Start** visar en översikt över din kundbas och viktiga mätvärden för att spåra ditt företags hälsa.

> [!div class="mx-imgBorder"] 
> ![Insikter på startsidan](media/home-page-insights.png "Insikter på startsidan")

Under **senaste segment** visas grupper med kunder utifrån demografiska, beteende- eller transaktionella attribut som du har definierat. [Genom att skapa segment](segments.md) blir det lättare att rikta in sig på sina affärsaktiviteter.

**Senaste mått** visar paneler med [mått](measures.md). Mått är KPI:er som du har definierat. Det kan till exempel vara sannolikheten kundomsättning eller genomsnittligt antal online-utgifter per kund.

I avsnittet **Senast använda** visas resultaten av de nya anriknings körningarna som har slutförts nyligen. Omfattande lägg till information om kundbasen. Du kan till exempel förstå de intressen och märken som de har tillhörighet för. Denna information kan låsas upp med hjälp av [beriknings](enrichment-microsoft-graph.md)funktionerna efter det att du har slutfört faserna [mappning](map-entities.md), [matchning](match-entities.md) och [sammanslagning](merge-entities.md).

## <a name="change-between-environments"></a>Växla mellan miljöer

När du har konfigurerat dina [datakällor](data-sources.md) bör du växla från en demomiljö till en verklig miljö. Genom att använda produktions miljön kan du arbeta med dina egna kunddata. Välj kontrollen **miljö** i det övre högra hörnet av sidan om du vill ändra miljöer.

> [!div class="mx-imgBorder"] 
> ![Växla miljö](media/home-page-environment-switcher.png "Växla miljö")

Administratörer kan skapa och hantera [flera miljöer](manage-environments.md). Det kan vara bra att upprätthålla mer än en miljö om din organisation exempelvis arbetar internationellt och du behöver åtskilja data och insikter på olika sätt.

## <a name="next-step"></a>Nästa steg

Om du vill visa dina egna insikter på startsidan måste du först [lägga till datakällor](data-sources.md) och [förena](data-unification.md) dina data för att skapa kundprofiler.
