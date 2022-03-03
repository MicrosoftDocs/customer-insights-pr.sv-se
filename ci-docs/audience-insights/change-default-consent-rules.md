---
title: Hantera standardregler för samtycke i segment
description: Med funktionen för godkännandehantering kan du inaktivera eller ändra standardgodkännandereglerna om åsidosättningar har aktiverats.
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228961"
---
# <a name="disable-or-change-default-consent-rules"></a>Inaktivera eller ändra standardregler för samtycke

Om dina organisationer använder [funktionen för hantering av samtycke](../consent-management/overview.md) i kombination med målgruppsinsikter, [kan administratörer framtvinga godkännanderegler](activate-consent.md) för segment. 

Med framtvingade samtyckesregler i segmentområdet informerar varje segment om tillståndet för samtyckeskontroll och regler. Om åsidosättningar tillåts är standardregler för samtycke inaktiverade för vissa segment. Alla som skapat ett segment kan lägga till fler samtyckesregler ovanpå standardreglerna för det segmentet. 

## <a name="for-administrators"></a>För administratörer

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmentverktyget med alternativ för samtyckesregel.":::

**Inaktivera standardregler för samtycke:**

1. I meddelandet **Samtyckesregler**, välj **Visa information**. 

1. Ange växlingen **standardregler för samtycke** till **Av**.

**Lägg till fler samtyckesregler:**

1. I meddelandet **Samtyckesregler**, välj **Visa information**. 

1. Välj **Lägg till samtyckesregler** och välj en samtyckesregel i listrutan **Välj samtyckesdatatyp**.

1. Välj **Spara** om du vill använda den nya regeln för segment.

## <a name="for-contributors"></a>För deltagare

Om du vill skapa ett segment utan genomdrivna samtyckesregler måste du samarbeta med Administratör för att inaktivera dem i ditt segment. Du kan dock lägga till egna samtyckesregler i segment som du äger och hanterar.

Det är en process i tre steg: 
1. [Skapa ett segment](segments.md)i målgruppinsikter och spara det. 

1. Dela segmentnamnet med administratören och be dem [aktivera åsidosättningar för ditt segment](activate-consent.md). 

1. Öppna segmenten igen. I aviseringen **Godkännanderegler**, välj **Se information** och lägg till de samtyckesregler du vill tillämpa. Sedan **Spara** och **Kör** ditt segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
