---
title: Prediktion för omsättning av prenumeration (innehåller video)
description: Förutsäg huruvida en kund löper risk att inte längre kunna använda företagets prenumerationsprodukter eller -tjänster.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610258"
---
# <a name="predict-subscription-churn"></a>Förutsäga prenumerationsomsättning

Förutsäg huruvida en kund löper risk att inte längre kunna använda företagets prenumerationsprodukter eller -tjänster. Prenumerationsdata omfattar aktiva och inaktiva prenumerationer för varje kund så det finns flera poster per kund-ID.

Du måste ha affärskunskaper för att förstå vad omsättningen innebär för företaget. Vi har stöd för tidsbaserade omsättningsdefinitioner, vilket innebär att en kund anses ha omsatt en tidsperiod när dennes prenumeration har avslutats.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Testa förutsägelse av prenumerationsomsättning med exempeldata: [Guide för förutsägelse av prenumerationsomsättning](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md).
- Minst 10 kundprofiler, helst mer än 1 000 unika kunder.
- Kundidentifierare: Unik identifierare som matchar prenumerationer till en kund
- Prenumerationsdata för minst dubbla det valda tidsfönstret. Helst två till tre års prenumerationsdata. Prenumerationshistoriken måste innehålla:
  - **Prenumerations-ID:** En unik identifierare för en prenumeration.
  - **Slutdatum för prenumeration:** Det datum då prenumerationen förfaller för kunden.
  - **Startdatum för prenumeration:** Det datum då prenumerationen börjar för kunden.
  - **Transaktionsdatum:** Det datum då en prenumeration ändras. Till exempel en kund som köper eller avbryter en prenumeration.
  - **Gäller det ett återkommande abonnemang:** Ett booleskt sant/falskt-fält (true/false) som avgör om prenumerationen ska förnyas med samma prenumerations-ID utan kundåtgärd.
  - **Upprepningsfrekvens (i månader):** För återkommande prenumerationer är detta den månad då prenumerationen förnyas. Ett årligt abonnemang som automatiskt förnyas varje år för en kund har exempelvis värdet 12.
  - **Abonnemangsbelopp**: Det valutabelopp som en kund betalar för att förnya prenumerationen. Detta kan underlätta identifiering av mönster för olika prenumerationsnivåer.
- Du behöver minst två aktivitetsposter för 50 % av de kunder som du vill beräkna omsättning för. Kundaktiviteter måste omfatta:
  - **Primärnyckel:** En unik identifierare för en aktivitet. Exempelvis ett besök på en webbplats eller en användningspost som visar att kunden sett ett avsnitt av en TV-serie.
  - **Tidsstämpel:** Datum och tid för händelsen som identifierats av primärnyckeln.
  - **Händelse:** Namnet på den händelse som du vill använda. Ett fält med namnet "UserAction" i en videotjänst för direktuppspelning kan t.ex. ha värdet "Visat".
  - **Detaljer:** Detaljerad information om händelsen. Ett fält med namnet "ShowTitle" i en videotjänst för direktuppspelning kan t.ex. ha värdet för en video som en kund har tittat på.
- Mindre än 20 % av de värden som saknas i entitetens datafält

## <a name="create-a-subscription-churn-prediction"></a>Skapa en förutsägelse om abonnemangsomsättning

Välj **Spara utkast** om du vill prediktion utkast. Förutsägelseutkastet visas i fliken **Mina förutsägelser**.

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Kundomsättningsmodell**.

1. Välj **prenumeration** för typen av omsättning och **Kom igång**.

1. **Ge modellen** och **utdataentiteten ett namn** för att särskilja dem från andra modeller eller entiteter.

1. Välj **Nästa**.

### <a name="define-customer-churn"></a>Definiera kundomsättning

1. Ange antalet **Dagar sedan prenumerationen avslutades** som företaget betraktar en kund som varandes i omsättningstillstånd. Denna period används vanligtvis för affärsaktiviteter som erbjudanden och andra marknadsföringsåtgärder som försöker förhindra att kunden går förlorad.

1. Ange antal **dagar i framtiden att förutsäga kundomsättning för**. Du kan till exempel förutse risken för omsättning av dina kunder under de kommande 90 dagarna för att anpassa dina marknadsföringsinsatser för att behålla kunder. Om risken ökar för längre eller kortare tidsperioder kan det bli svårare att ta sig an faktorerna i riskprofilen, beroende på företagets specifika behov.

1. Välj **Nästa**.

### <a name="add-required-data"></a>Lägg till obligatoriska data

1. Välj **Lägg till data** för **Prenumerationshistorik**.

1. Välj typ av semantisk aktivitet **prenumeration** som innehåller den nödvändiga informationen om prenumerationshistorik. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var semantiskt mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Lägga till obligatoriska data för modell för prenumerationsomsättning":::

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Välj **Lägg till data** för **Kundaktiviteter**.

1. Välj den typ av aktivitet av typen för inaktivitet som innehåller information om kundaktiviteten. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var semantiskt mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Lägg till fler aktiviteter eller välj **Näst**.

### <a name="set-update-schedule"></a>Ange uppdateringsschema

1. Välj frekvens för att träna om modellen. Den här inställningen är viktig för att uppdatera precisionen för förutsättningar eftersom nya data förs in i Customer Insights. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

### <a name="review-and-run-the-model-configuration"></a>Granska och köra modellkonfigurationen

Steget **Granska och kör** visar en sammanfattning av konfigurationen och ger en chans att göra ändringar innan du skapar förutsägelse.

1. Välj **Redigera** på något av stegen för att granska och göra eventuella ändringar.

1. Om du är nöjd med dina val, välj **Spara och kör** för att starta modellen. Välj **Klar**. Fliken **Mina prognoser** visas när prediktion skapas. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visa förutsägelsens resultat

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Mina förutsägelser**, välj den förutsägelse du vill visa.

Det finns tre primära dataområden på resultatsidan:

- **Prestanda för övningsmodell**: Betyget A, B eller C indikerar prestandan för förutsägelsen och kan hjälpa dig att fatta beslutet att använda de resultat som är lagrade i utdataentiteten.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Bild på rutan med information om modellpoäng tillsammans med betyg A.":::

  Betyg fastställs utifrån följande regler:
  - **A** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är större än den historiska genomsnittliga omsättningen med minst 10 %.
  - **B** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är större än den historiska genomsnittliga omsättningen med minst 10 %.
  - **C** när modellen noggrant förutsäger mindre 50 % av det totala antalet prediktioner, eller när procenten av exakta prediktioner för kunder som har blivit mindre än den historiska genomsnittliga omsättningen.
  
- **Sannolikhet för omsättning (antal kunder)**: Kundgrupper utifrån deras förutsedda omsättningsrisk. Alternativt kan du [skapa kundsegment](prediction-based-segment.md) med hög omsättningsrisk. Sådana segment hjälper dig att förstå var avgränsarna bör finnas för segmentmedlemskap.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graf som visar distributionen av omsättningsresultat uppdelad i intervall från 0-100 %":::

- **Faktorer med störst påverkan:** Det finns många faktorer som bör beaktas när du skapar en förutsägelse. Var och en av faktorerna har en betydelse beräknad för de aggregerade förutsägelserna som skapas av en modell. Använda dessa faktorer för att validera resultatet av en förutsägelse. Du kan också använda den här informationen senare om du vill [skapa segment](.//prediction-based-segment.md) som kan påverka omsättningsrisken för en kund.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lista som visar tongivande faktorer och deras betydelse för att förutsäga omsättningsresultatet.":::

> [!NOTE]
> I utdataentiteten för denna modell visar *ChurnScore* den förutsagda sannolikheten för omsättning och *IsChurn* är en binär etikett baserad på *ChurnScore* med 0,5 tröskel. Om standardtröskeln inte fungerar för ditt scenario [skapar du ett nytt segment](segments.md) med det önskade tröskelvärdet. För att visa omsättningspoängen, gå till **Data** > **Entiteter** och visa datafliken för den utdataenhet som du definierade för den här modellen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
