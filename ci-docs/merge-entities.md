---
title: Gör kundfälten enhetliga för dataförening
description: Slå samman entiteter för att skapa enhetliga kundprofiler.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081946"
---
# <a name="unify-customer-fields-for-data-unification"></a>Gör kundfälten enhetliga för dataförening

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

I det här steget i processen väljer du och utesluter attribut som ska sammanfogas i din enhetliga profilentitet. Om det till exempel finns tre entiteter med e-postdata kanske du vill behålla alla tre separata e-postfält eller koppla dem till ett enda e-postfält för den enhetliga profilen. Vissa attribut kombineras automatiskt av systemet. Du kan skapa stabilt och unikt kund-ID och gruppera relaterade profiler i ett kluster.

:::image type="content" source="media/m3_unify.png" alt-text="Sammanslå sida i dataförlopp som visar tabell med kopplade fält som definierar den enhetliga kundprofilen.":::

## <a name="review-and-update-the-customer-fields"></a>Granska och uppdatera kundfält

1. Granska listan över fält som ska vara enhetliga under fliken **Kundfält** i tabellen. Gör eventuella ändringar.

   1. För alla kombinerade fält kan du:
      - [Redigera](#edit-a-merged-field)
      - [Byt namn](#rename-fields)
      - [Separat](#separate-merged-fields)
      - [Exkludera](#exclude-fields)
      - [Flytta upp eller ned](#change-the-order-of-fields)

   1. För alla enskilda fält kan du:
      - [Kombinera fält](#combine-fields-manually)
      - [Kombinera grupp med fält](#combine-a-group-of-fields)
      - [Byt namn](#rename-fields)
      - [Exkludera](#exclude-fields)
      - [Flytta upp eller ned](#change-the-order-of-fields)

1. Alternativt, [generera kund-ID-konfigurationen](#configure-customer-id-generation).

1. Alternativt, [gruppera profiler i hushåll eller kluster](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Nästa steg: Granska sammanslagningen](review-unification.md)

### <a name="edit-a-merged-field"></a>Redigera ett sammanslaget fält

1. Välj ett kopplat fält och välj **Redigera**. Rutan Kombinera fält visas.

1. Ange hur fälten ska kombineras eller slås samman från ett av tre alternativ:
    - **Betydelse**: Identifierar det vinnande värdet baserat på det prioritetsvärde som angetts för de deltagande fälten. Det här är standardalternativet för sammanfogning. Välj **Flytta upp/ned** för att ange prioritet.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Alternativet Prioritet i dialogrutan för att slå samman fält.":::

    - **Senaste:** Identifierar det vinnande värdet baserat på aktualitet. Kräver ett datum eller ett numeriskt fält för varje deltagande entitet i omfånget för att slå samman fält för att definiera aktualitet.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Alternativet Aktualitet i dialogrutan för att slå samman fält.":::

    - **Minst aktuell**: Identifierar det vinnande värdet baserat på minsta aktualitet. Kräver ett datum eller ett numeriskt fält för varje deltagande entitet i omfånget för att slå samman fält för att definiera aktualitet.

1. Du kan lägga till fler fält för att delta i sammanfogningsprocessen.

1. Du kan byta namn på det sammanslagna fältet.

1. Välj **Klart** för att införa ändringarna.

### <a name="rename-fields"></a>Ändra namn på fälten

Ändra visningsnamn kopplade eller separata fält. Du kan inte ändra namn på utdataentitet.

1. Välj fältet och välj **Byt namn**.

1. Ange det nya visningsnamnet.

1. Välj **Utfört**.

### <a name="separate-merged-fields"></a>Separera sammanslagna fält

Om du vill separera sammanslagna fält hittar du attributet i tabellen. Separerade fält visas som enskilda datapunkter i den enhetliga kundprofilen.

1. Markera det kopplade fältet och välj **Separata fält**.

1. Bekräfta separationen.

### <a name="exclude-fields"></a>Utelämna fält

Utelämna ett kopplat eller separat fält från Unified customer profile. Om fältet används i andra processer, till exempel i ett segment, tar du bort det från dessa processer innan du utesluter det från kundprofilen.

1. Välj ett fält och välj **Utelämna**.

1. Bekräfta uteslutningen.

Om du vill visa listan över alla uteslutna fält väljer du **Utelämnade fält**. Du kan läsa det utelämnade fältet om det behövs.

### <a name="change-the-order-of-fields"></a>Ändra ordning på fält

Vissa entiteter innehåller mer information än andra. Om en entitet innehåller de senaste data om ett fält kan du prioritera den framför andra entiteter när du kopplar samman värden.

1. Välj fältet.
  
1. Välj **Flytta upp/ned** för att ange ordern eller dra och släpp dem i önskad position.

### <a name="combine-fields-manually"></a>Kombinera fält manuellt

Kombinera avgränsade fält och skapa ett kopplat attribut.

1. Välj **Kombinera** > **Fält**. Rutan Kombinera fält visas.

1. Ange policy för sammanslående i listrutan **Kombinera fält efter**.

1. Välj **Lägg till fält** att kombinera fler områden.

1. Ange ett **Namn** och ett **Utdatafältsnamn**.

1. Välj **Klart** för att införa ändringarna.

### <a name="combine-a-group-of-fields"></a>Kombinera grupp med fält

En grupp fält används som en enskild enhet. Om posterna till exempel innehåller fälten Adress 1, Adress2, Ort, Delstat och Postnummer, vill vi inte koppla till en annan posts Adress2, eftersom vi tror att informationen blir mer fullständig.

1. Välj **Kombinera** > **Grupp av fält**.

1. Ange policy för sammanslående i listrutan **Rangordna grupper efter**.

1. Välj **Lägg till** och välj om du vill lägga till fler fält eller grupper till fälten.

1. Ange ett **namn** och ett **utdatanamn** för alla kombinerade fält.

1. Ange ett **namn** för gruppen av fält.

1. Välj **Klart** för att införa ändringarna.

## <a name="configure-customer-id-generation"></a>Konfigurera generering av kund-ID

Ange hur värden för kund-ID ska genereras, de unika kundprofil-ID:erna. Ett steg i processen för att ena fält genererar den unika kundprofil-ID:t. Identifieraren är *CustomerId* i entiteten *Kund* som resulterar ur datasamordningsprocessen.

*CustomerId* baseras på en hash av det första värdet av de primärnycklar som inte är nollvinnare. Nycklarna kommer från entiteterna som används i data och används sedan i matchningsordningen.Kund-ID:t som genereras kan därför ändras när ett primärnyckelvärde ändras i den primära entiteten i matchningsordningen. Därför kanske inte värdet för den primära nyckeln alltid motsvarar samma kund.

Genom att konfigurera ett stabilt kund-ID kan du undvika detta beteende.

1. Välj fliken **Nycklar**.

1. Håll markören på raden **CustomerId** och välj **Konfigurera**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontroll för att anpassa ID-genereringen.":::

1. Välj upp till fem fält som ska utgöra ett unikt kund-ID och som är stabilare. För poster som inte överensstämmer med konfigurationen används ett systemkonfigurations-ID i stället.  

1. Välj **Utfört**.

## <a name="group-profiles-into-households-or-clusters"></a>Gruppera profiler i organisationer som är för sig eller i kluster

Du kan definiera regler för att gruppera relaterade profiler i ett kluster. Det finns för närvarande två typer av kluster tillgängliga – förkluster och anpassade kluster. Systemet väljer automatiskt att använda fördefinierade regler om entiteten *Kund* innehåller de semantiska fälten *Person.LastName* och *Location.Address*. Du kan också skapa ett kluster med dina egna regler och villkor, på samma sätt som med [matchningsregler](match-entities.md#define-rules-for-match-pairs).

1. Välj **Avancerad** > **Skapa kluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontroll för att skapa ett nytt kluster.":::

1. Välj mellan ett kluster för **Hushåll** eller ett **Anpassat** kluster. Om fältet *Person.LastName* och *Location.Address* finns i entiteten *Kund* väljs automatiskt.

1. Ange ett namn på klustret och välj **Klar**.

1. Markera fliken **Kluster** för att hitta klustret du skapat.

1. Ange regler och villkor för att definiera klustret.

1. Välj **Utfört**. Klustret skapas när sammanslagningsprocessen är klar. Kluster-ID:erna till som nya fält i entiteten *kund*.

> [!div class="nextstepaction"]
> [Nästa steg: Granska sammanslagningen](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
