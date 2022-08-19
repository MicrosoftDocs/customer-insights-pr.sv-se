---
title: Tilldela användarbehörigheter
description: Läs om behörigheter och användarroller.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245441"
---
# <a name="assign-user-permissions"></a>Tilldela användarbehörigheter

Åtkomst till Customer Insights är begränsad till användare i organisationen som läggs till i programmet av en administratör. En administratör kan lägga till, redigera eller ta bort användare. En användare kan vara en enskild användare, en grupp eller ett program. En användare kan ha tre typer av roller:

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
- Hantera och skapa export utifrån [anslutningar som delas med deltagare](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administratör

- Alla behörigheter som är tillgängliga för deltagare.
- Ändra inställningarna på sidan **System**, inklusive arbetsspråket, uppdateringsscheman för systemprocesserna och exportering av diagnostikloggar..
- Ändra inställningarna på sidan **Säkerhet**, inklusive användare, API-nycklar, privata länkar och key vault.
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
- [Återställa och ta bort](manage-environments.md#reset-an-existing-environment-preview) miljön.

## <a name="add-users"></a>Lägg till användare

1. Gå till **Admin** > **Säkerhet** och välj fliken **Användare**.

1. Välj **Lägg till användare** för att öppna fönstret **Lägg till/redigera behörigheter**.

1. Använd fältet **Sök** fältet för att hitta den Azure Active Directory-användare eller -grupp du vill lägga till. Välj en **roll** som ska tilldelas användaren eller gruppen.

1. Välj **Spara**. Den aktuella miljön delas automatiskt med användaren eller medlemmarna i gruppen. Användarna kan komma åt appen Customer Insights och arbeta enligt den angivna rollen.

## <a name="view-current-permissions"></a>Visa aktuella behörigheter

Gå till **Admin** > **Säkerhet** och välj fliken **Användare** om du vill visa listan över aktiva användare och deras rolltilldelningar. Du kan sortera listan med användare efter valfri kolumn eller använda sökrutan för att hitta en viss användare.

## <a name="manage-current-users"></a>Hantera aktuella användare

Gå till **Admin** > **Säkerhet** och välj fliken **Användare**. Du kan sortera listan med användare efter valfri kolumn eller använda sökrutan för att hitta den användare du vill hantera.

Välj en användare om du vill visa tillgängliga åtgärder.

- **Redigera** för att redigera användarens roll i Customer Insights. Välj **Spara** för att bekräfta ändringen.
- **Ta bort** för att ta bort användarens åtkomst till Customer Insights. Välj **Ta bort** för att borttagningen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
