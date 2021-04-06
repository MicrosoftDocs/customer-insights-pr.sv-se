---
title: Berikning med tredjepartsberikningen Experian
description: Allmän information om tredjepartsberikningen Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597809"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Berika kundprofiler med demografisk information från Experian (förhandsversion)

Experian är en global ledare inom konsument- och affärskreditrapportering och marknadsföringstjänster. Med Experians databerikningstjänster kan du skapa en djupare förståelse för dina kunder genom att berika dina kundprofiler med demografiska uppgifter som hushållsstorlek, inkomst och mer.

## <a name="prerequisites"></a>Förutsättningar

För att konfigurera Experian måste följande villkor vara uppfyllda:

- Du har en aktiv Experian-prenumeration. Om du vill få en prenumeration [kontaktar du Experian](https://www.experian.com/marketing-services/contact) direkt. [Läs mer om Experian databerikande](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Du har användar-ID, part-ID och modellnummer för ditt SSH-aktiverade Secure Transport-konto (ST) som Experian skapat åt dig.
- Du har [administratörs](permissions.md#administrator)behörigheter i målgruppsinsikter.

## <a name="configuration"></a>Konfiguration

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Berika mina data** på Experian-panelen.

   > [!div class="mx-imgBorder"]
   > ![Experian-panel](media/experian-tile.png "Experian-panel")

1. Välj **komma igång** och ange användar-ID, part-ID och modellnummer för ditt Experian Secure Transport-konto. Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**. Bekräfta alla indata genom att välja **tillämpa**.

## <a name="map-your-fields"></a>Mappa dina fält

1.  Välj **Lägg till data** och välj den **kunddatauppsättning** du vill berika med demografidata från Experian. Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.

1. Välj nyckelidentifierare från **Namn och adress**, **E-post** eller **Telefon** att skicka till Experian för identitetslösning.

   > [!TIP]
   > Fler nyckel-ID-attribut som skickas till Experian ger troligen en högre matchningsfrekvens.

1. Välj **Nästa** och mappa motsvarande attribut från entiteten Enhetlig kund för de valda nyckel-ID-fälten.

1. Välj **Lägg till attribut** för att mappa ytterligare attribut som du vill skicka till Experian.

1.  Välj **Spara** för att slutföra fältmappningen.

    > [!div class="mx-imgBorder"]
    > ![Experian fältmappning](media/experian-field-mapping.png "Experian fältmappning")

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på kundens data och de eventuella processer som har konfigurerats för ditt konto av Experian.

När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Experian tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data i din instruktion, men du ansvarar för att Experian uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]