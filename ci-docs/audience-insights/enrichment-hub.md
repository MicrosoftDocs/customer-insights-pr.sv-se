---
title: Berika enhetliga kundprofiler
description: Använd kapaciteter för att berika dina kunddata.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032550"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Berikning för kundprofiler (förhandsversion)

Använd data från källor som Microsoft och andra partners för att berika dina kunddata.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Sida för förbättringsnav.":::

I målgruppsinsikter går du till **Data** > **Berikning** för att arbeta med berikningsalternativ.  

Du måste ha behörighet för Deltagare eller Administratör för att kunna skapa eller redigera berikningar. Mer information finns under [Behörigheter](permissions.md).

På fliken **Identifiera** finns följande berikningar:

- [Varumärken](enrichment-microsoft.md) som tillhandahålls av Microsoft
- [Intressen](enrichment-microsoft.md) som tillhandahålls av Microsoft
- [Förbättrade adresser](enrichment-enhanced-addresses.md) från Microsoft
- [Företagsdata](enrichment-leadspace.md) tillhandahålls av Leadspace
- [Demografiska uppgifter](enrichment-experian.md) tillhandahålls av Experian
- [Platsdata](enrichment-here.md) tillhandahålls av HERE Technologies
- [Anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol)

På fliken **Mina berikningar** kan du se vilka berikningar du har konfigurerat och redigera deras egenskaper.

## <a name="manage-existing-enrichments"></a>Hantera befintliga berikningar

Gå till fliken **Mina berikningar** om du vill visa alla konfigurerade berikningar. Varje berikning representeras som en rad som innehåller ytterligare information om berikningen.

Markera förbättringen om du vill visa tillgängliga alternativ. Du kan också välja ellips (...) på ett listobjekt om du vill visa alternativen. Om du har konfigurerat flera förbättringar kan du använda sökrutan för att hitta den snabbt.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativ för hantering av listan över förbättringar.":::

- **Visa** detaljerad information om hur många kundprofiler som har berikats.
- **Redigera** konfiguration för berikning.
- **Kör** berikningen för att uppdatera kundprofiler med senaste data.
- **Inaktivera** en befintlig berikning om du vill förhindra att den uppdateras automatiskt vid alla schemalagda uppdateringar. Data från den senaste uppdateringen kommer fortfarande att vara tillgängliga. **Aktivera** en inaktiv anrikning för att starta om automatisk uppdatering vid alla schemalagda uppdateringar.
- **Ta bort** förbättringen.

Kör eller inaktivera flera förbättringar samtidigt genom att markera dem i listan. Visning- och redigeringsalternativ är inte tillgängliga som massåtgärd. De arbetar bara för en förbättring i taget.

## <a name="enrichments-and-connections"></a>Berikningar och anslutningar

Tredjepartsutslag konfigureras med hjälp av [anslutningar](connections.md), som en administratör konfigurerar med autentiseringsuppgifter och ger sitt godkännande för informationsöverföring. Anslutningen kan användas av administratörer och bidragsgivare för att konfigurera berikningar.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flera berikningar av samma typ

Entiteten som ska utökas anges under konfiguration för berikning, vilket gör att du endast kan utöka en delmängd av dina profiler. Berika till exempel endast data för ett visst segment. Du kan konfigurera flera anrop av samma typ och återanvända samma anslutning. För vissa berikningar begränsas antalet berikningar av samma typ som kan skapas. Begränsningarna och den aktuella användningen visas på sidan **Berikningar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
