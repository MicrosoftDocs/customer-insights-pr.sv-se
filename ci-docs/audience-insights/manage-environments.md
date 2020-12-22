---
title: Skapa och hantera miljöer
description: Läs om hur du registrerar dig för tjänsten och hur du hanterar miljöer.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644155"
---
# <a name="manage-environments"></a>Hantera miljöer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

I den här artikeln beskriver vi hur du skapar en ny organisation och hur du etablerar en miljö.

## <a name="sign-up-and-create-an-organization"></a>Registrera dig och skapa en organisation

1. Gå till [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) webbplatsen.

2. Välj **Komma igång**.

3. Välj önskat inloggningsscenario och välj motsvarande länk.

4. Godkänn villkoren och välj **Fortsätt** när du vill börja skapa organisationen.

5. När miljön har skapats omdirigeras du till [Customer Insights](https://home.ci.ai.dynamics.com).

6. Använd demonstrationsmiljön för att utforska appen eller skapa en ny miljö genom att följa stegen i nästa avsnitt.

7. När du har angett miljöinställningarna väljer du **skapa**.

8. Du kommer att vara inloggad efter att miljön har skapats.

## <a name="create-an-environment-in-an-existing-organization"></a>Skapa en miljö i en befintlig organisation

En ny miljö kan skapas på två olika sätt. Du kan antingen ange en helt ny konfiguration, eller också kan du kopiera vissa konfigurationsinställningar från en befintlig miljö.

För att skapa en miljö i:

1. Välj symbolen **inställningar** i programmets huvud.

1. Välj **Ny miljö**.

   > [!div class="mx-imgBorder"]
   > ![Miljöinställningar](media/environment-settings-dialog.png)

1. I dialogrutan **Skapa ny miljö** välj **Ny miljö**.

   Om du vill [Kopiera data från den aktuella miljön](#additional-considerations-for-copy-configuration-preview) väljer du **Kopiera från befintlig miljö**. Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.

1. Ange följande information:
   - **Namn**: Namnet på miljön. Detta fält är redan ifyllt om du har kopierat en befintlig miljö, men du kan ändra det.
   - **Region**: Den region där tjänsten disribueras och förvaras
   - **Typ**: Välj om du vill skapa en produktions- eller sandbox-miljö.

2. Alternativt kan du välja **Avancerade inställningar**:

   - **Spara alla data till**: anger var du vill lagra de utflödesdata som genererades från Customer Insights. Du har två alternativ: **Customer Insights-lagring** (en Azure Data Lake som hanteras av Customer Insights-teamet) och **Azure Data Lake Storage Gen2** (din egen Azure Data Lake Storage). Som standard är alternativet för Customer Insights-lagring markerat.

   > [!NOTE]
   > Genom att spara data i Azure Data Lake Storage godkänner du att data överförs till och lagras på rätt geografiska plats för Azure Storage-kontot, som kan skilja sig från varifrån data lagras i Dynamics 365 Customer Insights. [Läs mer i Microsoft Trust Center.](https://www.microsoft.com/trust-center)
   >
   > För närvarande lagras hämtade entiteter alltid i Customer Insights hanterade Data Lake.
   > Vi stöder endast Azure Data Lake Gen2-lagringskonton från samma Azure-region som du valde när du skapade miljön.
   > Vi stöder endast Azure Data Lake Gen2 hierarkiska namnrymd (HNS) lagringskonton.

   - För alternativet Azure Data Lake Storage Gen2 kan du välja mellan ett resursbaserat alternativ och ett prenumerationsbaserat alternativ för autentisering. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md). Namnet på **behållare** går inte att ändra, utan kommer att vara "customerinsights".
   
   - Om du vill använda [förutsägelser](predictions.md) anger du Common Data Service-instansens URL i fältet **Serveradress** under **Använd förutsägelser**.

   När du kör processer, till exempel datainmatning eller skapande av segment, kommer motsvarande mappar att skapas i det lagringskonto du angav ovan. Datafiler och model.json-filer skapas och läggs till i motsvarande undermappar baserat på den process du kör.

   Om du skapar flera miljöer av Customer Insights och väljer att spara utdataentiteterna från dessa miljöer i ditt lagringskonto, kommer separata mappar att skapas för varje miljö med ci_<environmentid> i behållaren.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Ytterligare överväganden för kopieringskonfiguration (förhandsversion)

Följande konfigurationsinställningar kan kopieras:

- Funktionskonfigurationer
- Insamlade/importerade datakällor
- Dataföreningskonfiguration (mappning, matchning, sammanslagning)
- Segments
- Mått
- Relationer
- Aktiviteter
- Sök och filtrera index
- Exportmål
- Schemalagd uppdatering
- Berikning
- Modellhantering
- Rolltilldelningar

Följande konfigurationsinställningar kan *inte* kopieras:

- Kundprofiler.
- Autentiseringsuppgifter för datakälla. Du måste ange autentiseringsuppgifterna för varje datakälla och uppdatera datakällorna manuellt.
- Datakällor från Common Data Model-mappen och den Common Data Service-hanterade sjön. Du måste skapa dessa datakällor manuellt med samma namn som i källmiljön.

När du kopierar en miljö visas ett bekräftelsemeddelande om att den nya miljön har skapats. Välj **gå till datakällor** om du vill visa listan över datakällor.

I alla data källor visas statusen **Autentiseringsuppgifter krävs**. Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem.

> [!div class="mx-imgBorder"]
> ![Datakällor som kopierats](media/data-sources-copied.png)

När datakällorna har uppdaterats går du till **Data** > **Förena**. Här hittar du inställningar från källmiljön. Redigera dem efter behov eller välj **kör** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.

När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.

## <a name="edit-an-existing-environment"></a>Redigera en befintlig miljö

Du kan redigera vissa av detaljerna i befintliga miljöer.

1. Gå till **Admin** > **System** > **Om**.

2. Välj **Redigera**.

3. Du kan uppdatera miljöns **Visningsnamn**, men du kan inte ändra **Region** eller **Typ**.

4. Om en miljö är konfigurerad att lagra data i Azure Data Lake Storage Gen2 kan du uppdatera **kontonyckeln**. Du kan emellertid inte ändra **Kontonam** eller namnet för **Behållare**.

5. Alternativt kan du uppdatera från en kontonyckelbaserad anslutning till en resursbaserad eller prenumerationsbaserad anslutning. När du har uppgraderat kan du inte återgå till kontonyckeln efter uppdateringen. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md). Du kan inte ändra informationen **Behållare** när anslutningen uppdateras.

## <a name="reset-an-existing-environment"></a>Återställa en befintlig miljö

Du kan återställa en miljö till ett tomt tillstånd om du vill ta bort alla konfigurationer och ta bort de inmatade data.

1.  Gå till **Admin** > **System** > **Om**.

2.  Välj **Återställ**. 

3.  Bekräfta borttagningen genom att ange miljönamnet och välj **Återställ**.


## <a name="delete-an-existing-environment"></a>Ta bort en befintlig miljö

1. Gå till **Admin** > **System** > **Om**.

1. Välj **Ta bort**.

1. Bekräfta borttagningen genom att ange miljö namnet och välja **ta bort**.
