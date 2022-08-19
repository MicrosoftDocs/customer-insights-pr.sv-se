---
title: Översikt över anslutningar (förhandsversion)
description: Anslutningar till andra tjänster från Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245533"
---
# <a name="connections-preview-overview"></a>Översikt över anslutningar (förhandsversion)

Anslutningar är nyckeln till datadelning till och från Customer Insights. Varje anslutning upprättar datadelning med en viss tjänst. Använd anslutningar för att [konfigurera berikningar från tredje part](enrichment-hub.md) och [konfigurera exporter](export-destinations.md). Samma anslutning kan användas flera gånger. En anslutning till Dynamics 365 Marketing fungerar till exempel för flera exporter och en Leadspace-anslutning kan användas för flera utskick.

## <a name="export-connections"></a>Exportera anslutningar

Endast administratörer kan konfigurera nya anslutningar, men de kan [ge deltagare åtkomst](#allow-contributors-to-use-a-connection-for-exports) till befintliga anslutningar. Administratörer styr vart data kan ta vägen. Deltagare anger vilken nyttolast och frekvens som passar deras behov.

## <a name="enrichment-connections"></a>Berikningsanslutningar

Endast administratörer kan konfigurera nya anslutningar, men de skapade anslutningarna är alltid tillgängliga för både administratörer och deltagare. Administratörer hanterar autentiseringsuppgifter och ger sitt godkännande till att använda data. Anslutningarna kan sedan användas för ut mer information av både administratörer och deltagare.

## <a name="add-a-new-connection"></a>Lägg till ny anslutning

### <a name="prerequisites"></a>Förutsättningar

- [Administratörsbehörighet](permissions.md)
- Andra Microsoft-tjänster, om det finns några, finns i samma organisation

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj vilken typ av anslutning du vill skapa. Eller gå till fliken **Upptäck** och välj **Konfigurera** på en anslutningspanel.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Ange den information som behövs. Exakt vilka fält som är beroende av vilken tjänst du ansluter till. Mer information om en specifik anslutningstyp finns i artikeln om måltjänsten.

1. Om du [använder ditt eget Key Vault](use-azure-key-vault.md) för att lagra hemligheter aktiverar du **Använd Key Vault** och väljer hemligheten i listan.

1. Granska datasekretess och efterlevnad och välj **Jag godkänner**.

1. Välj **Spara** för att skapa anslutningen.

### <a name="data-privacy-and-compliance"></a>Datasekretess och regelefterlevnad

När du aktiverar Dynamics 365 Customer Insights för att överföra data till tredje part eller andra Microsoft-produkter tillåter du överföring av data utanför efterlevnadsgränsen för Dynamics 365 Customer Insights, inklusive potentiellt känsliga uppgifter såsom personuppgifter. Microsoft kommer att överföra dessa data enligt dina instruktioner, men du ansvarar för att tredjepart uppfyller de sekretess- eller säkerhetskrav som du kan ha. Mer information finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administratör kan när som helst ta bort anslutningen i syfte att avbryta användningen av den här funktionen.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Tillåt deltagare använda en anslutning för export

När du ställer in eller redigerar en exportanslutning väljer du vilka användare som ska kunna använda den här specifika anslutningen för att definiera [exporter](export-destinations.md). Som standard är en anslutning tillgänglig för användare med administratörsroll. Ändra inställningen **Välj vem som kan använda den här anslutningen** för att låta användare med rollen deltagare använda den här anslutningen.

- Deltagare kan inte visa eller redigera anslutningen. Här ser de endast visningsnamn och dess typ när en export skapas.
- Genom att dela en anslutning tillåter du deltagare att använda en anslutning. Deltagare ser delade anslutningar när de upprättar exporter. De kan hantera alla exporter som använder den här specifika anslutningen.
- Du kan ändra den här inställningen samtidigt som du behåller de exporter som redan har definierats av deltagare.

## <a name="manage-existing-connections"></a>Hantera befintliga anslutningar

1. Gå till **Admin** > **Anslutningar**.

1. Välj fliken **Berikning** eller **Exporter** om du vill visa en lista med anslutningar för berikning eller export, anslutningstyp, när den skapades och vem som har åtkomst. Du kan sortera listan över anslutningar efter valfri kolumn.

1. Välj anslutningen om du vill visa tillgängliga åtgärder.

   - **Redigera** anslutningen.
   - [**Ta bort**](#remove-a-connection) en anslutning.

### <a name="remove-a-connection"></a>Vill du ta bort anslutningen

Om anslutningen som du tar bort används för att utöka eller exportera måste du först koppla från eller ta bort den. I dialogrutan för borttagning guidas du till relevanta förbättringar eller exporter.

> [!TIP]
> Inaktiverade berikningar och frånkopplade exporter blir inaktiva. Du aktiverar dem på nytt genom att lägga till en ny anslutning till dem på sidan [Berikningar](enrichment-hub.md) eller [Exporter](export-destinations.md)..

1. Gå till **Admin** > **Anslutningar**.

1. Välj fliken **Berikning** eller **Exporter**.

1. Markera anslutningen du vill ta bort.

1. Välj **Ta bort** från listrutan. En dialogruta för bekräftelse visas.

   1. Om det finns anläggningar eller exporter med hjälp av den här anslutningen markerar du knappen för att se vad som använder anslutningen.
      - **Exporter:** Välj att antingen **Ta bort** exporten eller **Koppla från anslutningen**. Genom att koppla från anslutningen behålls exportkonfigurationen, men den körs inte förrän en annan anslutning har lagts till i den.
      - **Berikningar:** Välj att antingen **Ta bort** eller **Inaktivera** berikningarna.
   1. När anslutningen inte längre har några beroenden går du tillbaka till **Admin** > **Anslutningar** och försök att ta bort anslutningen igen.

1. Bekräfta borttagningen genom att markera **Ta bort**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Upprätta anslutningar med hemligheter som hanteras av ditt eget Key Vault

Vissa anslutningar behöver hemligheter som API-nycklar eller lösenord. Vissa anslutningar stöder hemligheter som lagras i ditt eget Key Vault. Läs mer om anslutningar som stöds och hur du upprättar en [egen Key Vault för Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
