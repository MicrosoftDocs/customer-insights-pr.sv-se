---
title: Utöka företagsprofiler med Dun & Bradstreet
description: Allmän information om utökning från tredje part Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755422"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Utöka företagsprofiler med Dun & Bradstreet (förhandsversion)

Dun & Bradstreet tillhandahåller kommersiella data, analyser och insikter för företag. Det gör det möjligt för kunder med enhetliga kundprofiler för företag att berika sina data. Utöka inkluderar attribut, till exempel DUNS-nummer, företagsstorlek, plats, bransch med mera.

## <a name="prerequisites"></a>Förutsättningar

För att konfigurera utöka Dun & Bradstreet måste följande villkor vara uppfyllda:

- Du har en aktiv [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-licens.
- Du har [enhetliga kundprofiler](customer-profiles.md) för företag.
- En Dun & Bradstreet [anslutning](connections.md) konfigureras av en administratör. Du kan skapa den om du har [Administratör](permissions.md#admin) behörighet och autentiseringsuppgifter från Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Konfigurera ditt Dun & Bradstreet-projekt

Som licensierad användare av Dun & Bradstreet kan du skapa ett projekt i [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Logga in på [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). För att hämta autentiseringsuppgifterna [återställer du lösenordet](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Hämta [csv-mallfilen](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) som ska användas för att mappa fältet för Customer Insights till motsvarande Dun & Bradstreet-fält.

1. Överför filen i steget **Överför data** i projektgenereringsupplevelsen för Dun & Bradstreet.

1. Markera de horisontella prickarna under den relevanta **källan** i det nyskapade Dun & Bradstreet-projektet om du vill se de tillgängliga alternativen.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Skärmbild av prickar i ett Dun & Bradstreet-projekt.":::

1. Välj **Hämta S3 information**. Lagra informationen på en säker plats. Du behöver den för att [konfigurera anslutningen för berikning](#configure-a-connection-for-dun--bradstreet) i Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Skärmbild av urval av S3-information i ett Dun & Bradstreet-projekt.":::

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning**.

1. Välj **Utöka mina data på** panelen Dun & Bradstreet och välj **Kom igång**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Skärmbild av panelen Dun & Bradstreet.":::

1. Välj en [anslutning](connections.md) i listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är administratör kan du skapa en anslutning. Välj **Lägg till anslutning** och välj **Dun & Bradstreet**.

1. Välj **Anslut till Dun & Bradstreet** för att bekräfta anslutningen.

1. Välj **Nästa** och välj den **Datauppsättning för kund** om du vill berika med företagsdata från Dun & Bradstreet. Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja entiteten segment för att endast berika enhetliga kundprofiler i det segmentet.

1. Välj **Nästa** och definiera vilka fält från dina enhetliga profiler som används för att söka efter matchande företagsdata från Dun & Bradstreet. Antingen fälten **DUNS-nummer** eller **Namn på företag** och **Land** krävs. Landfältet har stöd för [två eller tre landskoderna med bokstäver](https://www.iso.org/iso-3166-country-codes.html), landsnamn på engelska, landsnamn på ursprungsspråk och telefonprefix. Några vanliga landvarianter är:

- US: USA, Amerikas förenta stater, Förenta staterna, Amerika.
- CA: Kanada.
- GB: Förenade kungariket, Storbritannien, GB, Förenade kungariket av Storbritannien och Nordirland, Förenade kungariket av Storbritannien.
- AU: Australien, Australiska statsförbundet.
- FR: Frankrike, Republiken Frankrike.
- DE: Tyskland, tyska, Deutschland, Allemagne, Förbundsrepubliken Tyskland.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Rutan Dun & Bradstreet-fältmappning.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett namn för berikning och välj **Spara berikning** efter att ha granskat dina val.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurera en anslutning för Dun & Bradstreet

Du måste vara en administratör för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar en berikning *eller* gå till **Admin** > **Anslutningar** och välj **Konfigurera** på panelen Dun & Bradstreet.

1. Välj **Komma igång**.

1. Ange ett namn för anslutningen i rutan **visningsnamn**.

1. Tillhandahåll giltiga autentiseringsuppgifter för Dun & Bradstreet och projektinformation *Region, Släpp mappsökväg och Släpp mappnamn*. Du [får denna information](#setting-up-your-dun--bradstreet-project) från Dun & Bradstreet-projektet.

1. Granska och ge ditt samtycke till **Data sekretess och efterlevnad** genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. Välj **Spara** när verifieringen har slutförts.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet anslut konfigurationssidan.":::

## <a name="enrichment-results"></a>Berikningsresultat

När du har uppdaterat en anrikning kan du granska de nya data som har utökats under [Mina berikningar](enrichment-hub.md). Du kan hitta tidpunkten för den senaste uppdateringen och antalet berikade profiler.

Du kan få tillgång till en detaljerad vy över respektive utökad profil genom att markera **Visa utökade data**.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Dun & Bradstreet tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att Dun & Bradstreet uppfyller eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.

[!INCLUDE[footer-include](includes/footer-banner.md)]
