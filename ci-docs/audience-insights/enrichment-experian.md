---
title: Berikning med tredjepartsberikningen Experian
description: Allmän information om tredjepartsberikningen Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896395"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Berika kundprofiler med demografisk information från Experian (förhandsversion)

Experian är en global ledare inom konsument- och affärskreditrapportering och marknadsföringstjänster. Med Experians databerikningstjänster kan du skapa en djupare förståelse för dina kunder genom att berika dina kundprofiler med demografiska uppgifter som hushållsstorlek, inkomst och mer.

## <a name="prerequisites"></a>Förutsättningar

För att konfigurera Experian måste följande villkor vara uppfyllda:

- Du har en aktiv Experian-prenumeration. Om du vill få en prenumeration [kontaktar du Experian](https://www.experian.com/marketing-services/contact) direkt. [Läs mer om Experian databerikande](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-anslutning har redan konfigurerats av en administratör *eller* eller så har du [administratör](permissions.md#administrator) behörigheter. Du behöver också användar-ID, part-ID och modellnummer för ditt SSH-konto (Secure Transport) som Experian har skapat åt dig.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Berika mina data** på Experian-panelen.

   > [!div class="mx-imgBorder"]
   > ![Experian-panel](media/experian-tile.png "Experian-panel")
   > 

1. Välj en [anslutning](connections.md) från listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja Experian från listrutan. 

1. Välj **Anslut till Experian** för att bekräfta anslutningsvalet.

1.  Välj **Nästa** och välj den **kunddatauppsättning** du vill utöka med demografi från Experian. Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. Välj **Nästa** och definiera vilken typ av fält från dina enhetliga profiler som ska användas för att söka efter matchande demografi från Experian. Minst ett av fälten **Namn och adress**, **Telefon** eller **E-post** krävs. För en bättre matchning kan du lägga till upp till två andra fält. Det här valet påverkar mappningsfälten du har åtkomst till i nästa steg.

    > [!TIP]
    > Fler nyckel-ID-attribut som skickas till Experian ger troligen en högre matchningsfrekvens.

1. Välj **Nästa** för att starta fältmappningen.

1. Definiera vilka fält från dina enhetliga profiler som ska användas för att leta efter matchande demografiska data från Experian. Behövliga fält är markerade.

1. Ange ett namn för berikningen och ett namn för den utgående enheten.

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="configure-the-connection-for-experian"></a>Konfigurera anslutningen för Experian 

Du måste vara en administratör för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar ett tillägg *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på Experian-panelen.

1. Välj **Komma igång**.

1. Ange ett namn för anslutningen i rutan **visningsnamn**.

1. Ange giltigt användar-ID, parti-ID och modellnummer för ditt Experian Secure Transport-konto.

1. Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. Välj **Spara** när verifieringen har slutförts.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Konfigurationsfönster för Experian-anslutning":::

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
