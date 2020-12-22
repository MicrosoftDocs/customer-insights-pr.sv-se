---
title: Berika enhetliga kundprofiler
description: Använd kapaciteter för att berika dina kunddata.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667116"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Berikning för kundprofiler (förhandsversion)

Använd data från källor som Microsoft och andra partners för att berika dina kunddata.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Sidan för berikningsnav":::

I målgruppsinsikter går du till **Data** > **Berikning** för att arbeta med berikningsalternativ.    
Du måste ha behörighet för Deltagare eller Administratör för att kunna skapa eller redigera berikningar. Mer information finns under [Behörigheter](permissions.md).

På fliken **Identifiera** finns följande berikningar:

- [Varumärken](enrichment-microsoft-graph.md) tillhandahålls av Microsoft Graph
- [Intressen](enrichment-microsoft-graph.md) tillhandahålls av Microsoft Graph
- [Företagsdata](enrichment-leadspace.md) tillhandahålls av Leadspace
- [Demografi](enrichment-experian.md) tillhandahålls av Experian
- [Platsdata](enrichment-here.md) tillhandahålls av HERE Technologies
- [Anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol)

På fliken **Mina berikningar** kan du se vilka berikningar du har konfigurerat och redigera deras egenskaper.

## <a name="manage-existing-enrichments"></a>Hantera befintliga berikningar

Gå till **Mina berikningar** för att se alla konfigurerade berikningar. Varje berikning representeras som en rad som innehåller ytterligare information om berikningen.

Välj en berikning för att se de tillgängliga alternativen. Alternativt kan du välja tre punkter (...) i ett listobjekt för att se alternativen.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativ för hantering av listan över berikningar":::

- **Visa** detaljerad information om hur många kundprofiler som har berikats.
- **Redigera** konfiguration för berikning.
- **Kör** berikningen för att uppdatera kundprofiler med senaste data.
- **Inaktivera** en befintlig berikning om du vill förhindra att den uppdateras automatiskt vid alla schemalagda uppdateringar. Data från den senaste uppdateringen kommer fortfarande att vara tillgängliga. **Aktivera** en inaktiv anrikning för att starta om automatisk uppdatering vid alla schemalagda uppdateringar.
- **Ta bort** en berikning.

Du kan köra eller inaktivera flera berikningar samtidigt genom att markera dem i listan. Visnings- och redigeringsalternativ är inte tillgängliga som massåtgärd och fungerar bara för en berikning åt gången.
