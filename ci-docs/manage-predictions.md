---
title: Hantera förutsägelser
description: Lär dig hur du hanterar, felsöker och förfinar förutsägelser.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a180f6462452d9830d0daa150a35a9d0acad925a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081923"
---
# <a name="manage-predictions"></a>Hantera förutsägelser

I den här artikeln beskrivs några uppgifter som de flesta prediktionsscenarier delar.

## <a name="troubleshoot-a-failed-prediction"></a>Felsöka en misslyckad förutsägelse

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Välj de lodräta ellipserna bredvid den förutsägelse som du vill visa felloggarna för.

1. Välj **Loggar**.

1. Granska alla fel. Det finns flera typer av fel som kan inträffa, och dessa beskriver vilket villkor som orsakat problemet. Ett fel som till exempel innebär att det inte finns tillräckligt med data för att förutsäga problemet korrekt löses vanligtvis genom att ytterligare data läses in i Customer Insights.

## <a name="input-data-usability-report"></a>Användbarhetsrapport över inmatning av data

Rapporten om användbarhet av indata ger en konsoliderad vy över de fel och varningar som dina färdiga förutsägelser kan generera. Det ger också rekommendationer om hur man förbättrar modellens prestanda.

Rapporten är tillgänglig när en modell har slutfört sin utbildningsprocess. Den skapas för varje modell separat, oavsett om den har slutförts eller inte.

### <a name="view-the-input-data-usability-report"></a>Se användbarhetsrapport över inmatning av data

När en färdig modell har slutfört utbildningssteget, visa rapporten:
- Välj ellipserna bredvid modellnamnet och välj rapporten **Användbarhetsrapport för indata**.
- Välj status för en modell välj **Se användbarhetsrapporten för indata** i sidorutan.
- Välj en av modellerna i listan och välj rapporten **Användbarhetsrapport för indata** i kommandofältet.
- Öppna modellresultatsidan och välj rapporten **Användbarhetsrapport för indata** i kommandofältet.

### <a name="information-in-the-input-data-usability-report"></a>Information i användbarhetsrapport över inmatning av data

Följande kolumner i rapporten innehåller användbar information för att förbättra data för modellen.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exempel på en användbarhetsrapport för indata som visar en tabell med fel, varningar och rekommendationer.":::

- **Namn:** Beskrivande namn på felet, varningen eller rekommendationen.
- **Steg:** Modellfas, tåg eller poäng, som informationen refererar till.
- **Tillstånd:** Informationens allvarlighetsgrad (fel, varning, rekommendation).
- **Kolumnnamn:** Kolumn i en entitet som måste ändras för att förbättra modellens prestanda.
- **Entitetsnamn:** Namn på en entitet som måste ändras för att förbättra modellens prestanda.
- **Information:** Information om fel, varning eller rekommendation.

## <a name="refresh-a-prediction"></a>Uppdatera en förutsägelse

Förutsägelser uppdateras automatiskt i samma [schema som dina data uppdaterar](system.md#schedule-tab) enligt konfigurationen i inställningarna. Du kan uppdatera dem manuellt.

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Markera de lodräta punkterna bredvid den förutsägelse du vill uppdatera.

1. Välj **Uppdatera**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Ta bort en förutsägelse

Om du tar bort en förutsägelse tas även dess utdataentitet bort.

1. Gå till **Intelligens** > **Förutsägelser** och välj fliken **Mina förutsägelser**.

1. Markera de lodräta punkterna bredvid den förutsägelse du vill ta bort.

1. Välj **Ta bort**.
