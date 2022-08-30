---
title: Välj källfält för samordning av data
description: Det första steget i föreningsprocessen är att välja entiteter, attribut, primära nycklar och lösningstyper för att mappa data till Unified customer profile.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304587"
---
# <a name="select-source-fields-for-data-unification"></a>Välj källfält för samordning av data

Det första steget i frågan är att välja vilka entiteter och fält i dina datauppsättningar som du vill ena. Välj entiteter som innehåller kundrelaterad information, t.ex. namn, adress, telefonnummer och e-post. Du kan välja en eller flera entiteter.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Välj entiteter och fält

1. Gå till **Data** > **Förena**.

   För enskilda kunder (B2C), visar landningssidan **Förena** **Komma igång** på det första steget **Källfält**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Skärmbild på en ena landningssida för första körningen för enskilda kunder.":::

   För affärskonon (B2B), visar landningssidan **Förena** **Förena konton** med **Komma igång** på det första steget **Källfält**. Stegen **Förena kontakter (förhandsversion)** är valfria och väntar på att kontot ska slutföras.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Skärmbild på en ena landningssida för första körningen för affärskonton.":::

1. Välj **Komma igång**.

1. På sidan **Källfält**, välj **Välj enheter och fält**. Rutan **Välj entiteter och fält** visas.

1. Välj minst en entitet.

1. Identifiera de fält du vill använda för varje vald entitet för att matcha kundposter och fält som ska ingå i den enhetliga profilen. Dessa fält kallas *Attribut*. Du kan välja vilka attribut som krävs individuellt från en entitet eller ta med alla attribut från en entitet genom att markera kryssrutan på entitetsnivå. Du kan söka på nyckelord för alla attribut och entiteter för att välja vilka attribut som ska mappas.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Skärmbild av markerade entiteter och attribut.":::

   I det här exemplet lägger vi till entiteterna **eCommerceContacts** och **loyCustomer**. Genom att välja de här entiteterna kan du få insikter om vilka av de online-kunder som är medlemmar i ett förmånsprogram.

1. Välj **Bekräfta** för att bekräfta dina val. Markerade entiteter och attribut visning.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Välj primär nyckel och semantisk typ för attribut

   :::image type="content" source="media/m3_select_primary.png" alt-text="Skärmbild av markerade entiteter där primärnyckeln inte är markerad." lightbox="media/m3_select_primary.png":::

Utför följande steg för varje entitet.

1. Välj **primärnyckel**. Den primära nyckeln är ett attribut som är unikt för entiteten. För att ett attribut ska vara en giltig primär nyckel bör det inte innehålla dubblettvärden, saknade värden och null-värden. Sträng-, heltals- och GUID-datatypattribut stöds som primärnycklar.

1. För att använda AI-modeller för smart förutsägelse av semantik, spara tid och förbättra noggrannheten, se till **Intelligent mappning** är på. Intelligent mappningen ger rekommendation av AI-baserad semantik i fältet **Typ**.

1. Välj en semantik för varje attribut **Typ** som bäst beskriver det attributet, som namn, stad eller e-postadress.

   > [!NOTE]
   > I B2C bör ett fält mappas till typen *Person.FullName* för att fylla kundnamnet i kundkorten. I B2B ska kontonamnet mappa till *Organization.Name*. Annars visas inget namn på kundkorten.

   1. För att åsidosätta en attributtyp som identifierats av systemet, välj ett annat alternativ. Om typen inte finns kan du skapa en anpassad **typ** av teckentyp genom att välja typfältet för attributet och ange namnet på din anpassade typ.

   1. Om du vill lägga till ett attribut som innehåller en URL till offentliga profilbilder eller logotyper väljer du den entitet och det fält som innehåller URL:en. I fältet **Typ**, ange följande:
      - För en person: Person.ProfileImage
      - För en organisation: Organization.LogoImage

1. Granska attributen där en attributtyp identifieras automatiskt. Dessa attribut visas under **Granska mappade fält**. Endast attribut med samma typ kan kombineras i steget **Förenade kundfält**. Olika typer av tecken används för att automatiskt föreslå insikter. Se till att de typer du väljer är enhetliga för alla markerade entiteter.

1. För attribut som inte automatiskt mappas till en semantisk typ, välj ett semantisk typfält, ange ditt anpassade attributtypnamn eller lämna dem omappade. De här attributen visas under **Definiera data i de omappade fälten**.

1. När du har slutfört stegen för varje entitet, välj **Spara källfält**.

1. Välj **Nästa**.

> [!div class="nextstepaction"]
> [Nästa steg: Ta bort dubbletter](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
