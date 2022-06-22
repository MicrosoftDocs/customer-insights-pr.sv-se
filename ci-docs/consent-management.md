---
title: Använd kundmedgivande
description: Godkänn dina kunders samtyckesinställningar i Customer Insights genom att importera samtyckesdata.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947509"
---
# <a name="use-customer-consent"></a>Använd kundmedgivande

Regler om dataskydd och sekretess ger enskilda personer rätt att styra hur en organisation använder sina personuppgifter. Exempel på sådana bestämmelser är den allmänna dataskyddsförordningen i Europeiska unionen eller California Consumer Privacy Act i USA. Med hjälp av dessa regler kan personer välja bort att samla in, bearbeta eller dela sina personuppgifter med tredje part.  

Kunderna kan välja att ta bort eller undanhålla sitt samtycke till specifika kontaktformulär. De kan också begära att du avanmäler dig från insamling, lagring, användning eller försäljning av deras personliga data. Det är viktigt att din organisation godkänner alla kunders samtycken och sekretessinställningar.  

Dynamics 365 Customer Insights hjälper dig att uppfylla kundernas önskemål genom att importera och lagra deras preferenser som en del av enhetliga kundprofiler.

Om samtyckesdata lagras separat från dina kundprofiler [lägger du till dina samtyckesdata som en ny datakälla](#import-and-unify-consent-data). Den datakälla som innehåller samtyckesuppgifterna läggs till i dataprocess. Godkännande av samtyckesdata och kundprofiler leder sedan till enhetliga kundprofiler som innehåller samtyckesinformationen. För kundprofiler som redan innehåller samtyckesinformation går du direkt till avsnittet [använd samtyckesdata](#use-consent-data).

## <a name="prerequisites"></a>Förutsättningar

Följande information måste finnas tillgänglig i dina källdata för att ena samtyckesdata till andra kundprofiler:

- Alternativ nyckel att mappa samtyckesinformationen till användarprofiler i Customer Insights. Till exempel en e-postadress eller ett telefonnummer.
- Samtyckesvärde för att fastställa status för kundens samtycke.

Överväg att lägga till följande *valfritt* information:

- Primärnyckel för att uppdatera samtyckesstatus om en kund begär en ändring.
- Typ av godkännande, om det finns mer än ett sätt att bearbeta kundinformation.
- Datum för godkännande eller någon annan typ av data som är relevanta för dina samtyckesscenarier.

Exempeltabell för en enkel samtyckesdatabas med flera samtyckesalternativ:

|Samtyckes-ID (primärnyckel)   |E-post (alternativ nyckel)  |Alternativ för godkännande  |Medgivandevärde  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Nyhetsbrev       |  Falsk       |
|2    |  holly@contoso.com       |  Produktuppdateringar       |  Sann       |
|3    |  frank@contoso.com       |  Nyhetsbrev       | Sann        |
|4    |  frank@contoso.com       |  Produktuppdateringar       |  Falsk       |

## <a name="import-and-unify-consent-data"></a>Importera och ena samtyckesdata

Du kan importera samtyckesdata på samma sätt som andra datakällor till Customer Insights. Mer information om datakällor som stöds och hur du importerar dem finns i [översikt över datakällor](data-sources.md).

Mer information om att ena dina datakällor finns i [Översikt över datasammanslutning](data-unification.md).

## <a name="use-consent-data"></a>Använd samtyckesdata

När dina samtyckesdata är en del av dina Unified Customer Profile kan du använda dem i Customer Insights. Du kan till exempel skapa ett segment med en regel för att säkerställa att du är nöjd med kundernas önskemål om sekretess och dataskydd. Regler som stöder samtyckesinställningar används för att utesluta användare från ett segment baserat på profilattribut. Lägga till en regel i ett segment som utesluter kundprofiler som inte ger samtycke till kontakt.

Ett segment kan referera till exempeltabellen ovan och innehålla följande regel: `Consent option=Newsletter & Consent value=True`. Den här konfigurationen resulterar i ett segment som tillämpar kontaktinställningar för att skicka ett nyhetsbrev.

Mer information om hur du skapar segment finns i [Skapa segment](segment-builder.md).

När du har skapat ett segment kan du använda ett av de många [exportalternativen](export-destinations.md) för att använda segment i andra program.

## <a name="ensure-updated-consent-status"></a>Säkerställa uppdaterad samtyckesstatus

Det är viktigt att du håller kundens samtyckesstatus uppdaterad. Den schemalagda uppdateringen i Customer Insights importerar alltid det senaste tillståndet för dina datakällor. Informationen bearbetas sedan med hjälp av data och resulterar i uppdaterade kundprofiler. Dessa uppdaterade profiler används sedan för att uppdatera segment för att se till att du arbetar med den allra senaste informationen.

Med andra ord bör du se till att de källdata som importeras till Customer Insights alltid har den senaste informationen.

Mer information finns i [Uppdatera segment manuellt](segments.md#refresh-segments) eller [konfigurera en schemalagd uppdatering](system.md#schedule-tab).
