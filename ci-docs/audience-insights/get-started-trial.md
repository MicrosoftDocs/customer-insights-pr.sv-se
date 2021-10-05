---
title: Skapa och konfigurera en utvärderingsversion av Customer Insights
description: Steg för att få en utvärderingsprenumeration på Dynamics 365 Customer Insights och konfigurera den.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558847"
---
# <a name="set-up-a-trial-environment"></a>Konfigurera en utvärderingsmiljö 

I en utvärderingsversion Dynamics 365 Customer Insights kan du granska viktiga funktioner och läsa mer om de olika funktionerna. En utvärderingsprenumeration tas bort när den har förfallit. Utvärderingsmiljöer skapas av enskilda användare som blir administratörer för sin utvärderingsmiljö. De kan bjuda in fler användare till utvärderingsversionen och konfigurera de olika funktionerna.

## <a name="create-a-trial-environment"></a>Skapa en utvärderingsmiljö

Du kan registrera dig för en utvärderingsversion på [sidan för registrering av utvärderingsversion](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Välj alternativet **Registrera dig för en kostnadsfri utvärderingsversion** och välj **Registrera nu**.

1. Ange din e-postadress för ditt arbete eller din skola, berätta mer om dig själv och välj **Kom igång**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogruta för att registrera sig för en utvärderingsinstans":::

1. Granska villkoren och markera **Godkänn** för att bekräfta.

1. Ange ett **namn** för den nya miljön. 

1. Ange **miljötypen** som **Utvärdering**.

1. I fältet **Välj en branschdemonstration** kan du välja en branschspecifik datauppsättning (valfritt). Du kan också [byta till en branschdemonstration](#use-industry-specific-demo-data-sets-in-audience-insights) senare och börja med standarddatauppsättningen.

1. Välj en **Region** för din miljö.

1. Om du är administratör för en Dynamics 365-organisation kan du alternativt även välja **Avancerade inställningar** och ange URL-adressen för din organisation om du vill använda funktioner som exempelvis kundomsättningsprognoser. 

1. Välj **Skapa**. 

Det tar en liten stund att slutföra miljökonfigurationen. När du är klar omdirigeras du till demonstrationsmiljön eller den branschdemonstration du väljer i steget ovan. Nu kan du utforska appen med skrivskyddade demodata. Information om hur du lägger till egna data i miljön finns i [Skapa scenariospecifika demodata i din egen miljö](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Skärmbild av en nyskapad utvärderingsmiljö.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Använd branschspecifika demodatauppsättningar i målgruppsinsikter

Att ansluta verkliga datakällor är ett av de viktigaste stegen när det gäller att använda kraften i Customer Insights. Om du vill prova funktioner utan att störa dina egna data kan du även använda branschspecifika demodata. Det finns några demodatauppsättningar tillgängliga för följande branscher: 

-   Bil
-   Banktjänster
-   Konsumentvaror
-   Myndighet
-   Hälsovård
-   Besöksnäring
-   Försäkring
-   Tillverkning
-   Professionella tjänster
-   Detaljhandel

### <a name="see-industry-specific-demo-data-in-trials"></a>Visa branschspecifika demodata i utvärderingsversioner

För en skrivskyddad version av Customer Insights, skräddarsydda för en viss bransch eller ett specifikt scenario, starta i demomiljön. 
 
1.  I publikinsikterna väljer du miljön **Demo** i miljöväljaren.

2.  På **Startsidan** väljer du ett alternativ i listrutan Välj en branschdemonstration.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Välj en bransch för utvärderingsmiljön.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Skapa scenariospecifika demodata i den egna miljön

Som administratör väljer du miljöväljaren i apphuvudet om du vill skapa en ny miljö. I den nya miljön kan du konfigurera dina egna datakällor och konfigurera appen enligt dina krav. 

1.  I målgruppsinsikter går du till **Data** > **Datakällor**.

2.  Om du vill importera dina egna datakällor går du till [guiden för datainmatning](data-sources.md).     
   Om du föredrar att arbeta med exempeldata som gör att du kan prova datainmatning kan du skapa demonstrationsdatan för bransch i din miljö. Välj alternativet **Importera från Datahub** och följ stegen nedan.

3.  Välj det branschkort som passar ditt scenario. 

4.  Granska och eventuellt uppdatera det föreslagna namnet på datakällan. 

5.  Välj **Nästa** för att mata in exempeldatan. 

Du kan nu använda den inmatade datan för att skräddarsy Customer Insights efter ditt scenario. Om du vill se en miljö som är specifik för inmatade demodata väljer du alternativet **<Industry> Demo** i miljöväljaren.

## <a name="limitations-in-trials"></a>Begränsningar i utvärderingsversioner

- Utvärderingsversioner är aktiva i 30 dagar som standard. Du kan emellertid utöka dem efter dag 23 när du loggar in på din utvärderingsversion.
- Du kan inte använda ditt eget Azure Data Lake-lagringskonto för att lagra utdata under en utvärderingsversion. Du kan däremot mata in data från ett Data Lake-lagringskonto.
- Du kan spara upp till 3 GB data i den Dataverse-miljö som tillhandahålls automatiskt när du startar en utvärderingsversion av Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopiera data från en utvärderingsversion till en betald prenumeration

Vanligtvis rekommenderar vi att du börjar om från början med dina egna data när du uppgraderar till betalversionen av Customer Insights. 

Alternativt kan du kopiera dina data från en utvärderingsmiljö om du köper Customer Insights. Du måste vara administratör för utvärderingsversionen av Customer Insights och global administratör för din Microsoft 365-klientorganisation, alternativt Dynamics 365-administratör inom organisationen, om du vill migrera inställningarna från en utvärderingsmiljö till en betalmiljö. 

När du har loggat in på din betalinstans av Customer Insights för första gången uppmanas du att skapa en ny miljö. I den här processen kan du välja att kopiera konfigurationen från en befintlig miljö och migrera de flesta inställningar. Om du har de behörigheter som anges ovan visas utvärderingsmiljön i den här listan. Mer information finns i [Kopiera miljökonfigurationen](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Nästa steg

Läs följande artiklar för att komma igång med att konfigurera Customer Insights. 

- [Lägg till fler användare och tilldela behörigheter](permissions.md).
- [Mata in dina datakällor](data-sources.md) och kör dem genom [samordningsprocessen för data](data-unification.md) för att får [enhetliga kundprofiler](customer-profiles.md).
- [Utöka de enhetliga kundprofilerna](enrichment-hub.md) eller [kör prediktiva modeller](predictions-overview.md).
- Create [segments](segments.md) to group customers and [measures](measures.md) review KPIs.
- Konfigurera [anslutningar](connections.md) och [exporter](export-destinations.md) för att bearbeta underuppsättningar av dina data i andra program.
