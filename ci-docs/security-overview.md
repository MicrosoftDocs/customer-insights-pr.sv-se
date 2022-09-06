---
title: Konfigurera säkerhetsinställningar
description: Lär dig mer om säkerhetsinställningar i Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387280"
---
# <a name="configure-security-settings"></a>Konfigurera säkerhetsinställningar

Hantera API-nycklar, få åtkomst till kunddata och konfigurera en Azure Private Link.

## <a name="manage-api-keys"></a>Hantera API-nycklar

Visa och hantera nycklarna till att använda [Customer Insights API:er](apis.md) med data i miljön.

1. Gå till **Admin** > **Säkerhet** > och välj fliken **API:er**.

1. Om API-åtkomst till miljön inte har konfigurerats väljer du **Aktivera**. Eller om du vill blockera API-åtkomst till miljön väljer du **Inaktivera** och bekräftar.

1. Hantera primära och sekundära API-nycklar:

   1. Välj symbolen **Visa** om du vill visa den primära eller sekundära API-nyckeln.

   1. Välj symbolen **Kopiera** om du vill kopiera den primära eller sekundära API-nyckeln.

   1. Välj **Återskapa primär** eller **Återskapa sekundär** om du vill skapa nya primära och sekundära API-nycklar.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Få säker åtkomst till kunddata med Customer Lockbox (förhandsversion)

Customer Insights använder funktionen Power Platform Customer Lockbox. Customer Lockbox innehåller ett gränssnitt för att granska och godkänna (eller avvisa) förfrågningar om dataåtkomst. Dessa förfrågningar uppstår när dataåtkomst till kunddata behövs för att lösa ett supportärenden. För att kunna använda den här funktionen måste Customer Insights ha en befintlig anslutning till en Microsoft Dataverse miljö i din klientorganisation.

Mer information om Customer Lockbox finns i [sammanfattningen](/power-platform/admin/about-lockbox#summary) för Power Platform. I artikeln beskrivs även [arbetsflödet](/power-platform/admin/about-lockbox#workflow) och krävs [konfiguration](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) att aktivera Customer Lockbox.

> [!IMPORTANT]
> Globala administratörer för Power Platform eller Power Platform administratörer kan godkänna Customer Lockbox som utfärdas för Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Konfigurera en Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview) låter Customer Insights ansluta till ditt Azure Data Lake Storage-konto via en privat slutpunkt i ditt virtuella nätverk. För data i ett lagringskonto, som inte är synligt för det offentliga Internet, aktiverar Private Link anslutningen till det begränsade nätverket.

> [!IMPORTANT]
> Krav på minimiroll för att konfigurera en Private Link-anslutning:
>
> - Customer Insights: Administratör
> - Azure inbyggd roll: [Lagringskonto deltagare](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Behörigheter för anpassad Azure-roll: [Microsoft.Storage/storageAccounts/read och Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. I Customer Insights, gå till **Admin** > **Säkerhet** och välj fliken **Private Links**.

1. Välj **Lägg till Private Link**.

   I rutan **Lägg till Private Link** visas de lagringskonton från din klientorganisation som du har behörighet att se.

1. Välj prenumeration, resursgrupp och lagringskonto.

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara**.

1. Gå till ditt lagringskonto för Data Lake och öppna länken som visas på skärmen.

1. Godkänn Private Link.


[!INCLUDE [footer-include](includes/footer-banner.md)]
