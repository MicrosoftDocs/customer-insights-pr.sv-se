---
title: Skapa en ny miljö
description: Steg för att skapa miljöer i Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304290"
---
# <a name="create-a-new-environment"></a>Skapa en ny miljö

När du har [köpt en prenumerationslicens för Dynamics 365 Customer Insights](paid-license.md) får den globala administratören av Microsoft 365-klientorganisationen ett e-postmeddelande som bjuder in denne till att skapa miljön. Gå till [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) för att komma igång. I det här scenariot, starta med [Steg 1: Ge grundläggande information](#step-1-provide-basic-information).

När den första miljön har skapats kan den globala administratör för Microsoft 365-klientorganisationen [lägga till användare från sin organisation som administratörer](permissions.md). Dessa administratörer kan sedan hantera användare och miljöer. Om din organisation köper fler än en licens för Customer Insights [kontaktar du vårt supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) för att öka antalet tillgängliga miljöer. Mer information om kapacitet och tilläggskapacitet finns i [Dynamics 365 licensguiden](https://go.microsoft.com/fwlink/?LinkId=866544). När du har möjlighet att skapa ytterligare miljöer går du till [Starta processen för att skapa miljön](#start-the-environment-creation-process).

> [!TIP]
> Om du vill prova tjänsten finns mer information i [Konfigurera en utvärderingsmiljö](trial-signup.md).

## <a name="prerequisites"></a>Förutsättningar

[Administratörbehörigheter](permissions.md) i Customer Insights

## <a name="start-the-environment-creation-process"></a>Starta processen för att skapa miljö

1. Öppna miljöväljaren och välj **+ Ny**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Välj miljöväljaren.":::

1. Följ den guidade upplevelsen som beskrivs i följande avsnitt för att ge all nödvändig information för en ny miljö.

## <a name="step-1-provide-basic-information"></a>Steg 1: Tillhandahåll grundläggande information

1. Välj om du vill skapa en miljö från grunden eller kopiera data från en annan miljö. [Kopiera data från en annan miljö](#copy-the-environment-configuration) kräver ytterligare steg

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog för att skapa en ny Customer Insights-miljö.":::

1. Ange följande information:

   - **Namn**: Namnet på miljön. Detta fält är redan ifyllt om du har kopierat en befintlig miljö, men du kan ändra det.
   - **Välj din verksamhet**: Primär målgrupp för den nya miljön: enskilda konsumenter (B2C) eller [affärskonton](work-with-business-accounts.md) (B2B). Om organisationen i huvudsak gör affärer med enskilda personer, till exempel en återförsäljare eller en kafé, väljer du enskilda kunder. Om din primära målgrupp är andra företag, till exempel en biltillverkare eller ett pappersföretag, väljer du företagskonton.
   - **Typ**: Typ av miljö: produktion eller sandbox. Sandbox-miljöer tillåter inte att schemalagda data uppdateras, och är avsedda för förimplementering och testning. I begränsat läge används samma primära målgrupp som den produktionsmiljö som för närvarande är markerad.
   - **Region**: Den region där tjänsten distribueras och förvaras Om du vill [använda ditt eget Azure Data Lake Storage-konto](own-data-lake-storage.md) eller [ansluta till en befintlig Microsoft Dataverse-organisation](customer-insights-dataverse.md) måste Customer Insights-miljön finnas i samma region.

1. Välj **Nästa**.

## <a name="step-2-configure-data-storage"></a>Steg 2: Konfigurera datalagring

1. Välj var du vill lagra Customer Insights-data:

   - **Customer Insights-lagring**: Datalagring hanteras automatiskt. Detta är standardalternativet, och om det inte finns särskilda krav för att lagra data i ditt eget lagringskonto rekommenderar vi att du använder det här alternativet.
   - **Azure Data Lake Storage**: Ditt eget Azure Data Lake Storage-konto för lagring av data så att du har fullständig kontroll över var data lagras. Följ anvisningarna i [Använd ditt eget Azure Data Lake Storage konto](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Välj föredraget alternativ för att lagra dina data.":::

1. Välj **Nästa**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Steg 3: Anslut till Microsoft Dataverse

Om du har en Dataverse-miljö, anslut till Customer Insights. Dela data med Dataverse för att använda den med affärsappar baserade på Dataverse, exempelvis Dynamics 365 Marketing eller modellbaserade program i Power Apps.

1. Följ anvisningarna i [Arbeta med Customer Insights-data i Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="-datadelning med Microsoft Dataverse automatiskt aktiverat för nya miljöer.":::

1. Välj **Nästa**.

## <a name="step-4-finalize-the-settings"></a>Steg 4: Slutför inställningarna

Granska de angivna inställningarna. När allt ser klart väljer du **Skapa** för att konfigurera miljön.

Information om hur du ändrar några av inställningarna senare finns i [Hantera miljöer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeta med den nya miljön

Läs följande artiklar för att hjälpa dig att komma igång med att konfigurera Customer Insights:

- [Lägg till fler användare och tilldela behörigheter](permissions.md).
- [Mata in dina datakällor](data-sources.md) och kör dem genom [samordningsprocessen för data](data-unification.md) för att får [enhetliga kundprofiler](customer-profiles.md).
- [Utöka de enhetliga kundprofilerna](enrichment-hub.md) eller [kör prediktiva modeller](predictions-overview.md).
- [Skapa segment](segments.md) för att gruppera kunder och [mått](measures.md) för att granska KPI:er.
- [Konfigurera anslutningar](connections.md) och [exporter](export-destinations.md) för att bearbeta underuppsättningar av dina data i andra program.

## <a name="copy-the-environment-configuration"></a>Kopiera miljökonfigurationen

Om du som administratör väljer att kopiera konfigurationen från en befintlig miljö väljer du i listan över alla tillgängliga miljöer i organisationen.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skärmbild av inställningsalternativen i miljöinställningarna.":::

Följande konfigurationsinställningar kan kopieras:

- Datakällor som importeras via Power Query
- Konfiguration av datasammanslutning
- Segment
- Mått
- Relationer
- Aktiviteter
- Sök och filtrera index
- Exporter
- Uppdatera schema
- Berikningar
- Prediktionsmodeller
- Rolltilldelningar

### <a name="set-up-a-copied-environment"></a>Konfigurera en kopierad miljö

När du kopierar en miljökonfiguration visas ett bekräftelsemeddelande om att den kopierade miljön har skapats. Utför följande steg för att bekräfta autentiseringsuppgifterna.

1. Välj **gå till datakällor** om du vill visa listan över datakällor. I alla data källor visas statusen **Autentiseringsuppgifter krävs**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista över datakällor som kopierats och som behöver autentisering.":::

1. Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem. Datakällor från mappen Common Data Model och Dataverse måste skapas manuellt med samma namn som i källmiljön.

1. När datakällorna har uppdaterats går du till **Data** > **Förena**. Här hittar du inställningar från källmiljön. Redigera dem efter behov eller välj **Förena** > **Förena kundprofiler och beroenden** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.

   > [!TIP]
   > För konton och kontaktpersoner väljer du **Förena konton** > **Förena profiler och beroenden**.

1. När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.

1. Gå till **Administratör** > **Anslutningar** för att återautentisera anslutningarna i din nya miljö.

1. Gå till **Data** > **Berika** och **Data** > **Exporter** om du vill återaktivera dem.

[!INCLUDE [footer-include](includes/footer-banner.md)]
