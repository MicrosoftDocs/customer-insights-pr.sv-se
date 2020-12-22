---
title: Omsättningsprediktion för abonnemang
description: Förutsäg huruvida en kund löper risk att inte längre kunna använda företagets prenumerationsprodukter eller -tjänster.
ms.date: 08/19/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 03178fc1bfe611b1b0ced08bbbef876035875825
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643750"
---
# <a name="subscription-churn-prediction-preview"></a>Förutsäga abonnemangsomsättning (förhandsversion)

Förutsägelse av abonnemangsomsättning hjälper dig att förutsäga huruvida en kund löper risk att inte längre kunna använda företagets prenumerationsprodukter eller -tjänster. Du kan skapa nya förutsägelser om abonnemangsomsättning via sidan **Intelligens** > **Förutsägelser**. Välj **Mina förutsägelser** för att se andra förutsägelser som du har skapat.

> [!TIP]
> Testa självstudierna för en förutsägelse av prenumerationsomsättning med exempeldata: [Guide för förutsägelse av prenumerationsomsättning](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md).
- Affärskunskaper för att förstå vad omsättningen innebär för företaget. Vi har stöd för tidsbaserade omsättningsdefinitioner, vilket innebär att en kund anses ha omsatt en tidsperiod när dennes prenumeration har avslutats.
- Information om dina prenumerationer och deras historik:
    - Prenumerationsidentifierare för att urskilja prenumerationer.
    - Kundidentifierare för att matcha prenumerationer mot dina kunder.
    - Datum för prenumerationshändelser som definierar startdatum, slutdatum och datum då prenumerationshändelserna inträffade.
    - Prenumerationsinformation för att definiera om det är en återkommande prenumeration och hur ofta denna förnyas.
    - Det semantiska dataschemat för prenumerationer kräver följande information:
        - **Prenumerations-ID:** En unik identifierare för en prenumeration.
        - **Slutdatum för prenumeration:** Det datum då prenumerationen förfaller för kunden.
        - **Startdatum för prenumeration:** Det datum då prenumerationen börjar för kunden.
        - **Transaktionsdatum:** Det datum då en prenumeration ändras. Till exempel en kund som köper eller avbryter en prenumeration.
        - **Gäller det ett återkommande abonnemang:** Ett booleskt sant/falskt-fält (true/false) som avgör om prenumerationen ska förnyas med samma prenumerations-ID utan kundåtgärd
        - **Upprepningsfrekvens (i månader):** För återkommande prenumerationer är detta den period som prenumerationen förnyas för. Den anges i månader. Ett årligt abonnemang som automatiskt förnyas varje år för en kund har exempelvis värdet 12.
        - (Valfritt) **Abonnemangsbelopp:** Det valutabelopp som en kund betalar för att förnya prenumerationen. Detta kan underlätta identifiering av mönster för olika prenumerationsnivåer.
- Data om kundaktiviteter:
    - Aktivitetsidentifierare för att särskilja aktiviteter av samma typ.
    - Kundidentifierare för att mappa aktiviteter mot dina kunder.
    - Aktivitetsinformation som innehåller namnet och datumet för aktiviteten.
    - Det semantiska dataschemat för kundaktiviteter omfattar:
        - **Primärnyckel:** En unik identifierare för en aktivitet. Exempelvis ett besök på en webbplats eller en användningspost som visar att kunden sett ett avsnitt av en TV-serie.
        - **Tidsstämpel:** Datum och tid för händelsen som identifierats av primärnyckeln.
        - **Händelse:** Namnet på den händelse som du vill använda. Ett fält med namnet "UserAction" i en videotjänst för direktuppspelning kan t.ex. ha värdet "Visat".
        - **Detaljer:** Detaljerad information om händelsen. Ett fält med namnet "ShowTitle" i en videotjänst för direktuppspelning kan t.ex. ha värdet för en video som en kund har tittat på.
   > [!NOTE]
   > Du behöver minst två aktivitetsposter för 50 % av de kunder som du vill beräkna omsättning för.

## <a name="create-a-subscription-churn-prediction"></a>Skapa en förutsägelse om abonnemangsomsättning

1. I målgruppsinsikter går du till **Intelligens** > **Förutsägelser**.
1. Välj ikonen **Modell för prenumerationsomsättning (förhandsversion)** och välj sedan **Använd denna modell**.
   > [!div class="mx-imgBorder"]
   > ![Ikon för prenumerationsomsättningsmodell med knappen Använd denna modell](media/subscription-churn-usethismodel.PNG "Ikon för prenumerationsomsättningsmodell med knappen Använd denna modell")

### <a name="name-model"></a>Namnge modell

1. Ange ett namn för modellen om du vill särskilja den från andra modeller.
1. Ange ett namn för entiteten för utdata med endast bokstäver och siffror utan blanksteg. Detta är det namn som modellentiteten kommer att använda. Välj sedan **Nästa**.

### <a name="define-customer-churn"></a>Definiera kundomsättning

1. Ange antalet **Dagar sedan prenumerationen avslutades** som företaget betraktar en kund som varandes i omsättningstillstånd. Denna period används vanligtvis för affärsaktiviteter som erbjudanden och andra marknadsföringsåtgärder som försöker förhindra att kunden går förlorad.
1. Ange antalet **dagar för att undersöka framtid för att förutse omsättningen** och ställ in ett fönster för att förutse omsättningen för. Om du till exempel vill förutsäga risken för omsättning för dina kunder under de kommande 90 dagarna för att anpassa sig efter dina marknadsföringsåtgärder. Om du förväntar omsättningsrisker under längre eller kortare tidsperioder kan det bli svårare att åtgärda faktorerna i din omsättningsprofil, men det är mycket beroende av dina specifika affärskrav. Fortsätt **Nästa** för att fortsätta
   >[!TIP]
   > Du kan välja att **Spara och stänga** när som helst när du vill spara förutsägelsen som ett utkast. Du hittar utkastförutsägelsen i fliken **Mina förutsägelser** om du vill fortsätta med den.

### <a name="add-required-data"></a>Lägg till obligatoriska data

1. Välj **Lägg till data** för **Prenumerationshistorik** och välj den entitet som tillhandahåller prenumerationshistoriken enligt beskrivningen bland [kraven](#prerequisites).
1. Om fälten nedan inte är ifyllda konfigurerar du relationen från entiteten för prenumerationshistorik till entiteten Kund.
    1. Välj **entiteten Prenumerationshistorik**.
    1. Välj det **fält** som identifierar kunden i entiteten för prenumerationshistorik. Detta måste relatera till primärt kund-ID för entiteten Kund.
    1. Välj den **Kundentitet** som matchar den primära kundentiteten.
    1. Ange ett namn som beskriver relationen.
       > [!div class="mx-imgBorder"]
       > ![Sidan för prenumerationshistorik som anger skapandet av en relation till en kund](media/subscription-churn-subscriptionhistoryrelationship.PNG "Sidan för prenumerationshistorik som anger skapandet av en relation till en kund")
1. Välj **Nästa**.
1. Mappa semantikfälten till attribut i entiteten för prenumerationshistorik och välj **Spara**. För beskrivningar av fälten, läs igenom [kraven](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Sidan för prenumerationshistorik som visar semantiska attribut som mappats till fält i den valda entiteten för prenumerationshistorik](media/subscription-churn-subscriptionhistorymapping.PNG "Sidan för prenumerationshistorik som visar semantiska attribut som mappats till fält i den valda entiteten för prenumerationshistorik")
1. Välj **Lägg till data** för **Kundaktiviteter** och välj den entitet som tillhandahåller information om kundaktivitet enligt beskrivet bland kraven.
1. Välj en aktivitetstyp som överensstämmer med den typ av kundaktivitet som du konfigurerar.  Välj **Skapa nytt** och ange ett namn om du inte ser något alternativ som överensstämmer med den aktivitetstyp du behöver.
1. Du måste konfigurera relationen mellan entiteten för kundaktivitet och entiteten Kund.
    1. Välj det fält som identifierar kunden i tabellen för kundaktivitet, som kan vara direkt relaterad till det primära kund-ID:t för entiteten Kund.
    1. Välj den kundentitet som matchar den primära kundentiteten
    1. Ange ett namn som beskriver relationen.
1. Välj **Nästa**.
1. Mappa semantikfälten till attribut i entiteten för kundaktivitet och välj **Spara**. För beskrivningar av fälten, läs igenom [kraven](#prerequisites).
1. (Valfritt) Om du har andra kundaktiviteter som du vill ta med upprepar du stegen ovan.
   > [!div class="mx-imgBorder"]
   > ![Definiera entitetsrelation](media/subscription-churn-customeractivitiesmapping.PNG "Sidan för kundaktiviteter som visar semantiska attribut som mappats till fält i den valda entiteten för kundaktivitet")
1. Välj **Nästa**.

### <a name="set-schedule-and-review-configuration"></a>Ange schema och granska konfigurationen

1. Ange en frekvens för att träna om modellen. Den här inställningen är viktig för att uppdatera noggrannheten i förutsägelser när nya data matas in i målgruppsinsikter. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.
1. Välj **Nästa**.
1. Granska konfigurationen. Du kan gå tillbaka till valfri del av förutsägelsekonfigurationen genom att välja **Redigera** under visat värde. Du kan också välja ett konfigurationssteg via förloppsindikatorn.
1. Om alla värden är korrekt konfigurerade väljer du **Spara och kör** för att starta förutsägelseprocessen. På fliken **Mina förutsägelser** visas statusen för dina förutsägelser. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

## <a name="review-a-prediction-status-and-results"></a>Granska en förutsägelsestatus och resultat

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.
   > [!div class="mx-imgBorder"]
   > ![Vy över sidan Mina förutsägelser](media/subscription-churn-mypredictions.PNG "Vy över sidan Mina förutsägelser")
1. Välj den prediktion du vill granska.
   - **Namn på förutsägelse:** Det namn på förutsägelsen som angavs när den skapades.
   - **Förutsägelsetyp:** Den typ av modell som används för förutsägelsen
   - **Utdataentitet:** Namnet på den entitet där utflödet för förutsägelsen ska lagras. Du kan söka efter en entitet med det här namnet på **Data** > **Entiteter**.
   - **Förutsagt fält:** Det här fältet fylls endast i för vissa typer av förutsägelser och används inte i förutsägelse om prenumerationsomsättning.
   - **Status:** Aktuell status för förutsägelsens körning.
        - **Köade:** Förutsägelsen väntar för närvarande på att andra processer ska köras.
        - **Uppdaterar:** Förutsägelsen kör i nuläget processtadiet "resultat" för att generera resultat som ska skickas till utdataenheten.
        - **Slutfördes ej:** förutsägelsen misslyckades. Välj **Loggar** om du vill ha mer information.
        - **Slutfördes:** förutsägelsen har slutförts. Välj **Visa** under de lodräta punkterna för att granska förutsägelsen
   - **Redigerad:** Det datum då konfigurationen för förutsägelsen ändrades.
   - **Senaste uppdatering:** Det datum då förutsägelsen uppdaterade resultat i utdataenheten.
1. Markera de lodräta punkterna bredvid den förutsägelse som du vill granska resultat för och välj **Visa**.
   > [!div class="mx-imgBorder"]
   > ![Vy över alternativ på menyn med lodräta punkter för en förutsägelse, bland annat redigera, uppdatera, visa, loggar och ta bort](media/subscription-churn-verticalellipses.PNG "Vy över alternativ på menyn med lodräta punkter för en förutsägelse, bland annat redigera, uppdatera, visa, loggar och ta bort")
1. Det finns tre primära dataområden på resultatsidan:
    1. **Prestanda för övningsmodell** A, B eller C är möjliga poäng. Detta resultat anger förutsägelsens prestanda och kan hjälpa dig att fatta beslutet att använda resultaten som lagras i utdataenheten.
        - Poängen bestäms utifrån följande regler:
            - **A** om modellen noggrant förutsäger minst 50 % av det totala antalet prediktioner och när procentsatsen av exakta prediktioner för kunder som har blivit utdelad är större än den historiska genomsnittliga omsättningen med minst 10 % av den historiska genomsnittliga omsättningen.
            - **B** om modellen noggrant förutsäger minst 50 % av det totala antalet prediktioner och när procentsatsen av exakta prediktioner för kunder som har blivit utdelad är upp till 10 % större än den historiska genomsnittliga omsättningen av den historiska genomsnittliga omsättningen.
            - **C** när modellen noggrant förutsäger mindre 50 % av det totala antalet prediktioner, eller när procenten av exakta prediktioner för kunder som har blivit mindre än den historiska genomsnittliga omsättningen.
               > [!div class="mx-imgBorder"]
               > ![Vy över modellprestandaresultat](media/subscription-churn-modelperformance.PNG "Vy över modellprestandaresultat")
    1. **Sannolikhet för omsättning (antal kunder):** Kundgrupper utifrån deras förutsedda omsättningsrisk. Den här informationen kan hjälpa dig senare om du vill skapa ett kundsegment med hög omsättningsrisk. Sådana segment hjälper dig att förstå var avgränsarna bör finnas för segmentmedlemskap.
       > [!div class="mx-imgBorder"]
       > ![Graf som visar distributionen av omsättningsresultat uppdelad i intervall från 0-100 %](media/subscription-churn-resultdistribution.PNG "Graf som visar distributionen av omsättningsresultat uppdelad i intervall från 0-100 %")
    1. **Faktorer med störst påverkan:** Det finns många faktorer som bör beaktas när du skapar en förutsägelse. Betydelsen för var och en av faktorerna beräknas för de ansamlade förutsägelser som skapas av en modell. Du kan använda dessa faktorer för att validera resultatet av en förutsägelse. Du kan också använda den här informationen senare om du vill [skapa segment](segments.md) som kan påverka omsättningsrisken för en kund.
       > [!div class="mx-imgBorder"]
       > ![Lista som visar tongivande faktorer och deras betydelse för att förutsäga omsättningsresultatet](media/subscription-churn-influentialfactors.PNG "Lista som visar tongivande faktorer och deras betydelse för att förutsäga omsättningsresultatet")

## <a name="fix-a-failed-prediction"></a>Åtgärda en misslyckad förutsägelse

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.
1. Välj den förutsägelse du vill visa felloggar för och välj **Loggar**.
   > [!div class="mx-imgBorder"]
   > ![Vy över menyraden för resultat inklusive knapparna Stäng, Redigera modell och Loggar](media/subscription-churn-logsbutton.PNG "Vy över menyraden för resultat inklusive knapparna Stäng, Redigera modell och Loggar")
1. Granska alla fel. Det finns flera typer av fel som kan inträffa, och dessa beskriver vilket villkor som orsakat problemet. Till exempel ett fel som innebär att det inte finns tillräckligt med data för att förutse åtgärdas vanligtvis genom att ytterligare data läses in.

## <a name="refresh-a-prediction"></a>Uppdatera en förutsägelse

Förutsägelser uppdateras automatiskt i samma [schema som dina data uppdaterar](system.md#schedule-tab) enligt konfigurationen i inställningarna.

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.
1. Markera de lodräta punkterna bredvid den förutsägelse du vill uppdatera.
1. Välj **Uppdatera**.

## <a name="delete-a-prediction"></a>Ta bort en förutsägelse

1. Gå till fliken **Mina förutsägelser** under **Intelligens** > **Förutsägelser**.
1. Markera de lodräta punkterna bredvid den förutsägelse du vill ta bort.
1. Välj **Ta bort**.

> [!NOTE]
> Om du tar bort en prediktion tas dess utdataenhet bort.
