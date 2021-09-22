---
title: Roller och behörigheter
description: Översikt över tillgängliga roller och behörigheter för arbetsytemedlemmar.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036715"
---
# <a name="roles-and-permissions"></a>Roller och behörigheter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En arbetsyta är hur du lagrar och hanterar händelser och rapporter. En medlem är en användare som kan komma åt en arbetsyta. Du kan tilldela medlemmar till din arbetsyta och definiera deras roller och behörigheter. Administratörroller hanterar arbetsytor och miljöer samt konfigurerar interaktionsinsikter för andra användare. Deltagarrollerna är inriktade på analytiker som inte behöver konfigurera interaktionsinsikter utan vill skapa egna rapporter, &quot;trattar&quot; eller segment.

## <a name="permissions"></a>Behörigheter
  
I följande diagram visas behörigheter för varje roll. 

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
