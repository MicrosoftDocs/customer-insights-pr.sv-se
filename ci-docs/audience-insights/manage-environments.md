---
title: Skapa och hantera miljöer
description: Läs om hur du registrerar dig för tjänsten och hur du hanterar miljöer.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2d977ef4eb585e26b36139681552db22d84759c9
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673766"
---
# <a name="manage-environments"></a>Hantera miljöer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

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

## <a name="reset-an-existing-environment"></a>Återställa en befintlig miljö

Som en administratör kan du återställa en miljö till ett tomt tillstånd om du vill ta bort alla konfigurationer och ta bort de inmatade data.

1.  Välj **Miljö**-väljaren i apphuvudet. 

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Återställ**. 

4.  Bekräfta borttagningen genom att ange miljönamnet och välj **Återställ**.

## <a name="delete-an-existing-environment"></a>Ta bort en befintlig miljö

Som en administratör kan du ta bort en miljö som du administrerar.

1.  Välj **Miljö**-väljaren i apphuvudet.

2.  Välj den miljö du vill återställa och välj ellipsen (**...**). 

3. Välj alternativet **Ta bort**. 

4.  Bekräfta borttagningen genom att ange miljö namnet och välja **ta bort**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
