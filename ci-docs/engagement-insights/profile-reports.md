---
title: Aktivera färdig profilrapporter
description: Så här skapar du färdig profilrapporter grupperade efter ålder, region eller ursprung.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033974"
---
# <a name="out-of-box-profile-reports"></a>Färdig profilrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En rapport är en samling med datavisualisering som hjälper dig att förstå hur användare uppträder. Genom att ansluta till Customer Insights målgruppinsikter, engagemangsinsikter kan insikter om åtaganden visa en rapport med information om enhetliga kundprofiler. I rapporten ingår antalet profiler, grupperade efter ålder och geografisk plats.

## <a name="prerequisites"></a>Förutsättningar

I miljö för målgruppinsikter måste data lagras i ett kundhanterat Azure Data Lake Storage-konto.

Om du använder en utvärderingsversion av funktionen målgruppinsikter eller en miljö i en Customer Insights hanterade datasjö, [kontakta oss](https://go.microsoft.com/fwlink/?linkid=2145734) för hjälp.  


## <a name="enable-the-customer-profile-report"></a>Aktivera rapporten kundprofil

En miljöadministratör måste [skapa en anslutning för målgruppinsikter](configure-connections.md).

När administratören har specificerat anslutningsinformationen kan han eller hon ge åtkomst till andra personer i organisationen för att se rapporten. Miljöadministratören som ställer in anslutningen får automatiskt åtkomst till rapporten. 

När anslutningen har avslutats blir funktionen **Profiler** tillgänglig i det vänstra navigeringsfönstret. 

- Gå till **Upptäck** > **Profiler** om du vill visa rapporten.

Rapporten **Profiler** innehåller visualiseringar om de anslutna kundprofilerna, deras ålder och geografiska placering.

:::image type="content" source="media/customer-profiles.png" alt-text="Rapport för kundprofil.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]