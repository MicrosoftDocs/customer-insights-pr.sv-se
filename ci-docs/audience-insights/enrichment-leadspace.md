---
title: Berikning av företagsprofiler med tredjepartsberikning från Leadspace
description: Allmän information om tredjepartsberikningen Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668745"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Berikning av företagsprofiler med Leadspace (förhandsversion)

Leadspace är ett datavetenskapsföretag som tillhandahåller en B2B-kunddataplattform. Det gör det möjligt för kunder med enhetliga kundprofiler för företag att berika sina data. Berikning inkluderar ytterligare attribut, till exempel företagsstorlek, plats, industri med mera.

## <a name="prerequisites"></a>Förutsättningar

Följande krav måste vara uppfyllda för att du ska kunna konfigurera Leadspace:

- Du har en aktiv Leadspace-licens och en "evig nyckel" (kallas **Leadspace-token**). Kontakta direkt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) för mer information om deras produkter.
- Du har [administratörs](permissions.md#administrator)behörigheter.
- Du har [enhetliga kundprofiler](customer-profiles.md) för företag.

## <a name="configuration"></a>Konfiguration

1. I målgruppsinsikter går du till **Data** > **Berikning**.

1. Välj **utöka mina data** på Leadspace-panelen.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skärmbild av Leadspaces-panelen.":::

1. Välj **Kom igång** och ange sedan ett aktivt **Leadspace-token** (evig nyckel). Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**. Bekräfta båda indata genom att välja **Anslut till Leadspace**.

1. Välj **Mappa data** och definiera vilka fält från dina enhetliga profiler som ska användas för att söka efter matchande företagsdata från Leadspace. Fältet **Företagets namn** är obligatoriskt. För högre matchningsnoggrannhet kan upp till två ytterligare fält, **Företagets webbplats** och **Företagets plats**, läggas till.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Fältmappningsfönstret för Leadspace.":::
   
1. Välj **Tillämpa** för att slutföra fältmappningen.

1. Välj **Kör** för att berika företagsprofilerna. Hur lång tid en berikning tar beror på antalet enhetliga kundprofiler.

## <a name="enrichment-results"></a>Berikningsresultat

När du har uppdaterat en anrikning kan du granska de nya data som har utökats under [Mina berikningar](enrichment-hub.md). Du kan hitta tidpunkten för den senaste uppdateringen och antalet berikade profiler.

Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.

Mer information finns på [API:er för Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Leadspace tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Leadspace uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.