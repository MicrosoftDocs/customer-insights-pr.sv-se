---
title: Exportera Customer Insights-data till Adobe Campaign Standard
description: Lär dig hur segment av målgruppsinsikter i Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 6b90ee53236fdd601ecdfd8e6117a15269a08084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227780"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Använda Customer Insights-segment i Adobe Campaign Standard (förhandsgranskning)

Som användare av målgruppsikter i Dynamics 365 Customer Insights kan du ha skapat segment i avsikt att göra dina marknadsföringskampanjer mer effektiva genom att rikta dig till relevanta målgrupper. Om du vill använda ett segment för målgruppsinsikter Adobe Experience Platform och program som Adobe Campaign Standard, måste du följa några steg som beskrivs i den här artikeln.

:::image type="content" source="media/ACS-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a>Förutsättningar

-   Dynamics 365 Customer Insights-licens
-   Adobe Campaign Standard licens
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Kampanjöversikt

Om du vill ha en bättre förståelse av hur du kan använda segment från målgruppsinsikter i Adobe Experience Platform ska vi titta på en fiktiv exempelkampanj.

Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA. Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration. För att behålla dessa kunder vill du skicka ett kampanjerbjudande via e-post med Adobe Campaign Standard.

I det här exemplet vill vi köra kampanjen via e-post en gång. Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång. Däremot kan målgruppsinsikter och Adobe Campaign Standard konfigureras så att de också fungerar för ett återkommande kampanjscenario.

## <a name="identify-your-target-audience"></a>Identifiera din målgrupp

I vårt scenario antar vi att e-postadresserna till kunderna finns tillgängliga målgruppsinsikter och deras kampanjinställningar har analyserats för att identifiera medlemmar i segmenten.

Det [segment du definierar i målgruppsinsikter](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen. Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.

## <a name="export-your-target-audience"></a>Exportera din målgrupp

### <a name="configure-a-connection"></a>Konfigurera en anslutning

Med målgruppen identifierad kan vi konfigurera exporten från målgruppsinsikter till ett Azure Blob Storage-konto.

1. I målgruppsinsikter, gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Adobe Campaign** om du vill konfigurera anslutningen, eller välj **Konfigurera** i panelen **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationspanel för Adobe Campaign Standard.":::

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Om du inte gör något blir standardvärdet Administratörer. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Azure Blob Storage-konto som du vill exportera segmentet till.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 

   - Om du vill veta mer om hur du hittar Azure Blob Storage-kontots namn och kontonyckel, se [Hantera inställningar för lagringskonto i Azure-portalen](/azure/storage/common/storage-account-manage).

   - Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Välj **Spara** för att slutföra anslutningen.

### <a name="configure-an-export"></a>Konfigurera en export

Du kan konfigurera den här exporten om du har åtkomst till en anslutning av den här typen. Mer information finns i [Behörigheter som behövs för att konfigurera en export](export-destinations.md#set-up-a-new-export).

1. Gå till **Data** > **Exporter**.

1. Välj för att skapa en ny export **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet Adobe Campaign. Om avsnittets namn inte visas är inga anslutningar av den här typen tillgängliga för dig.

1. Välj det segment som du vill exportera. I det här exemplet är det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. Välj **Nästa**.

1. Nu mappar vi fältet **källa** från segmentet målgruppsinsikter till fältnamnet i **Mål** för Adobe Campaign Standard-profilens schema.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Fältmappning för Adobe Campaign Standard-anslutning.":::

   Om du vill lägga till fler attribut väljer du **Lägg till attribut**. Målnamnet kan vara ett annat än källfältsnamnet så att du ändå kan mappa segment utdata från målgruppsinsikter till Adobe Campaign Standard om fälten inte har samma namn i de två systemen.

   > [!NOTE]
   > E-postadress används som ett identitetsfält, men du kan använda en annan identifierare från din kundprofil för målgruppsinsikter för att mappa data till Adobe Campaign Standard.

1. Välj **Spara**.

När du har sparat exportmålet visas det i **Data** > **Exporter**.

Nu kan du [exportera segmentet på begäran](export-destinations.md#run-exports-on-demand). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).

> [!NOTE]
> Kontrollera att antalet poster i det exporterade avsnittet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.

Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan. Följande mappsökväg skapas automatiskt i behållaren:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurera Adobe Campaign Standard

När ett segment från målgruppsinsikter exporteras innehåller det de kolumner du valde när du definierade exportmålet i föregående steg. Dessa data kan användas för att [skapa profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

För att kunna använda segmenten Adobe Campaign Standard, måste profilschemat i Adobe Campaign Standard utökas till att omfatta ytterligare två fält. Lär dig hur du [utökar profilresursen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nya fält i Adobe Campaign Standard.

I vårt exempel är dessa fält *Segmentnamn och Segmentdatum (valfritt)*.

Vi använder fälten för att identifiera profilerna i Adobe Campaign Standard som vi vill rikta oss till för den här kampanjen.

Om det inte finns några andra poster i Adobe Campaign Standard, förutom de du ska importera, kan du hoppa över det här steget.

## <a name="import-data-into-adobe-campaign-standard"></a>Importera data till Adobe Campaign Standard

Nu när allt är på plats måste vi importera de förberedda målgruppsdata från målgruppsinsikter till Adobe Campaign Standard för att skapa profiler. Lär dig [hur du importerar profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) med ett arbetsflöde.

Importarbetsflödet i bilden nedan har konfigurerats att köras var åttonde timme och söka efter exporterade segment för målgruppsikter (.csv-fil i Azure Blob Storage). Arbetsflödet extraherar .csv-filens innehåll i en angiven kolumnordning. Arbetsflödet har skapats för att utföra grundläggande felhantering och säkerställa att varje post har en e-postadress innan data skickas i Adobe Campaign Standard. Arbetsflödet extraherar också segmentnamnet från filnamnet innan det förs in (upsert) i profildata för Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skärmbild av ett importarbetsflöde i användargränssnittet Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Hämta målgrupp Adobe Campaign Standard

När data har importerats till Adobe Campaign Standard [kan du skapa arbetsflöde](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) och [fråga](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kunderna baserade på *Segmentnamn* och *Segmentdatum* för att välja profiler som identifierats för vår exempelkampanj.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Skapa och skicka e-postmeddelandet med Adobe Campaign Standard

Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-post med förnyelseerbjudande från Adobe Campaign Standard.":::
