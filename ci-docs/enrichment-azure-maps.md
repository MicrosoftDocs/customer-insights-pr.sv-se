---
title: Utöka kundprofiler med platsdata från Azure Maps (förhandsversion)
description: Allmän information om förstapartsberikande för Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238064"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Utöka kundprofiler med platsdata från Azure Maps (förhandsversion)

Azure Maps tillhandahåller platscentrerade data och tjänster för att leverera erfarenheter baserade på data med inbyggd platsintelligens. Datautökandetjänster för Azure Maps förbättrar precisionen för platsinformation om dina kunder. Detta inkluderar funktioner som exempelvis adressnormalisering samt latitud och longitudextraktion till Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Förutsättningar

- En aktiv Azure Maps-prenumeration. För att få ett abonnemang, [registrera dig för en kostnadsfri utvärderingsversion](https://azure.microsoft.com/services/azure-maps/).

- En Azure Maps [anslutning](connections.md) är [konfigureras](#configure-the-connection-for-azure-maps) av en administratör.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurera anslutningen för Azure Maps

Du måste vara en [Administratör](permissions.md#admin) i Customer Insights och ha en aktiv Azure Maps API-nyckel.

1. Välj **Lägg till anslutning** när du konfigurerar en utökning, eller gå till **Administratör** > **Anslutningar** och välj **Konfigurera** i panelen Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Konfigurationssida för Azure Maps-anslutning.":::

1. Ange ett namn för anslutningen och en giltig Azure Maps API-nyckel.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras och välj sedan **Spara**.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **Plats** från panelen Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Panelen Azure Maps.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj anslutning. Kontakta en administratör om det inte finns någon anslutning.

1. Välj **Nästa**.

1. Välj **Kunddatauppsättning** och välj profilen eller segmentet du vill berika med data från Microsoft. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Ange vilken typ av fält från dina enhetliga profiler som ska användas för matchning: den primära och/eller sekundära adressen. Du kan ange en fältmappning för både adresser och utöka profilerna för båda adresserna separat. Till exempel för en hemadress och en affärsadress. Välj **Nästa**.

1. Mappa dina fält till platsdata från Azure Maps. Fälten **Gata 1** och **Postnummer** är obligatoriska för den valda primära och/eller sekundära adressen. Lägg till fler fält för bättre matchningsnoghet.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps-attributmappning.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Granska **avancerade inställningar** som ger maximal flexibilitet för att hantera avancerade användningsfall. Följande standardvärden behöver vanligtvis inte ändras.

   - **Adresstyp**: Returer för matchning av bästa adresser även om de inte är slutförda. Om du endast vill hämta fullständiga adresser&mdash;till exempel adresser som innehåller husnumret&mdash;avmarkerar du alla kryssrutor utom **Punktadresser**.
   - **Språk**: Adresser returneras på språket baserat på adressområdet. Välj språk i listrutan om du vill använda ett standardiserat adressspråk. Om du t.ex. väljer **engelska** returneras **Köpenhamn, Danmark** i stället för **København, Danmark**.
   - **Maximalt antal resultat**: Antal resultat per adress.

1. Välj **Nästa**.

1. Ange ett **Namn** för berikningen och **utgående enhetsnamn**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="view-enrichment-results"></a>Visa resultat för berikande

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal berikade kunder efter fält** ger detaljerad information om omfattningen för respektive berikat fält.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
