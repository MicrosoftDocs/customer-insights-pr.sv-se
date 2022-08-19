---
title: 'Gör så här: Skapa en ny miljö'
description: Steg för att skapa miljöer i Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245625"
---
# <a name="how-to-create-a-new-environment"></a>Gör så här: Skapa en ny miljö

När du har [köpt en prenumerationslicens för Dynamics 365 Customer Insights](paid-license.md) får den globala administratören av Microsoft 365-klientorganisationen ett e-postmeddelande som bjuder in denne till att skapa miljön. Gå till [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) för att komma igång. I det här scenariot kan du gå direkt till [Steg 1: Ge grundläggande information](#step-1-provide-basic-information).

När den första miljön har skapats kan den globala administratör för Microsoft 365-klientorganisationen [läga till användare från sin organisation som administratörer](permissions.md). Längre fram kan dessa administratörer hantera användare och miljöer. Om din organisation köper fler än en licens för Customer Insights [kontaktar du vårt supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) för att öka antalet tillgängliga miljöer. Mer information om kapacitet och tilläggskapacitet finns i [Dynamics 365 licensguiden](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Om du vill prova tjänsten finns mer information i [Konfigurera en utvärderingsmiljö](trial-signup.md).

## <a name="prerequisites"></a>Förutsättningar

Du måste ha [administratörsbehörigheter](permissions.md) i Customer Insights för att skapa eller hantera miljöer.

## <a name="start-the-environment-creation-process"></a>Starta processen för att skapa miljö

1. Öppna miljöväljaren och välj **+ Ny**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Välj miljöväljaren.":::

1. Följ den guidade upplevelsen som beskrivs i följande avsnitt för att ge all nödvändig information för en ny miljö. Om du har konfigurerat en miljö tidigare kan du också [kopiera konfigurationen](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Steg 1: Tillhandahåll grundläggande information

I steget **Grundläggande information** väljer du om du vill skapa en miljö från grunden eller [kopiera data från en annan miljö](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog för att skapa en ny Customer Insights-miljö.":::

Ange följande information:

- **Namn**: Namnet på miljön. Detta fält är redan ifyllt om du har kopierat en befintlig miljö, men du kan ändra det. Om du har mer än en arbetsmiljö, ge var och en ett lätt identifierbart namn.
- **Välj din verksamhet**: Välj den primära målgrupp för den nya miljön. Du kan arbeta med enskilda konsumenter (B2C) eller [affärskonton](work-with-business-accounts.md) (B2B). Om organisationen i huvudsak gör affärer med enskilda personer, till exempel en återförsäljare eller en kafé, väljer du enskilda kunder. Om din primära målgrupp är andra företag, till exempel en biltillverkare eller ett pappersföretag, väljer du företagskonton.
- **Typ**: Välj om du vill skapa en produktions- eller sandbox-miljö. Sandbox-miljöer tillåter inte att schemalagda data uppdateras, och är avsedda för förimplementering och testning. I begränsat läge används samma primära målgrupp som den produktionsmiljö som för närvarande är markerad.
- **Region**: Den region där tjänsten disribueras och förvaras Om du vill [använda ditt eget Azure Data Lake Storage-konto](own-data-lake-storage.md) eller [ansluta till en befintlig Microsoft Dataverse-organisation](customer-insights-dataverse.md) måste Customer Insights-miljön finnas i samma region.

## <a name="step-2-configure-data-storage"></a>Steg 2: Konfigurera datalagring

I steget **Datalagring** välj var du vill lagra data från Customer Insights.

Du kan välja mellan två alternativ:

- **Customer Insights-lagring**: Datalagring hanteras av Customer Insights-teamet. Detta är standardalternativet, och om det inte finns särskilda krav för att lagra data i ditt eget lagringskonto rekommenderar vi att du använder det här alternativet.
- **Azure Data Lake Storage**: Ange ditt eget Azure Data Lake Storage-konto för lagring av data så att du har fullständig kontroll över var data lagras. Mer information finns i [Använda ditt eget Azure Data Lake Storage-konto](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Välj föredraget alternativ för att lagra dina data.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Steg 3: Anslut till Microsoft Dataverse

I **Microsoft Dataverse** steget kan du koppla Customer Insights till din Dataverse miljö. Dela data med Dataverse för att använda den med affärsappar baserade på Dataverse, exempelvis Dynamics 365 Marketing eller modellbaserade program i Power Apps.

Lämna detta fält tomt om du inte har din egen Dataverse-miljö, så skapar vi en.

Mer information finns i [Arbeta med Customer Insights-data i Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="-datadelning med Microsoft Dataverse automatiskt aktiverat för nya miljöer.":::

### <a name="step-4-finalize-the-settings"></a>Steg 4: Slutför inställningarna

I steget **granskning**, gå igenom alla angivna inställningar. När allt ser klart väljer du **Skapa** för att konfigurera miljön.

Du kan också ändra vissa av inställningarna senare. Mer information finns i [Hantera miljöer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeta med den nya miljön

Läs följande artiklar för att hjälpa dig att komma igång med att konfigurera Customer Insights:

- [Lägg till fler användare och tilldela behörigheter](permissions.md).
- [Mata in dina datakällor](data-sources.md) och kör dem genom [samordningsprocessen för data](data-unification.md) för att får [enhetliga kundprofiler](customer-profiles.md).
- [Utöka de enhetliga kundprofilerna](enrichment-hub.md) eller [kör prediktiva modeller](predictions-overview.md).
- [Skapa segment](segments.md) för att gruppera kunder och [mått](measures.md) för att granska KPI:er.
- [Konfigurera anslutningar](connections.md) och [exporter](export-destinations.md) för att bearbeta underuppsättningar av dina data i andra program.

## <a name="copy-the-environment-configuration"></a>Kopiera miljökonfigurationen

Som administratör kan du välja att kopiera konfigurationen från en befintlig miljö när du skapar en ny.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skärmbild av inställningsalternativen i miljöinställningarna.":::

Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.

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

## <a name="set-up-a-copied-environment"></a>Konfigurera en kopierad miljö

När du kopierar miljökonfigurationen måste du gå igenom några extra steg för att bekräfta autentiseringsuppgifter:

- Kundprofiler. Först autentiserar och bekräftar du dina datakällor och kör data för att skapa kundprofilerna på nytt.
- Autentiseringsuppgifter för datakälla. Du måste ange autentiseringsuppgifterna för varje datakälla om du vill autentisera och uppdatera datakällorna manuellt.
- Datakällor från mappen Common Data Model och Dataverse. Du måste skapa dessa datakällor manuellt med samma namn som i källmiljön.
- Anslutningshemligheter som används för export och berikanden. Du måste återautentisera anslutningarna och sedan återaktivera berikanden och exporter.

Ett bekräftelsemeddelande visas när den kopierade miljön har skapats. Välj **gå till datakällor** om du vill visa listan över datakällor.

I alla data källor visas statusen **Autentiseringsuppgifter krävs**. Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista över datakällor som kopierats och som behöver autentisering.":::

När datakällorna har uppdaterats går du till **Data** > **Förena**. Här hittar du inställningar från källmiljön. Redigera dem efter behov eller välj **kör** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.

När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.

Innan du återaktiverar exporter och berikanden går du till **Administratör** > **Anslutningar** för att återautentisera anslutningarna i din nya miljö.

[!INCLUDE [footer-include](includes/footer-banner.md)]
