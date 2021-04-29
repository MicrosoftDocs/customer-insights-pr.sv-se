---
title: Exportera data från Customer Insights
description: 'Hantera dataexport för att dela data. '
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896165"
---
# <a name="exports-preview-overview"></a>Exporter (förhandsversion) översikt

På sidan **Exporter** visas alla konfigurerade exporter. Med exporter delar du specifika data med olika program. De kan inkludera kundprofiler eller entiteter, scheman och mappningsdetaljer. För varje export krävs en [anslutning, konfigurerad av en administratör, för att hantera autentisering och åtkomst](connections.md).

> [!NOTE]
> Fram till mars 2021 skapades automatiskt en anslutning till motsvarande tjänst. För export krävs nu en [anslutning som har skapats och delats av en administratör](connections.md) innan du kan skapa dem.

Gå till **Data** > **Exporter** om du vill visa exportsidan. Alla användarroller har åtkomst till att visa konfigurerade exporter. Använda sökfältet i kommandofältet för att söka efter exporter efter namn, anslutningsnamn eller anslutningstyp.

## <a name="set-up-a-new-export"></a>Ställ in en ny export

Om du vill konfigurera eller redigera en export måste anslutningarna vara tillgängliga för dig. Anslutningarna beror på din [användarroll](permissions.md):
- Administratörer har åtkomst till alla anslutningar. De kan också skapa nya anslutningar när de upprättar en export.
- Deltagare kan ha åtkomst till specifika anslutningar. De är beroende av administratörer för att konfigurera och dela anslutningar. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Det går bara att visa befintlig export men inte skapa den.

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export** om du vill skapa en ny exportmål.

1. I rutan **Ställ in export** väljer du vilken anslutning som ska användas. [Anslutningarna ](connections.md) hanteras av administratörer. 

1. Ange den information som krävs och välj **Spara** för att skapa exporten.

### <a name="edit-an-export"></a>Redigera export

1. Markera den vertikala ellipsen för det exportmål du vill redigera.

1. Välj **Redigera** från listrutan.

1. Ändra de värden du vill uppdatera och välj **Spara**.

## <a name="view-exports-and-export-details"></a>Visa export- och exportinformation

Efter att ha skapat exportdestinationer listas de på **Data** > **Exporter**. Alla användare kan se vilka data som delas och dess senaste status.

1. Gå till **Data** > **Exporter**.

1. Användare utan redigeringsbehörighet väljer **Visa** i stället för **Redigera** visas exportinformationen.

1. I den här sidan visas hur exporten har ställts in. Du kan inte ändra värden utan att redigera behörigheter. Välj **Stäng** om du vill återgå till exportsidan.

## <a name="run-exports-on-demand"></a>Kör exporter på begäran

När du har konfigurerat en export körs den med alla [schemalagda uppdateringar](system.md#schedule-tab) så länge den har en fungerande anslutning.

För att exportera data utan att vänta på en schemalagd uppdatering, gå till **Data** > **Exporter**. Du har två alternativ:

- Om du vill köra alla exporter väljer du **Kör alla** i kommandofältet. 
- Om du vill köra en enskild export markerar du denlipsen (...) på ett listobjekt och väljer sedan **Kör**.

## <a name="remove-an-export"></a>Ta bort en export

1. Gå till **Data** > **Exporter**.

1. Markera den vertikala ellipsen för det export du vill ta bort.

1. Välj **Ta bort** från listrutan.

1. Bekräfta borttagningen genom att välja **ta bort** på bekräftelseskärmen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
