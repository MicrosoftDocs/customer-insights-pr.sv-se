---
title: Exportera Customer Insights-data till Adobe Campaign Standard
description: Lär dig använda målgruppsinsikter i Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596337"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Använd Customer Insights-segment i Adobe Campaign Standard (förhandsversion)

Som användare av målgruppsinsikter för Dynamics 365 Customer Insights kan du ha skapat segment som gör dina marknadsföringskampanjer effektivare genom att rikta sig mot relevanta målgrupper. Om du vill använda ett segment från målgruppsinsikter i Adobe Experience Platform och program som Adobe Campaign Standard måste du följa stegen i den här artikeln.

:::image type="content" source="media/ACS-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a>Förutsättningar

-   Dynamics 365 Customer Insights-licens
-   Licens för Adobe Campaign Standard
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Översikt över kampanj

För att få en bättre förståelse av hur du kan använda segment från målgruppsinsikter i Adobe Experience Platform, ska vi titta på en fiktiv exempelkampanj.

Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA. Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration. Om du vill behålla kunderna måste du skicka ett kampanjerbjudande via e-post med Adobe Campaign Standard.

I det här exemplet vill vi köra kampanjen via e-post en gång. Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång. Målgruppsinsikter och Adobe Campaign Standard konfigureras dock så att de också fungerar för ett återkommande kampanjscenario.

## <a name="identify-your-target-audience"></a>Identifiera din målgrupp

I vårt scenario antar vi att e-postadresserna till kunderna finns tillgängliga målgruppsinsikter och deras kampanjinställningar har analyserats för att identifiera medlemmar i segmenten.

Det [segment du definierar i målgruppsinsikter](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen. Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.

## <a name="export-your-target-audience"></a>Exportera din målgrupp

Med målgruppen identifierad kan vi konfigurera exporten från målgruppsinsikter till ett Azure Blob Storage-konto.

1. I målgruppsinsikter går du till **Admin** > **Exportdestinationer**.

1. I panelen **Adobe Campaign** väljer du **Konfigurera**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationspanel för Adobe Campaign Standard.":::

1. Tillhandahåll ett **visningsnamn** för denna nya exportdestination och ange sedan **kontonamn**, **kontonyckel** och **behållare** för Azure Blob Storage-kontot som du vill exportera segmentet till.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. "::: 

   - Om du vill veta mer om hur du hittar Azure Blob Storage-kontots namn och kontonyckel, se [Hantera lagringsinställningar i Azure-portalen](/azure/storage/common/storage-account-manage).

   - Mer information om hur du skapar en behållare finns i [skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Välj **Nästa**.

1. Välj det segment som du vill exportera. I det här exemplet är det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. Välj **Nästa**.

1. Nu mappar vi fälten **Källa** från målgruppsinsiktssegmentet till fälten **Mål** i Adobe Campaign Standard-profilschemat.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Fältmappning för Adobe Campaign Standard-anslutningsprogrammet.":::

   Om du vill lägga till fler attribut väljer du **Lägg till attribut**. Målnamnet kan vara ett annat än källfältets namn så du kan mappa segmentutdata från målgruppsinsikter till Adobe Campaign Standard om fälten inte har samma namn i de två systemen.

   > [!NOTE]
   > E-postadress används som ett identitetsfält, men du kan använda en annan identifierare från din kundprofil för målgruppsinsikter för att mappa data till Adobe Campaign Standard.

1. Välj **Spara**.

När du har sparat exportmålet hittar du det under **Admin** > **Exporter** > **Mina exportdestinationer**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Skärmbild av lista över exporter och exempelsegment markerade.":::

Nu kan du [exportera segmentet på begäran](export-destinations.md#export-data-on-demand). Exporten kommer också att köras med alla [schemalagda uppdateringar](system.md).

> [!NOTE]
> Kontrollera att antalet poster i det exporterade segmentet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.

Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan. Följande mappsökväg skapas automatiskt i behållaren:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurera Adobe Campaign Standard

När ett segment från målgruppsinsikter exporteras innehåller det de kolumner du valde när du definierade exportmålet i föregående steg. Dessa data kan användas för att [skapa profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

För att kunna använda segmenten i Adobe Campaign Standard måste vi utöka profilschemat i Adobe Campaign Standard så att det omfattar ytterligare två fält. Lär dig hur du [utökar profilresursen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nya fält i Adobe Campaign Standard.

I vårt exempel är dessa fält *Segmentnamn och Segmentdatum (valfritt).*

Vi använder fälten för att identifiera vilka profiler i Adobe Campaign Standard som ska användas för kampanjen.

Om det inte finns några andra poster i Adobe Campaign Standard, förutom de du ska importera, kan du hoppa över det här steget.

## <a name="import-data-into-adobe-campaign-standard"></a>Importera data till Adobe Campaign Standard

Nu när allt är på plats måste vi importera förberedda målgruppsdata från målgruppsinsikter till Adobe Campaign Standard för att skapa profiler. Lär dig [hur du importerar profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) med hjälp av ett arbetsflöde.

Importarbetsflödet i bilden nedan har konfigurerats att köras var 8:e timme och söker efter exporterade målgruppsinsiktssegment (.csv-fil i Azure Blob Storage). Arbetsflödet extraherar .csv-filens innehåll i en angiven kolumnordning. Arbetsflödet har skapats för att utföra grundläggande felhantering och se till att varje post har en e-postadress innan data skickas i Adobe Campaign Standard. Arbetsflödet extraherar också segmentnamnet från filnamnet innan det konfigureras i ACS-profildata.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skärmbild av ett importarbetsflöde i användargränssnittet i Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Hämta målgrupp i Adobe Campaign Standard

När data har importerats till Adobe Campaign Standard kan du [skapa ett arbetsflöde](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) och [fråga](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kunderna baserat på *Segmentnamn* och *Segmentdatum* för att välja profiler som identifierades för exempelkampanjen.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Skapa och skicka e-postmeddelandet med Adobe Campaign Standard

Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-postmeddelande med förnyelseerbjudande från Adobe Campaign Standard.":::