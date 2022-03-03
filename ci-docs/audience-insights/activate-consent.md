---
title: Aktivera samtyckesregler för segment
description: Följ stegen för att länka samtyckesdata och aktivera samtyckeskontroller målgruppsinsikter. En administratör kan även inaktivera samtyckeskontroller.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4b55c82229b1a6189c0dd67d145386344286df8a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227515"
---
# <a name="activate-consent-rules"></a>Aktivera samtyckesregler

Med [Samtyckescenter (förhandsversion)](../consent-management/overview.md) kan du godkänna samtyckesuppgifter från olika källor. Använd den enhetliga entiteten *Samtycke* för att tillämpa standard samtyckeskontroller. När du har importerat samtyckesdata i Samtyckescenter och konfigurerat reglerna för data synkroniseras entiteten *Samtycke* automatiskt målgruppsinsikter.

## <a name="enable-consent-checks"></a>Aktivera samtyckeskontroller

Med samtyckesdata importerade till Samtyckescenter (förhandsversion) och regler kan du aktivera godkännandekontroller. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Fliken Samtycke i inställningar för målgruppsinsikter med aktiverade samtyckesdata.":::

1. I målgruppsinsikter går du till **Admin** > **System**.

1. Välj fliken **Samtycke (förhandsversion)**.

1. I avsnittet **Aktivera samtyckeskontroller** anger du växlingen för alla de områden du vill aktivera för **På**.

1. Markera kryssrutan **Tillåt åsidosättning av standardregler** för samtycke om du vill ta bort standardkontroller för samtycke som tillämpas för ett visst segment. 

1. Välj var du vill tillåta åsidosättningar på listrutan.     

1. I avsnittet **Länka samtycke till kundprofiler** väljer du attributet som används som en identifierare för att länka samtyckesdata till kunddata. Det är antagligen ett telefonnummer eller en e-postadress. 

1. Välj **Spara** för att tillämpa inställningen.

## <a name="disable-consent-checks"></a>Inaktivera samtyckeskontroller

För att sluta använda samtyckesdata i målgruppsinsikter måste administratören uppdatera systeminställningarna därefter.

1. I målgruppsinsikter går du till **Admin** > **System**.

1. Välj fliken **Samtycke (förhandsversion)**.

1. I avsnittet **Aktivera samtyckeskontroller** ställer du in växling till **Av**.

> [!TIP]
> Om du vill sluta använda funktionen för godkännandehantering går du [Systeminställningar i Medgivandecenter (förhandsversion)](../consent-management/system-settings.md).
