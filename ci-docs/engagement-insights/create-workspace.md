---
title: Skapa en ny arbetsyta
description: Syftet med en arbetsyta och hur du skapar en ny.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673515"
---
# <a name="create-a-new-workspace-and-add-members"></a>Skapa en ny arbetsyta och lägg till medlemmar

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En arbetsyta är hur du visar användaraktiviteter i realtid för att få en bättre målgrupp. Det är här som du lagrar och hanterar händelser och rapporter.

När du skapar en arbetsyta väljer du vilken typ av data du vill fokusera på. Du kan när som helst lägga till andra användare eller medlemmar i en befintlig arbetsyta. 

## <a name="create-a-new-workspace"></a>Skapa en ny arbetsyta

När du skapar en arbetsyta konfigureras *miljön* för att organisera arbetsytan. En miljö är ett utrymme som kan innehålla en eller flera arbetsytor. Du kan använda en miljö för att hantera dina arbetsytor och anslutningar målinsikter.

1. Välj **+Nytt** i arbetsyteväljaren.

   :::image type="content" source="media/new-workspace.png" alt-text="Customer Insights-sidan med bildtext i navigeringsfönstret och beskrivning.":::

1. I fönstret **Arbetsyta** ange ett **Arbetsytenamn**.

   :::image type="content" source="media/workspace-name.png" alt-text="Skriv ett arbetsytenamn.":::

1. Välj den plattformstyp (webb eller mobil) du vill mäta.

1. Välj **Visa avancerade inställningar** om du vill aktivera eller inaktivera dessa valfria inställningar:

   - Växla **okänd till känd** som aktiverad för att associera webbhändelser med användare som tidigare autentiserats. Mer information finns i [Identifiera webbhändelser från tidigare autentiserade besökare](unknown-to-known.md)
   - Växla **Filtrera robottrafik** till "aktiverad" för att ta bort webbtrafiken genom att lägga till filter för den här arbetsytan. 

1. Välj **Slutför** när du är klar. 

1. Installera koden så kodavsnitt ta emot data och välj **Slutför** för att skapa arbetsytan. Mer information finns i [Översikt över utvecklarresurser](developer-resources.md).

> [!NOTE]
> Nu kan du lägga till medlemmar och tilldela deras behörighetsnivå i listan **Roll**. Mer information finns i [Roller och behörigheter](user-roles.md). 

För mer information, se [Hantera miljöer och arbetsytor](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
