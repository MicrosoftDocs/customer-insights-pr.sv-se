---
title: Roller och behörigheter
description: Översikt över tillgängliga roller och behörigheter för arbetsytemedlemmar.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645559"
---
# <a name="roles-and-permissions"></a>Roller och behörigheter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En arbetsyta är där du lagrar och hanterar händelser och rapporter. Mer information finns i [Skapa en arbetsyta och lägga till medlemmar](create-workspace.md). 

En arbetsyta kan innehålla följande roller och behörigheter:

- *Medlemsroller* är användare som kan komma åt en arbetsyta. Du kan tilldela medlemmar till din arbetsyta och definiera deras roller och behörigheter. 
- *Administratörroller* hanterar arbetsytor och miljöer samt konfigurerar interaktionsinsikter för andra användare. 
- *Deltagarroller* är inriktade på analytiker som inte behöver konfigurera engagemangsinsikter utan vill skapa egna rapporter, trattar eller segment.

## <a name="permissions"></a>Behörigheter
  
I följande tabell visas behörigheter för varje roll. 

| Behörighet | Miljöadministratör | Administratör för arbetsyta | Miljödeltagare | Deltagare för arbetsyta | 
|--|--|--|--|--|
| Skapa miljöer (skaparen blir automatiskt miljöadministratör) | X* | X* | X* | X* |  
| Konfigurera miljö (miljömedlemmar, ta bort miljö) | X |  |  |  |  
| Skapa arbetsytor | X |  |  |  |  
| Konfigurera arbetsytor (arbetsytemedlemmar, ta bort arbetsyta) | X | X |  |  |  
| Konfigurera händelser och förfinade händelser | X | X | |  |  
| Visa händelser på arbetsytan och förfinade händelser | X | X | |  |  
| Visa arbetsyteresurser (rapporter, segment och mått)| X | X | X | X |  
| Skapa anpassade rapporter och &quot;trattar&quot; | X | X | X | X |  
| Skapa grundmått och mått| X | X |  |  |  
| Skapa segment| X | X | X | X |  

*Det går bara att skapa utvärderingsmiljöer i förhandsversionen. 

## <a name="add-members"></a>Lägg till medlemmar

Du kan lägga till och ta bort medlemmar från arbetsytor och miljöer. För mer information, se [Miljöer och arbetsytor](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
