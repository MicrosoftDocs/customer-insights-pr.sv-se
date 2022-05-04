---
title: Mappa entiteter och attribut för samordning av data
description: Välj entiteter, attribut, primära nycklar och typer av attribut för mappning av data till den enhetliga kundprofilen.
ms.date: 10/18/2020
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bebc600e91db471c3cd50eccb5e42be309ff09c9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647600"
---
# <a name="map-entities-and-attributes"></a>Mappa entiteter och attribut

**Mappning** är det första stadiet i föreningsprocessen för data. Mappningen består av tre faser:

- *Entitetsurval*: identifiera de entiteter som leder till en datauppsättning med mer fullständig information om kunderna.
- *Val av attribut*: identifiera kolumnerna som du vill kombinera och stämma av i faserna *matchning* och *koppling* för varje entitet. Dessa kolumner kallas *Attribut*.
- *Primär nyckel och semantisk typ markering*: för varje entitet identifierar du ett attribut som du vill definiera som primär nyckel för den entiteten och identifierar en semantisk typ som bäst beskriver attributet.

Mer information om det allmänna flödet av dataförening finns i [förena](data-unification.md).

## <a name="select-the-first-entities"></a>Välj de första entiteterna

1. Gå till **Data** > **Förena** > **Mappa**.

2. Starta mappningsfasen genom att välja **Välj entiteter**.

3. Välj de entiteter och attribut du vill använda i faserna *matchning* och *koppla*. Du kan välja de attribut som krävs separat från en entitet eller ta med alla attribut från en entitet genom att markera kryssrutan **Inkludera alla fält** på entitetsnivån. Vi rekommenderar att du väljer minst två entiteter att dra nytta av föreningsprocessen för data.

   > [!div class="mx-imgBorder"]
   > ![Lägg till entitetsexempel.](media/data-manager-configure-map-add-entities-example.png "Lägg till entitetsexempel")

   I det här exemplet lägger vi till entiteterna **eCommerceContacts** och **loyCustomers**. Genom att välja de här entiteterna kan du få insikter om vilka av de online-kunder som är medlemmar i ett förmånsprogram.
   
   Du kan söka på nyckelord för alla attribut och entiteter för att välja vilka attribut som ska mappas.
   
     > [!div class="mx-imgBorder"]
   > ![Exempel på sökfält.](media/data-manager-configure-map-search-fields-example.png "Exempel på sökfält")

4. Välj **Bekräfta** för att bekräfta dina val.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Välj primär nyckel och semantisk typ för attribut

När du har valt entiteter **Karta** visas de valda entiteterna i översiktssidan för recensionen. Definiera primär nyckeln för en entitet och identifiera semantisk typ för ett attribut i entiteten.

- **Primärnyckel**: Markera ett attribut som primärnyckel för varje entitet. För att ett attribut ska vara en giltig primär nyckel bör det inte innehålla dubblettvärden, saknade värden och null-värden. Attribut av typen sträng, heltal och GUID-datatyp stöds som primära nycklar och visas i ett fält där du kan välja från.

- **Attribut semantisk typ**: kategorier för attribut, t.ex. e-postadress eller namn. Om du vill använda AI-modeller för smart prediktion av semantik, spara tid och förbättra precisionen, anger du **Intelligent mappning** till **PÅ**. Intelligent mappningen visar rekommendation av AI-baserad semantik i fältet **Typ**. Om du väljer **AV** ser du våra rekommendationer för regelbunden mappning. Du kan välja valfri semantisk typ i listan med tillgängliga alternativ och ersätta det föreslagna urvalet.

> [!div class="mx-imgBorder"]
> ![Attributtyp och semantisk förutsägelse.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtyp och semantisk prediktion")

Det går också att lägga till en anpassad entitetstyp. Välj typfältet för ett attribut och ange namnet på den anpassade semantiska typen. PÅ så sätt kan du också ändra vilka attributtyper som identifieras av systemet.

Alla attribut för vilka en semantisk typ identifieras identifieras automatiskt i avsnittet **granska mappade fält**. Granska attributen och deras semantiska typer eftersom de används för att kombinera entiteterna i kopplingssteget av dataföreningen.

Attribut som inte mappas automatiskt till en semantisk typ grupperas i **definiera data i avsnittet omappade fält**. Välj fältet semantisk typ för de omappade attributen eller ange ett eget namn för attributtypen.

> [!div class="mx-imgBorder"]
> ![Primärnyckel och attributtyp.](media/data-manager-configure-map-add-attributes.png "Primärnyckel och attributtyp")

> [!NOTE]
> Ett fält ska mappas till den semantiska typen Person.FullName som fyller i kundnamnet på kundkortet. Annars visas inget namn på kundkorten. 

## <a name="add-and-remove-attributes-and-entities"></a>Lägga till och ta bort attribut och entiteter

1. I **Förena** > **Karta**, välj **Redigera fält**.

2. I rutan **Redigera fält** lägger du till eller tar bort attribut och entiteter. Använd sökningen eller bläddra för att hitta och välja dina attribut och enheter av intresse. Du kan inte ta bort ett attribut eller en entitet om de redan har matchats.

   > [!div class="mx-imgBorder"]
   > ![Lägg till eller ta bort attribut.](media/configure-data-map-edit.png "Lägg till eller ta bort attribut")

3. Välj **tillämpa**.

## <a name="add-images-to-profiles"></a>Lägg till bilder i profiler

Om en entitet innehåller URL:er till allmänt tillgängliga profilbilder eller logotyper kan du lägga till dem i den enhetliga kundprofilen.

Välj entiteten och leta upp det fält som innehåller URL-adressen till profilbilden. I inmatningsfältet **Typ** anger du manuellt följande värde: 
- För en person: Person.ProfileImage
- För en organisation: Organization.LogoImage

Fortsätt med föreningsstegen och se till att attributet som innehåller bild-URL också läggs till i steget [sammanslagning](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Ange attribut för organisationer

För organisationer (förhandsgranskning) ska attributtypen mappas till "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Primärnyckel och attributtyp B2B.](media/configure-data-map-edit-b2b.png "Primärnyckel och attributtyp B2B")

## <a name="next-step"></a>Nästa steg

Som en del av föreningsprocessen för dat går du till sidan **matchning**. Besök [**matchning**](match-entities.md) om du vill ha mer information om den här fasen.

> [!TIP]
> Se följande videoklipp: [komma igång: skapa en enhetlig kundprofil](https://youtu.be/oBfGEhucAxs).


[!INCLUDE [footer-include](includes/footer-banner.md)]