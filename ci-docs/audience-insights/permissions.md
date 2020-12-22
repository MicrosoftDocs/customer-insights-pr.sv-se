---
title: Hantera användarbehörigheter
description: Läs om behörigheter och användarroller.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689242"
---
# <a name="user-permissions"></a>Användarbehörigheter

Sidan **Behörigheter** är där du ska konfigurera roller och behörigheter för att använda målgruppsinsikter.

Du måste ha administratörsbehörighet för att kunna visa sidan. Om du vill komma åt behörighetssidan i målgruppsinsikter går du till **Admin** > **Behörigheter**.

Det finns tre typer av roller:

## <a name="viewer"></a>Tittare

- Utforska insikter och segment på sidorna **Start** och **Segment**.
- Sök och filtrera kundprofiler med hjälp av sidan **kunder**. Fälten måste vara sökbara.
- Visa och utforska sidan **Berikning**.
- Utforska och exportera entiteter med hjälp av sidan **entiteter**.
- Visa status för systemprocesser med hjälp av sidan **system**.
- Exportera segment från sidan **Segment**.
- Installera och använd instrumentpanelen **Power BI Customer Insights**.

## <a name="contributor"></a>Deltagare

- Alla behörigheter som är tillgängliga för visningsprogrammet.
- Läsa in och transformera data från sidan **Datakällor**.
- Slutför avsnitten *Dataförening* (**Mappa**, **Matcha** och **Sammanslå**) som resulterar i den enhetliga entiteten för kundprofilen.
- Definiera **Relationer** och **Aktiviteter**.
- Skapa segment med hjälp sidan **Segment**.
- Skapa mått med hjälp av sidan **Mått**.
- Hantera konfiguration och berika kundprofiler från sidan **Berikning** (endast för de förstapartsberikningar).

## <a name="administrator"></a>Administratör

- Alla behörigheter som är tillgängliga för deltagare.
- Ändra inställningarna på sidan **System**, inklusive arbetsspråket och uppdateringsscheman för systemprocesserna.
- Visa och lägg till behörigheter med hjälp av sidan **Behörigheter**.
- Ange sök- och filterdefinitioner för sidan Kunder med hjälp av sidan **Sök- och filterindex** (nås via sidan **Kunder**).
- Definiera segmentmål för Dynamics 365 Sales med hjälp av sidan **Exportmål**.
- Hantera konfigurationer och berika kundprofiler från sidan **Berikning** (för samtliga berikningar).
- Installera och använd **Tillägget för kundkort**.
- Lägg till och använd **Power Apps anslutningsprogram**.
- Aktivera användning av [Customer Insights-API:er](apis.md).

## <a name="assign-roles-and-permissions"></a>Tilldela roller och behörigheter

1. I målgruppsinsikter går du till **Admin** > **Behörigheter**.

1. Välj **Lägg till användare** för att öppna fönstret **Lägg till/redigera behörigheter**.

1. Använd fältet **Sök** fältet för att hitta den Azure Active Directory-användare eller -grupp vars behörigheter du vill justera. Välj en **roll** som ska tilldelas användaren eller gruppen.

1. Välj **Spara**. Den aktuella miljön kommer automatiskt att delas med användaren eller medlemmarna i gruppen vars behörigheter du har ändrat. Användarna kan komma åt appen Customer Insights och arbeta enligt den angivna rollen.

## <a name="view-current-permissions"></a>Visa aktuella behörigheter

I målgruppsinsikter går du till **Admin** > **Behörigheter** för att se vilken rolltilldelning som är aktiv för tillfället.

- Kolumnen **typ** anger en enskild användare, grupp eller ett program. Systemet stöder enskilda användare och grupper.
- Roller anges i kolumnen **roll**.
- Markera valfri kolumnrubrik om du vill sortera resultaten efter värdet i kolumnen.
- Använd fältet **Sök** högst upp på sidan om du vill söka efter specifika användare.
