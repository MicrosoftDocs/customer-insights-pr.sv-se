---
title: Hitta liknande kunder med AI (innehåller video)
description: Hitta liknande kundsegment med artificiell intelligens.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de337ae989558c81fff25a6ff7cca01890ed306b
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934862"
---
# <a name="similar-customers-preview"></a>Liknande kunder (förhandsversion)

Med den här funktionen kan du söka efter liknande kunder i kundbasen med hjälp av artificiell intelligens. Du måste ha minst ett segment skapat för att kunna använda den här funktionen. Om du utvidgar villkoren för ett befintligt segment kan du hitta kunder som liknar det segmentet.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Söka efter liknande kunder* använder automatiska metoder för att utvärdera data och göra förutsägelser baserade på dessa data och har därför möjlighet att använda som en metod för profilering, eftersom den termen definieras av allmän dataskyddsförordning ("GDPR"). Kundens användning av den här funktionen för att bearbeta data kan vara föremål för GDPR eller andra lagar eller förordningar. Du ansvarar för att din användning av Dynamics 365 Customer Insights, inklusive förutsägelser, följer alla tillämpliga lagar och förordningar, inklusive lagar som rör sekretess, personuppgifter, biometriska data, dataskydd och sekretess för kommunikation.

## <a name="finding-similar-customers"></a>Hitta liknande kunder

1. I målgruppsinsikter går du till **Segment** och väljer det segment som du vill basera ditt nya segment på. Det är ditt *källsegment*.

1. Välj **Sök efter liknande kunder** i åtgärdsfältet.

1. Granska det föreslagna namnet för det nya segmentet och ändra det vid behov.

1. Granska fälten som definierar det nya segmentet. Dessa fält definierar grunden för hur systemet ska försöka hitta liknande kunder i källsegmentet. Rekommenderade fält väljs som standard i systemet.
  Fält som avsevärt kan minska modellens prestanda utesluts automatiskt:
  
   - Fält med följande datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Fält med en kardinalitet (antalet element i ett fält) som understiger 2 eller mer än 30

1. Välj om du vill ta med **Alla kunder** eller endast kunder i ett **specifikt befintligt segment** i det nya segmentet.

1. Exkludera kunder i källsegmentet genom att markera kryssrutan **exkludera alla i källsegment**.

1. Som standard föreslår systemet även 20 % av målpublik storlek i resultatet. Redigera tröskelvärdet efter behov. Om du ökar tröskelvärdet minskas precisionen.

1. Klicka på **kör** längst ned på sidan om du vill starta en binär klassificeringsaktivitet (en metod för maskininlärning) som analyserar datauppsättning.

## <a name="view-the-similar-segment"></a>Visa liknande segment

När du har bearbetat liknande segment hittar du det nya segmentet på sidan **segment**.

> [!div class="mx-imgBorder"]
> ![Liknande kundsegment.](media/expanded-segment.png "Liknande kundsegment")

Välj **Visa** i åtgärdsfältet för att öppna segmentdetaljen. Den här vyn innehåller information om resultatfördelningen mellan olika [likhetsresultat](#about-similarity-scores). Du hittar också liknande poängvärden i **Förhandsversion av segmentmedlemmar**.

## <a name="use-the-output-of-a-similar-segment"></a>Använda utdata från ett liknande segment

Du kan [arbeta med resultatet av samma segment](segments.md) som med andra segment. Du kan till exempel exportera segmentet eller bygga ett mått.

## <a name="refresh-and-edit-a-similar-segment"></a>Uppdatera och redigera liknande segment

Om du vill uppdatera ett liknande segment markerar du det på sidan **Segment** och välj **Uppdatera** i åtgärdsfältet.

Om du redigerar ett liknande segment bearbetas dina data på samma sätt. Det segment som skapades tidigare uppdateras med uppdaterade data.    
Om du vill redigera ett liknande segment markerar du det på sidan **Segment** och välj **redigera** i åtgärdsfältet. Tillämpa ändringarna och välj **kör** för att starta bearbetningen.

## <a name="delete-a-similar-segment"></a>Ta bort ett liknande segment

Välj segment på sidan **Segment** och välj **Ta bort** i åtgärdsfältet. Bekräfta sedan borttagningen.

## <a name="about-similarity-scores"></a>Om likhetspoäng

Den binära klassificering maskininlärningsmodellen tilldelar en poäng till kunder i det liknande segmentet. Poängen baseras på likheten med kunder i källsegmentet.

- Likhetspoäng under 0,55 är kunderna systemet klassificerat som *inte liknande* till kunderna i källsegmentet
- Likhetsresultat mellan 0,55 – 0,7 klassificeras som *något liknande*
- Likhetsresultat mellan 0,7 – 0,85 klassificeras som *liknande*
- Likhetsresultat mellan 0,85 – 1 är kunder systemet klassificerat lika *mycket likt*

Kunder med likhetspoäng under 0,4 ingår inte i modellens utdata. Systemet anser inte att det är lika tillräckligt för källsegmentet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]