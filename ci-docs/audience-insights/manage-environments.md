---
title: Skapa och hantera miljöer
description: Läs om hur du registrerar dig för tjänsten och hur du hanterar miljöer.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683495"
---
# <a name="manage-environments"></a>Hantera miljöer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Växla miljö

Välj kontrollen **miljö** i det övre högra hörnet av sidan om du vill ändra miljöer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skärmbild av kontrollen för att växla miljöer.":::

Administratörer kan [skapa](get-started-paid.md) och hantera miljöer.

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
   > - [Förutsägelse rörande saknade värden i en entitet](predictions.md) och inbäddade PowerBI-rapporter i målgruppsinsikter (om detta har aktiverats i din miljö) stöds inte för närvarande när du aktiverar datadelning med en Microsoft Dataverse-hanterad datasjö.

   När du har aktiverat datadelning med Microsoft Dataverse startas en fullständig uppdatering av dina datakällor och andra processer. Om processer körs för tillfället visas inte alternativet att aktivera datadelning med Microsoft Dataverse. Vänta tills processerna har slutförts eller avbrutits om du vill aktivera datadelning. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse.":::
   
   När du kör processer, till exempel datainmatning eller skapande av segment, kommer motsvarande mappar att skapas i det lagringskonto du angav ovan. Datafiler och model.json-filer skapas och läggs till i respektive undermappar, beroende på vilken process du kör.

## <a name="copy-the-environment-configuration"></a>Kopiera miljökonfigurationen

När du skapar en ny miljö kan du välja att kopiera konfigurationen från en befintlig miljö. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skärmbild av inställningsalternativen i miljöinställningarna.":::

Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.

Följande konfigurationsinställningar kan kopieras:

- Inmatade/importerade datakällor
- Dataföreningskonfiguration (mappning, matchning, sammanslagning)
- Segments
- Mått
- Relationer
- Aktiviteter
- Sök och filtrera index
- Exportmål
- Schemalagd uppdatering
- Berikningar
- Modellhantering
- Rolltilldelningar

Följande data kopieras *inte*:

- Kundprofiler.
- Autentiseringsuppgifter för datakälla. Du måste ange autentiseringsuppgifterna för varje datakälla och uppdatera datakällorna manuellt.
- Datakällor från mappen Common Data Model och Dataverse-hanterad Data Lake. Du måste skapa dessa datakällor manuellt med samma namn som i källmiljön.

När du kopierar en miljö visas ett bekräftelsemeddelande om att den nya miljön har skapats. Välj **gå till datakällor** om du vill visa listan över datakällor.

I alla data källor visas statusen **Autentiseringsuppgifter krävs**. Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista över datakällor som kopierats och som behöver autentisering.":::

När datakällorna har uppdaterats går du till **Data** > **Förena**. Här hittar du inställningar från källmiljön. Redigera dem efter behov eller välj **kör** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.

När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.

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
