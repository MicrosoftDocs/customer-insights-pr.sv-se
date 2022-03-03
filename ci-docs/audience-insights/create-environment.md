---
title: Skapa miljöer i Customer Insights
description: Steg för att skapa miljöer med en licensierad prenumeration för Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c37afd5649f8cf40d5379f3d39d0cbd96cde3bd3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354117"
---
# <a name="create-an-environment-in-audience-insights"></a>Skapa en miljö i målgruppsinsikter

I den här artikeln finns information om hur du skapar en ny miljö när organisationen har köpt en Dynamics 365 Customer Insights-prenumeration. 

Organisationer kan skapa *två* miljöer för varje Customer Insights-licens. Om din organisation köper fler än en licens [kontaktar du vårt supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) för att öka antalet tillgängliga miljöer. Om du vill ha mer information om kapacitet och tilläggskapacitet hämtar du [Licensguiden för Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Om du vill prova tjänsten finns mer information i [Konfigurera en utvärderingsmiljö](../trial-signup.md). 

## <a name="create-a-new-environment"></a>Skapa en ny miljö

När du har köpt en prenumerationslicens för Customer Insights får den globala administratören av Microsoft 365-klientorganisationen ett e-postmeddelande som bjuder in denne till att skapa miljön. Gå till [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) för att komma igång. 

En guidad upplevelse hjälper dig genom stegen för att samla in all nödvändig information för en ny miljö. Du måste ha [administratörsbehörigheter](permissions.md) i målgruppsinsikter för att skapa eller hantera miljöer.

1. Öppna målgruppsinsikter och välj **+ Nytt** i miljön.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Välj miljöväljaren.":::

1. Följ den guidade upplevelsen som beskrivs i följande avsnitt.

### <a name="step-1-provide-environment-information"></a>Steg 1: Tillhandahåll miljöinformation

I steget **Grundläggande information** väljer du om du vill skapa en miljö från grunden eller [kopiera data från en annan miljö](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog för att skapa en ny Customer Insights-miljö.":::

Ange följande information:
   - **Namn**: Namnet på miljön. Detta fält är redan ifyllt om du har kopierat en befintlig miljö, men du kan ändra det.
   - **Välj din verksamhet**: Välj den primära målgrupp för den nya miljön. Du kan arbeta med enskilda konsumenter (B2C) eller [affärskonton](work-with-business-accounts.md) (B2B).
   - **Typ**: Välj om du vill skapa en produktions- eller sandbox-miljö. Sandbox-miljöer tillåter inte att schemalagda data uppdateras, och är avsedda för förimplementering och testning. I begränsat läge används samma primära målgrupp som den produktionsmiljö som för närvarande är markerad.
   - **Region**: Den region där tjänsten disribueras och förvaras

### <a name="step-2-configure-data-storage"></a>Steg 2: Konfigurera datalagring

I steget **Datalagring** välj var du vill lagra data från målgruppsinsikter.

Du har två alternativ: **Customer Insights-lagring** (en Azure-datasjö som hanteras av Customer Insights-teamet) och **Azure Data Lake Storage** (din egen Azure Data Lake Storage). Som standard är alternativet för Customer Insights-lagring markerat.

:::image type="content" source="media/data-storage-environment.png" alt-text="Välj Azure Data Lake Storage om du vill lagra målgruppsinsikter.":::

Genom att spara data Azure Data Lake Storage till godkänner du att data överförs till och lagras på rätt geografiska plats för det Azure-lagringskontot. Den här platsen kan skilja sig från platsen där data lagras i Dynamics 365 Customer Insights. Läs mer i [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights stöder för närvarande följande:
> - Inmatad entiteter Power BI dataflöden som lagras i en Microsoft Dataverse hanterad Data Lake.  
> - Azure Data Lake Storage-konton från samma Azure-region som du valde när du skapade miljön.
> - Azure Data Lake Storage-konton som är Gen2 och har *hierarkiskt namnområde* aktiverat. Azure Data Lake Gen1-lagringskonton stöds inte.

För alternativet Azure Data Lake Storage kan du välja mellan ett resursbaserat alternativ och ett prenumerationsbaserat autentiseringsalternativ. Mer information finns i [Ansluta till ett Azure Data Lake Storage-konto med hjälp av ett Azure-tjänsthuvudkonto](connect-service-principal.md). Namnet **Behållare** kommer att vara `customerinsights` kan inte ändras.

När systemprocesser som datainmatning är slutförd skapas motsvarande mappar i det angivna lagringskontot. Datafiler och *model.json*-filer skapas och läggs till i mappar baserat på processnamn.

Om du skapar flera miljöer med Customer Insights och väljer att spara utdataentiteterna från dessa miljöer till ditt lagringskonto skapar Customer Insights separata mappar för varje miljö med `ci_environmentID` i behållare.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Steg 3: Anslut till Microsoft Dataverse
   
I **Microsoft Dataverse** steget kan du koppla Customer Insights till din Dataverse miljö.

Tillhandahåll din egen Microsoft Dataverse-miljö för att dela data (profiler och insikter) med företagsprogram baserade på Dataverse, som Dynamics 365 Marketing eller modellbaserade program i Power Apps. Lämna fältet tomt om du inte har din egen Dataverse-miljö så tillhandahåller vi en.

Om du ansluter till din Dataverse-miljö kan du [även hämta data från lokala datakällor med Power Platform-dataflöden och gateways](data-sources.md#add-data-from-on-premises-data-sources). Du kan också använda [färdiga prediktionsmodeller](predictions-overview.md?tabs=b2c#out-of-box-models) genom att ansluta till en Dataverse-miljö.

> [!IMPORTANT]
> Customer Insights och Dataverse måste finnas i samma region för att kunna dela data.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datadelning med Microsoft Dataverse automatisk aktiverad för nya instanser.":::

> [!NOTE]
> Customer Insights stöder inte följande datadelningsscenarier:
> - Om du sparar alla data till din egen Azure Data Lake Storage kommer du inte att kunna aktivera datadelning med en Dataverse-hanterad datasjö.
> - Om du aktiverar datadelning med Dataverse kommer du inte kunna [skapa förutsagda eller saknade värden i en entitet](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Steg 4: Slutför inställningarna

I steget **granskning**, gå igenom alla angivna inställningar. När allt ser klart väljer du **Skapa** för att konfigurera miljön. 

Du kan också ändra de flesta av inställningarna senare. Mer information finns i [Hantera miljöer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeta med den nya miljön

Läs följande artiklar för att hjälpa dig att komma igång med att konfigurera Customer Insights: 

- [Lägg till fler användare och tilldela behörigheter](permissions.md).
- [Mata in dina datakällor](data-sources.md) och kör dem genom [samordningsprocessen för data](data-unification.md) för att får [enhetliga kundprofiler](customer-profiles.md).
- [Utöka de enhetliga kundprofilerna](enrichment-hub.md) eller [kör prediktiva modeller](predictions-overview.md).
- [Skapa segment](segments.md) för att gruppera kunder och [mått](measures.md) för att granska KPI:er.
- [Konfigurera anslutningar](connections.md) och [exporter](export-destinations.md) för att bearbeta underuppsättningar av dina data i andra program.
