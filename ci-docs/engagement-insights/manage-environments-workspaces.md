---
title: Hantera arbetsytor och miljöer
description: Att skapa, byta namn på och ta bort arbetsytor och miljöer.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486058"
---
# <a name="manage-environments-and-workspaces"></a>Hantera miljöer och arbetsytor

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Översikt

En arbetsyta är ett utrymme för att lagra och hantera händelser och rapporter. Det är här som du kan visa användaraktiviteter i realtid. När du skapar en arbetsyta väljer du vilken typ av data du vill skicka till arbetsyta. För närvarande stöds webbdata och mobilappar.

En miljö är ett utrymme där du hanterar arbetsytor och anslutningar. Hur du använder miljöer beror på din organisation och ditt användningsfall. Du kan till exempel skapa:

-   En enda miljö.
-   Separata miljöer för test och produktion.
-   Separata miljöer för specifika team eller avdelningar i organisationen som innehåller relevanta händelser för varje målgrupp.
-   Separata miljöer för olika globala grenar av ditt företag.
-   Anslutningar till funktionen målgruppinsikter för Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Välj en miljö och skapa en arbetsyta 

Alla arbetsytor måste finnas i en miljö. Du kan välja en befintlig miljö eller skapa en ny när du skapar en arbetsyta. Sedan kan du välja att lägga till arbetsytemedlemmar och börja samla in data.

**Att skapa din första arbetsyta**

1. I engagemangsinsikter, välj **Ny** från arbetsyteväljaren. 

   :::image type="content" source="media/New-workspace.png" alt-text="Arbetsyteväljare på Customer Insights-sidan.":::

1. Välj miljön i listan eller välj **Skapa ny miljö**.

1. Ange ett namn i **Arbetsytenamn**. 

1. Välj vilken typ av miljö du vill skapa, beroende på om du vill mäta vad som händer på en webbplats eller i en mobilapp. 

1. Du kan lägga till medlemmar och tilldela deras behörighetsnivå i listan **Roll**. Välj sedan **Slutför** om du vill skapa arbetsytan eller **Nästa** för att installera kod. 

1. Installera kodavsnitt för att börja emot data och välj **Klar**. 

## <a name="manage-a-workspace"></a>Hantera en arbetsyta

Du kan ha flera arbetsytor samtidigt i en miljö. Din [roll](user-roles.md) avgör hur du kan arbeta med dem. 

 - Du måste vara miljöadministratör eller arbetsyteadministratör för att kunna hantera arbetsytan.
 - Som arbetsyteadministratör kan du byta namn på befintliga arbetsytor eller ta bort dem. 

### <a name="edit-a-workspace-name"></a>Redigera arbetsytans namn

1. Gå till fliken **Administratör** > **Arbetsyta** och välj **Inställningar**.

1. I rutan **Arbetsytenamn**, ange ett nytt namn.

1. Välj **Spara** för att införa ändringarna.

### <a name="delete-a-workspace"></a>Ta bort en arbetsyta

Om du tar bort arbetsytan tas allt innehåll, alla data, inställningar och behörigheter bort permanent. Det går inte att ångra.

1. Gå till fliken **Administratör** > **Arbetsyta** och välj **Inställningar**.

1. Välj **Ta bort arbetsyta**. 

1. I dialogrutan **Ta bort arbetsyta**, ange **BEKRÄFTA BORTTAGNING**. 

1. Välj **Ta bort** om du vill ta bort arbetsytan permanent.

### <a name="manage-workspace-members"></a>Hantera arbetsytemedlemmar

1. Gå till fliken **Administratör** > **Arbetsyta** och välj **Medlemmar**.

1. Välj **Lägg till medlemmar** för att ge åtkomst och [tilldela roller](user-roles.md). För tillfället är endast **arbetsyteadministratör** tillgänglig.

1. Välj **Lägg till medlemmar** om du vill lägga till dem på arbetsytan.

## <a name="manage-an-environment"></a>Hantera miljö

Som miljöadministratör kan du komma åt en miljö från det vänstra navigeringsfönstret. Du kan konfigurera miljöinställningar, andra miljöadministratörer och arbetsytor. Välj flikar som ska flyttas mellan olika områden i administrationscenter.

:::image type="content" source="media/New-environment.png" alt-text="Administrationscenter för miljö.":::

### <a name="create-an-environment"></a>Skapa en miljö

1. I arbetsyteväljaren väljer du **+Ny**.

1. I den guidade upplevelsen öppnar du listrutemenyn **Miljö** och väljer **Skapa ny miljö**. 

1. Ange ett **miljönamn**.

   :::image type="content" source="media/create-environment.png" alt-text="Steg i den guidade upplevelsen för att ange miljöinformationen.":::

1. Välj **Region** och sedan **Nästa**. 

1. Ange ett namn på arbetsytan och välj vilken typ av arbetsyta du vill skapa. 

1.  Alternativt kan du lägga till medlemmar och kopiera kodavsnittet för att slutföra framställandet.

### <a name="rename-an-environment"></a>Ge miljön ett nytt namn

1. Gå till fliken **Administratör** > **Miljö** och välj **Inställningar**.

1. Uppdatera **Miljönamn** och välj **Spara** för att tillämpa dina ändringar.

### <a name="manage-environment-members"></a>Hantera till miljömedlemmar

1. Gå till fliken **Administratör** > **Miljö** och välj **Medlemmar**.

1. Välj **Lägg till medlemmar** för att uppdatera medlemmar och [tilldela roller](user-roles.md). För tillfället är endast **Miljöadministratör** tillgänglig.

1. Välj **Lägg till medlemmar** om du vill lägga till dem i miljön.

### <a name="delete-an-environment"></a>Ta bort en miljö

Miljöadministratörer kan ta bort miljöer. Innan du kan ta bort en miljö måste du ta bort alla arbetsytor under den.

1. Gå till fliken **Administratör** > **Miljö** och välj **Inställningar**.

1. Välj **Ta bort miljö**. 

1. I dialogrutan **Ta bort arbetsyta**, ange **BEKRÄFTA BORTTAGNING**. 

1. Välj **Ta bort** för att ta bort miljön permanent.

## <a name="manage-connections"></a>Hantera anslutningar

Genom att upprätta anslutningar för målgruppinsikter kan du se rapporter i engagemangsinsikter baserade på enhetliga kundprofiler. 

Mer information finns i [Skapa en länk mellan målgruppsinsikter och engagemangsinsikter](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Hantera personlig information

För att skydda kundens personliga data kan du ta bort eller exportera identifierbara data från slutanvändaren.

För mer information, se [Ta bort och exporterar händelsedata som innehåller personuppgifter](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
