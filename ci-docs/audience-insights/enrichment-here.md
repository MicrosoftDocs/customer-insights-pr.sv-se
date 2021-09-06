---
title: Berikande med tredjepartsberikande HERE Technologies
description: Allmän information om tredjepartsberikningen HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: be0ac9fa29ce1569d06e4e539e95824c0a3ada4dcf49802c2b574e9d91730630
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032596"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Berikning av kundprofiler med HERE Technologies (förhandsversion)

HERE Technologies är ett plattformsföretag som tillhandahåller platsrelaterade data och tjänster. Med HERE Technologies databerikande tjänster kan du få en mer exakt förståelse för kundens plats, med adress, latitud och longitud och så vidare.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera HERE Technologies-berikning:

- Du har en aktiv HERE Technologies-prenumeration. Om du vill få en prenumeration kan du [registrera dig här](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkt. [Läs mer om HERE Technologies platsberikning.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- En HERE-[anslutning](connections.md) är tillgänglig *eller* också har du [administratörs](permissions.md#administrator)behörigheter och API-nyckel för HERE Technologies.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning**. 

1. Välj **Utöka mina data** på panelen HERE Technologies och välj **Kom igång**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-panel.](media/HERE-tile.png "HERE Technologies-panel")

1. Välj en [anslutning](connections.md) i listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning**. Välj **HERE Technologies** i listrutan. 

1. Välj **Anslut till HERE Technologies** för att bekräfta anslutningsvalet.

1.  Välj **Nästa** och välj den **kunddatauppsättning** du vill utöka med platsdata från HERE Technologies. Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. Välj om du vill mappa fält till den primära och/eller sekundära adressen. Du kan ange en fältmappning för både adresser och utöka profilerna för båda adresserna separat. Till exempel om det finns ett hem och en affärsadress. Välj **Nästa**.

1. Definiera vilka fält från dina enhetliga profiler som ska användas för att söka efter matchande platsdata från HERE Technologies. Fälten **Gata 1** och **Postnummer** är obligatoriska för den valda primära och/eller sekundära adressen. För en högre matchningsnoggrannhet kan fler fält läggas till.

   > [!div class="mx-imgBorder"]
   > ![Sida för förbättringskonfiguration av HERE Technologies-](media/enrichment-HERE-configuration.png "Sida för konfiguration av HERE Technologies-berikning")

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett namn för anrikningen. 

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurera anslutningen för HERE Technologies 

Du måste vara en administratör för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på HERE technologies.

1. Ange ett namn för anslutningen i rutan **visningsnamn**.

1. Ange en giltig API-nyckel för HERE Technologies.

1. Granska och ge ditt samtycke till **Data sekretess och efterlevnad** genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. Välj **Spara** när verifieringen har slutförts.

   > [!div class="mx-imgBorder"]
   > ![Konfigurationssida för HERE technologies-anslutning.](media/enrichment-HERE-connection.png "Konfigurationssida för HERE technologies-anslutning")

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på kunddata och API-svarstiderna från HERE Technologies.

När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md) och [mått](measures.md) och till och med [exportera datan](export-destinations.md) för att leverera anpassade upplevelser till dina kunder.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till HERE Technologies tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data på din instruktion, men du ansvarar för att HERE Technologies uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
