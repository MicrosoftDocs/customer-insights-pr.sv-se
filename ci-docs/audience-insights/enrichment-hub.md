---
title: Utöka enhetliga kundprofiler
description: Använd kapaciteter för att utöka dina kunddata.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: e44e973bf7713ed5c31dfb9849419decd4ad1c78
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884238"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Berikning för kundprofiler (förhandsversion)

Använd data från källor som Microsoft och andra partners för att utöka dina kunddata.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Sida för förbättringsnav.":::

I målgruppsinsikter går du till **Data** > **Berikning** för att arbeta med berikningsalternativ.  

Du måste ha behörighet för Deltagare eller Administratör för att kunna skapa eller redigera berikningar. Mer information finns under [Behörigheter](permissions.md).

På fliken **Upptäck** hittar du alla alternativ för berikning som stöds.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

- [Varumärken](enrichment-microsoft.md) som tillhandahålls av Microsoft
- [Intressen](enrichment-microsoft.md) som tillhandahålls av Microsoft
- [Förbättrade adresser](enrichment-enhanced-addresses.md) från Microsoft 
- [Demografiska uppgifter](enrichment-experian.md) tillhandahålls av Experian
- [Anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol) 
- [Azure Maps](enrichment-azure-maps.md) som tillhandahålls av Microsoft

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

- [Företagsdata](enrichment-leadspace.md) tillhandahålls av Leadspace
- [Förbättrade adresser](enrichment-enhanced-addresses.md) från Microsoft 
- [Berikade företagsdata ](enrichment-enhanced-company-data.md) från Microsoft
- [Platsdata](enrichment-here.md) tillhandahålls av HERE Technologies 
- [Anpassade data](enrichment-SFTP-custom-import.md) genom SFTP (Secure File Transfer Protocol) 
- [Azure Maps](enrichment-azure-maps.md) som tillhandahålls av Microsoft
- [Data för kontoengagemang](enrichment-office.md) som tillhandahålls av Microsoft

---

På fliken **Mina berikningar** kan du se vilka berikningar du har konfigurerat och redigera deras egenskaper.

## <a name="manage-existing-enrichments"></a>Hantera befintliga berikningar

Gå till fliken **Mina berikningar** om du vill visa alla konfigurerade berikningar. Varje berikning representeras som en rad som innehåller ytterligare information om berikningen.

Markera förbättringen om du vill visa tillgängliga alternativ. Du kan också välja ellips (…) på ett listobjekt om du vill visa alternativen. Om du har konfigurerat flera förbättringar kan du använda sökrutan för att hitta den snabbt.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativ för hantering av listan över förbättringar.":::

- **Visa** detaljerad information om hur många kundprofiler som har utökats.
- **Redigera** konfiguration för berikning.
- **Kör** berikningen för att uppdatera kundprofiler med senaste data.
- **Inaktivera** en befintlig berikning om du vill förhindra att den uppdateras automatiskt vid alla schemalagda uppdateringar. Data från den senaste uppdateringen kommer fortfarande att vara tillgängliga. **Aktivera** en inaktiv anrikning för att starta om automatisk uppdatering vid alla schemalagda uppdateringar.
- **Ta bort** förbättringen.

Kör eller inaktivera flera förbättringar samtidigt genom att markera dem i listan. Visning- och redigeringsalternativ är inte tillgängliga som massåtgärd. De arbetar bara för en förbättring i taget.

## <a name="enrichments-and-connections"></a>Berikningar och anslutningar

Tredjepartsutslag konfigureras med hjälp av [anslutningar](connections.md), som en administratör konfigurerar med autentiseringsuppgifter och ger sitt godkännande för informationsöverföring. Anslutningarna kan användas av administratörer och deltagare för att konfigurera berikningar.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flera berikningar av samma typ

Entiteten som ska utökas anges under konfiguration för berikning, vilket gör att du endast kan utöka en delmängd av dina profiler. Utöka till exempel endast data för ett visst segment. Du kan konfigurera flera anrop av samma typ och återanvända samma anslutning. För vissa berikningar begränsas antalet berikningar av samma typ som kan skapas. Begränsningarna och den aktuella användningen visas på sidan **Berikningar**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Se utökandeprocessens förlopp

Du kan hitta information om bearbetningen av ett utökande, inklusive status och möjliga problem i samband med uppdatering eller efter det att en uppdatering har slutförts. Ta reda på vilka processer som är inblandade för att uppdatera ett utökande och hur lång tid det tog att köra processerna. Utökandestatusen stöds för Experian, Leadspace, HERE Technologies, SFTP-import och Azure Maps.

Så här ser du statusen för ett utökande

1. Gå till **Data** > **Berikning**. 
1. På fliken **Mina utökanden** väljer du statusen för ett utökande om du vill öppna ett sidofönster. 
1. I fönstret **Förloppsinformation** expanderar du avsnittet **Utökanden**. 
1. Under det utökande du vill visa förloppet för väljer du **Visa information**. 
1. I fönstret **Uppgiftsinformation** väljer du **Visa information** om du vill se vilka processer som är involverade i att uppdatera utökandet samt statusen för dessa. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
