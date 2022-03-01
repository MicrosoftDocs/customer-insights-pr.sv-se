---
title: Exportmål
description: Exportera data och hantera exportdestinationer.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643885"
---
# <a name="export-destinations-preview"></a>Exportmål (förhandsversion)

På sidan **exportera destinationer** visas alla platser som du har konfigurerat för att exportera data till. Du kan också lägga till nya destinationer för export. Dessutom visas exportalternativ som är tillgängliga för tillfället. Få en snabb översikt, beskrivning och ta reda på vad du kan göra med de olika utökningsalternativen. Exportera enhetliga profiler, mått och segment till program som stöds och som är relevanta för ditt företag.

Gå till **administration** > **exportdestinationer** för att hitta följande utökningsalternativ:

- [Tillägget för kundkort i Dynamics 365](customer-card-add-in.md)
- [Anslutning för Facebook Ads Manager](export-facebook.md)
- [Power Automate anslutningsprogram](export-power-automate.md)
- [Power Apps anslutningsprogram](export-power-apps.md)
- [Power BI anslutningsprogram](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [LiveRamp&reg; anslutning](export-liveramp.md)
- [Robot för Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>Lägg till ett nytt exportmål

Om du vill lägga till exportdestinationer har du [administratörsbehörigheter](permissions.md). Om du exporterar till Microsoft-tjänster antar vi att båda tjänsterna finns i samma organisation.

1. Gå till **Administratör** > **Exportera mål**.

1. Gå till fliken **Mina exportdestinationer**.

1. Välj **Lägg till mål** om du vill skapa ett nytt exportmål.

1. I rutan **Lägg till mål** väljer du **Typ** av exportmål i listrutan.

1. Ange de uppgifter som krävs och välj **Nästa** för att skapa exportmålet.

Du kan också välja **Konfigurera** på panelen **Identifiering**.

## <a name="view-export-destinations"></a>Visa exportmål

När du har skapat exportmål hittar du dem i en tabell på fliken **Mina exportmål**. Tabellen har tre kolumner:

- **Visningsnamn**: det namn du angav när du skapade målet.
- **Typ**: den exportmåltyp du angav när du skapade målet.
- **Skapades**: Det datum då du skapade målet.

## <a name="edit-an-export-destination"></a>Redigera ett exportmål

1. Markera den vertikala ellipsen för det exportmål du vill redigera.

   > [!div class="mx-imgBorder"]
   > ![Lodrät ellips](media/export-destinations-page-ellipsis.png "Lodrät ellips")

1. Välj **Redigera** från listruta.

1. Ändra värdena som kräver uppdatering och välj **Spara**.

## <a name="export-data-on-demand"></a>Exportera data på begäran

När du har konfigurerat en anslutning till ett exportmål körs exporten med varje [schemalagd uppdatering](system.md#schedule-tab).

För att exportera data utan att vänta på en schemalagd uppdatering, gå till fliken **Mina exportmål** på **Administratör** > **Exportmål**.

> [!div class="mx-imgBorder"]
> ![Lodrät ellips](media/export-destinations-page-ellipsis.png "Lodrät ellips")

- Välj **Exportera** ovanför listan om du vill köra exporten till alla exportmål samtidigt.
- Markera ellipsknappen (...) efter ett listobjekt och välj alternativet **export** för att köra exporten för ett enskilt exportmål.

## <a name="remove-an-export-destination"></a>Ta bort ett exportmål

Om du vill ta bort ett exportmål går du till sidan **exportmål**.

1. Markera den vertikala ellipsen för det exportmål du vill ta bort.

   > [!div class="mx-imgBorder"]
   > ![Lodrät ellips](media/export-destinations-page-ellipsis.png "Lodrät ellips")

2. Välj **Ta bort** från listrutan.

3. Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.
