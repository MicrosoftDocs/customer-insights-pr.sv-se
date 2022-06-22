---
title: Utöka företagsprofiler med Dun & Bradstreet
description: Allmän information om utökning från tredje part Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953913"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Utöka företagsprofiler med Dun & Bradstreet (förhandsversion)

Dun & Bradstreet tillhandahåller kommersiella data, analyser och insikter för företag. Det gör det möjligt för kunder med enhetliga kundprofiler för företag att berika sina data. Utöka inkluderar attribut, till exempel DUNS-nummer, företagsstorlek, plats, bransch med mera.

## <a name="prerequisites"></a>Förutsättningar

- En aktiv [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-licens.
- [Enhetliga kundprofiler](customer-profiles.md) för företag.
- Ett Dun & Bradstreet [projekt](#set-up-your-dun--bradstreet-project) har ställts in.
- En Dun & Bradstreet [anslutning](connections.md) [konfigureras](#configure-a-connection-for-dun--bradstreet) av en administratör.

## <a name="set-up-your-dun--bradstreet-project"></a>Konfigurera ditt Dun & Bradstreet-projekt

Som licensierad användare av Dun & Bradstreet kan du skapa ett projekt i [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Logga in på [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). För att hämta autentiseringsuppgifterna [återställer du lösenordet](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Hämta [csv-mallfilen](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) som ska användas för att mappa fältet för Customer Insights till motsvarande Dun & Bradstreet-fält.

1. Överför filen i steget **Överför data** i projektgenereringsupplevelsen för Dun & Bradstreet.

1. Markera de horisontella prickarna under den relevanta **källan** i det nyskapade Dun & Bradstreet-projektet om du vill se de tillgängliga alternativen.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Skärmbild av prickar i ett Dun & Bradstreet-projekt.":::

1. Välj **Hämta S3 information**. Lagra informationen på en säker plats. Du behöver den för att [konfigurera anslutningen för berikning](#configure-a-connection-for-dun--bradstreet) i Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Skärmbild av urval av S3-information i ett Dun & Bradstreet-projekt.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurera en anslutning för Dun & Bradstreet

Du måste vara en [Administratör](permissions.md#admin) i Customer Insights och ha autentiseringsuppgifter från Dun & Bradstreet Connect.

1. Välj **Lägg till anslutning** när du konfigurerar en berikning **Admin** > **Anslutningar** och **Konfigurera** på panelen Dun & Bradstreet.

1. Ange ett namn på anslutningen.

1. Tillhandahåll giltiga autentiseringsuppgifter för Dun & Bradstreet och projektinformation *Region, Släpp mappsökväg och Släpp mappnamn*. Du [får denna information](#set-up-your-dun--bradstreet-project) från Dun & Bradstreet-projektet.

1. Granska och ge ditt samtycke till [Data sekretess och efterlevnad](#data-privacy-and-compliance) genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras och välj sedan **Spara**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet anslut konfigurationssidan.":::

### <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Dun & Bradstreet tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att Dun & Bradstreet uppfyller eventuella sekretess- eller säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.

## <a name="supported-countries-or-regions"></a>Länder eller regioner som stöds

Vi stöder för närvarande följande landsalternativ: Kanada (engelska) eller USA (engelska).

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **företagsdata** för panelen Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Skärmbild av panelen Dun & Bradstreet.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj anslutningen och bekräfta. Kontakta en administratör om ingen är tillgänglig.

1. Välj **Nästa**.

1. Välj **Kunddatauppsättning** och välj profilen eller segmentet du vill berika med företagsdata från Dun & Bradstreet. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Ange vilken typ av fält från dina enhetliga profiler som ska användas för att matcha företagsdata från Dun & Bradstreet. Minst ett av fälten **Namn och adress**, **Telefon** eller **E-post** krävs.

1. Välj **Nästa**

1. Mappa dina fält till företagsdata från Dun & Bradstreet. Antingen fälten **DUNS-nummer** eller **Namn på företag** och **Land** krävs.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Rutan Dun & Bradstreet-fältmappning.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett **Namn** för berikningen och **utgående enhetsnamn**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="enrichment-results"></a>Berikningsresultat

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
