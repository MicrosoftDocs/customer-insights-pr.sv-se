---
title: Trattrapporter
description: Använda trattrapporter för att förstå hur målgruppen fattar beslut.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7bb961c5ba8d42f704eefe0dcb22e561367f3efb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226283"
---
# <a name="create-and-manage-funnel-reports"></a>Skapa, distribuera och hantera trattrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I en trattrapport samlas information om de steg som sker i samband med kundens färd via webbplatsen eller mobilappen. Det hjälper dig att förstå hur målgruppen passerar en process och identifierar avsläppningsplatsen. Du kan till exempel använda en trattrapport för att identifiera sökvägar som kunderna tar innan de gör ett köp. I en trattrapport finns data som informerar om beslut och identifierar områden för optimering och processförbättringar.

## <a name="create-a-funnel-report"></a>Skapa en trattrapport

Om du vill skapa trattrapporten anger du de steg du vill ta med och aktiviteten för varje steg. En aktivitet är en [händelse](glossary.md) som representerar användarbeteende. I trattrapporten visas antalet användare som har slutfört varje definierat steg. 

1. Gå till **Trattar** och välj **+Ny tratt** för att starta en trattrapport.

1. I **Trattredigerare**, under **Steg** välj **+Lägg till steg.** 

1. Ange ett namn i **Stegrubriken**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Ny &quot;tratt&quot;-rapport.":::

1. Välj en **Aktivitet**. En aktivitetspost när en användare visar en sida (aktiviteten **Visa**) eller interagerar med innehåll (aktiviteten **Åtgärd**).

1. Använd **stegvillkor** för att ange aktivitetens storlek. [Dimensioner](dimensions.md) är attribut som kan beskriva, filtrera eller gruppera data.

1. Alternativt kan du konfigurera trattsteg med flera villkor. Välj **Lägg till villkor** för att ange fler dimensioner i ett steg. Ytterligare villkor måste använda samma aktivitetstyp. Du kan välja om flera villkor är kopplade till en OCH- eller en ELLER-operator.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Trattredigerare som visar stegkonfigurationen med steg med flera villkor.":::

1. Välj **Lägg till steg** tills du har slutfört alla steg du vill ha i rapporten.

1. Välj **Spara**, ge rapporten ett namn och **Spara** den igen. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Exempel: Fourth Coffee trattrapport för företaget

Följande scenario visar ett sätt att använda en trattrapport. En analytiker på företaget Fourth Coffee vill förstå hur en kampanj har påverkat prenumerationsgraden. Analytikern skapar en trattrapport för att identifiera kundaktiviteten. Det startar när kunderna kommer till företagets startsida tills de använder kampanjkoden för prenumerationen. Analytikern skapar en trattrapport med följande steg:

Steg 1: Kunder som landar på startsidan   
Steg 2: Kunder som gör ett köp   
Steg 3: Kunder som använder kampanjkoden för att få rabatt på en prenumeration   
Steg 4: Registrering av prenumeration   

:::image type="content" source="media/funnel-report-example.png" alt-text="exempel på &quot;trattrapport&quot;.":::
  
I den här tratten visas antalet användare som har använt kampanjkoden efter ett köp en gång för att registrera sig för prenumerationsprogrammet.

### <a name="configure-advanced-settings"></a>Konfigurera avancerade inställningar 

Med trattrapporter kan du definiera en begränsning på den tid det tar att slutföra en tratt. Du kan till exempel ange tiden det tar för tratten att slutföras till fyra dagar. Den här inställningen räknar endast lyckade prenumerationsregistreringar som inträffat inom fyra dagar efter det att en användare har besökt startsidan.

1. Gå till **Trattar** för att öppna **Trattbibliotek**.

1. Välj ett namn för att öppna rapporten. 

1. I fönstret **Trattredigerare** väljer du **Avancerade inställningar**. 

1. Ställ in Begränsa trattslutförande tid på **På**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Trattredigeraren visar avancerad inställning och alternativ för att begränsa tiden för att slutföra en tratt.":::

1. Välj den tid som tratten måste ha slutförts i listrutan **Ange begränsning som**.

1. Välj **Spara** för att införa ändringarna.


## <a name="cross-channel-funnel-reports"></a>Trattrapporter över flera kanaler 

Engagemangsinsikter kan också samla in beteendekunddata i mobilappen. När du har instrumenterat mobilappen med engagemangsinsikterna [Android SDK](get-started-android.md) eller [iOS SDK](get-started-ios.md) kan du skapa trattrapporter över flera kanaler. 

### <a name="create-a-cross-channel-funnel-report"></a>Skapa en trattrapport över flera kanaler 

1. Följ stegen för att [skapa en trattrapport](#create-a-funnel-report).    

1. Om du vill spåra hur kunderna interagerar med ditt varumärke på både webbplatsen och i mobilappen – eller flera webbplatser – använder du arbetsyteväxlaren för att skapa trattsteg med data från andra arbetsytor. I **Trattredigeraren**, under **Steg**, väljer du den arbetsyta som datan för ditt trattsteg ska komma ifrån.

## <a name="manage-funnel-reports"></a>Hantera trattrapporter

Du kan granska trattrapporter och analysera data, spåra prestanda och samla in insikter.

> [!NOTE]
> - Engagemangsinsikter i trattrapporter stöder för närvarande scenarier där alla användare i tratten är anonyma eller alla användare autentiseras. 
> - Tidigare data i trattrapporter är tillgängliga de senaste 30 dagarna.

### <a name="view-funnel-reports"></a>Visa trattrapporter

1. Gå till **Trattar** för att öppna **Trattbibliotek**.
1. Välj ett namn för att öppna rapporten.    

### <a name="see-the-data-collected-for-a-report"></a>Visa insamlade data för en rapport   

Visa information om en fas

- Peka på ett steg i rapporten.

:::image type="content" source="media/funnel-step-data.png" alt-text="&quot;trattdata&quot;.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Ändra datumintervall för trattrapporten

1. Gå till **Trattar** för att öppna **Trattbibliotek**.

1. Välj ett namn för att öppna rapporten.

1. Öppna **tidsintervall** och välj en ny tidsperiod i listan eller **Fast datumintervall** om du vill ange ett datumintervall.

## <a name="edit-or-delete-funnel-reports"></a>Redigera eller ta bort trattrapporter

Du kan ändra namnet på en trattrapport, ta bort den eller ändra stegen i rapporten.

### <a name="rename-or-delete-a-funnel-report"></a>Byta namn på eller ta bort en trattrapport

1. Gå till **Trattar** för att öppna **Trattbibliotek**. 

1. Markera **Fler** bredvid den rapport du vill ändra och välj **Redigera namn** eller **Ta bort**.

### <a name="edit-a-funnel-step"></a>Redigera ett trattsteg  

1. Gå till **Trattar** för att öppna **Trattbibliotek**. 

1. Välj ett namn för att öppna rapporten.

1. Välj ett steg som du vill redigera.

1. Välj **Redigera**.

1. I **Trattredigerare** uppdaterar du den information du vill ändra.  

1. Välj **Spara**.

### <a name="reorder-a-funnel-step"></a>Beställ om ett trattsteg

1. Gå till **Trattar** för att öppna **Trattbibliotek**. 

1. Välj ett namn för att öppna rapporten.

1. Välj ett steg som du vill beställa om.

1. Välj **Flytta** och sedan **Upp**, **Ned**, **Till början** eller **Till slutet**, för att flytta steget.

### <a name="delete-a-funnel-step"></a>Ta bort ett trattsteg

1. Gå till **Trattar** för att öppna **Trattbibliotek**. 

1. Välj ett namn för att öppna rapporten.

1. Markera steget du vill ta bort och välj sedan **Ta bort**.

## <a name="funnel-insights"></a>Trattinsikter 

Engagemangsinsikter erbjuder nu trattinsikter för kunder. Använd trattinsikter om du vill få en djupare inblick i kundbeteendet om stegen i trattrapporten. När du skapar och sparar en ny trattrapport skapas trattinsikter automatiskt för rapporten. 

:::image type="content" source="media/funnel-insights.png" alt-text="Trattinsikter.":::

> [!NOTE]
> Trattinsikter kan enbart skapas för trattsteg som **inte** innehåller anpassade dimensioner. För att skapa trattinsikter för alla steg i din tratt ska du använda färdiga dimensioner i engagemangsinsikter och skapa dina trattsteg. 

Du kan visa trattinsikter från följande kategorier, både på huvud- och stegnivåer: 

 - Konverteringsgrad
 -    Konverteringsgraden mellan utcheckning och köp är 22 %.
 - Övergångstid 
 -    Genomsnittlig övergångstid mellan kundvagn och utcheckning är 23 minuter. 
 - Slutförandetid 
 -    Genomsnittlig tid för kunden att slutföra tratten är 47 minuter. 

Använd dessa insikter om du vill utforska kundbeteendet djupare och få en bättre förståelse för avlämningspunkter och abonnemangsändringar för din trattrapport. 

För att jämföra insikter för olika steg väljer du **Se steguppdelning** eller **Jämför med andra steg** från insiktskorten. Det visas ett stapeldiagram där mått jämförs för alla steg i tratten. 

Trattinsikter beräknas om var 24:e timme eller när du **sparar** trattrapporten. 

> [!NOTE]
> För att kunna visa insikter för din tratt måste du spara rapporten varje gång du gör ändringar. 

