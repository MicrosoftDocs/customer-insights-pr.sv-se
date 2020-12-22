---
title: Slutför partiella data med hjälp av förutsägelser
description: Använd förutsägelser för att fylla i ofullständiga kunddata.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648733"
---
# <a name="complete-your-partial-data-with-predictions"></a>Komplettera dina ofullständiga data med förutsägelser

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Med hjälp av prediktioner kan du enkelt skapa förutsagda värden som förbättrar förståelsen av en kund. På sidan **Intelligens** > **Förutsägelser** kan du välja **Mina förutsägelser** för att se förutsägelser som du har konfigurerat i andra delar av målgruppinsikter och anpassa dem ytterligare.

> [!NOTE]
> Du kan inte använda den här funktionen om din miljö använder Azure Data Lake gen 2-lagring.
>
> I funktionen prediktioner används automatiska metoder för att utvärdera data och göra prediktioner baserade på dessa data och har därför möjlighet att använda som en metod för profilering, eftersom den termen definieras av allmän dataskyddsförordning ("GDPR"). Kundens användning av den här funktionen för att bearbeta data kan vara föremål för GDPR eller andra lagar eller förordningar. Du ansvarar för att din användning av Dynamics 365 Customer Insights, inklusive förutsägelser, följer alla tillämpliga lagar och förordningar, inklusive lagar som rör sekretess, personuppgifter, biometriska data, dataskydd och sekretess för kommunikation.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan använda funktionen prediktioner i organisationen bör du kontrollera att följande förutsättningar är uppfyllda:

1. Din organisation har en instans [konfigurerad i Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) och den är i samma organisation som Customer Insights.

2. Din miljö är kopplad till din Common Data Service-instans.

Om du [skapar en ny miljö](manage-environments.md) konfigurerar du den i dialogrutan **Skapa en miljö** och väljer **Avancerat**. Om du redan har skapat en miljö går du till dess inställningar och väljer **Avancerat**. Oavsett vilket anger du i avsnittet **Använd förutsägelser** Common Data Service-instansens URL som du vill koppla din miljö till.

## <a name="create-a-prediction-in-the-customer-entity"></a>Skapa en förutsägelse i entiteten Kund

1. I målgruppsinsikter går du till **Data** > **Entiteter**.

2. Välj entiteten **Kund**.

3. I entiteten **kund: CustomerInsights** väljer du fliken **fält**.

4. Sök efter det attributnamn som du vill förutsäga värden för och välj sedan ikonen **översikt** i kolumnen **sammanfattning**.
   > [!div class="mx-imgBorder"]
   > ![Ikonen Översikt](media/intelligence-overviewicon.png "Ikonen Översikt")

5. Om attributet saknar en hög hastighet på saknade värden väljer du **Predicera saknade värden** för att fortsätta med din prediktion.
   > [!div class="mx-imgBorder"]
   > ![Översiktsstatus med knappen predicera saknade värden visas](media/intelligence-overviewpredictmissingvalues.png "Översiktsstatus med knappen predicera saknade värden visas")

6. Ange ett **visningsnamn** och **utdataenhetens namn** för resultatet av prediktionen.

7. I en lista över alternativ som är i förväg visas var du kan mappa värdena till en fördefinierad kategori. I det här fallet är de enda kategorialternativen 0 eller 1 som mappas till den faktiska/falska eller binära typen av förutsägelse. I kolumnen Kategori, mappa de fältvärden som du vill ska vara klassificerade som "0" i den slutliga prediktionen till "0" och de objekt som du vill klassificera som "1" i den slutliga prediktionen till "1".
   > [!div class="mx-imgBorder"]
   > ![Exempel som visar mappade fältvärden för kategorier](media/intelligence-categorymapping.png "Exempel som visar mappade fältvärden för kategorier")

8. Välj **klart** och prediktionen kommer att bearbetas. Bearbetningen kan ta en stund, beroende på datastorlek och komplexitet. Resultatet blir tillgängligt i en ny entitet baserat på **Utdataenhetens namn** för den prediktion du skapade.

## <a name="create-a-prediction-while-creating-a-segment"></a>Skapa en prediktion när du skapar ett segment

Det går också att predicera saknade värden för ett specifikt val av attribut när du skapar ett segment. När du snabbt skapar ett segment utifrån antingen den enhetliga entiteten för entiteten kund eller entiteten Customer_Measure.

Som en del av detta flöde kan du välja ett specifikt attribut som du vill basera segmentet på, till exempel kundtillfredsställelse eller inköpsbelopp. När ett segment skapas föreslår systemet en metod för att förutsäga alla värden som saknas för attributet.

1. I målgruppsinsikter går du till **Segment** och väljer panelen **Profiler**.

2. Välj ett **fält** för att skapa ett segment på och välj en **operatör** och välj sedan **granska**.

3. Ange ett **namn** och ett **visningsnamn** för segmentet.

4. Välj **Spara**.

5. Om det segment du skapade innehåller ofullständiga data i källfältet kan du välja att förutsäga de saknade värdena.
   > [!div class="mx-imgBorder"]
   > ![Knappen prediktion](media/segments-predictoption.png "Knappen prediktion")

6. Ange ett **visningsnamn** och **utdataenhetens namn** för resultatet av prediktionen.

7. Markera **Klart**. Din prediktion skapas inom kort i en ny entitet med det namn du angav för **Utdataenhetens namn**.

## <a name="view-a-prediction"></a>Visa en prediktion

1. I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.

2. Välj den prediktion du vill granska.

3. Välj en ellips i kolumnen **Åtgärder** och välj **Visa**.

4. Du ser flera datapunkter i vyn av din prediktion.
   > [!div class="mx-imgBorder"]
   > ![Sidan Prediktioner](media/intelligence-predictionsviewpage.png "Sidan Prediktioner")

   - **Predicerade värden** visar den mappning du skapade vid fältvärdet för kategorimappning. Dessa är värden i dina datauppsättning som har mappats till en specifik kategori.
   -**Främsta influerare** är de faktorer inom datauppsättning som sannolikt skulle påverka prediktionens relevans för fältvärdet som mappas till en specifik kategori.
   - **Prestanda** indikerar hur prediktionerna fungerar. Välj länken om du vill veta mer.
   - **Förhandsgranskning** visar prover av utgående datauppsättning från din prediktion och sannolikheten eller vårt förtroende för det predicerade värdet där 0 är osäker och 1 är säker.

## <a name="update-a-prediction"></a>Uppdatera en prediktion

1. I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.

2. Markera den prediktion du vill uppdatera och välj ikonen **uppdatera**.

3. Prediktionen kommer att schemaläggas för bearbetning. Du kan se hur lång tid som uppdaterades senast i kolumnen **Uppdaterad** på sidan **prediktioner**.

## <a name="edit-a-prediction"></a>Redigera en prediktion

När du har skapat en prediktion kan du anpassa modellen i AI Builder för att öka modellens effektivitet.  

1. I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.

2. Markera den prediktion du vill redigera.

3. Välj en ellips i kolumnen **Åtgärder** och välj **Visa**.

4. Välj **Anpassa i AI Builder**.

5. Uppdatera modellen i AI Builder. [Mer information om hur du hanterar modeller i AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).

Nästa gång du kör din prediktion används den uppdaterade modell som du har skapat.

> [!NOTE]
> Nya modeller som skapats i AI Builder kommer inte att visas i målgruppsinsikter om inte modellen skapades från de upplevelser som anges ovan.

## <a name="remove-a-prediction"></a>Ta bort en prediktion

1. I målgruppsinsikter går du till **Intelligens** > **Förutsägelser** > **Mina förutsägelser**.

2. Markera den prediktion du vill ta bort.

3. Välj en ellips i kolumnen **Åtgärder** och välj **Ta bort**.

4. Bekräfta borttagningen.

## <a name="troubleshooting"></a>Felsökning

Om du inte kan slutföra anslutna Common Data Service-processen på grund av ett fel kan du försöka slutföra processen manuellt. Det finns två kända problem som kan uppstå under anslutningsprocessen:

- Tilläggslösningen Customer Card har inte installerats.
    1. Slutför anvisningarna för att [Installera och konfigurera lösningen](customer-card-add-in.md).

- Appbehörighet beviljas inte.
    1. Gå till [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Välj **Miljöer**.
    1. Markera ellipsknappen bredvid den miljö där du vill lägga till behörighet och markera **inställningar**.
    1. Expandera **användare + behörigheter** och välj **användare**.
    1. Välj **+ ny** och välj **användare**.
    1. Välj **programanvändare** om den inte redan är vald och ange följande information:
        - **Användarnamn:** cihelp@microsoft.com
        - **App-ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Förnamn:** Kund
        - **Efternamn** Insikter
        - **Primär e-post:** cihelp@microsoft.com
    1. Välj **Spara och stäng**.
    1. Välj den användare du just skapade.
    1. Välj **hantera roller** på den övre menyraden.
    1. Välj **Systemadministratör** och klicka sedan på **OK**.
