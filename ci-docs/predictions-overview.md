---
title: Preditionsöversikt
description: Prediktionsscenarier och alternativ som omfattas av Dynamics 365 Customer Insights-programmet.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610212"
---
# <a name="predictions-overview"></a>Preditionsöversikt

Dynamics 365 Customer Insights levereras med en mängd olika alternativ som utnyttjar AI och maskininlärning för att förutsäga data.

## <a name="out-of-box-models"></a>Färdiga modeller

Det enklaste sättet att börja med att förutsäga data är fördefinierade modeller, ofta kallade färdiga modeller. De kräver bara vissa data och strukturer för att generera insikter snabbt. Följande modeller är tillgängliga:

# <a name="individual-consumers-b-to-c"></a>[Enskilda konsumenter (B2C)](#tab/b2c)

- [Kundens livstidsvärde](predict-customer-lifetime-value.md): Förutsäger en kunds potentiella intäkter under hela interaktionen med ett företag.
- [Produktrekommendation](predict-product-recommendation.md): Föreslår uppsättningar av prediktiva produktrekommendationer baserade på köpbeteende och kunder med liknande inköpsmönster.
- [Prenumerationsomsättning](predict-subscription-churn.md): Förutsäger om en kund riskerar att inte längre använda ditt företags prenumerationsprodukter eller tjänster.
- [Transaktionsbortfall](predict-transactional-churn.md): Förutsäger om en enskild kund inte längre kommer att köpa dina produkter eller tjänster inom en viss tidsram.
- [Sentimentanalys](sentiment-analysis.md): Analyserar sentiment av kundfeedback och identifierar affärsaspekter som nämns ofta.

# <a name="business-accounts-b-to-b"></a>[Företagskonton (B2B)](#tab/b2b)

- [Transaktionsbortfall](predict-transactional-churn.md): Förutsäger om ett kundkonto inte längre kommer att köpa dina produkter eller tjänster inom en viss tidsram.

---

> [!TIP]
> Vi rekommenderar att du regelbundet uppdaterar färdiga modeller med uppdaterade data i syfte att se till att de informerar ditt affärsanvändningsfall på ett korrekt sätt. Data uppdateras ad hoc när systemet matar in nya eller uppdaterade datakällor. I det här fallet kommer modeller emellertid endast att omutvärdera och fortsätta använda befintliga utbildningsdata.
>
> Konfigurera ett **uppdateringsschema** genom att ange modellschema för omprogrammering under konfiguration. Modellen omprogrammeras och omutvärderas i detta schema, som du kan ändra när som helst.

## <a name="azure-machine-learning-integration"></a>Integration av Azure Machine Learning

Om en organisation redan använder maskininlärningsscenarier baserade på Azure Machine Learning-experiment hjälper funktionen anpassade modeller i Customer Insights till att ansluta punkterna. Skapa arbetsflöden som hjälper dig att välja de data du vill generera insikter från och mappa resultaten till dina enhetliga kundprofiler. Mer information finns i [anpassade maskininlärningsmodeller](custom-models.md).

## <a name="manage-existing-predictions"></a>Hantera befintliga förutsägelser

Gå till sidan **Intelligens** > **Prediktioner**. På fliken **Mina förutsägelser** visar du förutsägelserna du skapade, deras förutsägelsetyp, namn på utdataenheten, status, senaste gången förutsägelsen redigerades och senaste gången data uppdaterades. Du kan sortera listan över förutsägelser efter någon kolumn.

Välj en förutsägelse om du vill visa tillgängliga åtgärder.

:::image type="content" source="media/predictions.png" alt-text="Sidan Mina förutsägelser.":::

- **Redigera** förutsägelsen om du vill ändra dess egenskaper.
- [**Uppdatera**](#refresh-a-prediction) förutsägelsen att inkludera de senaste uppgifterna.
- **Visa** prediktionsinformation.
- [**Användbarhetsrapport för data**](#view-the-input-data-usability-report) om du vill visa fel, varningar och rekommendationer.
- **Ta bort** förutsägelsen.

### <a name="refresh-a-prediction"></a>Uppdatera en förutsägelse

Förutsägelser kan uppdateras på ett automatiskt schema eller uppdateras manuellt på begäran. Om du vill uppdatera alla prognoser manuellt väljer du **Uppdatera alla**. Om du vill uppdatera en förutsägelse markerar du den och väljer **Uppdatera alla**. Om du vill [schemalägga en automatisk uppdatering](schedule-refresh.md) går du till **Admin** > **System** > **Schemalägg**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Se användbarhetsrapport över inmatning av data

Rapporten om användbarhet av indata ger en konsoliderad vy över de fel och varningar som dina färdiga förutsägelser kan generera. Det ger också rekommendationer om hur man förbättrar modellens prestanda.

Rapporten är tillgänglig när en modell har slutfört sin utbildningsprocess. Den skapas för varje modell separat, oavsett om träningen har slutförts eller inte.

På fliken **Mina förutsägelser** markerar du förutsägelsen och väljer **Användbarhetsrapport över inmatning av data**. Eller välj från vyn för förutsägelsedetaljer **Användbarhetsrapport över inmatning av data**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exempel på en användbarhetsrapport för indata som visar en tabell med fel, varningar och rekommendationer.":::

Rapporten innehåller:

- **Namn:** Beskrivande namn på felet, varningen eller rekommendationen.
- **Steg:** Modellfas, tåg eller poäng, som informationen refererar till.
- **Tillstånd:** Informationens allvarlighetsgrad (fel, varning, rekommendation).
- **Kolumnnamn:** Kolumn i en entitet som måste ändras för att förbättra modellens prestanda.
- **Entitetsnamn:** Namn på en entitet som måste ändras för att förbättra modellens prestanda.
- **Information:** Information om fel, varning eller rekommendation.

[!INCLUDE [footer-include](includes/footer-banner.md)]
