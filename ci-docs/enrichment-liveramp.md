---
title: Utöka kundprofiler med identitetsdata från LiveRamp (förhandsversion)
description: Utöka kundprofiler med data från LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 334440493c50448005ec90d0cfac11358d677b73
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081766"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Utöka kundprofiler med identitetsdata från LiveRamp (förhandsversion)

LiveRamp anger identitetsmatchning offline och konsoliderar kunddata. Du kan mappa personliga identifierare i dina kunddata till identitetsdiagrammet AbiliTec och ta emot AbiliTec ID. Därefter kan du använda de här ID:erna för att bättre ta fram kunddata.

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Vi stöder för närvarande endast att utöka kundprofiler med LiveRamp-data i USA.

## <a name="prerequisites"></a>Förutsättningar

- En aktiv LiveRamp-prenumeration. Om du vill få en prenumeration kontaktar du ditt LiveRamp-kontoteam eller till [dynamics@liveramp.com](mailto:dynamics@liveramp.com) för mer information.

- En aktiv AbiliTec-prenumeration med klient-ID och åtkomst till API:et. Mer information finns i [AbiliTec API utvecklarnav](https://developers.liveramp.com/abilitec-api/).

- En LiveRamp [anslutning](connections.md) är [konfigurerad](#configure-the-connection-for-liveramp) av en administratör.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurera anslutningen för LiveRamp

Du måste vara en [administratör](permissions.md#admin) i Customer Insights och ha ett aktivt LiveRamp klient-ID och hemlighet.

1. Välj **Lägg till anslutning** när du konfigurerar tillägget eller gå till **Admin**  > **Anslutningar** och välj **Konfigurera** på panelen LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurationsfönster för att konfigurera anslutningen till LiveRamp AbiliTec-tjänsten. ":::

1. Ange ett namn för anslutningen och ett giltigt LiveRamp klient-ID och ett namn.

1. Granska och ge ditt samtycke till [Data sekretess och efterlevnad](#data-privacy-and-compliance) genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras och välj sedan **Spara**.

### <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till LiveRamp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att LiveRamp uppfyller eventuella sekretess- eller säkerhetskrav. För mer information, läs [Microsoft sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732). Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på **Identitet** från panelen LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitetspanel på översiktssidan för utökande. ":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Välj anslutning. Kontakta en administratör om ingen är tillgänglig.

1. Välj **Nästa**.

1. Välj **Kunddatauppsättning** och välj profilen eller segmentet du vill berika med identitetsdata från LiveRamp. Entiteten *Kund* berikar alla dina kundprofiler medan ett segment endast berikar kundprofiler som finns i det segmentet.

1. Ange vilken typ av fält från dina enhetliga profiler som ska användas för att matcha identitetsdata från LiveRamp. Minst ett av fälten **Namn och adress**, **E-post** eller **Telefon** krävs. Lägg till fler fält för bättre matchningsnoggrannhet. Välj **Nästa**.

1. Mappa dina fält till identifieringsdata från LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Datamappningsalternativ för LiveRamp-berikande.":::

1. Välj **Nästa** för att slutföra fältmappningen.

1. Ange ett **Namn** för berikningen och **utgående enhetsnamn**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Kör** om du vill starta anrichment-processen eller stäng för att återgå till sidan för **berikande**.

## <a name="view-enrichment-results"></a>Visa resultat för berikande

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal berikade kunder efter fält** ger detaljerad information om omfattningen för respektive berikat fält.

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina utökade kunddata. Använd AbiliTec ID:erna för att konsolidera kundprofiler i en personbaserad vy.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
