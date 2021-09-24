---
title: Slå samman entiteter i datasammanslutningen
description: Slå samman entiteter för att skapa enhetliga kundprofiler.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494341"
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

1. Markera ett sammanslaget fält.
  
1. Välj **Visa fler** och välj **Uteslut**.

1. Bekräfta uteslutningen.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna. 

På sidan **Sammanslå**, välj **Uteslutna fält** om du vill visa listan över alla uteslutna fält. I den här rutan kan du lägga till uteslutna fält bakåt.

## <a name="edit-a-merged-field"></a>Redigera ett sammanslaget fält

1.  Markera ett sammanslaget fält.

1.  Välj **Visa fler** och välj **Redigera**.

1.  Ange hur fälten ska kombineras eller slås samman från ett av tre alternativ:
    - **Betydelse**: Identifierar det vinnande värdet baserat på det prioritetsvärde som angetts för de deltagande fälten. Det här är standardalternativet för sammanfogning. Välj **Flytta upp/ned** för att ange prioritet.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Alternativet Prioritet i dialogrutan för att slå samman fält."::: 
    - **Senaste:** Identifierar det vinnande värdet baserat på aktualitet. Kräver ett datum eller ett numeriskt fält för varje deltagande entitet i omfånget för att slå samman fält för att definiera aktualitet.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Alternativet Aktualitet i dialogrutan för att slå samman fält.":::
    - **Minst aktuell**: Identifierar det vinnande värdet baserat på minsta aktualitet. Kräver ett datum eller ett numeriskt fält för varje deltagande entitet i omfånget för att slå samman fält för att definiera aktualitet.

1.  Du kan lägga till ytterligare fält som ska delta i sammanslagningsprocessen.

1.  Du kan byta namn på det sammanslagna fältet.

1. Välj **Klart** för att införa ändringarna.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna. 

## <a name="manually-combine-fields"></a>Kombinera fält manuellt

Ange ett kopplat attribut manuellt. 

1. På sidan **Sammanslå**, välj **Kombinera fält**.

1. Ange policy för sammanslående i listrutan **Kombinera fält efter**.

1. Välj ett fält att lägga till. Välj **Lägg till fält** för att kombinera fler fält.

1. Ange ett **Namn** och ett **Utdatafältsnamn**.

1. Välj **Klart** för att införa ändringarna.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna. 

## <a name="change-the-order-of-fields"></a>Ändra ordning på fält

Vissa entiteter innehåller mer information än andra. Om en entitet innehåller de senaste data om ett fält kan du prioritera den framför andra entiteter när du kopplar samman värden.

1. Välj det sammanslagna fältet.
  
1. Välj **Visa fler** och välj **Redigera**.

1. I rutan **Kombinera fält**, välj **Flytta upp/ned** för att ange ordning eller dra och släpp dem i önskad position.

1. Bekräfta ändringen.

1. Välj **Spara** och **Kör** för att bearbeta ändringarna.

## <a name="configure-customer-id-generation"></a>Konfigurera generering av kund-ID 

När du har konfigurerat sammanslagningsfält kan du definiera hur värden för kund-ID ska genereras, de unika kundprofil-identifierarna. Sammanslagningssteget i datasamordningsprocessen genererar den unika kundprofilidentifieraren. Identifieraren är kund-ID:t i entiteten *Kund* som resulterar ur datasamordningsprocessen. 

Kund-ID:t i entiteten Kund baseras på ett hash med det första värdet för primärnycklarna som inte är null. Dessa nycklar kommer från de entiteter som används i matchnings- och sammanslagningsfasen och beror på matchningsordningen. Genererat kund-ID kan därför ändras när ett primärt nyckelvärde ändras i den primära entiteten i matchningsordningen. Därför kanske det primära nyckelvärdet inte alltid motsvarar samma kund.

Genom att konfigurera ett stabilt kund-ID kan du undvika detta beteende.

**Konfigurera ett unikt kund-ID**

1. Gå till **Förena** > **Sammanslå**.

1. På sidan **Sammanslå** väljer du fliken **Nycklar**. 

1. Håll markören över raden **CustomerId** och markera alternativet **Konfigurera**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontroll för att anpassa ID-genereringen.":::

1. Välj upp till fem fält som ska utgöra ett unikt kund-ID och som är stabilare. För poster som inte överensstämmer med konfigurationen används ett systemkonfigurations-ID i stället.  

1. Välj **Klar** och kör sammanslagningsprocessen för att tillämpa ändringarna.

## <a name="run-your-merge"></a>Kör din koppling

Oavsett om du kopplar attribut manuellt eller låter systemet koppla ihop dem kan du alltid köra kopplingen. Välj **Kör** på sidan **Koppla** för att starta processen.

> [!div class="mx-imgBorder"]
> ![Datakoppling Spara och kör.](media/configure-data-merge-save-run.png "Datakoppling Spara och kör")

Välj **Kör endast sammanslagning** om du bara vill visa utdata som reflekteras i entiteten för en enhetlig kund. Processer nedströms uppdateras enligt vad som [definieras i uppdateringsschemat](system.md#schedule-tab).

Välj **Kör sammanslagnings- och nedströmsprocesser** om du vill uppdatera systemet med ändringarna. Alla processer, inklusive berikning, segment och åtgärder, körs om automatiskt. När alla processer nedströms har slutförts återspeglar kundprofilerna alla ändringar du har gjort.

Om du vill göra fler ändringar och köra steget igen kan du avbryta en pågående koppling. Välj **Uppdatera…** och välj **Avbryt jobb** i sidorutan som visas.

> [!TIP]
> När du har kört kopplingsprocessen markerar du processtatusen och öppnar rutan **Uppgiftsinformation**. Den ger en översikt över bearbetningstiden, sista bearbetningsdatum och alla fel och varningar som är associerade med uppgiften. vÄLJ **vISA INFORMATION** om du vill se vilka entiteter som deltog i matchningsprocessen, om konfliktlösningen lyckades och om uppdateringarna publicerades korrekt.  
> Det finns [sex typer av status](system.md#status-types) för uppgifter/processer. Dessutom är de flesta processer [beroende av andra efterföljande processer](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Detaljerad sökväg för att komma åt processinformation från uppgiftsstatuslänken.":::

## <a name="next-step"></a>Nästa steg

Konfigurera [aktiviteter](activities.md), [berikning](enrichment-hub.md)eller [relationer](relationships.md) till mer information om kunderna.

Om du redan har konfigurerat aktiviteter, utökar eller segment, bearbetas de automatiskt för att använda de senaste kunddata.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
