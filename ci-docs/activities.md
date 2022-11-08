---
title: Kund- eller affärskontaktaktiviteter
description: Definiera kund- eller affärskontakt aktiviteter och visa dessa på en tidslinje för kundprofiler.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723803"
---
# <a name="customer-or-business-contact-activities"></a>Kund- eller affärskontaktaktiviteter

Kundaktiviteter är åtgärder eller händelser som utförs av kunder eller affärskontakter. Till exempel är transaktioner, varaktighet för supportsamtal, webbplatsens recensioner, köp eller returer. Aktiviteterna finns i en eller flera datakällor. Med Customers Insights konsoliderar du dina kundaktiviteter från dessa [datakällor](data-sources.md) och associerar dem med kundprofiler. Dessa aktiviteter visas kronologiskt i en tidslinje i kundprofilen. Inkludera tidslinjen i Dynamics 365-appar med [tilläggslösningen kundkort](customer-card-add-in.md).

## <a name="define-a-customer-activity"></a>Definiera kundaktivitet

En entitet måste ha minst ett attribut av typen **Datum** för att kunna tas med i en kundtidslinje. Kontrollen **Lägg till aktivitet** är inaktiverad om ingen sådan entitet hittas.

1. Gå till **Data** > **Aktiviteter**.

1. Välj **Lägg till aktivitet** för att starta den guidade upplevelsen.

1. I steget **aktivitetsdata** anger du följande information:

   - **Aktivitetsnamn**: Välj ett namn för aktiviteten.
   - **Aktivitetsentitet**: Välj en entitet som innehåller transaktions- eller aktivitetsdata.
   - **Primärnyckeln**: Välj fältet som används för unik identifiering av en post. Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.

     > [!NOTE]
     > Den primära nyckeln för varje rad måste vara konsekvent datakälla uppdateras. Om primärnyckeln för en rad uppdateras i en datakälla skapas dubbletter i utdataaktivitetsentiteten. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurera aktivitetsdata med namn, entitet och primärnyckel.":::

1. Välj **Nästa**.

1. I steget **Relation**, välj **Lägg till relation** för att ansluta dina aktivitetsuppgifter till motsvarande kundpost. Det här steget visualiserar anslutningen mellan entiteter.  

   - **Sekundärnyckel**: Fält för externa fält i aktivitetsentiteten som används för att upprätta en relation med en annan entitet.
   - **Till entitetsnamn**: Motsvarande källkundentitet som din aktivitetsentitet ska vara i relation till. Du kan endast relatera till källkundentiteter som används i datakällprocessen.
   - **Relationsnamn**: om det redan finns en relation mellan den här aktivitetsentiteten och den valda källkundentiteten är relationsnamnet i skrivskyddat läge. Om det inte finns någon sådan relation skapas en ny relation med det namn du anger i rutan.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiera entitetsrelation.":::

   > [!TIP]
   > I B2B-miljöer kan du välja mellan kontoentiteter och andra entiteter. Om du väljer en kontoentitet anges relationssökvägen automatiskt. För andra entiteter måste du definiera relationssökvägen över en eller flera mellanliggande entiteter tills du når en kontoentitet.

1. Välj **Tillämpa** för att skapa den anpassade relationen.

1. Välj **Nästa**.

1. I steget **Samordning av aktiviteter** välj aktivitetshändelsen och starttiden för din aktivitet.
   - **Obligatoriska fält**
      - **Händelseaktivitet**: Fält som är händelsen för aktiviteten.
      - **Tidsstämpel**: Fält som representerar aktivitetens starttid.

   - **Valfria fält**
      - **Ytterligare information**: Fält med relevant information för aktiviteten.
      - **Ikon**: Ikon som bäst representerar den här aktivitetstypen.
      - **Webbadress**: Fält som innehåller en URL med information om aktiviteten. Det kan till exempel vara det transaktionssystem som visar aktiviteten. Denna URL kan vara vilket fält som helst från datakällan, eller så kan den konstrueras som ett nytt fält med hjälp av en Power Query-omvandling. URL-data lagras i entiteten *Enhetlig aktivitet*, som kan användas nedströms med [API:er](apis.md). 

   - **Visa på tidslinje**
      - Välj om du vill visa denna aktivitet i tidslinjevyn för dina kundprofiler. Välj **Ja** om du vill visa aktiviteten på tidslinjen eller **Nej** för att dölja den.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Ange kundaktivitetsdata i en entitet för enhetlig aktivitet.":::

1. Välja **Nästa** för att välja aktivitetstyp eller välj **Slutför och granska** för att spara aktiviteten med aktivitetstypen inställd på **Andra**.

1. Välj aktivitetstyp i steget **Aktivitetstyp** och välj om du vill mappa några av aktivitetstyperna så att de kan användas i andra områden av Customer Insights. För tillfället har aktivitetstyperna *Feedback*, *Lojalitet*, *SalesOrder*, *SalesOrderLine* och *Prenumeration* stöd för semantik efter att ha gått med på att kartlägga fälten. Om en aktivitetstyp inte är relevant för den nya aktiviteten kan du välja *Annat* eller *Skapa ny* för en anpassad aktivitetstyp.

1. Välj **Nästa**.

1. I steget **Granska**, kontrollera dina val. Gå tillbaka till valfritt föregående steg och uppdatera informationen vid behov.

1. Välj **Spara aktivitet** om du vill tillämpa ändringarna och välj **Klar** för att gå tillbaka till **Data**  > **Aktiviteter**. Den skapade aktiviteten visas.

1. När du har skapat alla dina aktiviteter väljer du **Kör** för att bearbeta dem.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Hantera befintliga kundaktiviteter

Gå till **Data** > **Aktiviteter** för att se dina sparade aktiviteter, deras källenhet, aktivitetstypen och om de ingår i kundens tidslinje. Du kan sortera listan med aktiviteter efter valfri kolumn eller använda sökrutan för att hitta den aktivitet du vill hantera.

Välj aktivitet om du vill visa tillgängliga åtgärder.

- **Redigera** aktiviteten så att den ändras. Konfigurationen öppnas i granskningssteget. När du har ändrat konfigurationen väljer du **Spara aktivitet** och väljer **Kör** för att bearbeta ändringarna.
- **Byt namn** på aktivitet. Välj **Spara** för att införa ändringarna.
- **Radera** aktiviteten. För att ta bort mer än en aktivitet samtidigt, välj aktiviteterna och sedan **Radera**. Bekräfta borttagningen.

## <a name="view-activity-timelines-on-customer-profiles"></a>Visa tidslinjer för aktiviteter på kundprofiler

1. Om du valde **Visa i aktivitetstidslinjen** i aktivitetskonfigurationen, gå **Kunder** och välj en kundprofil för att se kundens aktiviteter i avsnittet **Tidslinje för aktivitet**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Visa konfigurerade aktiviteter i kundprofiler.":::

1. Så här filtrerar du aktiviteter i aktivitetens tidslinje:

   - Markera en eller flera av aktivitetsikonerna om du vill förfina resultatet så att endast valda typer ingår.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrera aktiviteter efter typ med hjälp av ikonerna.":::

   - Välj **Filter** om du vill öppna en filterpanel och konfigurera dina tidslinjefilter. Filtrera efter *ActivityType* och *Datum*. Välj **Verkställ**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Konfigurera filtervillkoren med hjälp av filterpanelen.":::

> [!NOTE]
> Aktivitetsfilter tas bort när du lämnar en kundprofil. Du måste tillämpa dem varje gång du öppnar i en kundprofil.

## <a name="define-a-contact-activity"></a>Definiera kontaktaktivitet

För affärskonton (B2B) använder du entitet *ContactProfile* för att samla in aktiviteter från kontakter. Du kan se aktivitetstidslinjen för ett konto vilken kontakt som ansvarade för varje aktivitet. De flesta steg följer aktivitetsmappningskonfigurationen för kund.

   > [!NOTE]
   > För att definiera en aktivitet på kontaktnivå, en entitet *ContactProfile* måste skapas antingen som ena [enhetlig kontaktprofil](data-unification-contacts.md) eller via [semantisk mappning](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Du måste ha båda attributen **AccountID** och **ContactID** för varje post i dina aktivitetsdata.
  
1. Gå till **Data** > **Aktiviteter**.

1. Välj **Lägg till aktivitet**.

1. I steget **aktivitetsdata** anger du följande information:

   - **Aktivitetsnamn**: Välj ett namn för aktiviteten.
   - **Aktivitetsentitet**: Välj en entitet som innehåller transaktions- eller aktivitetsdata.
   - **Primärnyckeln**: Välj fältet som används för unik identifiering av en post. Den ska inte innehålla några dubblettvärden, tomma värden eller värden som saknas.

     > [!NOTE]
     > Den primära nyckeln för varje rad måste vara konsekvent datakälla uppdateras. Om primärnyckeln för en rad uppdateras i en datakälla skapas dubbletter i utdataaktivitetsentiteten. 


1. I steget **Relationer**, skapa en indirekt relation mellan din aktivitetskällas data till konton, genom att använda din kontaktdata som en mellanliggande enhet. Mer information finns i [direkta och indirekta relationssökvägar](relationships.md#relationship-paths). 
   - Exempelrelation för en aktivitet med namnet *Inköp*:
      - **Aktivitetsdata för inköpskälla** > **Kontaktdata** på attributet **ContactID**
      - **Kontaktdata** > **Kontodata** i attributet **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Inställning av exempelrelation.":::

1. När du har Relationer väljer du **Nästa** och slutför konfiguration av aktivitetsmappning. Detaljerade steg när du skapar en aktivitet finns i [definiera en kundaktivitet](#define-a-customer-activity).

1. Kör dina aktivitetsmappningar.

1. Dina aktiviteter på kontaktnivå visas nu på din kundtidslinje.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Slutresultat efter konfigurering av kontaktaktiviteter":::

## <a name="contact-level-activity-timeline-filtering"></a>Tidslinjefiltrering på kontaktnivå

När du har konfigurerat en aktivitetsmappning på kontaktnivå och kör den uppdateras aktivitetstidslinjen för dina kunder. Det inkluderar deras ID eller namn, beroende på ditt *ContactProfile* konfiguration, för de aktiviteter de agerat på. Du kan filtrera aktiviteter efter kontakter i tidslinjen om du vill se specifika kontakter som du är intresserad av. Dessutom kan du visa alla aktiviteter som inte har tilldelats en viss kontakt genom att välja **Aktiviteter som inte är mappade till en kontakt**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Tillgängliga filtreringsalternativ för aktiviteter på kontaktnivå.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
