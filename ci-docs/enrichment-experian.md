---
title: Berikande med tredjepartsberikande Experian
description: Allmän information om tredjepartsberikande Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954109"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Berika kundprofiler med demografisk information från Experian (förhandsgranskning)

Experian är en global ledare inom rapporterings- och marknadsföringstjänster för konsument- och affärskreditföretag. Med hjälp av tjänsterna för datatillägg från Experian kan du öka förståelsen för dina kunder genom att berika dina kundprofiler med demografisk information, t.ex. storlek, inkomst och mycket annat.

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Vi stöder för närvarande endast berikande av kundprofiler i USA.

## <a name="prerequisites"></a>Förutsättningar

- En aktiv Experian prenumerationer. Om du vill få en prenumeration [kontaktar du Experian](https://www.experian.com/marketing-services/contact) direkt. [Läs mer om Experian-databerikande](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian [anslutning](connections.md) är [konfigureras](#configure-the-connection-for-experian) av en administratör.

- Experian användar-ID, part-ID och modellnummer för ditt SSH-aktiverade ST-konto (Secure Transport) som Experian skapat åt dig.

## <a name="configure-the-connection-for-experian"></a>Konfigurera anslutningen för Experian

Du måste vara en [administratör](permissions.md#admin) i Customer Insights och ha ett Experian användar-ID, part-ID och modellnummer.

1. Välj **Lägg till anslutning** när du konfigurerar ett berikande till **Admin** > **Anslutningar** och välj **Konfigurera** på panelen Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Konfigurationsruta för Experian-anslutning.":::

1. Ange ett namn för anslutningen och ett giltigt användar-ID, party-ID och modellnummer för ditt konto Experian för säker transport.

1. Granska och ge ditt samtycke till [Data sekretess och efterlevnad](#data-privacy-and-compliance) genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras och välj sedan **Spara**.

### <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till Experian tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Experian uppfyller dina eventuella sekretess- och säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732). Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **Demografi** från panelen Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian panel på översiktssidan för utökande. ":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj anslutning. Kontakta en administratör om ingen är tillgänglig.

1. Välj **Nästa**.

1. Välj **Kunddatauppsättning** och välj profilen eller segmentet du vill berika med demografidata från Experian. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. Ange vilken typ av fält från dina enhetliga profiler som ska användas för att matcha demografisk information från Experian. Minst ett av fälten **Namn och adress**, **Telefon** eller **E-post** krävs. Lägg till fler fält för bättre matchningsnoggrannhet. Välj **Nästa**.

1. Mappa fälten till demografisk information från Experian.

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett **Namn** för berikningen och **utgående enhetsnamn**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="enrichment-results"></a>Berikningsresultat

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal berikade kunder efter fält** ger detaljerad information om omfattningen för respektive berikat fält.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
