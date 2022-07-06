---
title: Översikt över anslutningar (förhandsversion)
description: Anslutningar till andra tjänster från Customer Insights.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: a8b4b8a9bdcf7cf43c47a67d547405dd20dad60d
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081743"
---
# <a name="connections-preview-overview"></a>Översikt över anslutningar (förhandsversion)

Anslutningar är nyckeln till datadelning till och från Customer Insights. Varje anslutning upprättar datadelning med en viss tjänst. Anslutningar utgör grunden för [konfigurera berikningar från tredje part](enrichment-hub.md) och [konfigurera exporter](export-destinations.md). Samma anslutning kan användas flera gånger. En anslutning till Dynamics 365 Marketing fungerar till exempel för flera exporter och en Leadspace-anslutning kan användas för flera utskick.

Gå till **Admin** > **Anslutningar** för att skapa och visa anslutningar.

På fliken **Anslutningar** visas alla aktiva anslutningar. I listan visas en rad för varje anslutning.

Få en snabb översikt, beskrivning och ta reda på vad du kan göra med varje utbyggbarhetsalternativ på fliken **Upptäck**.

## <a name="exports"></a>Exporter

Endast administratörer kan konfigurera nya anslutningar, men de kan ge deltagare åtkomst till befintliga anslutningar. Administratörer styr vart data kan ta vägen. Deltagare anger vilken nyttolast och frekvens som passar deras behov. Mer information finns i [Tillåt att deltagare använder en anslutning för export](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Berikningar

Endast administratörer kan konfigurera nya anslutningar, men de skapade anslutningarna är alltid tillgängliga för både administratörer och deltagare. Administratörer hanterar autentiseringsuppgifter och ger sitt godkännande till att använda data. Anslutningarna kan sedan användas för ut mer information av både administratörer och deltagare.

## <a name="add-a-new-connection"></a>Lägg till ny anslutning

Om du vill lägga till anslutningar måste du ha [administratörsbehörighet](permissions.md). Om du ansluter till andra Microsoft-tjänster förutsätter vi att båda tjänsterna finns i samma organisation.

1. Gå till **Admin** > **Anslutningar (förhandsversion)**.

1. Gå till fliken **Anslutningar**.

1. Välj **Lägg till kontakt** om du vill skapa en ny anslutning. Välj i listrutan vilken typ av anslutning du vill skapa.

1. I fönstret **Konfigurera anslutning** ange de uppgifter som krävs.
   1. En **Visningsnamn** och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.
   1. Exakt vilka fält som är beroende av vilken tjänst du ansluter till. Mer information om en specifik anslutningstyp finns i artikeln om måltjänsten.
   1. Om du [använder ditt eget Key Vault](use-azure-key-vault.md) för att lagra hemligheter aktiverar du **Använd Key Vault** och väljer hemligheten i listan.

1. Välj för att skapa anslutningen **Spara**.

Du kan också välja **Konfigurera** på panelen **Identifiering**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Tillåt deltagare använda en anslutning för export

När du ställer in eller redigerar en exportanslutning väljer du vilka användare som ska kunna använda den här specifika anslutningen för att definiera [exportera](export-destinations.md). Som standard är en anslutning tillgänglig för användare med administratörsroll. Du kan ändra den här inställningen under **Välj vem som kan använda den här anslutningen** och tillåta användare deltagare ska använda den här anslutningen.

- Deltagare kan inte visa eller redigera anslutningen. Här ser de endast visningsnamn och dess typ när en export skapas.
- Genom att dela en anslutning tillåter du deltagare att använda en anslutning. Deltagare ser delade anslutningar när de upprättar exporter. De kan hantera alla exporter som använder den här specifika anslutningen.
- Du kan ändra den här inställningen samtidigt som du behåller de exporter som redan har definierats av deltagare.

## <a name="edit-a-connection"></a>Redigera en anslutning

1. Gå till **Admin** > **Anslutningar (förhandsversion)**.

1. Gå till fliken **Anslutningar**.

1. Markera den vertikala ellipsen (&vellip;) för anslutningen du vill redigera.

1. Välj **Redigera**.

1. Ändra de värden du vill uppdatera och välj **Spara**.

## <a name="remove-a-connection"></a>Vill du ta bort anslutningen

Om anslutningen som du tar bort används för att utöka eller exportera måste du först ta bort eller ta bort den. I dialogrutan för borttagning guidas du till relevanta förbättringar eller exporter.

Fristående berikningar och export blir inaktiva. Du aktiverar dem på nytt genom att lägga till en ny anslutning till dem på sidan [Berikningar](enrichment-hub.md) eller [Exporter](export-destinations.md)..

1. Gå till **Admin** > **Anslutningar (förhandsversion)**.

1. Gå till fliken **Anslutningar**.

1. Markera den vertikala ellipsen (&vellip;) för anslutningen du vill ta bort.

1. Välj **Ta bort** från listrutan. En dialogruta för bekräftelse visas.

   1. Om det finns anläggningar eller exporter med hjälp av den här anslutningen markerar du knappen för att se vad som använder anslutningen.
      - **Export:** Du kan välja att antingen ta bort eller koppla bort exporten för att kunna ta bort anslutningen. Administratörer kan använda åtgärden **Koppla från** för att koppla från export. Åtgärden är tillgänglig för enskilda och flera markerade exporter. Genom att koppla från behålls exportkonfigurationen, men den körs inte förrän en annan anslutning har lagts till i den.
      - **Berikningar:** Du kan välja att antingen ta bort eller inaktivera berikningarna för att kunna ta bort anslutningen.
   1. När anslutningen inte längre har några beroenden går du tillbaka till **Admin** > **Anslutningar** och försök att ta bort anslutningen igen.

1. Bekräfta borttagningen genom att markera **Ta bort**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Upprätta anslutningar med hemligheter som hanteras av ditt eget Key Vault

Vissa anslutningar behöver hemligheter som API-nycklar eller lösenord. Vissa anslutningar stöder hemligheter som lagras i ditt eget Key Vault. Läs mer om anslutningar som stöds och hur du upprättar en [egen Key Vault för Customer Insights](use-azure-key-vault.md).