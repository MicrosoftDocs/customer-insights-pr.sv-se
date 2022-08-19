---
title: Berika företagsprofiler med Leadspace (förhandsversion)
description: Allmän information om tredjepartsberikningen Leadspace.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237972"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Berika företagsprofiler med Leadspace (förhandsversion)

Leadspace är ett dataföretag som tillhandahåller en B2B-kunddataplattform. Det gör att miljöer med enhetliga kundprofiler baserade på konton kan utöka sina data. Utöka *kundprofiler* med attribut som företagsstorlek, plats eller bransch. Utöka *kontaktprofiler* med attribut som rubrik-, persona- eller e-postverifiering.

## <a name="prerequisites"></a>Förutsättningar

- En aktiv Leadspace-licens.
- [Enhetliga kundprofiler](customer-profiles.md) som bygger på konton.
- En Leadspace [anslutning](connections.md) är [konfigurerad](#configure-the-connection-for-leadspace) av en administratör. Kontakta [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direkt för mer information om produkten.

## <a name="configure-the-connection-for-leadspace"></a>Konfigurera anslutningen för Leadspace

Du måste vara en [administratör](permissions.md#admin) i Customer Insights och ha "nyckelnyckeln" (kallas för **Leadspace-token**).

1. Välj **Lägg till anslutning** när du konfigurerar ett tillägg eller gå till **Admin**  > **Anslutningar** och välj **Konfigurera** på Leadspace-panelen.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfigurationssida för Leadspace-anslutning":::

1. Ange ett namn för anslutningen och en giltig Leadspace-token.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras och välj sedan **Spara**.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **företagsdata** från Leadspace-panelen.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skärmbild av Leadspaces-panelen.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj anslutning. Kontakta en administratör om det inte finns någon anslutning.

1. Välj **Nästa**.

1. Välj **Kunddatauppsättning** och välj profilen eller segmentet du vill berika med företagsdata från Leadspace. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. Ange vilken typ av fält från dina enhetliga profiler som ska användas för matchning: den primära och/eller sekundära adressen. Du kan ange en fältmappning för både adresser och utöka profilerna för båda adresserna separat. Till exempel för en hemadress och en affärsadress. Välj **Nästa**.

1. Mappa dina fält till företagsdata från Leadspace. Fältet **Företagets namn** är obligatoriskt. För högre matchningsnoggrannhet kan upp till två ytterligare fält, **Företagets webbplats** och **Företagets plats**, läggas till.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Fältmappningsfönstret för Leadspace.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Markera kryssrutan om du har *kontaktprofiler* som du vill utöka. Customer Insights automatiskt de obligatoriska fälten.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Utöka kontaktposter i leadutrymme.":::

1. Välj **Nästa**.

1. Ange ett **Namn** för berikningen och **utgående enhetsnamn**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="view-enrichment-results"></a>Visa resultat för berikande

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Mer information finns på [API:er för Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
