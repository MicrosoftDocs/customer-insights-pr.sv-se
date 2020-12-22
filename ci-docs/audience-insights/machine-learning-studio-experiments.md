---
title: Machine Learning Studio (klassisk) experiment
description: Använd Machine Learning Studio-modeller (klassisk) i Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 556b6810db0ed2733a3f086291757bd85b77e371
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4669040"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Använd modeller baserade på Azure Machine Learning Studio (klassisk)

Enhetliga data i Dynamics 365 Customer Insights är en källa för maskininlärningsmodeller som kan generera ytterligare affärsinsikter. Customer Insights integreras med Machine Learning Studio (klassisk) för att använda dina egna anpassade modeller. Om du vill se hur modeller som utvecklats i Azure Machine Learning integreras med Customer Insights, se [Azure Machine Learning-experiment](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Förutsättningar

- Åtkomst till Customer Insights
- Aktiv prenumeration på Azure Enterprise
- [Enhetliga kundprofiler](data-unification.md)
- [Konfigurera entitetsexport till Azure Blob-lagring](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Konfigurera Machine Learning Studio klassisk

I ett första steg måste vi skapa en arbetsyta för och öppna Machine Learning Studio (klassisk).

1. Gå till [https://www.portal.azure.com](https://www.portal.azure.com/) och logga in.

1. Välj **Skapa en resurs**.

1. Sök **Machine Learning Studio-arbetsyta** och välj **Skapa**.

1. Ange de uppgifter som krävs för att [skapa arbetsytan](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). Välj **prisnivå för webbtjänstplanen** baserat på den mängd data du planerar att importera. Bästa prestanda uppnår du genom att välja den **plats** som är geografiskt närmast dig.

1. När du har skapat resursen visas instrumentpanelen för Machine Learning Studio-arbetsytan. Välj **Starta Machine Learning Studio**.

   ![Azure Machine Learning Studio-användargränssnitt](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Arbeta Azure Machine Learning Studio

Nu kan du skapa ett nytt experiment eller importera en befintlig mall från exempelgalleriet. Det finns exempelexperiment för tre standardscenarier:

- [Omsättningsprediktion](#churn-analysis)

- [Kundens livstidsvärde](#customer-lifetime-value-prediction)

- [Produktrekommendation eller nästa bästa åtgärd](#productrecommendation-or-next-best-action)

1. Om du skapar ett nytt experiment eller använder en experiment mall i galleriet måste du konfigurera egenskaperna **Importera data**. Använd den guidade upplevelsen eller ge detaljer direkt för att komma åt Azure Blob Storage som innehåller dina data.  

   ![Azure Machine Learning Studio-experiment](media/azure-machine-learning-studio-experiment.png)

1. Nu kan du skapa en anpassad processpipeline för att rengöra och förbehandla data, extrahera funktioner och utbilda en lämplig modell.

1. Testa och optimera modell prestanda.

1. När du är nöjd med kvaliteten på en modell markerar du **Konfigurera webbtjänst** > **Prediktiva webbtjänst**. Det här alternativet importerar den utbildade modellen och funktionalisering pipeline från utbildningsexperimentet till en prediktiv tjänst. För den prediktiva tjänsten kan du utföra en ny uppsättning indata med det schema som används i övningsexperimentet för att göra prognoser.

   ![Konfigurera en prediktiv webbtjänst](media/predictive-webservice-control.png)

1. När experimentet för prediktiv webbtjänst fungerar kan du distribuera det för automatisk schemaläggning. Om du vill att webbtjänsten ska fungera med Customer Insights väljer du **distribuera webbtjänst** > **förhandsversion av distribuera webbtjänst [ny]**. [Läs mer om distribuera en webbtjänst](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service)

   ![Distribuera en prediktiv webbtjänst](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Exempelmodeller från galleriet

Vi använder ett fiktivt scenario med Contoso hotell för modellerna i den här artikeln. Contoso Hotel samlar in följande data:

- CRM-data som består av hotell vistelseaktivitet. Datauppsättningen innehåller information om vilka datum som är kvar för varje registrerad kund. Den innehåller också information om bokning, rumstyper, detaljer om utgifter och så vidare. Uppgifterna omfattar fyra år, från 2014 till januari till januari 2018.
- Kund profiler för hotellgäster. Profilerna innehåller information om varje kund, inklusive namn, födelsedatum, postadress, kön och telefonnummer.
- Användning av tjänster som hotellen erbjuder, till exempel spa, tvätt, WiFi eller bud. Den här informationen loggas för varje registrerad kund. Användning av tjänster länkas vanligen till vistelsen. I vissa fall kan tjänster användas av kunder utan att behöva vistas på hotellet.

## <a name="churn-analysis"></a>Omsättningsanalys

Omsättningsanalysen gäller för olika affärs områden. I det här exemplet ska vi titta på tjänstomsättning, specifikt inom ramen för hotelltjänster enligt beskrivningen ovan. Den innehåller ett arbetsexempel på ett försäljningsförlopp som kan användas som utgångspunkt för vilken annan typ av omsättningsmodell som helst.

### <a name="definition-of-churn"></a>Definition av omsättning

Definitionen av omsättning kan skilja sig från de olika scenarierna. I det här exemplet bör en gäst som inte har besökt hotellet under det senaste året vara märkt som uppdelad på omsättning.  

Du kan importera experimentmallen från galleriet. Börja med att importera data för **hotelvistelseaktivitet**, **kunddata** och **tjänstens användningsdata** från Azure Blob Storage.

   ![Importera data för omsättningsmodell](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Funktionalisering

Baserat på definitionen av omsättningen identifierar vi först de obearbetade funktioner som påverkar etiketten. Sedan bearbetar vi dessa obearbetade funktioner till numeriska funktioner som kan användas med maskininlärningsmodeller. Dataintegrering sker i Customer Insights så att vi kan sammanfoga dessa tabeller genom att använda *kund-ID*.

   ![Anslut importerade data](media/join-imported-data.png)

Funktionalisering för att bygga modellen för omsättningsanalys kan vara lite knepigt. Data är en funktion av tid med ny hotellaktivitet registrerad dagligen. Under funktionalisering vill vi skapa statiska funktioner från de dynamiska data. I det här fallet genererar vi flera funktioner från hotellaktiviteten med ett skjutfönster för ett år. Vi expanderar även de kategorifunktionerna som rumstyp eller bokningstyp i separata funktioner med enkel kodning.  

Slutlig lista över funktioner:

| **Antal**  | **Original_Column**          | **Härledda funktioner**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Rumstyp                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Bokningstyp                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Resekategori              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Spenderade pengar                | TotalDollarSpent                                                                                                                          |
| 5           | Datum för incheckning och kassa  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Tjänsteanvändning                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Modellval

Nu måste du välja den optimala algoritm som ska användas. I det här fallet bygger de flesta funktioner på kategorifunktioner. Vanligtvis fungerar beslutsträdsbaserade modeller bra. Om det bara finns numeriska funktioner kan neuralt nätverk vara ett bättre val. Support vektormaskin (SVM) är också en bra kandidat i sådana situationer. men det behövs en del av finjusteringen för att extrahera bästa prestanda. Vi väljer **ett beslutsträd med två klasser** som den föredragna modellen, följd av **SVM i två klasser** som den andra modellen. Med Azure Machine Learning Studio kan du göra ett A/B-test och därför bör du börja med två modeller i stället för en.

I följande bild visas modellutbildning och utvärderingsförlopp från Azure Machine Learning Studio:

![Omsättningsmodell i Azure Machine Learning Studio](media/azure-machine-learning-model.png)

Vi kan också använda en metod med namnet **permutationsfunktionens prioritet**, en viktig aspekt av modelloptimeringen. De inbyggda modellerna har liten eller ingen insikt i effekten av någon särskild funktion på den slutliga prediktionen. I kalkylatorn för funktionsprioritet används en anpassad algoritm för att beräkna hur enskilda funktioner påverkas av resultatet för en viss modell. Funktionens prioritet är normaliserad mellan +1 och -1. En negativ inverkan betyder att motsvarande funktion har ett kontraintuitivt inflytande på resultatet och bör tas bort från modellen. Ett positivt inflytande tyder på att funktionen bidrar mycket över prediktion. De här värdena är inte korrelationskoefficienter eftersom de är olika mått. Mer information finns i [permutationsfunktionens prioritet](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Hela [omsättningsexperimentet finns tillgängligt i Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Prediktion av kundens livstidsvärde

Beräkningen av kundens livstidsvärde (CLTV) är ett av de nyckelvärden som ett företag kan använda för att utvärdera och segmentera sina kunder. För hotellverksamheterna är det mycket viktigt att känna till sina kunder. Till exempel är det viktigt att förstå faktorer som gör kunder bra. Det hjälper hotelledningen att utvärdera vilka funktioner de behöver fokusera på och förbättra för att tillfredsställa sina högt betalande kunder. Dessa beslut kan ha en direkt inverkan på försäljning och intäkter.  

### <a name="definition-of-cltv"></a>Definition av CLTV

I det här exemplet definierar vi CLTV för en kund som det totala belopp som kunden förväntas spendera under de kommande 365 dagarna. Vi använder de senaste tre årens data för alla kunder för att förutse detta värde.

### <a name="featurization"></a>Funktionalisering

I det här fallet ska funktionalisering vara ungefär som omsättningssituationen. Etiketterna och de förutsagda värdena är emellertid annorlunda än de som anges ovan.

### <a name="model-selection"></a>Modellval

Att förutsäga CLTV är ett regressionsproblem eftersom det förutsagda värdet är en positiv, kontinuerlig variabel. Baserat på funktionsegenskaperna väljer vi **Regression av förbättrat beslutsträd** som en algoritm och **Neural nätverksregression** som en annan algoritm för att utbilda modellen.

## <a name="product-recommendation-or-next-best-action"></a>Produktrekommendation eller näst bästa åtgärd

Produktrekommendationer i ett hotellscenario tolkas som en rekommendation av tjänster från hotellet till kunderna. Målet är att välja lämpliga tjänster för kunderna så att användningen av dem maximeras. Det påminner om film rekommendationer för användare av tjänster för videoströmning.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definition av produktrekommendation eller nästa bästa åtgärd

Vi definierar målet med att maximera antalet kronor i tjänstanvändningen genom att erbjuda de bästa tjänsterna till hotellkunder utifrån deras intresse.

### <a name="featurization"></a>Funktionalisering

Precis som i omsättningsmodellen sammanfogar vi hotellets ServiceCustomerID med CustomerID för att skapa rekommendationer konsekvent per CustomerID.

![Funktionalisering för rekommendationsmodellen](media/azure-machine-learning-model-featurization.png)

Data hämtas från tre olika entiteter och funktioner hämtas från dem. Funktionalisering för rekommendationsproblemet skiljer sig jämfört med omsättnings- eller CLTV-scenarier. För rekommendationsmodellen krävs indata i form av tre uppsättningar funktioner.

### <a name="model-selection"></a>Modellval

Vi förutsäger produkter eller tjänster med hjälp av algoritmen som kallas **Träna Matchbox-rekommenderaren** för att träna rekommendationsmodellen.

![Algoritmen för produktrekommendationer](media/azure-machine-learning-model-recommendation-algorithm.png)

De tre ingångsportarna för modellen **Träna Matchbox-rekommenderaren** tar in utbildningstjänstens användningsdata, kundbeskrivning (valfritt) och tjänstbeskrivning. Det finns tre olika sätt att bedöma modellen på. En är för modellutvärdering, där en poäng för normaliserad diskonterad vinst (NDCG) beräknas för att rangordna de klassificerade objekten. I det här testet har vi NDCG-poängen som 0,97. De andra två alternativen bedömer modellen för hela den rekommenderade tjänstkatalogen, eller endast de artiklar som användarna inte har använt tidigare.

Om vi tittar närmare på fördelningen av rekommendationer i hela tjänstkatalogen, ser vi att telefon, WiFi och kurir är de tjänster som rekommenderas mest. Detta överensstämmer med vad som upptäcktes från distributionerna av tjänstens förbrukningsdata:

![Resultat för rekommendationsmodell](media/azure-machine-learning-model-output.png)

Hela [produktrekommendationsexperimentet finns i Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrera anpassade modeller

Om du vill använda dessa förutsägelser i Customer Insights måste du **exportera** förutsägelserna tillsammans med kund-ID. [Exportera dem till samma Azure Blob Storage-plats](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs) som du exporterar källdata till. Den förutsägbara webbtjänsten kan schemaläggas att köras regelbundet och uppdateras.

Data som genereras av den anpassade modellen kan användas för att ytterligare berika dina kunddata. Mer information finns i [anpassade maskininlärningsmodeller](custom-models.md).
