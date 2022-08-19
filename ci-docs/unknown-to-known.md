---
title: Anpassa dina erfarenheter med data om kända och okända användare
description: Införliva informationen om tidigare okända användare när du vet deras identitet.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224317"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Anpassa dina erfarenheter med data om kända och okända användare

Att hantera kunddata är ingen ny utmaning, men det är allt svårare för användarna att navigera i de olika digitala kanalerbjudandet. En användare som är känd (autentiserad) i en kanal blir okänd (oautentisering) i en annan om den inte är inloggad. Problemet är ofta att oautentiserade (okända) användare inte har ett gemensamt ID. Den kan användas för att associera meningsfulla profilattribut och skapa enhetliga kundprofiler. Customer Insights hjälper dig att lösa det här problemet genom att samla in data från spårningsmetoder i dina källsystem. Genom att konsolidera okända och kända profiler får organisationer en fullständig vy över aktuella profiler och deras tidigare transaktioner, beteenden och demografi. Det går ännu ett steg längre genom att tillhandahålla identitetsmatchning som gör att du kan ena kundaktiviteten över flera kanaler, inklusive din webbplats, köp i butik, lojalitetsprogram etc.

## <a name="sample-scenario"></a>Exempelscenario

Tänk på ett kaffe med en omfattande kundbas som köper kaffe och mat i affärer och beställer produkter online. Ofta autentiseras inte onlinebesökare när de bläddrar i produkterna, vilket gör dem till "okända användare". Det är svårt för kaffet att leverera anpassade erbjudanden och erfarenheter om användarna är okända. Å andra sidan kan kunderna logga in på sina konton och bli "kända användare" till företaget genom att gå med i ett lojalitetssystem, vilket i sin tur tillåter mer anpassade erfarenheter. Customer Insights kan hjälpa kaffet att få information om kända och tidigare okända användare.

Med Customer Insights kan företaget kombinera kundprofiler med aktivitetsdata från oautentiserade (okända) sessioner efter att en användare loggar in och blir känd. Kaffekedjan kan hämta data från andra datakällor med hjälp av inbyggda kopplingar till Customer Insights för att koppla identiteter till kunder från olika kanaler.

## <a name="prerequisites"></a>Förutsättningar

- Webbdata samlas in och innehåller "besöks-ID" för alla besökare.
- Webbdata innehåller "autentiserade användar-ID" för inloggade besökare. Dessa ID är kopplade till lojalitetssystemet.
- Information om viktiga händelser som "Produktvy" och "Utcheckning" definieras och tas med i källdata tillsammans med händelsens tidsstämpel och ett händelse-ID.

I följande tabell visas ett förenklat exempel på hur webbhändelser med högt värde kan fångas in.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Produktvy|
|2|07-23-2022 10:05:00|abc123|707|Lojalitetsinloggning|
|3|07-23-2022 10:10:00|abc123|707|Utcheckning|
|4|07-23-2022 10:20:00|xyz789|--|Produktvy|

## <a name="data-ingestion"></a>Datainsamling

Data om kunder kan komma från din webbplats som händelseinformation och den kan lagras på egen hand eller i dataanalystjänster från tredje part. Webbdata innehåller kända och okända användare om webbplatsen har ett autentiseringsflöde som integrerar med en autentiseringstjänst. Exempelvis ett eCommerce-system som kräver att användarna anger sin fullständiga information för att slutföra en köptransaktion. Eller ett lojalitetssystem som kräver autentisering för att bekräfta en giltig mottagare av rabatterna.

Händelsedata i vårt exempel ovan innehåller de olika profil-ID:erna för de kända och okända användarna. I händelse 1 och 4 är användarna okända och i händelse 2 och 3 registrerar användaren med ID abc123 ett lojalitetsprogram.

:::image type="content" source="media/website-data-source.png" alt-text="Datakällor, inklusive Contoso-webbplats.":::

För mer information om tillgängliga alternativ för datainmatning, se [Översikt över datakällor](data-sources.md).

## <a name="data-unification"></a>Dataförening

Att skapa okända identiteter med kända identiteter underlättar personlig anpassning utifrån användarbeteenden, oavsett deras profiltillstånd (känd eller okänd). Anpassat innehåll för alla användare hjälper kunder att snabbt komma åt de mest relevanta produkter eller tjänster de är intresserade av för tillfället.

Eftersom några av användarna i våra data är kända kan vi använda Customer Insights för att kombinera dessa data med användarens profil. Mer information om att ena dina kundprofiler finns i [Översikt över datasammanslutning](data-unification.md).

1. Välj källfält från entiteten för webbdata. Använd profildata som lagras i dina webbdata och välj vilka fält som ska representera ID:er med demografisk information.

   :::image type="content" source="media/website-source-fields.png" alt-text="Källfält för webbdatakällan":::

1. Lägg till regler om du vill koppla dubblettposter. För webbdata väljer du de mest fyllda data.

1. Konfigurera matchningsregler och villkor. Webbprofilerna händelsedata i det här exemplet matchas på ID med profilerna från de andra datakällorna som innehåller kundinformation. Ange exakta matchningsregler på ID:n som separata regler med var och en av de andra profilentiteterna som har en motsvarande primärnyckel eller ID-matchning. I exemplet används webbhändelseprofildata som den sista matchande entiteten så att andra profildata kombineras först.
   1. Om du inte kontrollerar **inkludera alla poster** skapas enhetliga profiler för kända användare och deras motsvarande okända användar-ID. Det är användbart i scenarier när du är intresserad av att visa kända användares tidigare beteendeaktiviteter när de fortfarande var okända.
   1. Genom att kontrollera **Inkludera alla poster** skapas separata profilposter för okända användare. Okända användare får ett unikt kund-ID. Om en känd profil associeras i profildata för webbhändelser kan den nyligen kända användarens profil också visas och användas för personlig anpassning utifrån tidigare okända beteendedata.

:::image type="content" source="media/website-match-rule.png" alt-text="Matchningsregel för webbplatsens datakälla entitet.":::

## <a name="get-insights"></a>Skaffa insikter

Om kundprofiler skapas för okända och kända användare kan webbhändelsedata med högt värde användas som [aktiviteter](activities.md). Dessa aktiviteter kan användas för att skapa fler insikter. Kunder som till exempel har besökt en webbplats för sex månader sedan (när de fortfarande var okända) eller kunder som inte har ett lojalitets-ID har aldrig gått ut och checkade ut.

:::image type="content" source="media/website-known-unknown.png" alt-text="Skärmbild på kundsidan med kända och okända kunder.":::

[Utöka](enrichment-hub.md) data, skapa [mått](measures.md) och skapa segment [för](segments.md) ytterligare aktivering.

Du kan till exempel skapa segment av kända användare som inte gick ut med några produkter.

Mer information finns i [Segment – översikt](segments.md).

## <a name="activate-insights"></a>Aktivera insikter

Det finns flera sätt att exportera data och vidta åtgärder utifrån underliggande insikter.

Mer information finns i [Översikt över exporter](export-destinations.md).
