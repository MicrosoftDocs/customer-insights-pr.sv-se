---
title: Säkerhetsinställningar i Customer Insights
description: Lär dig mer om säkerhetsinställningar i Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947437"
---
# <a name="security-settings-in-customer-insights"></a>Säkerhetsinställningar i Customer Insights

På sidan **Säkerhet** visas alternativ för att konfigurera användarbehörigheter och funktioner som gör Dynamics 365 Customer Insights det säkrare. Endast administratörer kan komma åt den här sidan.

Gå till **Admin** > **Säkerhet** för att konfigurera inställningarna.

Sidan **Säkerhet** innehåller följande flikar:

- [Användare](#users-tab)
- [API:er](#apis-tab)
- [Privata länkar](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Få säker åtkomst till kunddata med Customer Lockbox (förhandsversion)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Fliken Användare

Åtkomst till Customer Insights är begränsad till användare i organisationen som har lagts till i programmet av en administratör. På fliken **Användare** kan du hantera användaråtkomst och deras behörigheter. Mer information finns i [Användarbehörigheter](permissions.md).

## <a name="apis-tab"></a>Fliken API:er

Visa och hantera nycklarna till att använda [Customer Insights API:er](apis.md) med data i miljön.

Du kan skapa nya primära och sekundära nycklar genom att välja **Återskapa primär** eller **Återskapa sekundär**. 

Om du vill blockera API-åtkomst till miljön väljer du **Inaktivera**. Om API:er är inaktiverade kan du välja **Aktivera** för att bevilja åtkomst igen.

## <a name="private-links-tab"></a>Fliken Private Link

[Azure Private Link](/azure/private-link/private-link-overview) låter Customer Insights ansluta till ditt Azure Data Lake Storage-konto via en privat slutpunkt i ditt virtuella nätverk. För data i ett lagringskonto, som inte är synligt för det offentliga Internet, aktiverar Private Link anslutningen till det begränsade nätverket.

> [!IMPORTANT]
> Krav på minimiroll för att konfigurera en Private Link-anslutning:
>
> - Customer Insights: Administratör
> - Azure inbyggd roll: [Lagringskonto deltagare](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Behörigheter för anpassad Azure-roll: [Microsoft.Storage/storageAccounts/read och Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Att konfigurera Private Link i Customer Insights är en process i två steg. Först startar du skapandet av en Private Link från **Admin** > **Säkerhet** > **Private Links** i Customer Insights. I rutan **Lägg till Private Link** visas de lagringskonton från din klientorganisation som du har behörighet att se. Välj ett lagringskonto och godkänn att skapa den Private Link.

Nästa steg är att godkänna Private Link på kontosidan För Data Lake Storage. Öppna länken som visas på skärmen om du vill godkänna den nya Private Link.

## <a name="key-vault-tab"></a>Fliken Key Vault

På fliken **Key Vault** kan du länka och hantera ditt eget [Azure Key Vault](/azure/key-vault/general/basic-concepts) till miljön.
Dedikerade nyckelvalv kan användas för att arrangera och använda hemligheter i en organisations efterlevnadsgräns. Customer Insights kan använda hemligheterna i Azure Key Vault för att [konfigurera anslutningar](connections.md) till system från tredje part.

Mer information finns i [Använd ditt eget Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Få säker åtkomst till kunddata med Customer Lockbox (förhandsversion)

Customer Insights använder funktionen Power Platform Customer Lockbox. Customer Lockbox innehåller ett gränssnitt för att granska och godkänna (eller avvisa) förfrågningar om dataåtkomst. Dessa förfrågningar uppstår när dataåtkomst till kunddata behövs för att lösa ett supportärenden. För att kunna använda den här funktionen måste Customer Insights ha en befintlig anslutning till en Microsoft Dataverse miljö i din klientorganisation.

Mer information om Customer Lockbox finns i [sammanfattningen](/power-platform/admin/about-lockbox#summary) för Power Platform. I artikeln beskrivs även [arbetsflödet](/power-platform/admin/about-lockbox#workflow) och krävs [konfiguration](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) att aktivera Customer Lockbox.

> [!IMPORTANT]
> Globala administratörer för Power Platform eller Power Platform administratörer kan godkänna Customer Lockbox som utfärdas för Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
