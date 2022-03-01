---
title: LiveRamp anslutning
description: Lär dig hur du exporterar data till LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667206"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; kontakt (förhandsversion)

Aktivera dina data i LiveRamp om du vill ansluta med över 500 plattformar över digitala, sociala och TV-ekosystem. Arbeta med dina data i LiveRamp om du vill rikta, undertrycka och anpassa AD-kampanjer.

## <a name="prerequisites"></a>Förutsättningar

- Du måste ha en LiveRamp-prenumeration om du vill använda den här anslutningen.
- Om du vill få en prenumeration [kontaktar du LiveRamp](https://liveramp.com/contact/) direkt. [Läs mer om LiveRamp-registrering](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Anslut till LiveRamp

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. I panelen **LiveRamp** väljer du **Konfigurera**.

1. Ange ditt mål som ett beskrivande namn i fältet **visningsnamn**.

1. Ange ett **användarnamn** och **lösenord** för ditt LiveRamp-skyddade FTP-konto (SFTP).
Autentiseringsuppgifterna kan skilja sig från dina autentiseringsuppgifter för LiveRamp.

1. Välj **kontrollera** för att testa anslutningen till LiveRamp.

1. När du har verifierat klart anger du ditt medgivande för **Datasekretess och regelefterlevnad** genom att markera kryssrutan **Jag godkänner**.

1. Välj **Nästa** om du vill konfigurera LiveRamp-kopplingen.

## <a name="configure-the-connector"></a>Konfigurera kopplingen

1. I fältet **Välj din nyckelidentifierare** välj **E-post**,  **Namn och adress** eller **Telefon** att skicka till LiveRamp för identitetsmatchning.

1. Mappa motsvarande attribut från entiteten enhetlig kund för den valda nyckelidentifieraren.

1. Välj **Lägg till attribut** om du vill mappa ytterligare attribut att skicka till LiveRamp.

   > [!TIP]
   > Om du skickar fler attribut för nyckelidentifierare till LiveRamp får du troligen en högre matchningsfrekvens.

1. Markera de segment du vill exportera till LiveRamp.

1. Välj **Spara**.

> [!div class="mx-imgBorder"]
> ![LiveRamp-koppling med attributmappning](media/export-liveramp-segments.png "LiveRamp-koppling med attributmappning")

## <a name="export-the-data"></a>Exportera data

Exporten startar kort om alla nödvändiga förutsättningar för exporten har slutförts. Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md#schedule-tab).
När exporten har slutförts kan du logga in på LiveRamp-registrering för att aktivera och distribuera dina data.

## <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till Liveramp tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga data som t.ex. personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att Liveramp uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).
Din administratör av Dynamics 365 Customer Insights kan när som helst ta bort det här exportmålet för att sluta använda den här funktionen.