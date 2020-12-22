---
title: Systemkonfiguration i målgruppsinsikter
description: Läs om systeminställningar för funktionen målgruppsinsikter i Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407105"
---
# <a name="system-configuration"></a>Systemkonfiguration

På sidan **System** finn fyra flikar: **Status**, **Schema**, **Om** och **Allmänt**.

> [!div class="mx-imgBorder"]
> ![Systemsida](media/system-tabs.png "Systemsida")

## <a name="status-tab"></a>Fliken status

På fliken **Status** kan du spåra förlopp för datainmatning, dataexporter samt flera andra viktiga produktprocesser. Granska informationen på den här fliken för att säkerställa fullständigheten av aktiva processer.

På den här fliken finns statustabeller för **datakällor**, **systemprocesser** och **dataförberedelse**. I varje tabell spåras **namnet** på uppgiften och tillhörande entitet, **statusen** för dess senaste körning och när den **senast uppdaterades**.

Visa information om de senaste körningarna av en uppgift genom att välja dess namn.

### <a name="status-types"></a>Statustyper

Det finns sex typer av status för uppgifter. Följande statustyper visas även på sidorna *Matchning*, *Sammanslagning*, *Datakällor*, *Segment*, *Mått*, *Bberikning*, *Aktiviteter* och *Förutsägelser*:

- **Pågår**: uppgiften pågår. Status kan ändras till lyckat eller misslyckat.
- **Klart:** uppgiften har slutförts.
- **Hoppades över:** Uppgiften hoppades över. En eller flera processer längre fram som denna uppgift är beroende av fallerar eller hoppas över.
- **Fel:** Det gick inte att bearbeta uppgiften.
- **Avbruten:** bearbetningen avbröts av användaren innan den avslutades.
- **Köad:** bearbetningen är satt i kö och startas när alla efterföljande aktiviteter har slutförts. Mer information finns i [uppdatera principer](#refresh-policies).

### <a name="refresh-policies"></a>Uppdateringsprinciper

Den här listan visar uppdateringsprinciperna för var och en av huvudprocesserna:

- **Datakällor:** körs enligt det [konfigurerade schemat](#schedule-tab). Är inte beroende av någon annan process. Matchningen beror på att processen har slutförts.
- **Matchning:** körs enligt det [konfigurerade schemat](#schedule-tab). Är beroende av behandlingen av datakällor som används i matchningsdefinitionen. Sammanslagning beror på att processen har slutförts.
- **Sammanslagning**: körs enligt det [konfigurerade schemat](#schedule-tab). Beror på att matchningsprocessen har slutförts. Segment, mått, berikning, sökning, aktiviteter, prediktion och dataförberedelse är beroende av att processen har slutförts.
- **Segment**: körs manuellt (enkel uppdatering) och enligt det [konfigurerade schemat](#schedule-tab). Är beroende av sammanslagning. Insikter beror på behandlingen.
- **Mått**: körs manuellt (enkel uppdatering) och enligt det [konfigurerade schemat](#schedule-tab). Är beroende av sammanslagning.
- **Aktiviteter**: körs manuellt (enkel uppdatering) och enligt det [konfigurerade schemat](#schedule-tab). Är beroende av sammanslagning.
- **Berikning**: körs manuellt (enkel uppdatering) och enligt det [konfigurerade schemat](#schedule-tab). Är beroende av sammanslagning.
- **Sök**: körs manuellt (enkel uppdatering) och enligt det [konfigurerade schemat](#schedule-tab). Är beroende av sammanslagning.
- **Dataförberedelse**: körs enligt det [konfigurerade schemat](#schedule-tab). Är beroende av sammanslagning.
- **Insikter**: körs manuellt (enkel uppdatering) och enligt det [konfigurerade schemat](#schedule-tab). Är beroende av segment.

Välj status för en uppgift om du vill visa information om förloppet för hela jobbet. Med uppdateringsprinciperna ovan kan du få en uppfattning om vad du kan göra för att ta itu med en **överhoppad** eller **köad** uppgift.

## <a name="schedule-tab"></a>Fliken Schemalägg

Använd fliken **Schema** för att schemalägga automatiska uppdateringar av alla dina [inmatade datakällor](data-sources.md). Automatiska uppdateringar hjälper till att se till att uppdateringarna från dina datakällor återspeglas i dina enhetliga kundprofiler.

1. I målgruppsinsikter går du till **Admin** > **System** och väljer fliken **Schema**.

2. Standardtillståndet för den schemalagda uppdateringen är **av**. För att aktivera schemalagda uppdateringar, ändra växlingsknappen överst på skärmen till **På**.

3. Välj mellan **veckovis** (standard) och **daglig** uppdatering. Om du vill schemalägga en ny veckovis uppdatering väljer du en eller flera dagar då du vill att uppdateringen ska utföras.

4. Ange din **Tidszon** och använd sedan listrutan **Tid** för att ange uppdateringstiden. När du är klar väljer du **Ange**. Om du vill schemalägga flera uppdateringar under en och samma dag väljer du **Lägg till en annan tid**.

5. Välj **Spara** för att införa ändringarna.

## <a name="about-tab"></a>Fliken Om

Fliken **Om** innehåller organisationens **Visningsnamn**, aktivt **Miljö-ID**, **Region** och **Sessions-ID**. Om du har mer än en arbetsmiljö bör du ge var och en ett lätt identifierbart visningsnamn.

## <a name="general-tab"></a>Fliken Allmänt

Det finns två alternativ på fliken **Allmänt**, **Språk** och **Land/region-format**.

Appen [stöder ett antal språk](supported-languages.md). Om du vill ändra önskat språk väljer du ett **språk** i listrutan.

Om du vill ändra förvald formatering för datum, tid och tal använder du listrutan **Land/region-format**. En förhandsgranskning av formatering visas under det här fältet. Systemet kommer automatiskt att föreslå ett urval när du väljer ett nytt språk.

Välj **Spara** och bekräfta dina val.

## <a name="api-usage-tab"></a>Fliken API-användning

Hitta information om API-användning i realtid och se vilka händelser som har ägt rum inom ett visst tidsintervall. Mer information finns i [Datainmatning i realtid](real-time-data-ingestion.md).
