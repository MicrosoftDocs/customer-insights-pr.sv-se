---
title: Aktivera samtyckesregler för segment
description: Följ stegen för att länka samtyckesdata och aktivera samtyckeskontroller i Dynamics 365 Customer Insights. En administratör kan även inaktivera samtyckeskontroller.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755192"
---
# <a name="activate-consent-rules"></a>Aktivera samtyckesregler

Med [Samtyckescenter (förhandsversion)](consent-management/overview.md) kan du godkänna samtyckesuppgifter från olika källor. Använd den enhetliga entiteten *Samtycke* för att tillämpa standard samtyckeskontroller. När du har importerat samtyckesdata och konfigurerat mappningsregler kommer entiteten *Samtycke* synkroniseras automatiskt till Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Aktivera samtyckeskontroller

Med samtyckesdata importerade till Samtyckescenter (förhandsversion) och regler kan du aktivera godkännandekontroller. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Fliken Samtycke i inställningar för Customer Insights med aktiverade samtyckesdata.":::

1. I Customer Insights, gå till **Admin** > **System**.

1. Välj fliken **Samtycke (förhandsversion)**.

1. I avsnittet **Aktivera samtyckeskontroller** anger du växlingen för alla de områden du vill aktivera för **På**.

1. Markera kryssrutan **Tillåt åsidosättning av standardregler** för samtycke om du vill ta bort standardkontroller för samtycke som tillämpas för ett visst segment. 

1. Välj var du vill tillåta åsidosättningar på listrutan.     

1. I avsnittet **Länka samtycke till kundprofiler** väljer du attributet som används som en identifierare för att länka samtyckesdata till kunddata. Det är antagligen ett telefonnummer eller en e-postadress. 

1. Välj **Spara** för att tillämpa inställningen.

## <a name="disable-consent-checks"></a>Inaktivera samtyckeskontroller

För att sluta använda samtyckesdata i Customer Insights måste administratören uppdatera systeminställningarna därefter.

1. I Customer Insights, gå till **Admin** > **System**.

1. Välj fliken **Samtycke (förhandsversion)**.

1. I avsnittet **Aktivera samtyckeskontroller** ställer du in växling till **Av**.

> [!TIP]
> Om du vill sluta använda funktionen för godkännandehantering går du [Systeminställningar i Medgivandecenter (förhandsversion)](consent-management/system-settings.md).
