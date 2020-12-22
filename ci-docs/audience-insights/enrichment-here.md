---
title: Berikning med tredjepartsberikningen HERE Technologies
description: Allmän information om tredjepartsberikningen HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668700"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Berikning av kundprofiler med HERE Technologies (förhandsversion)

HERE Technologies är ett plattformsföretag som tillhandahåller platsrelaterade data och tjänster. Med HERE Technologies databerikande tjänster kan du få en mer exakt förståelse för kundens plats, med adress, latitud och longitud och så vidare.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas för att du ska kunna konfigurera HERE Technologies-berikning:

- Du har en aktiv HERE Technologies-prenumeration. Om du vill få en prenumeration kan du [registrera dig hä](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakta HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkt. [Läs mer om HERE Technologies platsberikning.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Du använder HERE Technologies API-nyckel.

- Du har [administratörs](permissions.md#administrator)behörigheter.

## <a name="configuration"></a>Konfiguration

1. Gå till **Data** > **Berikning**.

1. Välj **Berika mina data** i panelen HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-panel](media/HERE-tile.png "HERE Technologies-panel")

1. Ange en aktiv **API-nyckel för HERE Technologies**. Granska och ge ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**. 

1. Bekräfta båda indata genom att välja **Anslut till HERE**.

1. Välj **Lägg till data** och välj om du vill mappa fält till den primära och/eller sekundära adressen. Du kan ange en fältmappning för båda adresserna (t.ex. hem- och affärsadress) och berika profilerna för båda adresserna separat. Välj **Nästa**.

1. Definiera vilka fält från dina enhetliga profiler som ska användas för att söka efter matchande platsdata från HERE Technologies. Fälten **Gata 1** och **Postnummer** är obligatoriska för den valda primära och/eller sekundära adressen. För en högre matchningsnoggrannhet kan fler fält läggas till.

   > [!div class="mx-imgBorder"]
   > ![Sida för konfiguration av HERE Technologies-berikning](media/enrichment-HERE-configuration.png "Sida för konfiguration av HERE Technologies-berikning")

1. Välj **Tillämpa** för att slutföra fältmappningen.

## <a name="enrichment-results"></a>Berikningsresultat

Starta berikningsprocessen genom att välja **kör** från kommandofältet. Du kan också låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Bearbetningstiden beror på storleken på kunddata och API-svarstiderna från HERE Technologies.

När en berikningsprocessen har slutförts kan du granska de nyligen utsatta kundprofildata under **Mina berikningar**. Du hittar också tid för den senaste uppdateringen och antalet utökat profilnamn.

Du kan få tillgång till en detaljerad vy över respektive berikad profil genom att markera **Visa berikade data**.

## <a name="next-steps"></a>Nästa steg

Skapa ovanpå dina berikade kunddata. Skapa [segment](segments.md), [mått](measures.md)och [exportera data](export-destinations.md) för att leverera anpassade funktioner till kunderna.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till HERE Technologies tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data på din instruktion, men du ansvarar för att HERE Technologies uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort den här berikningen för att avbryta användningen av den här funktionen.
