---
title: Slå samman entiteter i datasammanslutningen
description: Slå samman entiteter för att skapa enhetliga kundprofiler.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 24b523786158ff36c314601846ee25ea64cfabbe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650248"
---
# <a name="merge-entities"></a>Slå samman entiteter

Sammanslagningsfasen är den sista fasen i föreningsprocessen för data. Dess syfte avstäms av motstridiga data. Exempel på data som är i konflikt kan vara ett kundnamn som finns i två av dina datauppsättningar, men som visar lite annorlunda i varje (“Grant Marshall” jämfört med “Grant Marshal”), eller ett telefonnummer som skiljer sig från formatet (617-803-091X jämfört med 617803091X). Sammanfoga dessa motstridiga datapunkter görs på ett attribut till attributbasis.

:::image type="content" source="media/merge-fields-page.png" alt-text="Sammanslå sida i dataförlopp som visar tabell med kopplade fält som definierar den enhetliga kundprofilen.":::

Efter att ha avslutat [matchningsfasen](match-entities.md) kan du starta sammanslagningsfasen genom att välja panelen **Sammanslagning** på sidan **Enhet**.

## <a name="review-system-recommendations"></a>Granska systemrekommendationer

I **Data** > **Förena** > **Slå samman** väljer du och utesluter attribut att slå samman inom din enhetliga kundprofilenhet. Den enhetliga kundprofilen är resultatet av dataföreningsprocessen. Vissa attribut slås samman automatiskt av systemet.

Om du vill visa attributen som ingår i ett av dina automatiskt kopplade attribut väljer du det kopplade attributet på fliken **Kundfält** i tabellen. Attributen som utgör det sammankopplade attributet visas i två nya rader under det sammankopplade attributet.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separera, byta namn på, utesluta och redigera kopplade fält

Du kan ändra hur systemet bearbetar kopplade attribut för att skapa en enhetlig kundprofil. Välj **Visa fler** och välj vad du vill ändra.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Alternativ i listrutan Visa fler för att hantera kopplade attribut.":::

Mer information finns i följande avsnitt.

## <a name="separate-merged-fields"></a>Separera sammanslagna fält

Om du vill separera sammanslagna fält hittar du attributet i tabellen. Separerade fält visas som enskilda datapunkter i den enhetliga kundprofilen. 

1. Välj det sammanslagna fältet.
  
1. Välj **Visa fler** och välj **Separata fält**.
 
1. Bekräfta separationen.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna.

## <a name="rename-merged-fields"></a>Byta namn på kopplade fält

Ändra visningsnamn kopplade attribut. Du kan inte ändra namn på utdataentitet.

1. Välj det sammanslagna fältet.
  
1. Välj **Visa fler** och välj **Byt namn**.

1. Bekräfta det ändrade visningsnamnet. 

1. Välj **Spara** och **Kör** för att bearbeta ändringarna.

## <a name="exclude-merged-fields"></a>Utelämna sammanslagna fält

Utelämna ett attribut från den enhetliga kundprofilen. Om fältet används i andra processer, till exempel i ett segment, tar du bort det från dessa processer innan du utesluter det från kundprofilen. 

1. Välj det sammanslagna fältet.
  
1. Välj **Visa fler** och välj **Uteslut**.

1. Bekräfta uteslutningen.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna. 

På sidan **Sammanslå**, välj **Uteslutna fält** om du vill visa listan över alla uteslutna fält. I den här rutan kan du lägga till uteslutna fält bakåt.

## <a name="manually-combine-fields"></a>Kombinera fält manuellt

Ange ett kopplat attribut manuellt. 

1. På sidan **Sammanslå**, välj **Kombinera fält**.

1. Ange ett **Namn** och ett **Utdatafältsnamn**.

1. Välj ett fält att lägga till. Välj **Lägg till fält** för att kombinera fler fält.

1. Bekräfta uteslutningen.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna. 

## <a name="change-the-order-of-fields"></a>Ändra ordning på fält

Vissa entiteter innehåller mer information än andra. Om en entitet innehåller de senaste data om ett fält kan du prioritera den framför andra entiteter när du kopplar samman värden.

1. Välj det sammanslagna fältet.
  
1. Välj **Visa fler** och välj **Redigera**.

1. I rutan **Kombinera fält**, välj **Flytta upp/ned** för att ange ordning eller dra och släpp dem i önskad position.

1. Bekräfta ändringen.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna.

## <a name="run-your-merge"></a>Kör din koppling

Oavsett om du kopplar attribut manuellt eller låter systemet koppla ihop dem kan du alltid köra kopplingen. Välj **Kör** på sidan **Koppla** för att starta processen.

> [!div class="mx-imgBorder"]
> ![Datakoppling Spara och kör.](media/configure-data-merge-save-run.png "Datakoppling Spara och kör")

Välj **Kör endast sammanslagning** om du bara vill visa utdata som reflekteras i entiteten för en enhetlig kund. Processer nedströms uppdateras enligt vad som [definieras i uppdateringsschemat](system.md#schedule-tab).

Välj **Kör sammanslagnings- och nedströmsprocesser** om du vill uppdatera systemet med ändringarna. Alla processer, inklusive berikning, segment och åtgärder, körs om automatiskt. När alla processer nedströms har slutförts återspeglar kundprofilerna alla ändringar du har gjort.

Om du vill göra fler ändringar och köra steget igen kan du avbryta en pågående koppling. Välj **Uppdatera...** och välj **Avbryt jobb** i sidorutan som visas.

> [!TIP]
> När du har kört kopplingsprocessen markerar du processtatusen och öppnar rutan **Uppgiftsinformation**. Den ger en översikt över bearbetningstiden, sista bearbetningsdatum och alla fel och varningar som är associerade med uppgiften. vÄLJ **vISA INFORMATION** om du vill se vilka entiteter som deltog i matchningsprocessen, om konfliktlösningen lyckades och om uppdateringarna publicerades korrekt.  
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Detaljerad sökväg för att komma åt processinformation från uppgiftsstatuslänken.":::

## <a name="next-step"></a>Nästa steg

Konfigurera [aktiviteter](activities.md), [berikning](enrichment-hub.md)eller [relationer](relationships.md) till mer information om kunderna.

Om du redan har konfigurerat aktiviteter, utökar eller segment, bearbetas de automatiskt för att använda de senaste kunddata.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
