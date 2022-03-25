---
title: Skapa och hantera miljöer
description: Läs om hur du registrerar dig för tjänsten och hur du hanterar miljöer.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376898"
---
# <a name="manage-environments"></a>Hantera miljöer

## <a name="switch-environments"></a>Växla miljö

Välj kontrollen **miljö** i det övre högra hörnet av sidan om du vill ändra miljöer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skärmbild av kontrollen för att växla miljöer.":::

Administratörer kan [skapa](create-environment.md) och hantera miljöer.

## <a name="edit-an-existing-environment"></a>Redigera en befintlig miljö

Du kan redigera vissa av detaljerna i befintliga miljöer.

1.  Välj **Miljö**-väljaren i apphuvudet.

2.  Välj ikonen **Redigera**.

3. I rutan **Redigera miljö** kan du uppdatera miljöinställningarna.

Mer information om miljöinställningar finns i [Skapa en ny miljö](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Anslut till Microsoft Dataverse
   
I **Microsoft Dataverse** steget kan du koppla Customer Insights till din Dataverse miljö.

Om du vill använda [färdiga prediktionsmodeller](predictions-overview.md#out-of-box-models), konfigurera datadelning med Dataverse. Du kan också aktivera datainmatning från lokala datakällor, med den Microsoft Dataverse miljö-URL som organisationen administrerar.

> [!IMPORTANT]
> Customer Insights och Dataverse måste finnas i samma region för att kunna dela data.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Konfigurationsalternativ för att aktivera datadelning med Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights stöder inte följande datadelningsscenarier:
> - Om du sparar alla data till din egen Azure Data Lake Storage kommer du inte att kunna aktivera datadelning med en Dataverse-hanterad datasjö.
> - Om du aktiverar datadelning med Dataverse kommer du inte kunna [skapa förutsagda eller saknade värden i en entitet](predictions.md).

## <a name="copy-the-environment-configuration"></a>Kopiera miljökonfigurationen

När du skapar en ny miljö kan du välja att kopiera konfigurationen från en befintlig miljö. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skärmbild av inställningsalternativen i miljöinställningarna.":::

Du ser en lista över alla tillgängliga miljöer i organisationen som du kan kopiera data från.

Följande konfigurationsinställningar kan kopieras:

- Inmatade/importerade datakällor
- Dataföreningskonfiguration (mappning, matchning, sammanslagning)
- Segments
- Mått
- Relationer
- Aktiviteter
- Sök och filtrera index
- Exportmål
- Schemalagd uppdatering
- Berikningar
- Modellhantering
- Rolltilldelningar

Följande data kopieras *inte*:

- Kundprofiler.
- Autentiseringsuppgifter för datakälla. Du måste ange autentiseringsuppgifterna för varje datakälla och uppdatera datakällorna manuellt.

- Datakällor från mappen Common Data Model och Dataverse-hanterad datasjö. Du måste skapa dessa datakällor manuellt med samma namn som i källmiljön.

När du kopierar en miljö visas ett bekräftelsemeddelande om att den nya miljön har skapats. Välj **gå till datakällor** om du vill visa listan över datakällor.

I alla data källor visas statusen **Autentiseringsuppgifter krävs**. Redigera datakällorna och ange autentiseringsuppgifterna för att uppdatera dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista över datakällor som kopierats och som behöver autentisering.":::

När datakällorna har uppdaterats går du till **Data** > **Förena**. Här hittar du inställningar från källmiljön. Redigera dem efter behov eller välj **kör** om du vill starta föreningsprocessen för data och skapa entiteten för enhetliga kunder.

När dataföreningen är klar, gå till **Mått** och **Segment** för att uppdatera dem.

## <a name="change-the-owner-of-an-environment"></a>Byt ägare till miljön

Flera användare kan ha administratörsbehörigheter i Customer Insights, men bara en användare är ägare till en miljö. Som standard är det administratören som ursprungligen skapar en miljö. Som administratör för en miljö kan du tilldela ägarskap till en annan användare med administratörsbehörighet.

1. Välj **Miljö**-väljaren i apphuvudet.

1. Välj ikonen **Redigera**.

1. I rutan **Redigera miljö**, gå till steget **Grundläggande information**.

1. I fältet **Ändra miljöns ägare**, välj ny ägare för miljön.  

1. Välj **Granska och slutför**, sedan **Uppdatera** för att tillämpa ändringarna. 

## <a name="claim-ownership-of-an-environment"></a>Begära ägarskap för en miljö

Om ägaren till en miljö lämnar organisationen eller om användarkontot tas bort, har miljön ingen ägare. En användare med administratörsbehörighet kan begära ägarskapet och bli den nya ägaren. De kan fortsätta äga miljön eller [ändra ägarskapet till en annan administratör](#change-the-owner-of-an-environment). 

Om du vill begära ägarskap väljer du knappen **Ta ägarskap** som visas överst på varje sida i Customer Insights när den ursprungliga ägaren lämnar organisationen.

## <a name="reset-an-existing-environment"></a>Återställa en befintlig miljö

Som ägare av en miljö kan du återställa en miljö till ett tomt tillstånd om du vill ta bort alla konfigurationer och ta bort inrättade data.

1.  Välj **Miljö**-väljaren i apphuvudet. 

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Återställ**. 

4.  Bekräfta borttagningen genom att ange miljönamnet och välj **Återställ**.

## <a name="delete-an-existing-environment"></a>Ta bort en befintlig miljö

Som ägare av en miljö kan du ta bort en miljö som du administrerar.

1.  Välj **Miljö**-väljaren i apphuvudet.

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Ta bort**. 

4.  Bekräfta borttagningen genom att ange miljö namnet och välja **ta bort**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
