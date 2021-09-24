---
title: Introduktion av snabbstartprodukt
description: Förstahandsupplevelse för att konfigurera funktionen engagemangsinsikter.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 95caaa1f67a7740328b67face00acaea65452eb0
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494494"
---
# <a name="first-run-experience"></a>Välkomstprogram

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med funktionen engagemangsinsikter för Dynamics 365 Customer Insights, kan du samla in och mäta kundbeteende på webbplatsen. Den här artikeln innehåller information om hur du registrerar dig för engagemangsinsikter, anger en arbetsyta, lägger till medlemmar i den och gör ändringar.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>Registrera dig för en demonstration av engagemangsinsikter

Du måste ha ett aktivt Microsoft Azure Active Directory-användarkonto. 

1. Öppna webbplatsen [engagemangsinsikter](https://home.ci.ai.dynamics.com/app/engagement-insights). 

1. Logga in på ditt arbets- eller skolkonto.

1. Markera din region och använd kryssrutan för att ange om du vill få uppdateringar och erbjudanden via e-post.

1. Granska **Engagementinsikter (förhandsversion) användningsvillkoren** och **Sekretesspolicy** och välj sedan **Utforska demonstrationen** för att acceptera.

1. Utforska produkten med hjälp av en uppsättning exempeldata. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>Konfigurera din första arbetsyta med engagemangsinsikter

En arbetsyta är hur du lagrar och hanterar händelser och rapporter.

Att skapa din första arbetsyta

1. I engagemangsinsikter, välj **Anslut dina data** för att starta guiden. 

:::image type="content" source="media/banner.png" alt-text="Sidan Customer Insights med knappen Anslut dina data.":::

2. Välj vilken typ av aktivitet du vill mäta i en ny arbetsyta. För tillfället är endast **webbplatsaktivitet** tillgänglig. **Appaktivitet** och **Enhetsaktivitet** blir tillgängliga i framtida versioner.

1. Välj **Nästa** för att bekräfta och skapa arbetsytan.

1. Lägg till ett kodavsnitt till din webbplats för att börja ta emot data i engagemangsinsikter. Du kan implementera det här direkt eller dela koden och instruktionerna med webbplatsadministratören. För att hitta kodavsnitt senare går du till **Administratör** > **Arbetsyta** > **Installationsguide**.

   > [!IMPORTANT]
   > Data visas inte på arbetsytan förrän koden har implementerats på webbplatsen.

1. Välj **Klar** om du vill öppna den nya arbetsytan. 

## <a name="add-members-to-an-existing-workspace"></a>Lägga till medlemmar till en befintlig arbetsyta

Som standard är det bara den person som har skapat arbetsytan som har åtkomst till den. Du kan när som helst lägga till andra användare från din organisation i en befintlig arbetsyta.

:::image type="content" source="media/add-members.png" alt-text="Sidan Medlemmar med bildtext på knappen Lägg till medlemmar.":::

1. Gå till **Administration** > **Arbetsyta** > **Medlemmar**.

2. Välj **Lägg till medlemmar**. Använd rutan **Medlemmar** om du vill lägga till andra personer i organisationen. Du kan lägga till flera medlemmar samtidigt.

3. Välj en **roll** att tilldela till de nya medlemmarna. För tillfället är **arbetsyteadministratör** det enda tillgängliga valet. Andra roller läggs till i framtida versioner.

4. Välj **Lägg till medlemmar** för att bekräfta.

Ta bort medlemmar från en arbetsyta genom att markera **…** bredvid deras namn på sidan **Medlemmar**, och välj sedan **Ta bort** i listrutan.

## <a name="edit-a-workspace"></a>Redigera en arbetsyta

Du kan redigera informationen om befintliga arbetsytor när som helst.

:::image type="content" source="media/change-workspace-settings.png" alt-text="Sidan Arbetsyteinställningar med bildtext för arbetsytenamn och beskrivning.":::

1. Gå till **Administration** > **Arbetsyta** > **Inställningar**.

1. Ändra **Namn** på din arbetsyta.

1. Välj **Spara** för att införa ändringarna.

## <a name="add-another-new-workspace"></a>Lägg till en annan arbetsyta

:::image type="content" source="media/workspace-switcher.png" alt-text="Customer Insights-sida med bildtext i navigeringsfönstret och beskrivning.":::

Du kan skapa ytterligare arbetsytor för att kategorisera dina data.

1. I arbetsyteväljaren, välj **Ny arbetsyta**.

1. Ange ett **namn** och en valfri **beskrivning**.

1. Välj **Skapa**.

## <a name="switch-between-workspaces"></a>Växla mellan arbetsytor

Om du vill ändra mellan arbetsytor markerar du arbetsyteväljaren. Du kan också skapa en ny arbetsyta eller välja **Webbexempel** om du vill visa rapporter och prova funktioner med exempeldata. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]