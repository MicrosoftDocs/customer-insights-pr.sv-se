---
title: Berikande med tredjepartsberikande Experian
description: Allmän information om tredjepartsberikande Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fabc3cc9faf4e11f46c396782b561ef61cd0f6d5
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618543"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Berika kundprofiler med demografisk information från Experian (förhandsgranskning)

Experian är en global ledare inom rapporterings- och marknadsföringstjänster för konsument- och affärskreditföretag. Med hjälp av tjänsterna för datatillägg från Experian kan du öka förståelsen för dina kunder genom att berika dina kundprofiler med demografisk information, t.ex. storlek, inkomst och mycket annat.

## <a name="prerequisites"></a>Förutsättningar

För att konfigurera Experian måste följande villkor vara uppfyllda:

- Du måste ha en aktiv prenumeration på Experian. Om du vill få en prenumeration [kontaktar du Experian](https://www.experian.com/marketing-services/contact) direkt. [Läs mer om Experian-databerikande](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-anslutning har redan konfigurerats av en administratör, *eller* också har du [administratärs](permissions.md#administrator)behörighet. Du behöver också användar-ID, part-ID och modellnummer för ditt SSH-aktiverade ST-konto (Secure Transport) som Experian skapat åt dig.

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Vi stöder för närvarande endast berikande av kundprofiler i USA.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Berika mina data** i Experian-panelen.

   > [!div class="mx-imgBorder"]
   > ![Experian-ikon.](media/experian-tile.png "Experian tile")
   > 

1. Välj en [anslutning](connections.md) i listrutan. Kontakta en administratör om det inte finns någon anslutning. Om du är administratör kan du skapa en anslutning genom att välja **Lägg till anslutning** och välja Experian i listrutan. 

1. Bekräfta **Anslut till Experian** genom att bekräfta anslutningsvalet.

1.  Välj **Nästa** och välj **kunddatauppsättning** som du vill berika med demografisk information från Experian. Du kan välja entiteten **Kund** för att berika alla dina kundprofiler eller välja en segmentsentitet för att endast berika kundprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Bild när du väljer kunddatauppsättningen.":::

1. Välj **Nästa** och definiera vilken typ av fält från dina enhetliga profiler som ska användas för att söka efter matchande data från Experian. Minst ett av fälten **Namn och adress**, **Telefon** eller **E-post** krävs. För en bättre matchning kan du lägga till upp till två andra fält. Det här valet påverkar mappningsfälten du har åtkomst till i nästa steg.

    > [!TIP]
    > Fler attribut för nyckelidentifierare som skickas till Experian leder troligen till en högre matchningskvot.

1. Välj **Nästa** för att starta fältmappningen.

1. Definiera vilka fält i dina enhetliga profiler som ska användas för att söka efter matchande demografiska data från Experian. Behövliga fält är markerade.

1. Ange ett namn för berikningen och ett namn för den utgående enheten.

1. Välj **Spara berikning** när du har granskat dina val.

## <a name="configure-the-connection-for-experian"></a>Konfigurera anslutningen för Experian 

Du måste vara en administratör för att konfigurera anslutningar. Välj **Lägg till anslutning** när du konfigurerar ett berikande *eller* gå till **Administratör** > **Anslutningar** och välj **Konfigurera** i Experian-panelen.

1. Välj **Komma igång**.

1. Ange ett namn för anslutningen i rutan **visningsnamn**.

1. Ange giltigt användar-ID, part-ID och modellnummer för ditt Experian-konto för säker transport.

1. Granska och ge ditt samtycke till **Data sekretess och efterlevnad** genom att välja **Jag godkänner**.

1. Välj **Verifiera** om konfigurationen ska verifieras.

1. Välj **Spara** när verifieringen har slutförts.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Konfigurationsruta för Experian-anslutning.":::

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på dina kunddata och de berikningsprocesser som konfigurerats för ditt konto av Experian.

När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive utökad profil genom att markera **Visa utökade data**.

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du gör det möjligt för Dynamics 365 Customer Insights att överföra data till Experian tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som personuppgifter. Microsoft överför sådana data enligt dina instruktioner, men du är ansvarig för att säkerställa att Experian uppfyller dina eventuella sekretess- och säkerhetskrav. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort denna berikningen i syfte att avbryta användningen av den här funktionen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
