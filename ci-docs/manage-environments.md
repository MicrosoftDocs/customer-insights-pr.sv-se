---
title: Gör så här - Hantera miljöer
description: Lär dig hur du hanterar befintliga Customer Insights-miljöer som administratör.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833514"
---
# <a name="how-to-manage-environments"></a>Gör så här_ Hantera miljöer

Administratörer [skapar](create-environment.md) och hanterar miljöer. De kan ändra vissa inställningar i befintliga miljöer. Inställningar för företag, typ, region, lagringsalternativ och Dataverse åtgärdas när miljön har skapats. Om du vill ändra inställningarna återställer du miljön eller skapar en ny miljö.

## <a name="edit-an-existing-environment"></a>Redigera en befintlig miljö

Du kan redigera vissa av detaljerna i befintliga miljöer.

1. Välj **Miljö**-väljaren i apphuvudet.

1. Välj ikonen **Redigera**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon för att redigera miljöinställningarna.":::

1. I rutan **Redigera miljö** kan du uppdatera miljöinställningarna.

För att komma igång med en ny miljö, se [Skapa en ny miljö](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Byt ägare till miljön

Flera användare kan ha administratörsbehörigheter, men bara en användare är ägare till en miljö. Som standard är det administratören som ursprungligen skapar en miljö. Som administratör för en miljö kan du tilldela ägarskap till en annan användare med administratörsbehörighet.

1. Välj **Miljö**-väljaren i apphuvudet.

1. Välj ikonen **Redigera**.

1. I rutan **Redigera miljö**, gå till steget **Grundläggande information**.

1. I fältet **Ändra miljöns ägare**, välj ny ägare för miljön.  

1. Välj **Granska och slutför**, sedan **Uppdatera** för att tillämpa ändringarna.

## <a name="claim-ownership-of-an-environment"></a>Begära ägarskap för en miljö

Om ägarens användarkonto tas bort eller stängs av, har miljön ingen ägare. Alla administratörsanvändare kan begära ägarskap och bli den nya ägaren. De kan fortsätta äga miljön eller [ändra ägarskapet till en annan administratör](#change-the-owner-of-an-environment).

Om du vill begära ägarskap väljer du knappen **Ta ägarskap** som visas överst på varje sida i Customer Insights när den ursprungliga ägaren lämnar organisationen.

## <a name="reset-an-existing-environment-preview"></a>Återställa en befintlig miljö (förhandsversion)

Som ägare av en miljö kan du återställa en miljö till ett tomt tillstånd om du vill ta bort alla konfigurationer och ta bort inrättade data.

1. Välj **Miljö**-väljaren i apphuvudet.

1. Markera den miljö du vill återställa och välj den stående ellipsen (&vellip;).

1. Välj alternativet **Återställ**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontroll för att återställa en miljö.":::

1. Välj om du vill återställa hela miljön, allt utom datakällorna eller något som konfigurerats utöver den enhetliga kundprofilen.

1. Ange miljöns namn och välj **Återställ** för att bekräfta.

## <a name="delete-an-existing-environment"></a>Ta bort en befintlig miljö

Som ägare av en miljö kan du ta bort en miljö som du administrerar.

1. Välj **Miljö**-väljaren i apphuvudet.

1. Markera den miljö du vill återställa och välj den stående ellipsen (&vellip;). 

1. Välj alternativet **Ta bort**.

   :::image type="content" source="media/delete-environment.png" alt-text="Styr för att radera miljön.":::

1. Bekräfta borttagningen genom att ange miljö namnet och välja **ta bort**.

> [!IMPORTANT]
> Om du tar bort en miljö tas inte anslutningen till en Dataverse-miljö bort. Om du planerar att ansluta samma Dataverse-miljö till en ny Customer Insights-miljö i framtiden måste du ta bort den anslutningen. Lär dig [ta bort en befintlig anslutning till en Dataverse-miljö](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
