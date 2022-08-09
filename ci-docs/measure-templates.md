---
title: Skapa mått från mallar
description: Definiera mått med hjälp av mallar för vanliga användningsområden.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170795"
---
# <a name="create-measures-from-templates"></a>Skapa mått från mallar

Du kan använda fördefinierade mallar med vanliga [åtgärder](measures.md) för att skapa dem. Mallar bygger på mappade data från entiteten *Enhetlig aktivitet*. Kontrollera därför att du har konfigurerat [kundaktiviteter](activities.md) innan du skapar ett mått från en mall.

Måttmalla stöds endast i miljöer för **enskilda kunder**. Mer information om hur du skapar B2B finns i [Använda måttverktyget för att skapa mått från grunden](measure-builder.md).

Tillgängliga mätmallar:
- Genomsnittligt transaktionsvärde
- Totalt transaktionsvärde
- Genomsnittlig daglig intäkt
- Genomsnittlig månadsintäkt
- Genomsnittlig årlig intäkt
- Transaktionsantal
- Intjänade lojalitetspoäng
- Inlösta lojalitetspoäng
- Saldo för lojalitetspoäng
- Livslängd för aktiv kund
- Lojalitetsmedlemskapets varaktighet
- Tid sedan senaste inköpet

## <a name="build-a-new-measure-using-a-template"></a>Skapa ett nytt mått med hjälp av en mall

1. Gå till **Mått**.

1. Välj **Ny** och markera **Välj en mall**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Skärmbild på listrutan när du skapar ett nytt mått med markering i mallen.":::

1. Hitta den mall som passar dina behov och välj **Välj mall**.

1. Granska de data som krävs och välj **Kom igång** om alla data är på plats.

1. Välj **Redigera information** bredvid måttnamn. Ange ett namn för måttet. Alternativt kan du lägga till [taggar](work-with-tags-columns.md#manage-tags) i måttet.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogrutan Redigera information.":::

1. Välj **Utfört**.

1. I avsnittet **Ange tidsperiod** definierar du tidsram för de data. Välj om du vill att det nya måttet ska täcka hela datauppsättningen genom att välja **Hela tiden** eller att måttet ska fokusera på en **Speficik tidsperiod**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skärmbild som visar avsnittet tidsperiod när du konfigurerar ett mått från en mall.":::

1. Välj **Lägg till data** i nästa avsnitt om du vill välja aktiviteter och mappa motsvarande data från entiteten *Enhetlig aktivitet*.

    1. Steg 1 av 2: Under **Aktivitetstyp** väljer du vilken typ av entitet du vill använda. För **Aktiviteter**, välj de enheter du vill mappa och välj sedan **Näst**.
    1. Steg 2 av 2: Välj attributet från entiteten *Enhetlig aktivitet* för den komponent som krävs av formeln. För genomsnittstransaktionsvärdet är det till exempel attributet som representerar transaktionsvärdet. För **tidsstämpeln för aktivitet** väljer du attributet från entiteten *Enhetlig aktivitet* som representerar datum och tid för aktiviteten.
    1. Välj **Spara**.

    När datamappningen är klar kan du se statusen **Slutförd** och namnet på de mappade aktiviteterna och attributen.

1. Nu kan du välja **Kör** för att beräkna resultatet av åtgärden. Välj **Spara utkast** om du vill behålla den aktuella konfigurationen och köra måttet senare. Sidan **Mått** visas.

## <a name="next-step"></a>Gå vidare

Du kan använda befintliga åtgärder för att skapa [ett kundsegment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
