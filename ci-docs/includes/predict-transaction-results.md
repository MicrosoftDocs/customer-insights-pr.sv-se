---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611112"
---
- **Prestanda för övningsmodell**: Betyget A, B eller C indikerar prestandan för förutsägelsen och kan hjälpa dig att fatta beslutet att använda de resultat som är lagrade i utdataentiteten.

  Betyg fastställs utifrån följande regler:
  - **A** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är större än baslinjen med minst 10 %.
  - **B** När modellen korrekt förutsäger minst 50 % av det totala antalet förutsägelser, och när procentandelen av korrekta förutsägelser för kunder som har omsatts är upp till 10 % större än baslinjen.
  - **C** När modellen korrekt förutsäger mindre än 50 % av det totala antalet förutsägelser, eller när procentandelen av korrekta förutsägelser för kunder som har omsatts är mindre än baslinjen.
  - **Baslinjen** tar tidsintervallet för förutsägelse för modellen (till exempel 1 år) och skapar olika tidsintervall genom att dela det med 2 tills det når 1 månad eller mindre. De mindre tidsintervallen används för att skapa en affärsregel för kunder som inte har köpt något i denna tidsram. Dessa kunder betraktas som omsatta. Den tidsbaserade affärsregeln med den högsta förmågan att förutse vem som sannolikt omsätts väljs som baslinjemodell.

- **Sannolikhet för omsättning (antal kunder)**: Kundgrupper utifrån deras förutsedda omsättningsrisk. Alternativt kan du [skapa kundsegment](../prediction-based-segment.md) med hög omsättningsrisk. Sådana segment hjälper dig att förstå var avgränsarna bör finnas för segmentmedlemskap.

- **Faktorer med störst påverkan**: Det finns många faktorer som bör beaktas när du skapar en förutsägelse. Var och en av faktorerna har en betydelse beräknad för de aggregerade förutsägelserna som skapas av en modell. Använda dessa faktorer för att validera resultatet av en förutsägelse. Du kan också använda den här informationen senare om du vill [skapa segment](../prediction-based-segment.md) som kan påverka omsättningsrisken för en kund.