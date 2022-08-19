---
title: Utöka kundprofiler med data från HERE Technologies (förhandsgranska)
description: Allmän information om tredjepartsberikningen HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237880"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Utöka kundprofiler med data från HERE Technologies (förhandsgranska)

HERE Technologies är ett plattformsföretag som tillhandahåller platsrelaterade data och tjänster. HERE Technologies tjänster för databerikande förbättrar precisionen för platsinformation om dina kunder. Den tillhandahåller adresser för normalisering, extraktion av longitud med mera.

## <a name="prerequisites"></a>Förutsättningar

- En aktiv HERE Technologies-prenumeration. För att skaffa en prenumeration, [registrera dig](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkt. [Läs mer om HERE Technologies platsberikning.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- En HERE [anslutning](connections.md) är [konfigurerad](#configure-the-connection-for-here-technologies) av en administratör.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurera anslutningen för HERE Technologies

Du måste vara en [Administratör](permissions.md#admin) i Customer Insights och ha en aktiv HERE Technologies API-nyckel.

1. Välj **Lägg till anslutning** när du konfigurerar ett tillägg eller gå till **Admin**  > **Anslutningar** och välj **Konfigurera** på HERE technologies.

1. Ange ett namn för anslutningen och en giltig HERE Technologies API-nyckel.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras och välj sedan **Spara**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Konfigurationssida för HERE technologies-anslutning.":::

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **Plats** från panelen HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies-panel.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj anslutning. Kontakta en administratör om det inte finns någon anslutning.

1. Välj **Nästa**.

1. Välj **Kunddatauppsättning** och välj profilen eller segmentet du vill berika med data från HERE Technologies. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Ange vilken typ av fält från dina enhetliga profiler som ska användas för matchning: den primära och/eller sekundära adressen. Du kan ange en fältmappning för både adresser och utöka profilerna för båda adresserna separat. Till exempel för en hemadress och en affärsadress. Välj **Nästa**.

1. Mappa fälten till information från HERE Technologies. Fälten **Gata 1** och **Postnummer** är obligatoriska för den valda primära och/eller sekundära adressen. Lägg till fler fält för bättre matchningsnoghet.

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett **Namn** för berikningen och **utgående enhetsnamn**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="view-enrichment-results"></a>Visa resultat för berikande

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal berikade kunder efter fält** ger detaljerad information om omfattningen för respektive berikat fält.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
