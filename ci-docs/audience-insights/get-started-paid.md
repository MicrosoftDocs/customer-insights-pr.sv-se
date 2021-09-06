---
title: Skapa och konfigurera en betallicens för Customer Insights
description: Steg för att få en licensierad prenumeration på Dynamics 365 Customer Insights och konfigurera den.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034474"
---
# <a name="get-started-with-a-paid-subscription"></a>Komma igång med en betalprenumeration

I den här artikeln finns information om hur du skapar en ny miljö när organisationen har köpt en Dynamics 365 Customer Insights-prenumeration. Om du vill köpa Customer Insights listas våra kontaktalternativ på [Dynamics 365 Customer Insights-webbplatsen](https://dynamics.microsoft.com/ai/customer-insights/). 

Om du vill prova tjänsten och funktionerna finns mer information i [Konfigurera en utvärderingsmiljö](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Skapa en miljö i en befintlig organisation

När du har köpt en prenumerationslicens för Customer Insights får den globala administratören för Microsoft 365-klientorganisationen ett e-postmeddelande som bjuder in denne att skapa miljön. Gå till [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) för att komma igång. 

Customer Insights licensieras inte per användare, så det visas inte i området Licenser. Om du letar efter licensen i administrationscentret för Microsoft 365 går du till **Dina produkter**. 

> [!NOTE]
> Organisationer kan skapa *två* miljöer för varje Customer Insights-licens. Om din organisation köper mer än en gång licens [kontakta vårt supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) för att öka antalet tillgängliga miljöer. Om du vill ha mer information om kapacitet och tilläggskapacitet hämtar du [Licensguiden för Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

För att skapa en miljö i:

1. I dialogrutan **Skapa en miljö** väljer du **Ny miljö**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog för att skapa en ny Customer Insights-miljö.":::

   Vi rekommenderar att du börjar konfigurera en miljö helt från grunden. Om du är administratör eller medlem i en utvärderingsmiljö kan du emellertid [kopiera data från en annan miljö](manage-environments.md#copy-the-environment-configuration) genom att välja **Kopiera från befintlig miljö**. Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.

1. Ange följande information:
   - **Namn**: Namnet på miljön. Detta fält är redan ifyllt om du har kopierat en befintlig miljö, men du kan ändra det.
   - **Region**: Den region där tjänsten disribueras och förvaras
   - **Typ**: Välj om du vill skapa en produktions- eller sandbox-miljö. Sandbox-miljöer tillåter inte att schemalagda data uppdateras, och är avsedda för förimplementering och testning.
   
1. Alternativt kan du välja **Avancerade inställningar**:

   - **Spara alla data till**: anger var du vill lagra de utflödesdata som genererades från Customer Insights. Du har två alternativ: **Customer Insights-lagring** (en Azure Data Lake som hanteras av Customer Insights-teamet) och **Azure Data Lake Storage** (din egen Azure Data Lake Storage). Som standard är alternativet för Customer Insights-lagring markerat.

     > [!NOTE]
     > Genom att spara data i Azure Data Lake Storage godkänner du att data överförs till och lagras på rätt geografiska plats för Azure Storage-kontot, som kan skilja sig från varifrån data lagras i Dynamics 365 Customer Insights. [Läs mer i Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > För närvarande lagras inmatade entiteter från Power BI-dataflöden i det Microsoft Dataverse-hanterade Data Lake. 
     > 
     > Vi stöder endast Azure Data Lake Storage-konton från samma Azure-region som du valde när du skapade miljön. 
     > 
     > Vi stöder endast Azure Data Lake Storage.konton som har hierarkisk namnrymd aktiverad.


   - För alternativet Azure Data Lake Storage kan du välja mellan ett resursbaserat alternativ och ett prenumerationsbaserat autentiseringsalternativ. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md). Namnet på **Behållare** kan inte ändras och blir `customerinsights`.
   
   - Om du vill använda [färdiga modeller](predictions-overview.md#out-of-box-models) konfigurerar du datadelning med Microsoft Dataverse eller aktiverar datainmatning från lokala datakällor, tillhandahåller webbadressen (URL) för Microsoft Dataverse-miljön under **Konfigurera datadelning med Microsoft Dataverse samt aktiverar ytterligare funktioner**. Välj **Aktivera datadelning** för att dela Customer Insights-utdata med en Microsoft Dataverse-hanterad Data Lake.

     > [!NOTE]
     > - Datadelning med Microsoft Dataverse-hanterad Data Lake stöds för närvarande inte när du sparar alla data i din egen Azure Data Lake Storage.
     > - [Prediktion av värden som saknas i en entitet](predictions.md) stöds för närvarande inte när du aktiverar datadelning med Microsoft Dataverse-hanterad Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse.":::

   När systemprocesser som datainmatning har slutförts, skapar systemet motsvarande mappar på det angivna lagringskontot. Datafiler och model.json-filer skapas och läggs till i mappar baserat på processnamn.

   Om du skapar flera miljöer av Customer Insights och väljer att spara utdataentiteterna från dessa miljöer i ditt lagringskonto, kommer separata mappar att skapas för varje miljö med ci_<environmentid> i behållaren.

1. Välj **Skapa** för att konfigurera miljön. 

## <a name="configure-an-environment"></a>Konfigurera en miljö

Läs följande artiklar för att komma igång med att konfigurera Customer Insights. 

- [Lägg till fler användare och tilldela behörigheter](permissions.md).
- [Mata in dina datakällor](data-sources.md) och kör dem genom [samordningsprocessen för data](data-unification.md) för att får [enhetliga kundprofiler](customer-profiles.md).
- [Utöka de enhetliga kundprofilerna](enrichment-hub.md) eller [kör prediktiva modeller](predictions-overview.md).
- Create [segments](segments.md) to group customers and [measures](measures.md) review KPIs.
- Konfigurera [anslutningar](connections.md) och [exporter](export-destinations.md) för att bearbeta underuppsättningar av dina data i andra program.
