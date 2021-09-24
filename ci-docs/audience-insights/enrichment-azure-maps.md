---
title: Utöka kundprofiler med platsdata från Azure Maps
description: Allmän information om förstapartsberikande för Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466784"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Utökande av kundprofiler med Azure Maps (förhandsversion)

Azure Maps tillhandahåller platscentrerade data och tjänster för att leverera erfarenheter baserade på geospatiala data med inbyggd platsintelligens. Datautökandetjänster för Azure Maps förbättrar precisionen för platsinformation om dina kunder. Detta inkluderar funktioner som exempelvis adressnormalisering samt latitud och longitudextraktion till Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Förutsättningar

Följande krav måste uppfyllas för att du ska kunna konfigurera datautökandet för Azure Maps:

- Du måste ha en aktiv prenumeration på Azure Maps. Om du vill få en prenumeration kan du [registrera dig eller få en kostnadsfri utvärderingsversion](https://azure.microsoft.com/services/azure-maps/).

- En Azure Maps-[anslutning](connections.md) är tillgänglig, *ellerockså* har du [administratörs](permissions.md#administrator)rättigheter och en aktiv Azure Maps API-nyckel.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning**. 

1. I panelen **Plats** väljer du **Utöka mina data**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Panelen Azure Maps.":::

1. Välj en [anslutning](connections.md) i listrutan. Kontakta en administratör om det inte finns någon Azure Maps-anslutning tillgänglig. Om du är en Administratör kan du [konfigurera anslutningen för Azure Maps](#configure-the-connection-for-azure-maps). 

1. Välj **Nästa** för att bekräfta valet.

1. Välj den **kunddatauppsättning** som du vill utöka med platsdata från Azure Maps. Du kan välja entiteten **Kund** om du vill utöka alla dina enhetliga kundprofiler, eller välja en segmententitet för att utöka endast kundprofiler som ingår i det segmentet.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Skärmbild när du väljer kundens datauppsättning.":::

1. Välj om du vill mappa fält till den primära och/eller sekundära adressen. Du kan ange en fältmappning för båda adresser och utöka profilerna för båda adresser separat&mdash;till exempel för en hemadress och en företagsadress. Välj **Nästa**.

1. Definiera vilka fält i dina enhetliga profiler som du vill använda för att söka efter matchande platsdata från Azure Maps. Fälten **Gatuadress 1** och **Postnummer** är obligatoriska för vald primär och sekundär adress. Du kan lägga till fler fält för bättre matchningsprecision.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Konfirgurationssida för Azure Maps-utökande.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Utvärdera om du vill ändra **Avancerade inställningar**. Dessa tillhandahålls i syfte att ge maximal flexibilitet för hantering av avancerade användningsärenden, men standardvärdena är lämpliga i de flesta fall:
   - **Adresstyp**: Standardbeteendet är ett utökningen returnerar den bästa adressmatchningen även om denna inte är färdig. Om du endast vill hämta fullständiga adresser&mdash;till exempel adresser som innehåller husnumret&mdash;avmarkerar du alla kryssrutor utom **Punktadresser**. 
   - **Språk**: Som standard returneras adresser på det språk som används i den region som adressen har fastställts tillhöra. Välj språk i listrutan om du vill använda ett standardiserat adressspråk. Om du till exempel väljer **Engelska** returneras **Köpenhamn, Danmark** istället för **København, Danmark**.

1. Ange ett namn för anrikningen.

1. Granska dina val och välj sedan **Spara utökning**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurera anslutningen för Azure Maps

Du måste vara administratör inom målgruppsinsikter för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar en utökning, eller gå till **Administratör** > **Anslutningar** och välj **Konfigurera** i panelen Azure Maps.

1. I rutan **Visningsnamn** anger du ett namn på anslutningen.

1. Tillhandahåll en giltig API-nyckel för Azure Maps.

1. Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. Välj **Spara** när verifieringen har slutförts.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Konfigurationssida för Azure Maps-anslutning.":::

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på dina kunddata och API-svarstiderna.

När utökandeprocessen är klar kan du granska de nyligen utökade kundprofilerna under **Mina utökningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive utökad profil genom att markera **Visa utökade data**.

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina utökade kunddata. Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till Azure Maps tillåter du överföringen av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data såsom personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Azure Maps uppfyller alla eventuella sekretess- och säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
