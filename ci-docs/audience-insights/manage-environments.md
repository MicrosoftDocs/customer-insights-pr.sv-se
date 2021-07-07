---
title: Skapa och hantera miljöer
description: Läs om hur du registrerar dig för tjänsten och hur du hanterar miljöer.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304902"
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

> [!NOTE]
> Organisationer kan skapa *två* miljöer för varje Customer Insights-licens. Om din organisation köper mer än en gång licens [kontakta vårt supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) för att öka antalet tillgängliga miljöer. Mer information om kapacitet och kapacitet för tillägg finns i [Dynamics 365 licensguiden](https://go.microsoft.com/fwlink/?LinkId=866544).

För att skapa en miljö i:

1. Välj **Miljö**-väljaren i apphuvudet.

1. Välj **Nytt**.

   > [!div class="mx-imgBorder"]
   > ![Miljöinställningar.](media/environment-settings-dialog.png)

1. I dialogrutan **Skapa en miljö** väljer du **Ny miljö**.

   Om du vill [Kopiera data från den aktuella miljön](#considerations-for-copy-configuration-preview) väljer du **Kopiera från befintlig miljö**. Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.

1. Ange följande information:
   - **Namn**: Namnet på miljön. Detta fält är redan ifyllt om du har kopierat en befintlig miljö, men du kan ändra det.
   - **Typ**: Välj om du vill skapa en produktions- eller sandbox-miljö.
   - **Region**: Den region där tjänsten disribueras och förvaras
   
1. Alternativt kan du välja **Avancerade inställningar**:

   - **Spara alla data till**: anger var du vill lagra de utflödesdata som genererades från Customer Insights. Du har två alternativ: **Customer Insights-lagring** (en Azure Data Lake som hanteras av Customer Insights-teamet) och **Azure Data Lake Storage** (din egen Azure Data Lake Storage). Som standard är alternativet för Customer Insights-lagring markerat.

     > [!NOTE]
     > Genom att spara data i Azure Data Lake Storage godkänner du att data överförs till och lagras på rätt geografiska plats för Azure Storage-kontot, som kan skilja sig från varifrån data lagras i Dynamics 365 Customer Insights. [Läs mer i Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > För närvarande lagras inmatad entiteter alltid i Customer Insights hanterade Data Lake. 
     > 
     > Vi stöder endast Azure Data Lake Storage-konton från samma Azure-region som du valde när du skapade miljön. 
     > 
     > Vi stöder endast Azure Data Lake Storage.konton som har hierarkisk namnrymd aktiverad.


   - För alternativet Azure Data Lake Storage kan du välja mellan ett resursbaserat alternativ och ett prenumerationsbaserat autentiseringsalternativ. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md). Namnet på **Behållare** kan inte ändras och blir `customerinsights`.
   
   - Om du vill använda [prediktioner](predictions.md), konfigurerar du datadelning med Microsoft Dataverse eller aktiverar datainmatning från lokala datakällor tillhandahåller du Microsoft Dataverse miljö-URL under **Konfigurera datadelning med Microsoft Dataverse och aktiverar ytterligare funktioner**. Välj **Aktivera datadelning** för att dela Customer Insights-utdata med en Microsoft Dataverse-hanterad Data Lake.

     > [!NOTE]
     > - Datadelning med Microsoft Dataverse-hanterad Data Lake stöds för närvarande inte när du sparar alla data i din egen Azure Data Lake Storage.
     > - [Förutsägelse av saknade värden i en entitet](predictions.md) stöds för närvarande inte när du aktiverar datadelning med Microsoft Dataverse-hanterad Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   När du kör processer, till exempel datainmatning eller skapande av segment, kommer motsvarande mappar att skapas i det lagringskonto du angav ovan. Datafiler och model.json-filer skapas och läggs till i mappar, beroende på processnamnet.

   Om du skapar flera miljöer av Customer Insights och väljer att spara utdataentiteterna från dessa miljöer i ditt lagringskonto, kommer separata mappar att skapas för varje miljö med ci_<environmentid> i behållaren.

### <a name="considerations-for-copy-configuration-preview"></a>Att tänka på vid kopieringskonfiguration (förhandsgranskning)

Följande konfigurationsinställningar kan kopieras:

- Funktionskonfigurationer
- Inmatade/importerade datakällor
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
- Datakällor från mappen Common Data Model och Dataverse-hanterad Data Lake. Du måste skapa dessa datakällor manuellt med samma namn som i källmiljön.

När du kopierar en miljö visas ett bekräftelsemeddelande om att den nya miljön har skapats. Välj **gå till datakällor** om du vill visa listan över datakällor.

I alla data källor visas statusen **Autentiseringsuppgifter krävs**. Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem.

> [!div class="mx-imgBorder"]
> ![Datakällor som kopierats.](media/data-sources-copied.png)

När datakällorna har uppdaterats går du till **Data** > **Förena**. Här hittar du inställningar från källmiljön. Redigera dem efter behov eller välj **kör** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.

När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.

## <a name="edit-an-existing-environment"></a>Redigera en befintlig miljö

Du kan redigera vissa av detaljerna i befintliga miljöer.

1.  Välj **Miljö**-väljaren i apphuvudet.

2.  Välj ikonen **Redigera**.

3. I rutan **Redigera miljö** kan du uppdatera miljöns **visningsnamn**, men du kan inte ändra **Region** eller **Typ**.

4. Om en miljö har konfigurerats för att lagra data i Azure Data Lake Storage kan du uppdatera **kontonyckeln**. Du kan emellertid inte ändra **Kontonam** eller namnet för **Behållare**.

5. Alternativt kan du uppdatera från en kontonyckelbaserad anslutning till en resursbaserad eller prenumerationsbaserad anslutning. När du har uppgraderat kan du inte återgå till kontonyckeln efter uppdateringen. Mer information finns i [Ansluta målgruppsinsikter till ett Azure Data Lake Storage Gen2-konto med Azure-tjänstens huvudkonto](connect-service-principal.md). Du kan inte ändra informationen **Behållare** när anslutningen uppdateras.

6. Du kan även ange en Microsoft Dataverse miljö-URL under **Konfigurera datadelning med Microsoft Dataverse och aktivera ytterligare funktioner**. Dessa funktioner för datadelning med program och lösningar som bygger på Microsoft Dataverse, datainsamling som lokala datakällor eller användning av [prediktioner](predictions.md). Välj **Aktivera datadelning** för att dela Customer Insights-utdata med en Microsoft Dataverse-hanterad Data Lake.

   > [!NOTE]
   > - Datadelning med Microsoft Dataverse-hanterad Data Lake stöds för närvarande inte när du sparar alla data i din egen Azure Data Lake Storage.
   > - [Prediktion av värden som saknas i en entitet](predictions.md) stöds för närvarande inte när du aktiverar datadelning med Microsoft Dataverse-hanterad Data Lake.

   När du har aktiverat datadelning med Microsoft Dataverse startas en fullständig uppdatering av dina datakällor och andra processer. Om processer körs för tillfället visas inte alternativet att aktivera datadelning med Microsoft Dataverse. Vänta tills processerna har slutförts eller avbrutits om du vill aktivera datadelning. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse.":::
   
   När du kör processer, till exempel datainmatning eller skapande av segment, kommer motsvarande mappar att skapas i det lagringskonto du angav ovan. Datafiler och model.json-filer skapas och läggs till i respektive undermappar, beroende på vilken process du kör.

## <a name="reset-an-existing-environment"></a>Återställa en befintlig miljö

Som en administratör kan du återställa en miljö till ett tomt tillstånd om du vill ta bort alla konfigurationer och ta bort de inmatade data.

1.  Välj **Miljö**-väljaren i apphuvudet. 

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Återställ**. 

4.  Bekräfta borttagningen genom att ange miljönamnet och välj **Återställ**.

## <a name="delete-an-existing-environment"></a>Ta bort en befintlig miljö

Som en administratör kan du ta bort en miljö som du administrerar.

1.  Välj **Miljö**-väljaren i apphuvudet.

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Ta bort**. 

4.  Bekräfta borttagningen genom att ange miljö namnet och välja **ta bort**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
