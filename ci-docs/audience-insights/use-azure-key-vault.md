---
title: Hämta ditt eget Azure Key Vault för att hantera hemligheter
description: Lär dig hur du konfigurerar Customer Insights för att använda ditt eget Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606141"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Hämta ditt eget Azure Key Vault (förhandsgranskning)

Genom att länka ett dedikerat [Azure Key Vault](/azure/key-vault/general/basic-concepts) till en miljö med målgruppinsikter hjälper du organisationer att uppfylla krav på regelefterlevnad.
Dedikerade nyckelvalv kan användas för att arrangera och använda hemligheter i en organisations efterlevnadsgräns. Målgruppsinsikter kan använda hemligheterna i Azure Key Vault för att [konfigurera anslutningar](connections.md) till system från tredje part.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Länka nyckelvalv till miljö för målgruppinsikter

### <a name="prerequisites"></a>Förutsättningar

Om du vill konfigurera nyckelvalv i målgruppinsikter måste följande krav uppfyllas:

- Du måste ha en aktiv Azure-prenumeration.

- Du har rollen [Administratör](permissions.md#administrator) i målgruppinsikter. Läs mer om [användarbehörigheter i målgruppsinsikter](permissions.md#assign-roles-and-permissions).

- Du har rollerna [Deltagare](/azure/role-based-access-control/built-in-roles#contributor) och [Administratör för användaråtkomst](/azure/role-based-access-control/built-in-roles#user-access-administrator) på nyckelvalvet eller resursgruppen som nyckelvalvet tillhör. Mer information finns i [Lägga till eller ta bort Azure-rolltilldelningar via Azure-portalen](/azure/role-based-access-control/role-assignments-portal). Om du inte har rollen administratör för användaråtkomst i nyckelvalvet måste du konfigurera den rollbaserade åtkomstkontrollbehörigheten för Azure-tjänstens huvudnamn Dynamics 365 Customer Insights separat. Följ anvisningarna för att [använda Azure-tjänstens huvudkonto](connect-service-principal.md) för det nyckelvalv som ska länkas.

- Nyckelvalv måste ha brandväggen **inaktiverad**.

- Nyckelvalvet finns på samma [Azure-plats](https://azure.microsoft.com/global-infrastructure/geographies/#overview) som miljö för målgruppinsikter. Regionen för miljön för målgruppinsikter under **Admin** > **System** > **Om** > **Region**.

### <a name="link-a-key-vault-to-the-environment"></a>Länka ett nyckelvalv till miljön

1. Gå till **Admin** > **System** och välj fliken **Säkerhet**.
1. I panelen **Key Vault** välj **Installation**.
1. Välj en **prenumeration**.
1. Välj ett nyckelvalv i listrutan **Key Vault**. Om för många nyckelvalv visas väljer du en resursgrupp för att begränsa sökresultaten.
1. Godkänn **sekretesspolicyn för data och regelefterlevnad**.
1. Välj **Spara**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Steg för att konfigurera ett länkat nyckelvalv i målgruppsinsikter.":::

Panelen **Key Vault** visar nu det länkade nyckelvalvets namn, resursgrupp och prenumeration. Den är klar att användas i anslutningsprocessen.
Mer information om vilka behörigheter på nyckelvalvet som beviljas målgruppsinsikter hittar du på [Behörigheter för nyckelvalvet till publikinsikter](#permissions-granted-on-the-key-vault-to-audience-insights), senare i den här artikeln.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Använda nyckelvalv i anslutningsinstallationen

När du [konfigurerar anslutningar](connections.md) till system från tredje part kan hemligheterna från det länkade Key Vault användas för att konfigurera anslutningarna.

1. Gå till **Admin** > **Anslutningar**.
1. Välj **Lägg till anslutning**.
1. För de anslutningstyper som stöds är en växlingsknapp **Använd Key Vault** tillgänglig om du länkade ett nyckelvalv.
1. I stället för att gå in manuellt kan du välja namnet som pekar på värdet i nyckelvalvet.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Anslutningsfönstret med en SFTP-anslutning med en Key Vault-hemlighet.":::

## <a name="supported-connection-types"></a>Anslutningstyper som stöds.

Följande [exportanslutningar](export-destinations.md) stöds:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Behörigheter som ges i nyckelvalvet för målgruppsinsikter

Följande behörigheter beviljas målgruppsinsikter om ett länkat nyckelvalv om det är något av det [Key Vault åtkomstpolicy](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) eller [Azure-rollbaserad åtkomstkontroll](/azure/key-vault/general/rbac-guide?tabs=azure-cli) har aktiverats.

### <a name="key-vault-access-policy"></a>Åtkomstprincip för nyckelvalvet

| Type        | Behörigheter          |
| ----------- | -------------------- |
| Tangent         | [Hämta nycklar](/rest/api/keyvault/get-keys), [Hämta nycklar](/rest/api/keyvault/get-key)                                 |
| Hemlig      | [Hämta hemligheter](/rest/api/keyvault/get-secrets), [Hämta hemligheter](/rest/api/keyvault/get-secret)                     |
| Certifikat | [Hämta certifikat](/rest/api/keyvault/get-certificates), [Hämta certifikat](/rest/api/keyvault/get-certificate) |

De föregående värdena är minimivärdena som ska visas och läsas under körningen.

### <a name="azure-role-based-access-control"></a>Azure rollbaserad åtkomstkontroll

Användarrollerna Key Vault-läsare och Key Vault-hemlighet läggs till för målgruppsinsikter. Mer information om dessa roller finns i [Azure inbyggda roller för Key Vault-dataplanåtgärder](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Rekommendationer

- Använd ett separat eller dedicerat nyckelvalv som endast innehåller de hemligheter som krävs målgruppsinsikter. Läs mer om varför [separata nyckelvalv rekommenderas](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Följ [rekommendationer om du vill använda Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) för att styra åtkomst-, säkerhetskopierings-, gransknings- och återställningsalternativ.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kan målgruppsinsikter skriva hemligheter eller skriva över hemligheter i nyckelvalvet?

Nr. Endast läs- och listbehörigheter som beskrivs i avsnittet [beviljat tillstånd](#permissions-granted-on-the-key-vault-to-audience-insights) i denna artikel beviljas målgruppsinsikter. Systemet kan inte lägga till, ta bort eller skriva över hemligheter i nyckelvalvet. Det är också anledningen till att du inte kan ange autentiseringsuppgifter när en anslutning använder Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kan jag ändra en anslutning från Key Vault-hemligheter till standardautentisering?

Nr. Du kan inte byta tillbaka till en standardanslutning när du har konfigurerat den med en säkerhetsnyckel från ett länkat nyckelvalv. Skapa en separat anslutning och ta bort den gamla om du inte behöver den.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Hur upphäver jag åtkomsten till ett nyckelvalv för målgruppsinsikter?

Beroende på om [Key Vault åtkomstpolicy](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) eller [Azure rollbaserad åtkomstkontroll](/azure/key-vault/general/rbac-guide?tabs=azure-cli) är aktiverad måste du ta bort behörigheterna för tjänstens huvudkonto `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med namnet `Dynamics 365 AI for Customer Insights`. Alla anslutningar som använder nyckelvalv fungerar inte.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>En del som används i en anslutning tas bort från nyckelvalvet. Vad ska jag göra?

Ett meddelande visas målgruppsinsikter när en konfigurerad säkerhetsnyckel från nyckelvalv inte är tillgänglig. Aktivera [mjuk borttagning](/azure/key-vault/general/soft-delete-overview) i nyckelvalv för att återställa hemligheter om de tas bort av misstag.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>En anslutning fungerar inte, men min anslutning finns i nyckelvalvet. Vad kan vara orsaken?

Ett meddelande visas i målgruppsinsikter när den inte kan komma åt nyckelvalvet. Orsaken kan vara:

- Behörigheterna för huvudkonto för tjänsten målgrupp i målgruppinsikter. De måste återställas manuellt.

- Brandväggen i nyckelvalv är aktiverad. Brandväggen måste inaktiveras för att göra nyckelvalvet tillgängligt målgruppsinsikterna igen.
