---
title: Översikt över berikning av data (förhandsversion)
description: Utöka kunddata med hjälp av funktioner från Microsoft och andra tjänster från tredje part.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053902"
---
# <a name="data-enrichment-preview-overview"></a>Översikt över berikning av data (förhandsversion)

Använd data från källor som Microsoft och andra partners för att utöka dina kunddata. Tredjepartsutslag konfigureras med hjälp av [anslutningar](connections.md), som en administratör konfigurerar med autentiseringsuppgifter och ger sitt godkännande för informationsöverföring. Anslutningarna kan användas av administratörer och deltagare för att konfigurera berikningar.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flera berikningar av samma typ

Entiteten som ska utökas anges under konfiguration för berikning, vilket gör att du endast kan utöka en delmängd av dina profiler. Utöka till exempel endast data för ett visst segment. Du kan konfigurera flera anrop av samma typ och återanvända samma anslutning. För vissa berikningar begränsas antalet berikningar av samma typ som kan skapas. Begränsningarna och den aktuella användningen visas på varje panel på fliken **Upptäck** på sidan **berikande**.

## <a name="enrich-data-sources-before-unification"></a>Utöka datakällor innan de används

Du kan utöka kunddata innan data för att förbättra kvaliteten på en datamatchning. Mer information: [Berikande för datakällor](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Skapa en berikning

Du måste ha [behörighet](permissions.md) för Deltagare eller Administratör för att kunna skapa eller redigera berikningar.

Gå till **Data** > **Berikning**. På fliken **Upptäck** hittar du alla alternativ för berikning som stöds.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Sida för förbättringsnav.":::

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

- [AbiliTec-identitet](enrichment-liveramp.md) från LiveRamp AbiliTec
- [Varumärken](enrichment-microsoft.md) som tillhandahålls av Microsoft
- [Demografiska uppgifter](enrichment-experian.md) tillhandahålls av Experian
- [Förbättrade adresser](enrichment-enhanced-addresses.md) från Microsoft
- [Intressen](enrichment-microsoft.md) som tillhandahålls av Microsoft
- [Platsdata](enrichment-azure-maps.md) tillhandahålls av Microsoft Azure Maps
- [Platsdata](enrichment-here.md) tillhandahålls av HERE Technologies
- [SFTP anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol)

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

- [Data för kontoengagemang](enrichment-office.md) som tillhandahålls av Microsoft
- [Företagsdata](enrichment-dnb.md) som tillhandahålls från Dun & Bradstreet
- [Företagsdata](enrichment-leadspace.md) tillhandahålls av Leadspace
- [Förbättrade adresser](enrichment-enhanced-addresses.md) från Microsoft
- [Berikade företagsdata ](enrichment-enhanced-company-data.md) från Microsoft
- [Platsdata](enrichment-azure-maps.md) tillhandahålls av Microsoft Azure Maps
- [Platsdata](enrichment-here.md) tillhandahålls av HERE Technologies
- [SFTP anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol)

---

## <a name="manage-existing-enrichments"></a>Hantera befintliga berikningar

Gå till **Data** > **Berikning**. På fliken **Mina berikningar** visar du de konfigurerade berikningar, deras status, antal utökade kunder och sista gången data uppdaterades. Du kan sortera listan med utökar efter valfri kolumn eller använda sökrutan för att hitta det utökande du vill hantera.

Välj berikning om du vill visa tillgängliga åtgärder.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativ för hantering av listan över förbättringar.":::

- **Visa** detaljerad information om hur många kundprofiler som har utökats.
- **Redigera** konfiguration för berikning.
- [**Kör**](#run-or-refresh-enrichments) berikningen för att uppdatera kundprofiler med senaste data. Kör flera utökar samtidigt genom att markera dem i listan.
- **Aktivera** eller **inaktivera** ett berikande. Inaktiva utökar uppdateras inte vid en [schemalagd uppdatering](system.md#schedule-tab).
- **Ta bort** förbättringen.

Du kan också skapa [segment](segments.md) eller [mått](measures.md) utifrån berikande.

## <a name="run-or-refresh-enrichments"></a>Köra eller uppdatera berikande

När de har körts kan berikningar uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran.

1. Om du vill uppdatera en eller flera utökare manuellt markerar du dem och väljer **Kör**. Om du vill [schemalägga en automatisk uppdatering](system.md#schedule-tab) går du till **Admin** > **System** > **Schemalägg**. Bearbetningstiden beror på storleken på dina kunddata.

1. Alternativt kan du [se förloppet av berikandeprocessen](#see-the-progress-of-the-enrichment-process).

1. När berikningsprocessen är klar, gå till **Min berikning** för att granska de nyligen berikade kundprofilernas data, tidpunkten för den senaste uppdateringen och antalet berikade profiler.

1. Markera berikande om du vill visa [berikande-resultat](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Se utökandeprocessens förlopp

Du kan hitta information om bearbetningen av ett utökande, inklusive status och möjliga problem i samband med uppdatering eller efter det att en uppdatering har slutförts. Ta reda på vilka processer som är inblandade för att uppdatera ett utökande och hur lång tid det tog att köra processerna. Utökandestatusen stöds för Experian, Leadspace, HERE Technologies, SFTP-import och Azure Maps.

1. Gå till **Data** > **Berikning**.
1. På fliken **Mina berikanden**, välj status för berikande för att öppna en sidoruta.
1. I fönstret **Förloppsinformation** expanderar du avsnittet **Utökanden**.
1. Under det utökande du vill visa förloppet för väljer du **Visa information**.
1. I fönstret **Uppgiftsinformation** väljer du **Visa information** om du vill se vilka processer som är involverade i att uppdatera utökandet samt statusen för dessa.

## <a name="view-enrichment-results"></a>Visa resultat för berikande

När du har slutfört berikandekörningen kan du granska berikanderesultatet.

1. Gå till **Data** > **Berikning**.
1. På fliken **Mina berikanden** markerar du det berikande som du vill visa.

Alla berikanden anger grundläggande information, t.ex. antalet profiler, samt antalet berikade profiler över tid. Panelen **Förhandsgranskning av berikade kunder** visar ett urval av den genererade berikande enheten. För att se en detaljerad vy, välj **Se mer** och välj **Data**.

:::image type="content" source="media/enrichments-results.png" alt-text="Resultatsida för berikande.":::

Om tillgängligt ger **Antal berikade kunder efter fält** detaljerad information om omfattningen för respektive berikat fält.

I vissa berikanden visas också information som är specifik för den typen av berikande. Mer information finns i relaterad dokumentationen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
