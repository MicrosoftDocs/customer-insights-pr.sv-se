---
title: Roller och behörigheter
description: Översikt över tillgängliga roller och behörigheter för arbetsytemedlemmar.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227561"
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
