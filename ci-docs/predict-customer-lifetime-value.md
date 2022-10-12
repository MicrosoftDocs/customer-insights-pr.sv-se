---
title: Förutse kundens livstidsvärde
description: Förutse potentiell intäkt för aktiva kunder i framtiden.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610396"
---
# <a name="predict-customer-lifetime-value-clv"></a>Förutse kundens livstidsvärde

Förutse potentiellt värde (intäkt) som enskilda aktiva kunder ger verksamheten under en angiven tidsperiod i framtiden. Denna förutsägelse hjälper dig:

- Identifiera kunder med högt värde och bearbeta den här insikten.
- Skapa strategiska kundsegment utifrån deras potentiella värde för att köra anpassade kampanjer med riktad försäljning, marknadsföring och support.
- Vägleder produktutveckling genom att fokusera på funktioner som ökar kundvärdet.
- Optimera försäljnings- eller marknadsföringsstrategin och fördela budgeten på ett bättre sätt för att nå kunderna.
- Identifiera och uppmärksamma kunder med högt värde genom lojalitets- eller belöningsprogram.

Bestäm vad CLV betyder för din verksamhet. Vi stöder transaktionsbaserad förutsägelse av kundens livstidsvärde. Det förutsagda värdet för en kund baseras på transaktionshistoriken. Överväga att skapa flera modeller med olika indatainställningar och jämföra modellresultat för att se vilket modellscenario som passar dina affärsbehov bäst.

> [!TIP]
> Prova CLV-prediktion exempeldata: [CLV (kundens livstidsvärde) prediktion exempelguide](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md)
- Minst 100 kunder, helst fler än 10 000 kunder
- Kundidentifierare, en unik identifierare som matchar transaktioner till en enskild kund
- Minst ett års transaktionshistorik, helst två till tre år. Vilket minst två till tre transaktioner per kund-ID, helst över flera datum. Transaktionshistoriken måste innehålla:
  - **Transaktions-ID**: Unik identifierare för varje transaktion
  - **Transaktionsdatum**: Datum eller tidstämpel för varje transaktion
  - **Transaktionsbelopp**: Penningvärde (till exempel omsättning eller vinstmarginal) för varje transaktion
  - **Etikett tilldelad för returer**: Booleskt true/false värde som anger om transaktionen är en retur
  - **Produkt-ID**: Produkt-ID för produkten som är inblandad i transaktionen
- Data om kundaktiviteter:
  - **Primärnyckel**: En unik identifierare för en aktivitet
  - **Tidsstämpel**: Datum och tid för händelsen som identifierats av primärnyckeln
  - **Händelse (aktivitetsnamn)**: Namnet på händelsen som du vill använda
  - **Detaljer (belopp eller värde)**: Information om kundaktiviteten
- Ytterligare data som:
  - Webbaktiviteter: webbplatsbesökshistorik, e-posthistorik
  - Lojalitetsaktiviteter: insamlade lojalitetspoäng och inlösningshistorik
  - Kundtjänstlogg, servicesamtal, klagomål eller returhistorik
  - Information om kundprofil
- Mindre än 20 % saknade värden i obligatoriska fält

> [!NOTE]
> Det går bara att konfigurera en entitet för transaktionshistorik. Om det finns flera entiteter för inköp eller transaktion kan du kombinera dem i Power Query före datainmatningen.

## <a name="create-a-customer-lifetime-value-prediction"></a>Skapa en förutsägelse av kundens livstidsvärde

Välj **Spara utkast** om du vill prediktion utkast. Förutsägelseutkastet visas i fliken **Mina förutsägelser**.

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Kundens livstidsvärde**.

1. Välj **Komma igång**.

1. **Ge modellen** och **utdataentiteten ett namn** för att särskilja dem från andra modeller eller entiteter.

1. Välj **Nästa**.

### <a name="define-model-preferences"></a>Definiera modellinställningar

1. Ange en **tidsperiod för förutsägelse** för att definiera hur långt in i framtiden som du vill förutse kundens livstidsvärde. Som standard anges enheten som månader.

   > [!TIP]
   > För att korrekt kunna förutse kundens livstidsvärde för den tidsperiod du anger behöver du en jämförbar period av historiska data. Om du till exempel vill förutse CLV för de kommande 12 månaderna att du har minst 18–24 månaders historisk information.

1. Ange tidsramen inom vilken en kund måste ha minst en transaktion för att anses vara aktiv. Modellen förutser kundens livstid för **aktiva kunder**.
   - **Låt modellen beräkna inköpsintervall (rekommenderas)**: Modellen analyserar dina data och fastställer en tidsperiod utifrån tidigare köp.
   - **Ange intervall manuellt**: Tidsperiod för definitionen av en aktiv kund.

1. Definiera percentilen för **kunder med högt värde**.
    - **Modellberäkning (rekommenderas)**: Modellen använder 80/20-regel. Den procentandel kunder som under den historiska perioden har bidragit med 80 % av den kumulativa omsättningen för företaget betraktas som kunder med högt värde. Normalt bidrar mindre än 30–40 % av kunderna till en kumulativ omsättning på 80 %. Antalet kan dock variera beroende på ditt företag och din bransch.
    - **Procent av de mest aktiva kunderna**: Specifik percentil för en kund med högt värde. Ange till exempel **25** för att definiera kunder med högt värde som de översta 25 % av framtida betalande kunder.

    Om ditt företag definierar kunder med högt värde på ett annat sätt, [meddela oss, då vi gärna vill veta om det](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Välj **Nästa**.

### <a name="add-required-data"></a>Lägg till obligatoriska data

1. Välj **Lägg till data** för **Historik för kundtransaktioner**.

1. Välj typ av semantisk aktivitet **SalesOrder** eller **SalesOrderLine**, som innehåller transaktionshistorik. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var semantiskt mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Lägga till obligatoriska data för CLV-modell":::

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Lägg till fler aktiviteter eller välj **Näst**.

### <a name="add-optional-activity-data"></a>Lägg till valfri aktivitetsdata

För data som återspeglar viktiga kundinteraktioner (som webb-, kundtjänst- och händelseloggar) läggs sammanhang till i transaktionsposter. Fler mönster i dina kundaktivitetsdata kan förbättra precisionen för förutsägelserna.

1. Välj **Lägg data** under **Skapa bättre modellinsikter med ytterligare aktivitetsdata**.

1. Välj en aktivitetstyp som överensstämmer med den typ av kundaktivitet du lägger till. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Välj **Nästa**.

1. [Lägg till valfria kunddata](#add-optional-customer-data) eller välj **Nästa** och gå till [Ange uppdateringsschema](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Lägg till ytterligare kunddata

Välj bland de 18 vanliga kundprofilattribut som ska ingå som indata i modellen. De här attributen kan leda till mer anpassade, relevanta och användbara modellresultat för ärenden som används i företaget.

Exempel: Contoso Coffee vill rikta kundens livstidsvärde till kunder med ett anpassat erbjudande om lanseringen av den nya automaten. Contoso använder CLV-modellen och lägger till alla 18 kundprofilattribut för att se vilka faktorer som påverkar kundernas högsta värde. De tycker att kundens plats är den mest inflytelserika faktorn för dessa kunder.
Med den här informationen ordnar de en lokal händelse för lanseringen av maskinen och samarbetar med lokala leverantörer för personliga erbjudanden och en speciell upplevelse på händelse. Utan den här informationen kanske Contoso bara har skickat generiska marknadsföringsmeddelanden och missade möjligheten att anpassa för detta lokala segment av deras kunder med högt värde.

1. Välj **Lägg till data** under **Skapa ännu bättre modellinsikter med ytterligare kunddata**.

1. För **Entitet**, välj **Kund: Customer Insights** för att välja den enhetliga kundprofilen som mappas till kundattributdata. För **Kund-ID**, välj **System.Customer.CustomerId**.

1. Mappa fler fält om data är tillgängliga i dina enhetliga kundprofiler.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exempel på mappade fält för kundprofildata.":::

1. Välj **Spara**.

1. Välj **Nästa**.

### <a name="set-update-schedule"></a>Ange uppdateringsschema

1. Välj frekvens för att träna om din modell baserat på de senaste uppgifterna. Denna inställning är viktig för att uppdatera precisionen i förutsägelser när nya data hämtas till Customer Insights. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

### <a name="review-and-run-the-model-configuration"></a>Granska och köra modellkonfigurationen

Steget **Granska och kör** visar en sammanfattning av konfigurationen och ger en chans att göra ändringar innan du skapar förutsägelse.

1. Välj **Redigera** på något av stegen för att granska och göra eventuella ändringar.

1. Om du är nöjd med dina val, välj **Spara och kör** för att starta modellen. Välj **Klar**. Fliken **Mina prognoser** visas när prediktion skapas. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visa förutsägelsens resultat

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Mina förutsägelser**, välj den förutsägelse du vill visa.

Det finns tre primära dataområden på resultatsidan.

- **Prestanda för övningsmodell**: Betyget A, B eller C indikerar prestandan för förutsägelsen och kan hjälpa dig att fatta beslutet att använda de resultat som är lagrade i utdataentiteten.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Bild på rutan med information om modellpoäng tillsammans med betyg A.":::

  Customer Insights bedömer hur AI-modellen presterade för att förutsäga kunder med högt värde jämfört med en baslinjemodell.

  Betyg fastställs utifrån följande regler:
  - **A** när modellen korrekt förutsade minst 5 % fler kunder med högt värde jämfört med grundmodellen.
  - **B** när modellen korrekt förutsade mellan 0 och 5 % fler kunder med högt värde jämfört med grundmodellen.
  - **C** när modellen korrekt förutsade färre kunder med högt värde än grundmodellen.
  
  Välj [**Läs om den här poängen**](#learn-about-the-score) för att öppna **Modellbetyg** som visar ytterligare detaljer om AI-modellens prestanda och grundmodellen. Det hjälper dig bättre förstå de underliggande måtten för modellprestandan och hur det slutliga modellprestandabetyget sattes. Grundmodellen bygger på en icke-AI-baserad metod för beräkning av kundens livstidsvärde, främst baserat på tidigare köp som gjorts av kunder.

- **Kundernas värde efter percentil**: Kunder med låg eller högt värde visas i ett diagram. Håll markör över staplarna i histogrammet kan du se antalet kunder i varje grupp och det genomsnittliga kundlivstidsvärdet för gruppen. Alternativ, [skapa kundsegment](prediction-based-segment.md) utifrån förutsägelser av kundens livstidsvärde.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Kundvärde per percentil för CLV-modell":::

- **Mest inflytelserika faktorer**: Olika faktorer beaktas när du skapar förutsägelser av kundens livstidsvärde baserat på indata till AI-modellen. Betydelsen för var och en av faktorerna beräknas för de ansamlade förutsägelser som skapas av en modell. Använda dessa faktorer för att validera resultatet av en förutsägelse. Dessa faktorer ger också en bättre inblick i de mest inflytelserika faktorerna som bidrog till förutsägelsen av kundens livtidsvärde för alla dina kunder.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Faktorer som påverkar för CLV-modell":::

### <a name="learn-about-the-score"></a>Läs om den här poängen

Standardformeln som används för att beräkna kundens livstidsvärde enligt grundmodellen:

 _**Kundens livstidsvärde för varje kund** = Genomsnittligt månatligt köp som gjorts av kunden i det aktiva kundfönstret * Antal månader i perioden för förutsägelse av kundens livstidsvärde * Övergripande kvarhållning av alla kunder_

AI-modellen jämförs med grundmodellen utifrån två prestandamått.
  
- **Andel lyckade försök med att förutse kunder med högt värde**

  Se skillnaden mellan att förutse kunder med högt värde med AI-modellen jämfört med grundmodellen. En framgångsfrekvens på 84 % innebär till exempel att av alla kunder med högt värde i utbildningsdata kunde AI-modellen samla in 84 %. Sedan jämför vi den här framgångsfrekvensen med grundmodellens framgångsfrekvens och rapporterar den relativa förändringen. Det här värdet används för att tilldela modellen ett betyg.

- **Felmått**

  Granska modellens övergripande prestanda när det gäller fel vid förutsägelse av framtida värden. Vi använder det övergripande RMSE-måttet (Root Mean Squared Error) för att utvärdera felet. RMSE är ett standardiserat sätt att mäta fel i en modell när det gäller att förutse kvantitativa data. AI-modellens RMSE jämförs med RMSE för grundmodellen och den relativa skillnaden rapporteras.

AI-modellen prioriterar korrekt rangordning av kunder enligt det värde de ger verksamheten. Endast framgångsfrekvensen för förutsägelse av kunder med högt värde används för att få det slutliga modellbetyget. RMSE-måttet är känsligt för extremvärden. Om det finns en mindre procentandel kunder med extremt stora köpvärden kanske det övergripande RMSE-måttet inte ger en fullständig bild av modellens prestanda.

[!INCLUDE [footer-include](includes/footer-banner.md)]
