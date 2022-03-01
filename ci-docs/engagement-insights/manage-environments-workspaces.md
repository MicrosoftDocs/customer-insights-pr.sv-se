---
title: Hantera arbetsytor och miljöer
description: Att skapa, byta namn på och ta bort arbetsytor och miljöer.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645468"
---
# <a name="manage-environments-and-workspaces"></a>Hantera miljöer och arbetsytor

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Översikt

Detta ämne beskriver hur du hanterar arbetsytor och miljöer när de redan har skapats. 

- En *arbetsyta* är ett utrymme för att lagra och hantera händelser och rapporter. Det är här som du kan visa användaraktiviteter i realtid. När du skapar en arbetsyta väljer du vilken typ av data du vill skicka till arbetsyta. För närvarande stöds webbdata och mobilappar. Mer information finns i [Skapa en arbetsyta och lägga till medlemmar](create-workspace.md).

- En *miljö* är ett utrymme där du hanterar arbetsytor och anslutningar. Mer information finns i [Skapa en ny miljö](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Hantera en befintlig arbetsyta

Du kan ha flera arbetsytor samtidigt i en miljö. Din [roll](user-roles.md) avgör hur du kan arbeta med dem. 

 - Du måste vara miljöadministratör eller arbetsyteadministratör för att kunna hantera arbetsytan.
 - Som arbetsyteadministratör kan du byta namn på befintliga arbetsytor eller ta bort dem. 

:::image type="content" source="media/workspace-edit.png" alt-text="Administratörscenter för arbetsyta.":::

### <a name="edit-a-workspace-name"></a>Redigera arbetsytans namn

1. Gå till fliken **Administratör** > **Arbetsyta** och välj **Inställningar**.

1. I rutan **Arbetsytenamn**, ange ett nytt namn.

1. Välj **Spara** för att införa ändringarna.

### <a name="delete-a-workspace"></a>Ta bort en arbetsyta

Om du tar bort arbetsytan tas allt innehåll, alla data, inställningar och behörigheter bort permanent. Det går inte att ångra.

1. Gå till fliken **Administratör** > **Arbetsyta** och välj **Inställningar**.

1. Välj **Ta bort arbetsyta**. 

1. I dialogen **Ta bort arbetsyta**, ange **BEKRÄFTA RADERING** i versaler. 

1. Välj **Ta bort** om du vill ta bort arbetsytan permanent.

### <a name="manage-workspace-members"></a>Hantera arbetsytemedlemmar

1. Gå till fliken **Administratör** > **Arbetsyta** och välj **Medlemmar**.

1. Välj **Lägg till medlemmar** för att ge åtkomst och [tilldela roller](user-roles.md). För tillfället är endast **arbetsyteadministratör** tillgänglig.

1. Välj **Lägg till medlemmar** om du vill lägga till dem på arbetsytan.

## <a name="manage-an-existing-environment"></a>Hantera befintlig miljö

Som miljöadministratör kan du komma åt en miljö från det vänstra navigeringsfönstret. Du kan konfigurera miljöinställningar, andra miljöadministratörer och arbetsytor. Välj flikar som ska flyttas mellan olika områden i administrationscenter.

:::image type="content" source="media/environment-edit.png" alt-text="Administrationscenter för miljö.":::

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

1. I dialogen **Ta bort arbetsyta**, ange **BEKRÄFTA RADERING** i versaler. 

1. Välj **Ta bort** för att ta bort miljön permanent.

## <a name="manage-connections"></a>Hantera anslutningar

Genom att upprätta anslutningar för målgruppinsikter kan du se rapporter i engagemangsinsikter baserade på enhetliga kundprofiler. 

Mer information finns i [Skapa en länk mellan målgruppsinsikter och engagemangsinsikter](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Hantera personlig information

För att skydda kundens personliga data kan du ta bort eller exportera identifierbara data från slutanvändaren.

För mer information, se [Ta bort och exporterar händelsedata som innehåller personuppgifter](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
