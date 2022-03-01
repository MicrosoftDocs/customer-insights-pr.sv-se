---
title: Skapa en ny miljö
description: Syftet med en miljö och hur du skapar en ny.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648139"
---
# <a name="create-a-new-environment"></a>Skapa en ny miljö 

## <a name="overview"></a>Översikt

En miljö är ett utrymme där du hanterar arbetsytor och anslutningar. Hur du använder miljöer beror på din organisation och ditt användningsfall. Du kan till exempel skapa:

- En enda miljö.
- Separata miljöer för test och produktion.
- Separata miljöer för specifika team eller avdelningar i organisationen som innehåller relevanta händelser för varje målgrupp.
- Separata miljöer för olika globala grenar av ditt företag.
- Anslutningar till funktionen målgruppinsikter för Customer Insights.

## <a name="create-a-new-environment"></a>Skapa en ny miljö

1. På höger sida av huvudbanderollen väljer du miljöväljaren och sedan **+Ny**.

   :::image type="content" source="media/environment-picker.png" alt-text="Välj miljöväljaren.":::

1. I fönstret **Konfigurera**, skriv ett **Miljönamn**.

1. Välj **typ** av konto, beroende på din plantyp.

1. Välj **Region** och sedan **Nästa**. 

1. Skriv ett **namn på arbetsytan** så att du kan samla in data för en viss webbplats eller app. Mer information finns i [Skapa ett arbetsyta](create-workspace.md).

1. Välj **Typ av arbetsyta** (Webb eller mobil) som du vill skapa. 

1. Välj **Visa avancerade inställningar** om du vill aktivera eller inaktivera dessa valfria inställningar:

   - Växla **okänd till känd** som aktiverad för att associera webbhändelser med användare som tidigare autentiserats. Mer information finns i [Identifiera webbhändelser från tidigare autentiserade besökare](unknown-to-known.md)
   - Växla **Filtrera robottrafik** till "aktiverad" för att ta bort webbtrafiken genom att lägga till filter för den här arbetsytan. 

1. Välj **Slutför** när du är klar. 

1. Installera koden så kodavsnitt ta emot data och välj **Slutför** för att skapa arbetsytan. Mer information finns i [Översikt över utvecklarresurser](developer-resources.md).

> [!NOTE]
> Nu kan du lägga till medlemmar och tilldela deras behörighetsnivå i listan **Roll**. Mer information finns i [Roller och behörigheter](user-roles.md). 

För mer information, se [Hantera miljöer och arbetsytor](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Arbeta med den nya miljön

- [Skapa ett arbetsyta](../engagement-insights/create-workspace.md) och lägg till medlemmar.
- [Lägg till kod på webbplatsen](../engagement-insights/instrument-website.md) eller [mobilappen](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Visa en [realtidsrapport](../engagement-insights/view-reports.md) eller skapa [anpassade rapporter](../engagement-insights/custom-reports.md).
- [Skapa förfinade händelser](../engagement-insights/refined-events.md) för export.
- [Exportera data](../engagement-insights/export-events.md) till Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
