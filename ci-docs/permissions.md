---
title: Hantera användarbehörigheter
description: Läs om behörigheter och användarroller.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 74c7ff7cda8431c04dd34713becefa7e346331b4
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740925"
---
# <a name="user-permissions"></a>Användarbehörigheter

På sidan **Behörigheter** konfigureras roller och behörigheter för att använda Customer Insights.

Du måste ha administratörsbehörighet för att kunna visa sidan. Öppna behörighetssidan genom att gå till **Admin** > **Säkerhet** > **Användare**.

Det finns tre typer av roller:

## <a name="viewer"></a>Tittare

- Utforska insikter och segment på sidorna **Start** och **Segment**.
- Sök och filtrera kundprofiler med hjälp av sidan **kunder**. Fälten måste vara sökbara.
- Visa och utforska sidan **Berikning**.
- Utforska och exportera entiteter med hjälp av sidan **entiteter**.
- Visa status för systemprocesser med hjälp av sidan **system**.
- Visa exporter på sidan **Exporter**.
- Installera och använd instrumentpanelen **Power BI Customer Insights**.

## <a name="contributor"></a>Deltagare

- Alla behörigheter som är tillgängliga för visningsprogrammet.
- Läsa in och transformera data från sidan **Datakällor**.
- Slutför **föreningsprocessen** för entiteten Unified customer profile.
- Definiera **Relationer** och **Aktiviteter**.
- Skapa segment med hjälp sidan **Segment**.
- Skapa mått med hjälp av sidan **Mått**.
- Hantera konfiguration och berika kundprofiler från sidan **Berikning** (endast för de förstapartsberikningar).
- Hantera och skapa export utifrån anslutningar som delas med deltagare. [Läs mer om hur administratörer tillåter att deltagare använder en anslutning för exporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administratör

- Alla behörigheter som är tillgängliga för deltagare.
- Ändra inställningarna på sidan **System**, inklusive arbetsspråket och uppdateringsscheman för systemprocesserna.
- Visa och lägg till behörigheter med hjälp av sidan **Behörigheter**.
- Ange sök- och filterdefinitioner för sidan Kunder med hjälp av sidan **Sök- och filterindex** (nås via sidan **Kunder**).
- Hantera anslutningar och tillåt dem för andra användarroller på sidan **Anslutningar**.
- Hantera konfigurationer och berika kundprofiler från sidan **Berikning** (för samtliga berikningar).
- Hantera och skapa exporter på sidan **Exporter**.
- Installera och använd **Tillägget för kundkort**.
- Lägg till och använd **Power Apps anslutningsprogram**.
- Aktivera användning av [Customer Insights-API:er](apis.md).
- [Tilldela miljöägarskap](manage-environments.md#change-the-owner-of-an-environment) till en annan administratör.

## <a name="admin-owner"></a>Administratör (ägare)

- Alla behörigheter som är tillgängliga för administratören.
- [Återställa och ta bort](manage-environments.md#reset-an-existing-environment) miljön.

## <a name="assign-roles-and-permissions"></a>Tilldela roller och behörigheter

1. Gå till **Admin** > **Säkerhet** > **Användare**.

1. Välj **Lägg till användare** för att öppna fönstret **Lägg till/redigera behörigheter**.

1. Använd fältet **Sök** fältet för att hitta den Azure Active Directory-användare eller -grupp vars behörigheter du vill justera. Välj en **roll** som ska tilldelas användaren eller gruppen.

1. Välj **Spara**. Den aktuella miljön kommer automatiskt att delas med användaren eller medlemmarna i gruppen vars behörigheter du har ändrat. Användarna kan komma åt appen Customer Insights och arbeta enligt den angivna rollen.

## <a name="view-current-permissions"></a>Visa aktuella behörigheter

Gå till **Admin** > **Säkerhet** > **Användare** om du vill se vilka rolltilldelningar som är aktiva för tillfället.

- Kolumnen **typ** anger en enskild användare, grupp eller ett program. Systemet stöder enskilda användare och grupper.
- Roller anges i kolumnen **roll**.
- Markera valfri kolumnrubrik om du vill sortera resultaten efter värdet i kolumnen.
- Använd fältet **Sök** högst upp på sidan om du vill söka efter specifika användare.


[!INCLUDE [footer-include](includes/footer-banner.md)]
