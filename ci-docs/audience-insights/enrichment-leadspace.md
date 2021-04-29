---
title: Berikning av företagsprofiler med tredjepartsberikning från Leadspace
description: Allmän information om tredjepartsberikningen Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895935"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Berikning av företagsprofiler med Leadspace (förhandsversion)

Leadspace är ett datavetenskapsföretag som tillhandahåller en B2B-kunddataplattform. Det gör det möjligt för kunder med enhetliga kundprofiler för företag att berika sina data. Berikningar omfattar fler attribut, till exempel företagsstorlek, plats, industri med mera.

## <a name="prerequisites"></a>Förutsättningar

Följande krav måste vara uppfyllda för att du ska kunna konfigurera Leadspace:

- Du har en aktiv Leadspace-licens.
- Du har [enhetliga kundprofiler](customer-profiles.md) för företag.
- En Leadspace-anslutning har redan konfigurerats av en administratör eller så har du behörigheterna [administratör](permissions.md#administrator) och “evig nyckel” (kallas för **Leadspace-token**). Kontakta [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkt för mer information om produkten.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. I målgruppsinsikter går du till **Data** > **Berikning**.

1. Välj **Utöka mina data** på panelen Leadspace och välj **Kom igång**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skärmbild av Leadspaces-panelen.":::

1. Välj en [anslutning](connections.md) från listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja **Leadspace**. 

1. Välj **Anslut till Leadspace** för att bekräfta anslutningen.

1. Välj **Nästa** och välj den **kunddatauppsättning** du vill utöka med företagsdata från Leadspace. Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. Välj **Nästa** och definiera vilka fält från dina enhetliga profiler som används för att söka efter matchande företagsdata från Leadspace. Fältet **Företagets namn** är obligatoriskt. För högre matchningsnoggrannhet kan upp till två ytterligare fält, **Företagets webbplats** och **Företagets plats**, läggas till.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Fältmappningsfönstret för Leadspace.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett namn för berikning och välj **Spara berikning** efter att ha granskat dina val.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurera anslutningen för Leadspace 

Du måste vara en administratör för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på Leadspace-panelen.

1. Välj **Komma igång** 

1. Ange ett namn för anslutningen i rutan **visningsnamn**.

1. Ange en giltig Leadspace-token.

1. Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. Välj **Spara** när verifieringen har slutförts.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfigurationssida för Leadspace-anslutning":::

## <a name="enrichment-results"></a>Berikningsresultat

När du har uppdaterat en anrikning kan du granska de nya data som har utökats under [Mina berikningar](enrichment-hub.md). Du kan hitta tidpunkten för den senaste uppdateringen och antalet berikade profiler.

Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.

Mer information finns på [API:er för Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Leadspace tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Leadspace uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
