---
title: Välj källfält för samordning av data
description: Det första steget i föreningsprocessen är att välja entiteter, attribut, primära nycklar och lösningstyper för att mappa data till Unified customer profile.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741017"
---
# <a name="select-source-fields-for-data-unification"></a>Välj källfält för samordning av data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Det första steget i frågan är att välja vilka entiteter och fält i dina datauppsättningar som du vill ena. Välj entiteter som innehåller kundrelaterad information, t.ex. namn, adress, telefonnummer och e-post. Du kan välja en eller flera entiteter.

## <a name="select-entities-and-fields"></a>Välj entiteter och fält

1. Gå till **Data** > **Förena**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Skärmbild på en ena landningssida för första körningen med Komma igång för första gången.":::

1. Välj **Komma igång**.

1. På sidan **Källfält**, välj **Välj enheter och fält**. Rutan **Välj entiteter och fält** visas.

1. Välj minst en entitet.

1. Identifiera de fält du vill använda för varje vald entitet för att matcha kundposter och fält som ska ingå i den enhetliga profilen. Dessa fält kallas *Attribut*. Du kan välja vilka attribut som krävs individuellt från en entitet eller ta med alla attribut från en entitet genom att markera kryssrutan på entitetsnivå. Du kan söka på nyckelord för alla attribut och entiteter för att välja vilka attribut som ska mappas.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Skärmbild av markerade entiteter och attribut.":::

   I det här exemplet lägger vi till entiteterna **Kontakter** och **CustomerLoyalty**. Genom att välja de här entiteterna kan du få insikter om vilka av de online-kunder som är medlemmar i ett förmånsprogram.

1. Välj **Bekräfta** för att bekräfta dina val. Markerade entiteter och attribut visning.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Välj primär nyckel och semantisk typ för attribut

   :::image type="content" source="media/m3_select_primary.png" alt-text="Skärmbild av markerade entiteter där primärnyckeln inte är markerad." lightbox="media/m3_select_primary.png":::

Utför följande steg för varje entitet.

1. Välj **primärnyckel**. Den primära nyckeln är ett attribut som är unikt för entiteten. För att ett attribut ska vara en giltig primär nyckel bör det inte innehålla dubblettvärden, saknade värden och null-värden. Sträng-, heltals- och GUID-datatypattribut stöds som primärnycklar.

1. För att använda AI-modeller för smart förutsägelse av semantik, spara tid och förbättra noggrannheten, se till **Intelligent mappning** är på. Intelligent mappningen visar rekommendation av AI-baserad semantik i fältet **Typ**. Du kan åsidosätta det föreslagna valet genom att välja en valfri typ i den tillgängliga listan med alternativ.

1. Välj en semantik för varje attribut **Typ** som bäst beskriver det attributet, som namn, stad eller e-postadress.

   > [!NOTE]
   > Ett fält bör mappas till typen *Person.FullName* för att fylla kundnamnet i kundkorten. Annars visas inget namn på kundkorten.

   1. För att ändra en attributtyp som identifierats av systemet, välj en annan typ. Om typen inte finns kan du skapa en anpassad **typ** av teckentyp genom att välja typfältet för attributet och ange namnet på din anpassade typ.

   1. Om du vill lägga till ett attribut som innehåller en URL till offentliga profilbilder eller logotyper väljer du den entitet och det fält som innehåller URL:en. I fältet **Typ**, ange följande:
      - För en person: Person.ProfileImage
      - För en organisation: Organization.LogoImage

   1. För ett kontonamnsattribut anger du "Organization.Name" i **Typ**.

1. Granska attributen där en attributtyp identifieras automatiskt. Dessa attribut visas under **Granska mappade fält**. Endast attribut med samma typ kan kombineras i steget **Förenade kundfält**. Olika typer av tecken används för att automatiskt föreslå insikter. Se till att de typer du väljer är enhetliga för alla markerade entiteter.

1. För attribut som inte automatiskt mappas till en semantisk typ, välj ett semantisk typfält, ange ditt anpassade attributtypnamn eller lämna dem omappade. De här attributen visas under **Definiera data i de omappade fälten**.

1. När du har slutfört stegen för varje entitet, välj **Spara källfält**.

1. Välj **Nästa**.

> [!div class="nextstepaction"]
> [Nästa steg: Ta bort dubbletter](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
