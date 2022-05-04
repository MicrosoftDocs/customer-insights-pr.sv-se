---
title: Säkerhetsinställningar i Dynamics 365 Customer Insights
description: Lär dig mer om säkerhetsinställningar i Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653732"
---
# <a name="security-overview-page"></a>Sidan säkerhetsöversikt

På sidan **Säkerhet** visas alternativ för att konfigurera användarbehörigheter och funktioner som gör Dynamics 365 Customer Insights det säkrare. Endast administratörer kan komma åt den här sidan. 

Gå till **Admin** > **Säkerhet** för att konfigurera inställningarna.

Sidan **Säkerhet** innehåller följande flikar:
- [Användare](#users-tab)
- [API:er](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Fliken Användare

Åtkomst till Customer Insights är begränsad till användare i organisationen som har lagts till i programmet av en administratör. På fliken **Användare** kan du hantera användaråtkomst och deras behörigheter. Mer information finns i [Användarbehörigheter](permissions.md).

## <a name="apis-tab"></a>Fliken API:er

Visa och hantera nycklarna till att använda [Customer Insights API:er](apis.md) med data i miljön.

Du kan skapa nya primära och sekundära nycklar genom att välja **Återskapa primär** eller **Återskapa sekundär**. 

Om du vill blockera API-åtkomst till miljön väljer du **Inaktivera**. Om API:er är inaktiverade kan du välja **Aktivera** för att bevilja åtkomst igen.

## <a name="key-vault-tab"></a>Fliken Key Vault

På fliken **Key Vault** kan du länka och hantera ditt eget [Azure Key Vault](/azure/key-vault/general/basic-concepts) till miljön.
Dedikerade nyckelvalv kan användas för att arrangera och använda hemligheter i en organisations efterlevnadsgräns. Customer Insights kan använda hemligheterna i Azure Key Vault för att [konfigurera anslutningar](connections.md) till system från tredje part.

Mer information finns i [Använd ditt eget Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
