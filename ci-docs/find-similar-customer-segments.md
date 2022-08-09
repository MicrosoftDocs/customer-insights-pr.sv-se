---
title: Hitta liknande kunder med AI (förhandsversion) (innehåller video)
description: Hitta liknande kundsegment med artificiell intelligens.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170749"
---
# <a name="find-similar-customers-with-ai-preview"></a>Hitta liknande kunder med AI (förhandsversion)

Hitta liknande kunder i kundbasen med hjälp av artificiell intelligens. Du måste ha minst ett segment skapat för att kunna använda den här funktionen. Om du utvidgar villkoren för ett befintligt segment kan du hitta kunder som liknar det segmentet.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Sök efter liknande kunder* använder automatiserade metoder för att utvärdera data och göra prognoser utifrån dessa data. Den kan därför användas som profileringsmetod, vilket den termen definieras av den allmänna dataskyddsordningen ("GDPR"). Kundens användning av den här funktionen för att bearbeta data kan vara föremål för GDPR eller andra lagar eller förordningar. Du ansvarar för att din användning av Dynamics 365 Customer Insights, inklusive förutsägelser, följer alla tillämpliga lagar och förordningar, inklusive lagar som rör sekretess, personuppgifter, biometriska data, dataskydd och sekretess för kommunikation.

## <a name="find-similar-customers"></a>Sök efter liknande kunder

1. Gå till **Segment** och välj det segment du vill basera det nya segmentet på. Det är ditt *källsegment*.

1. Vält **Sök efter liknande kunder**.

1. Granska det föreslagna namnet för det nya segmentet och ändra det vid behov.

1. Alternativt kan du lägga till [taggar](work-with-tags-columns.md#manage-tags) i det nya segmentet.

1. Granska fälten som definierar det nya segmentet. Dessa fält definierar grunden för hur systemet ska försöka hitta liknande kunder i källsegmentet. Rekommenderade fält väljs som standard i systemet. Lägg till fler fält om det behövs.
  Fält som avsevärt kan minska modellens prestanda utesluts automatiskt:
  
   - Fält med följande datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Fält med en kardinalitet (antalet element i ett fält) som understiger 2 eller mer än 30

1. Välj om du vill ta med **Alla kunder** utom källsegmentet eller endast kunder i en **olika segment** i det nya segmentet.

1. Som standard föreslår systemet även 20 % av målpublik storlek i resultatet. Redigera tröskelvärdet efter behov. Om du ökar tröskelvärdet minskas precisionen.

1. Ta med kunder i källsegmentet genom att markera kryssrutan **Inkludera medlemmar från källsegmentet utöver kunder med likartade attribut**.

1. Klicka på **kör** längst ned på sidan om du vill starta en [binär klassificeringsaktivitet](#about-similarity-scores) (en metod för maskininlärning) som analyserar datauppsättning.

## <a name="view-the-similar-segment"></a>Visa liknande segment

När du har bearbetat liknande segment hittar du det nya segmentet på sidan **Segment** med typen **Upptagna**.

Välj **Vy** du vill visa resultatdistribution över [likhetspoäng](#about-similarity-scores) och likhetspoängvärden under **Förhandsgranskning av segmentmedlemmar**.

:::image type="content" source="media/expanded-segment.png" alt-text="Liknande kundsegment.":::

## <a name="manage-a-similar-segment"></a>Hantera ett liknande segment

[Arbeta och hantera resultatet av samma segment](segments.md#manage-existing-segments) som med andra segment. Du kan till exempel exportera segmentet eller bygga ett mått.

Redigera, uppdatera, byt namn på, ladda ner och ta bort ett liknande segment. Om du redigerar ett liknande segment bearbetas dina data på samma sätt. Det segment som skapades tidigare uppdateras med uppdaterade data.

## <a name="about-similarity-scores"></a>Om likhetspoäng

Den binära klassificering maskininlärningsmodellen tilldelar en poäng till kunder i det liknande segmentet. Poängen baseras på likheten med kunder i källsegmentet.

- Likhetspoäng under 0,55 är kunderna systemet klassificerat som *inte liknande* till kunderna i källsegmentet
- Likhetsresultat mellan 0,55 – 0,7 klassificeras som *något liknande*
- Likhetsresultat mellan 0,7 – 0,85 klassificeras som *liknande*
- Likhetsresultat mellan 0,85 – 1 är kunder systemet klassificerat lika *mycket likt*

Kunder med likhetspoäng under 0,4 ingår inte i modellens utdata. Systemet anser inte att det är lika tillräckligt för källsegmentet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
