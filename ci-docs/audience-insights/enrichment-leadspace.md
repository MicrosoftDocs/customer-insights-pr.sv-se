---
title: Berikning av företagsprofiler med tredjepartsberikning från Leadspace
description: Allmän information om tredjepartsberikningen Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c57eb0ceb50e3b778acac72a4bbfd733a5b0c401
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617476"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Berikning av företagsprofiler med Leadspace (förhandsversion)

Leadspace är ett datavetenskapsföretag som tillhandahåller en B2B-kunddataplattform. Det gör att miljöer med enhetliga kundprofiler baserade på konton kan utöka sina data. Utöka *kundprofiler* med attribut som företagsstorlek, plats eller bransch. Utöka *kontaktprofiler* med attribut som rubrik-, persona- eller e-postverifiering.

## <a name="prerequisites"></a>Förutsättningar

Följande krav måste vara uppfyllda för att du ska kunna konfigurera Leadspace:

- Du har en aktiv Leadspace-licens.
- Du har [enhetliga kundprofiler](customer-profiles.md) som bygger på konton.
- En Leadspace-anslutning har redan konfigurerats av en administratör eller så har du behörigheterna [administratör](permissions.md#administrator) och “evig nyckel” (kallas för **Leadspace-token**). Kontakta [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direkt för mer information om produkten.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. I målgruppsinsikter går du till **Data** > **Berikning**.

1. Välj **Utöka mina data** på panelen Leadspace och välj **Kom igång**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skärmbild av Leadspaces-panelen.":::

1. Välj en [anslutning](connections.md) i listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja **Leadspace**. 

1. Välj **Anslut till Leadspace** för att bekräfta anslutningen.

1. Välj **Nästa** och välj den **kunddatauppsättning** du vill utöka med företagsdata från Leadspace. Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. Välj **Nästa** och definiera vilka fält från dina enhetliga profiler som används för att söka efter matchande företagsdata från Leadspace. Fältet **Företagets namn** är obligatoriskt. För högre matchningsnoggrannhet kan upp till två ytterligare fält, **Företagets webbplats** och **Företagets plats**, läggas till.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Fältmappningsfönstret för Leadspace.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Markera kryssrutan om du har *kontaktprofiler* som du vill utöka. Målgruppen automatiskt de obligatoriska fälten.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Utöka kontaktposter i leadutrymme.":::
 
1. Ange ett namn för berikning och välj **Spara berikning** efter att ha granskat dina val.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurera anslutningen för Leadspace 

Du måste vara en administratör för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på Leadspace-panelen.

1. Välj **Komma igång**. 

1. Ange ett namn för anslutningen i rutan **visningsnamn**.

1. Ange en giltig Leadspace-token.

1. Granska och ge ditt samtycke till **Data sekretess och efterlevnad** genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. Välj **Spara** när verifieringen har slutförts.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfigurationssida för Leadspace-anslutning":::

## <a name="enrichment-results"></a>Berikningsresultat

När du har uppdaterat en anrikning kan du granska de nya data som har utökats under [Mina berikningar](enrichment-hub.md). Du kan hitta tidpunkten för den senaste uppdateringen och antalet berikade profiler.

Du kan få tillgång till en detaljerad vy över respektive utökad profil genom att markera **Visa utökade data**.

Mer information finns på [API:er för Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nästa steg


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Leadspace tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Leadspace uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
