---
title: Ansluta till ett Azure Data Lake Storage konto med hjälp av ett Azure-tjänstobjekt
description: Använd en Azure-huvudkonto för tjänsten och anslut till din egen datasjö.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081776"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ansluta till ett Azure Data Lake Storage konto med hjälp av ett Azure-tjänstobjekt

Denna artikel diskuterar hur du ansluter Dynamics 365 Customer Insights med ett Azure Data Lake Storage konto med ett Azure huvudkonto för tjänsten istället för lagringskontonycklar.

Automatiserade verktyg som använder Azure-tjänster bör alltid ha begränsade behörigheter. I stället för att låta program logga in som en fullt privilegierad användare erbjuder Azure huvudkonton för tjänsten. Du kan använda tjänstens huvudkonto för att säkert [lägga till eller redigera en mapp för Common Data Model som datakälla](connect-common-data-model.md) eller [skapa eller uppdatera en miljö](create-environment.md).

> [!IMPORTANT]
>
> - Data Lake Storage-kontot som använder tjänstens huvudkonto måste vara Gen2 och ha [hierarkiskt namnområde aktiverat](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1-lagringskonton stöds inte.
> - Du behöver administratörsbehörighet för din Azure-klientorganisation för att skapa ett huvudkonto för tjänsten.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Skapa ett Azure-huvudkonto för tjänsten för Customer Insights

Innan du skapar ett nytt tjänstens huvudkonto för Customer Insights bör du kontrollera om det redan finns i organisationen.

### <a name="look-for-an-existing-service-principal"></a>Leta efter ett befintligt huvudkonto för tjänsten

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

2. Från **Azure-tjänster**, välj **Azure Active Directory**.

3. Under **Hantera** väljer du **Microsoft-program**.

4. Lägg till ett filter för **Program-ID som startar med**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller sök efter namnet `Dynamics 365 AI for Customer Insights`.

5. Om du hittar en matchande post betyder det att huvudkonto för tjänsten redan finns.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skärmbild med ett befintligt huvudkonto för tjänsten.":::

6. Om inga resultat returneras kan du [skapa ett nytt huvudnamn för tjänsten](#create-a-new-service-principal). I de flesta fall finns detta redan, och du behöver då bara ge tjänstehuvudkontot behörighet till lagringskontot.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Bevilja behörighet till huvudkontot för tjänsten för åtkomst till lagringskontot

Gå till Azure-portalen och ge behörigheter till tjänstehuvudmannen för det lagringskonto du vill använda i Customer Insights. En av följande roller måste tilldelas till lagringskontot eller -behållare:

|Autentiseringsuppgift|Krav|
|----------|------------|
|För närvarande inloggad användare|**Roll**: Storage Blob Data-läsare, Storage Blob-deltagare eller Storage Blob-ägare.<br>**Nivå**: Behörigheter kan ges för lagringskontot eller behållare.</br>|
|Customer Insights huvudkonto -<br>Använda Azure Data Lake Storage som datakälla</br>|Alternativ 1<ul><li>**Roll**: Storage Blob Data-läsare, Storage Blob Data-deltagare eller Storage Blob Data-ägare.</li><li>**Nivå**: Behörigheter ska ges för lagringskontot.</li></ul>Alternativ 2 *(utan att dela tjänstobjekt åtkomst till lagringskontot)*<ul><li>**Roll 1**: Storage Blob Data-läsare, Storage Blob Data-deltagare eller Storage Blob Data-ägare.</li><li>**Nivå**: Behörigheter ska ges för behållare.</li><li>**Roll 2**: Storage Blob Data-delegerare.</li><li>**Nivå**: Behörigheter ska ges för lagringskontot.</li></ul>|
|Customer Insights huvudkonto - <br>Använda Azure Data Lake Storage som utdata eller destination</br>|Alternativ 1<ul><li>**Roll**: Storage Blob Data-deltagare eller Storage Blob-ägare.</li><li>**Nivå**: Behörigheter ska ges för lagringskontot.</li></ul>Alternativ 2 *(utan att dela tjänstobjekt åtkomst till lagringskontot)*<ul><li>**Roll**: Storage Blob Data-deltagare eller Storage Blob-ägare.</li><li>**Nivå**: Behörigheter ska ges för behållare.</li><li>**Roll 2**: Storage Blob-delegerare.</li><li>**Nivå**: Behörigheter ska ges för lagringskontot.</li></ul>|

1. Gå till [Azure admin-portalen](https://portal.azure.com) och logga in på din organisation.

1. Öppna det lagringskonto som du vill att tjänstansvarig för Customer Insights ska ha åtkomst till.

1. I den vänstra ruta, välj **Åtkomstkontroll (IAM)** och välj sedan **Lägg till** > **Lägg till rolltilldelning**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skärmbild som visar Azure-portalen och lägger till en rolltilldelning.":::

1. I fönstret **Lägg till rolltilldelning** ange följande egenskaper:
   - Roll: Storage Blob Data-läsare, Storage Blob-deltagare eller Storage Blob Data-ägare baserad på de autentiseringsuppgifter ovan.
   - Tilldela åtkomst till: **användare, grupp eller huvudkonto för tjänsten**
   - Välj medlemmar: **Dynamics 365 AI for Customer Insights** ([huvudkontot för tjänsten](#create-a-new-service-principal) du sökte tidigare i den här proceduren)

1. Välj **Granska + tilldela**.

Det kan ta upp till 15 minuter att distribuera ändringarna.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Ange Azure-resurs-ID eller Azure-prenumerationsinformationen i bilagan för lagringskontot i Customer Insights

Du kan bifoga ett Data Lake Storage-konton i Customer Insights för att [lagra utdata](manage-environments.md) eller [använda dem som datakälla](connect-dataverse-managed-lake.md). Med det här alternativet kan du välja mellan en resursbaserad metod eller en prenumerationsbaserad metod. Beroende på vilken metod du väljer följer du proceduren i något av följande avsnitt.

### <a name="resource-based-storage-account-connection"></a>Resursbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. I det vänstra fönstret går du till **Inställningar** > **Slutpunkter**.

1. Kopiera resurs-ID för lagringskonto.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiera resurs-ID för lagringskonto.":::

1. I Customer Insights infogar du resurs-ID:t i resursfältet som visas på skärmen för lagringskontoanslutning.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Ange resurs-ID för lagringskonto.":::   

1. Fortsätt med de återstående stegen i Customer Insights för att bifoga lagringskontot.

### <a name="subscription-based-storage-account-connection"></a>Prenumerationsbaserad anslutning till lagringskonto

1. Gå till [Azure admin-portalen](https://portal.azure.com), logga in till din prenumeration och öppna lagringskontot.

1. I den vänstra rutan, gå till **Inställningar** > **Egenskaper**.

1. Granska **Prenumeration**, **Resursgrupp** och **Namn** för lagringskontot för att se till att du väljer rätt värden i Customer Insights.

1. I Customer Insights väljer du värden för motsvarande fält när du bifogar ett lagringskonto.

1. Fortsätt med de återstående stegen i Customer Insights för att bifoga lagringskontot.

### <a name="create-a-new-service-principal"></a>Skapa ett nytt huvudkonto för tjänsten

1. Installera den senaste versionen av Azure Active Directory PowerShell for Graph. Mer information finns i [Installera Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. På datorn trycker du på Windows-tangenten på tangentbordet och söker efter **Windows PowerShell** och väljer **Kör som administratör**.

   1. I PowerShell-fönstret som öppnas anger du `Install-Module AzureAD`.

2. Skapa huvudkonto för tjänsten för Customer Insights med Azure AD PowerShell-modulen.

   1. I PowerShell-fönstret anger du `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Ersätt *[ditt katalog-ID]* med det faktiska Katalog-ID för din Azure-prenumeration där du vill skapa tjänstens huvudnamn. Parametern för miljönamn `AzureEnvironmentName` är valfri.
  
   1. Ange `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Det här kommandot skapar tjänsthuvudman för Customer Insights på den valda Azure-prenumerationen.

[!INCLUDE [footer-include](includes/footer-banner.md)]