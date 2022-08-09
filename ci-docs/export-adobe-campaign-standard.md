---
title: Exportera segmenten Customer Insights i Adobe Campaign Standard (förhandsversion)
description: Lär dig hur du använder segmenten Customer Insights i Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195542"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exportera segmenten Customer Insights i Adobe Campaign Standard (förhandsversion)

Exportera segment som riktar sig till relevanta målgrupper till Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Processdiagram över stegen som beskrivs i den här artikeln.":::

## <a name="prerequisites"></a>Förutsättningar

- En Adobe Campaign Standard licens.
- Ett [Azure Blob Storage-konto](/azure/storage/blobs/create-data-lake-storage-account) namn och kontonyckel. För att hitta namnet och nyckeln, se [Hantera inställningar för lagringskonto i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampanjöversikt

För att bättre förstå hur du kan använda segment från Customer Insights i Adobe Experience Platform, låt oss titta på en fiktiv exempelkampanj.

Låt oss anta att ditt företag erbjuder en månatlig, prenumerationsbaserad tjänst till dina kunder i USA. Du vill identifiera kunder vars prenumerationer ska förnyas inom de kommande åtta dagarna men ännu inte har förnyat sin prenumeration. För att behålla dessa kunder vill du skicka ett kampanjerbjudande via e-post med Adobe Campaign Standard.

I det här exemplet vill vi köra kampanjen via e-post en gång. Den här artikeln innehåller inte information om hur du kör kampanjen mer än en gång. Men Customer Insights och Adobe Campaign Standard kan också konfigureras för att fungera för ett återkommande kampanjscenario.

## <a name="identify-your-target-audience"></a>Identifiera din målgrupp

I vårt scenario förutsätter vi att kundernas e-postadresser är tillgängliga i Customer Insights och att deras reklampreferenser har analyserats för att identifiera medlemmar i segmenten.

[Segmentet du definierar i Customer Insights](segments.md) kallas **ChurnProneCustomers** och du planerar att skicka e-postkampanjen till dessa kunder.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skärmbild på segmentsidan med ChurnProneCustomers-segmentet som skapats.":::

E-postmeddelandet med erbjudandet som du vill skicka ut innehåller förnamn, efternamn och kundens slutdatum för prenumerationen. Det informerar kunderna om den rabatt de får om de förnyar prenumerationen innan den avslutas.

## <a name="export-your-target-audience"></a>Exportera din målgrupp

### <a name="set-up-connection-to-adobe-campaign"></a>Konfigurera anslutning till Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå till **Admin** > **Anslutningar**.

1. Välj **Lägg till anslutning** och välj **Adobe Campaign**.

1. Ge anslutningen ett beskrivande namn i fältet **visningsnamn**. Namn och typen av anslutning beskriver en anslutning. Vi rekommenderar att du väljer ett namn som förklarar syftet med och målet för anslutningen.

1. Välj vem som kan använda anslutningen. Som standard är det bara administratörer. Mer information finns i [Tillåt att deltagare använder en anslutning för export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ange **Kontonamn**, **Kontonyckel** och **Behållare** för ditt Blob Storage-konto.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skärmbild på lagringskontots konfiguration. ":::

1. Granska [Datasekretess och överensstämmelse](connections.md#data-privacy-and-compliance) och välj **Jag godkänner**.

1. Välj **Spara** för att slutföra anslutningen.

### <a name="configure-an-export"></a>Konfigurera en export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå till **Data** > **Exporter**.

1. Välj **Lägg till export**.

1. I fältet **Anslutning för export** väljer du en anslutning från avsnittet Adobe Campaign. Kontakta en administratör om det inte finns någon anslutning.

1. Ange ett namn för exporten.

1. Välj det segment som du vill exportera. I det här exemplet är det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skärmbild av användargränssnittet för att välja segment med ChurnProneCustomers-segmentet markerat.":::

1. Välj **Nästa**.

1. Nu mappar vi fälten **Källa** från Customer Insights segment till fältnamnen **Mål** i Adobe Campaign Standard profilschema.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Fältmappning för Adobe Campaign Standard-anslutning.":::

   Om du vill lägga till fler attribut väljer du **Lägg till attribut**. Målnamnet kan skilja sig från källfältsnamnet så att du fortfarande kan mappa segmentutdata från Customer Insights till Adobe Campaign Standard om fälten inte har samma namn i de två systemen.

   > [!NOTE]
   > E-postadress används som ett identitetsfält, men du kan använda andra identifierare från kundprofilen för att mappa data till Adobe Campaign Standard.

1. Välj **Spara**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Kontrollera att antalet poster i det exporterade avsnittet ligger inom den tillåtna gränsen för din Adobe Campaign Standard-licens.

Exporterade data lagras i den Azure Blob Storage-behållare som du konfigurerade ovan. Följande mappsökväg skapas automatiskt i behållare: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurera Adobe Campaign Standard

Exporterade segment innehåller de kolumner du markerade när du konfigurerade exporten. Dessa data kan användas för att [skapa profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

För att kunna använda segmenten Adobe Campaign Standard, [utökas profilschemat](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) i Adobe Campaign Standard till att omfatta ytterligare två fält.

I vårt exempel är dessa fält Segmentnamn och Segmentdatum. Vi använder fälten för att identifiera profilerna i Adobe Campaign Standard som vi vill rikta oss till för den här kampanjen.

Om det inte finns några andra poster i Adobe Campaign Standard, förutom de du ska importera, kan du hoppa över det här steget.

## <a name="import-data-into-adobe-campaign-standard"></a>Importera data till Adobe Campaign Standard

Importera den förberedda målgrupp från Customer Insights i Adobe Campaign Standard till [skapa profiler med hjälp av ett arbetsflöde](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Importarbetsflödet i bilden nedan har konfigurerats att köras var åttonde timme och söka efter exporterade Customer Insights (CSV-fil i Azure Blob Storage). Arbetsflödet extraherar .csv-filens innehåll i en angiven kolumnordning. Arbetsflödet har skapats för att utföra grundläggande felhantering och säkerställa att varje post har en e-postadress innan data skickas i Adobe Campaign Standard. Arbetsflödet extraherar också segmentnamnet från filnamnet innan det förs in (upsert) i profildata för Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skärmbild av ett importarbetsflöde i användargränssnittet Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Hämta målgrupp Adobe Campaign Standard

När data har importerats till Adobe Campaign Standard, [skapa ett arbetsflöde](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) och [fråga](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kunderna baserat på segmentnamn och segmentdatum för att välja profiler som identifierades för vår exempelkampanj.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Skapa och skicka e-postmeddelandet med Adobe Campaign Standard

Skapa e-postinnehållet och [testa och skicka](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-postmeddelandet.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exempel på e-post med förnyelseerbjudande från Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
