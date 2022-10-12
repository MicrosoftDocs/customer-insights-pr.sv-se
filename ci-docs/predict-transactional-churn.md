---
title: Prediktion för transaktionsomsättning (innehåller video)
description: Förutse om det finns en risk med att kunden inte längre vill köpa dina produkter eller tjänster.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610534"
---
# <a name="predict-transaction-churn"></a>Prediktion för transaktionsomsättning

Förutsägelse av transaktionell omsättning hjälper till att förutsäga om en kund inte längre kommer att köpa dina produkter eller tjänster i ett visst tidsfönster.

Du måste ha affärskunskaper för att förstå vad omsättningen innebär för företaget. Vi har stöd för tidsbaserade omsättningsdefinitioner, vilket innebär att en kund anses ha omsatts efter en period där inga inköp gjorts.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

För miljöer som bygger på affärskonton kan vi skapa transaktioner för ett konto och även en kombination av konto och en annan informationsnivå, till exempel produktkategori. Exempel kan lägga till en dimension hjälpa till att avgöra hur sannolikt det är att kontot "Contoso" slutar köpa produktkategorin "kontorsmaterial". Dessutom, för företagskonton kan vi också använda AI för att skapa en lista över potentiella skäl till varför ett konto sannolikt kommer att gå för en kategori av sekundär information.

> [!TIP]
> Prova om en förutsägelse om transaktionsomsättning med exempeldata: [Exempelguide för förutsägelse av transaktionsomsättning](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Förutsättningar

- Åtminstone [deltagarbehörigheter](permissions.md).
- Minst 10 kundprofiler, helst mer än 1 000 unika kunder.
- Kundidentifierare: Unik identifierare som matchar transaktioner till en kund
- Transaktionsdata för minst dubbla det valda tidsfönstret, t.ex. två till tre års transaktionshistorik. Minst två transaktioner per kund. Transaktionshistoriken måste innehålla:
  - **Transaktions-ID**: En unik identifierare för ett inköp eller en transaktion.
  - **Transaktionsdatum**: Datumet för köpet eller transaktionen.
  - **Värde för transaktionen**: Valutan eller numeriska värdet för transaktionen.
  - **Unikt produkt-ID**: ID för den produkt eller tjänst som köpts om dina data finns på en radartikelnivå.
  - **Om transaktionen var en retur**: Ett sant/falskt-fält som identifierar om transaktionen returnerades. Om **värdet för transaktionen** är negativt används för att härleda en retur.
- Aktivitetsdata för kund:
  - Kundidentifierare: Unik identifierare för att mappa aktiviteter till en kund
  - **Primärnyckel:** En unik identifierare för en aktivitet. Exempelvis kan ett besök på en webbplats eller en användningspost som visar att kunden testade ett exempel på din produkt.
  - **Tidsstämpel:** Datum och tid för händelsen som identifierats av primärnyckeln.
  - **Händelse:** Namnet på den händelse som du vill använda. Ett fält med namnet "UserAction" i en livsmedelsbutik kan till exempel vara en kuponganvändning av kunden.
  - **Detaljer:** Detaljerad information om händelsen. Ett fält med namnet "CouponValue" i en livsmedelsbutik kan till exempel vara valutavärdet på kupongen.
- Mindre än 20 % av de värden som saknas i entitetens datafält

För affärskonton (B2B) lägger du till kunddata som är justerade mot mer statiska attribut så att modellen fungerar bäst:
- **CustomerID:** En unik identifierare för en kund.
- **Skapad den:** Det datum då kunden ursprungligen lades till.
- **Region:** En kunds region eller region.
- **Land:** Land för en kund.
- **Bransch:** En kunds branschtyp. Ett fält med namnet Bransch i en kaffeställen kan till exempel visa om kunden var återförsäljningskund.
- **Klassificering:** Kategorisering av en kund för företaget. Ett fält med namnet ValueSegment i en kaffesoffa kan exempelvis vara kundnivån utifrån kundens storlek.

> [!NOTE]
> För ett företag med hög kundinköpsfrekvens (varannan vecka) bör du välja en kortare prediktion definition för fönster och kund. För låg inköpsfrekvens (med några månader eller en gång per år) väljer du en längre prediktion och omsättningsdefinitionen.

## <a name="create-a-transaction-churn-prediction"></a>Skapa prediktion för transaktionsomsättning

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Skapa**, välj **Använd modell** på panelen **Kundomsättningsmodell**.

1. Välj **transaktionell** för typen av omsättning och **Kom igång**.

1. **Ge modellen** och **utdataentiteten ett namn** för att särskilja dem från andra modeller eller entiteter.

1. Välj **Nästa**.

### <a name="define-customer-churn"></a>Definiera kundomsättning

Välj **Spara utkast** om du vill prediktion utkast. Förutsägelseutkastet visas i fliken **Mina förutsägelser**.

1. Ange **prediktionsperiod**. Du kan till exempel förutse risken för omsättning av dina kunder under de kommande 90 dagarna för att anpassa dina marknadsföringsinsatser för att behålla kunder. Om du förutser omsättningrisker under en längre eller kortare tid kan det bli svårare att åtgärda faktorerna i din omsättningsriskprofil, men det beror på dina specifika affärskrav.

1. Ange antalet dagar som ska definiera omsättning i fältet **Omsättningsdefinition**. Om en kund exempelvis inte har gjort några inköp under de senaste 30 dagarna kan han/hon betraktas som omsatt.

1. Välj **Nästa**.

### <a name="add-purchase-history"></a>Lägg till inköpshistorik

1. Välj **Lägg till data** för **Historik för kundtransaktioner**.

1. Välj typ av semantisk aktivitet **SalesOrder** eller **SalesOrderLine**, som innehåller transaktionshistorik informationen. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var semantiskt mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="En sidoruta som anger specifika aktiviteter under semantiktypen.":::

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Lägg till fler aktiviteter eller välj **Näst**.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Lägg till ytterligare data (valfritt)

1. Välj **Lägg till data** för **Kundaktiviteter**.

1. Välj den typ av semantisk aktivitet som innehåller de data du vill använda. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var semantiskt mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Välj **Nästa**

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Välj prediktionsnivå

De flesta prediktioner skapas på kundnivå. I vissa situationer kanske det inte är tillräckligt detaljerad för att kunna tillgodose företagets behov. Du kan använda den här funktionen för att skapa nya funktioner för en kundgren, till exempel i stället för kunden som helhet.

1. Välj **Välj entitet för en sekundär nivå**. Om alternativet inte är tillgängligt ser du till att du har slutfört avsnittet nedan.

1. Expandera de entiteter du vill välja den sekundära nivån från eller filtrera de markerade alternativen med hjälp av sökfilterrutan.

1. Välj attributet du vill använda som sekundär nivå och välj sedan **Lägg till**.

1. Välj **Nästa**.

> [!NOTE]
> De entiteter som är tillgängliga i det här avsnittet visas eftersom de har en relation till den entitet du valde i föregående avsnitt. Om du inte ser den entitet du vill lägga till ska du kontrollera att den har en giltig relation i **Relationer**. Endast en till en och flera-till-en relationer för den här konfigurationen.

### <a name="add-additional-data-optional"></a>Lägg till ytterligare data (valfritt)

1. Välj **Lägg till data** för **Kundaktiviteter**.

1. Välj den typ av semantisk aktivitet som innehåller de data du vill använda. Om aktiviteten inte har ställts in väljer du **här** och skapar den.

1. Under **Aktiviteter**, om aktivitetsattributen var semantiskt mappade när aktiviteten skapades, välj de specifika attributen eller entiteten som du vill att beräkningen ska fokusera på. Om ingen mappning har inträffat väljer du **Redigera** och mappar dina data.

1. Välj **Nästa** och granska attributen som krävs för modellen.

1. Välj **Spara**.

1. Välj **Nästa**

1. Alternativt väljer du **Lägg till data** för **Kunddata**.

1. Mappa attributen till fält i dina egna kunddata enligt vad som har identifierats. Data i fälten som används bör inte ändras ofta för att säkerställa modellens bästa prestanda. Om du till exempel väljer ett fält för Klassificering som ändras varje månad används bara det sista värdet i prediktion,även om tidigare samma värde kanske inte gäller kunden när de prediktionsmönster.

1. Välj **Nästa**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Ange en valfri lista med jämförelsekonton

Lägg till en lista över dina företagskunder och konton som du vill använda som riktmärken. Du får [information om dessa jämförelsekonton](#view-prediction-results), bland annat deras omsättningspoäng och de flesta funktioner som har påverkat deras prediktion.

1. Välj **+ Lägg till kunder**.

1. Välj vilka kunder som ska fungera som jämförelse.

1. Välj **Nästa**.

---

### <a name="set-update-schedule"></a>Ange uppdateringsschema

1. För steget **Datauppdateringar**, välj en frekvens för att omskola din modell. Denna inställning är viktig för att uppdatera precisionen i förutsägelser när nya data hämtas till Customer Insights. De flesta företag kan träna om en gång i månaden och få en god exakthet för sina förutsägelser.

1. Välj **Nästa**.

### <a name="review-and-run-the-model-configuration"></a>Granska och köra modellkonfigurationen

Steget **Granska och kör** visar en sammanfattning av konfigurationen och ger en chans att göra ändringar innan du skapar förutsägelse.

1. Välj **Redigera** på något av stegen för att granska och göra eventuella ändringar.

1. Om du är nöjd med dina val, välj **Spara och kör** för att starta modellen. Välj **Klar**. Fliken **Mina prognoser** visas när prediktion skapas. Det kan ta flera timmar att slutföra processen beroende på mängden data som används i förutsägelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visa förutsägelsens resultat

1. Gå till **Intelligens** > **Prediktioner**.

1. På fliken **Mina förutsägelser**, välj den förutsägelse du vill visa.

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

Det finns tre primära dataområden på resultatsidan:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

Det finns tre primära dataområden på resultatsidan:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Informationssidan **Analys av påverkansfaktor** innehåller fyra delar av data:

- I högra rutan, välj ett objekt från **De främsta kunderna** eller **Jämförelsekunder**. Båda listorna beställas genom att minska värdet på omsättningspoängen, oavsett om poängen endast är för kunden eller en kombinationspoäng för kunder och en sekundär nivå som produktkategori. Innehållet på den här sidan avgörs av det valda objektet.

  - **De främsta kunderna**: Lista över tio kunder som har den högsta risken för omsättning och lägsta risken för omsättning utifrån deras omsättningspoäng.
  - **Jämförelsekunder**: Lista över upp till 10 kunder som valdes när de konfigurerade modellen.

- **Omsättningspoäng:** Visar omsättningspoängen för det valda objektet i den högra rutan.

- **Riskfördelning av omsättning:** Visar riskfördelning av omsättning mellan kunder och den percentil den valda kunden finns i.

- **De främsta funktionerna som ökar och minskar omsättningsrisken:** För det valda objektet i den högra rutan visas de fem främsta funktionerna som har ökat och minskat omsättningsrisken. För varje funktion som har betydelse för objektet hittar du värdet av funktionen för objektet och dess påverkan på objektets resultat. Det finns även ett genomsnittsvärde för varje funktion i kundsegmenten med låg och hög omsättningsrisk. Det hjälper till att bättre kontextualisera värdena för de funktioner som valts för det valda objektet och jämföra det med kundsegment med låg eller hög omsättning.

  - Låg: konton eller kombinationer av konto och sekundär nivå med en poäng från 0 till 0,33.
  - Medel: konton eller kombinationer av konton och sekundära nivåer med en poäng från 0,33 till 0,66.
  - Hög: konton eller kombinationer av konton och sekundära nivåer med en poäng större än 0,66.

  Om du försöker lösa detta på kontonivån tas hänsyn till alla konton genom att beräkna genomsnittsvärdena för funktionen för segment av omsättning. För prognos på sekundär nivå för varje konto beror spridning av segment på den sekundära nivån för objektet som valts i sidoruta. Om ett objekt till exempel har en sekundär nivå av produktkategori (kontorsmaterial), beaktas endast de objekt som har kontorsmaterial som produktkategori när genomsnittsvärdena för funktionen för segment används. Den här logiken används för att säkerställa en korrekt jämförelse av objektets funktionsvärden med genomsnittsvärdena i segmenten låg, tjock och hög.

  I vissa fall är genomsnittsvärdet för segment med låg eller hög omsättning tom eller inte tillgänglig eftersom det inte finns några objekt i motsvarande segment för segmenten ovan.

  Tolkningen av värden under kolumnerna låg, medium och hög skiljer sig åt för kategorifunktioner som land och bransch. Eftersom begreppet om ett "genomsnittligt" funktionsvärde inte gäller kategorifunktioner är värdena i dessa kolumner proportionerna med kunder i omsättningssegment med låg, medium och hög omsättning som har samma värde för kategorifunktionen jämfört med objektet som valts i sidopanelen.

---

 > [!NOTE]
 > I utdataentiteten för denna modell visar *ChurnScore* den förutsagda sannolikheten för omsättning och *IsChurn* är en binär etikett baserad på *ChurnScore* med 0,5 tröskel. Om standardtröskeln inte fungerar för ditt scenario [skapar du ett nytt segment](segments.md#create-a-segment) med det önskade tröskelvärdet. Alla kunder behöver inte vara aktiva kunder. En del av dem kanske inte har haft någon aktivitet under en längre tid och betraktas som redan nedtonade, baserat på din definition. Det är inte bra att ta risken för kunder som redan har börjat använda programmet eftersom de inte är målgruppen av intresse.
>
> För att visa omsättningspoängen, gå till **Data** > **Entiteter** och visa datafliken för den utdataenhet som du definierade för den här modellen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
