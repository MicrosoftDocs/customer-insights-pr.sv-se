---
title: Redigera utöka identifieringsdata från LiveRamp
description: Utöka kundprofiler med data från LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373042"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Utöka kundprofiler med identitetsdata från LiveRamp (förhandsversion) 

LiveRamp anger identitetsmatchning offline och konsoliderar kunddata. Du kan mappa personliga identifierare i dina kunddata till identitetsdiagrammet AbiliTec och ta emot AbiliTec ID. Därefter kan du använda de här ID:erna för att bättre ta fram kunddata. 

## <a name="prerequisites"></a>Förutsättningar 

För att konfigurera berikningen måste följande villkor vara uppfyllda: 

- Du måste ha en aktiv LiveRamp-prenumeration. Om du vill få en prenumeration kontaktar du ditt LiveRamp-kontoteam eller till [dynamics@liveramp.com](mailto:dynamics@liveramp.com) för mer information.   

- En aktiv AbiliTec-prenumeration med klient-ID och åtkomst till API:et. Mer information finns i [AbiliTec API utvecklarnav](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Länder/regioner som stöds 

Vi stöder för närvarande endast att utöka kundprofiler med LiveRamp-data i USA. 

## <a name="configure-the-enrichment"></a>Konfiguration av berikning 

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**. 

1. Välj **Utöka mina data** på panelen **Identitet**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitetspanel på översiktssidan för utökande. ":::

1. Välj en [anslutning](connections.md) i listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är en Administratör kan du skapa en anslutning genom att välja **Lägg till anslutning**. Välj **LiveRamp** från listrutan. 

1. Välj **Nästa** och välj den **Datauppsättning för kund** om du vill berika med identitetsdata från LiveRamp. Du kan välja entiteten *Kund* för att berika alla dina kundprofiler eller välja entiteten *segment* för att endast berika kundprofiler i det segmentet. 

1. Välj **Nästa** och definiera vilken typ av fält från dina enhetliga profiler som ska användas för att söka efter matchande identitetsdata från LiveRamp. Minst ett av fälten **Namn och adress**, **Telefon** eller **E-post** krävs. 

   > [!TIP]
   > Ju fler nyckelidentifierare och fält du mappar, desto större chans har du att få en högre matchningstakt 

1. Mappa fälten från entiteten enhetlig *kund* som ska användas för matchning med LiveRamps AbiliTec ID-diagram. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Datamappningsalternativ för LiveRamp-berikande.":::

1. Välj **Nästa** för att slutföra fältmappningen. 

1. Ange ett **Namn** för berikningen och **utgående enhet**. 

1. Välj **Spara berikning** när du har granskat dina val. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigurera anslutningen för LiveRamp 

Du måste vara en administratör för att [konfigurera anslutningar](connections.md). Välj **Lägg till anslutning** när du konfigurerar tillägget eller gå till **Admin** > **Anslutningar** och välj **Konfigurera** på panelen **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurationsfönster för att konfigurera anslutningen till LiveRamp AbiliTec-tjänsten. ":::

1. För **visningsnamn** ange namnet på anslutningen. 

1. Ange ett giltigt LiveRamp-klient-ID och ett klient-ID. 

1. Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**. 

1. Välj **Verifiera** om konfigurationen ska verifieras. 

1. För att slutföra anslutningen välj **Spara**. 

## <a name="enrichment-results"></a>Berikningsresultat 

Starta berikningsprocessen genom att välja kör från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en  [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på dina kunddata. 

När anrikningsprocessen är klar kan du granska de nyligen berikade kundprofilernas data under  **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn. 

Du kan få tillgång till en detaljerad vy över respektive utökad profil genom att markera  **Visa berikade** data. 

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina utökade kunddata. Använd AbiliTec ID:erna för att konsolidera kundprofiler i en personbaserad vy. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad 

När du aktiverar Dynamics 365 Customer Insights för att överföra data till LiveRamp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att se till att LiveRamp uppfyller eventuella sekretess- eller säkerhetskrav. För mer information, läs [Microsoft sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732). Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
