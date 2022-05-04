---
title: Utöka kundprofiler med data från Microsoft Office 365
description: Använd tillverkarspecifika data från Microsoft Office för att utöka dina kundprofiler med kontaktdata.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 782042ff643bd0cc70ac53e5680bfd0c68944d84
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647760"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Utöka kundprofiler med data från kontaktdata (förhandsgranska)

Använd data från Microsoft Office 365 för att utöka dina kundkontoprofiler med insikter om åtaganden via Office 365 appar. Kontaktdata består av e-post- och mötesaktiviteter som samlas in på kontonivån. Till exempel antalet e-postmeddelanden från ett affärskonto eller antalet möten med kontot. Inga data om enskilda användare görs tillgängliga. 

Den här berikningen finns i följande regioner, Storbritannien, Europa och Nordamerika.

## <a name="prerequisites"></a>Förutsättningar

För att konfigurera berikningen måste följande villkor vara uppfyllda:

- Du måste ha en aktiv Office 365-molnlicens.
- Du har [enhetliga kundprofiler](customer-profiles.md) som bygger på [affärskonton](work-with-business-accounts.md).
- Din Customer Insights-miljö måste ha en [Microsoft Dataverse organisation bifogad](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Du har [administratör](permissions.md#admin) behörigheter.
- Du har, eller kan få, godkännande från din Office 365 klientorganisationsadministratör för att använda Office 365 data för att ge **Insikter för organisation** inom Dynamics 365-appar.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning**.

1. Gå till fliken **Upptäck** och välj **Berika mina data** på panelen **Kontoengagemang**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Panelen Kontoengagemang.":::
   
1. Välj **Nästa** i steget **Översikt** och ange e-postadresser från organisationen där Office-data ska samlas in. Endast data från de angivna e-postadresserna bearbetas för relevant kommunikation. Det bästa är att använda e-postgrupper, till exempel *amerikanska säljteam*, som är enkla att hantera i Office 365. Antalet e-postadresser i grupperna matchas och visas. Totalt antal e-postadresser måste vara minst 2 och får inte överskrida 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-postadresser till kontoengagemang.":::

1. Granska godkännandeutdraget, markera kryssrutan **Jag godkänner** och markera **Nästa**.

1. Välj kunddatauppsättningen och välj **Nästa**.

1. Mappa fältet kontaktadress och välj **Nästa**.

1. Granska konfiguration av berikande, ge berikande ett namn och välj **Spara berikande** för att spara berikandet.

## <a name="office-365-tenant-administrator-consent"></a>Medgivande från Office 365 klientorganisationsadministratör

Medgivande från en Office 365 klientorganisationsadministratör krävs för att aktivera berikande. Ett e-postmeddelande skickas till Office 365 klientorganisationens administratörer när berikande sparas vilket ber dem granska och ge samtycke till Dynamics 365 appar att använda ditt företags Office 365 data för att ge **Insikter till organisationen**. En Office 365 klientorganisations administratör kan också godkänna direkt i Office 365 administrationskonsolen genom att välja **Insikter för organisationen**.

## <a name="running-the-enrichment-for-the-first-time"></a>Köra berikande för första gången

När berikande startas för första gången, efter att Office 365 klientorganisationens administratör har gett sitt godkännande, börjar datahämtningen från Office 365. Den här processen kan ta lite tid. Den första berikande-körningen schemaläggs med en fördröjning på sex timmar. Du kan se hur många dagar informationen omfattar på översiktssidan för kontoengagemang när berikandet har avslutats. Med en stor datavolym kör du berikandet igen efter några dagar. Med den kan data alltid fyllas i under hela tidsfönstret, det vill vara ett år.

Starta processen genom att välja **Kör** på konfigurationssidan för kontoengagemang. Du kan även låta systemet köra anrikningen automatiskt som en del av en [schemalagd uppdatering](system.md#schedule-tab). Som standard körs berikande en gång i veckan.

Beroende på Office-datas storlek kan det ta flera timmar innan en berikandekörning slutförs.

När du gör ett berikande behandlar Microsoft data inom Office 365 efterlevnadsgränsen för att skapa aggregerade insikter som sedan läggs till i din Customer Insights-miljö. Inga data på enskild nivå (till exempel brödtexten i någon e-post eller kalenderinbjudning) blir tillgängliga för användare av Customer Insights. 

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Berikningsresultat

När du har kört berikande-processen går du till **Mina berikanden** för att granska berikanderesultatet. Du hittar det totala antalet utökade kunder och en översikt över berikanderesultaten. Det omfattar antalet bearbetade e-postmeddelanden och möten, antalet dagar för vilka data har sammanställts och med mera.

Du hittar också ett diagram med antalet berikade kunder över tid och en förhandsvisning av berikningsdata.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Förhandsgranskning av resultatet efter det att förbättringsprocessen har körts.":::

Alla data samlas in upp till kontonivån. Systemet beräknar en berikandepoäng, som är mellan 0 och 100, för varje konto. Berikandepoängen är ett sammansatt mått på kontoengagemang i alla e-postmeddelanden och möten i förhållande till dina andra konton. Följande lista innehåller aggregerade data som utökas för kontoengagemang:



| Data                                                                              | Kolumnnamn                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Engagemangspoäng                                                                  |  EngagementScore                         |
| Antal e-postmeddelanden till konto                                                       |  NoOfEmails_ToAccount                    |
| Antal e-postmeddelanden från konto                                                     |  NoOfEmails_FromAccount                  | 
| Antal möten startades av konto                                           |  NoOfMeetings_FromAccount                | 
| Antal möten startades av konto din organisation                                 |  NoOfMeetings_ToAccount                  | 
| Antal personer från organisationen i möten med konton                  |  NoOfContactsInvolved_Meetings           | 
| Antal personer från organisationen i e-postkonversationer med konton       |  NoOfContactsInvolved_Emails             | 
| Antal personer från konto i möten med organisationen                  |  NoOfAccountContactsInvolved_Meetings    | 
| Antal personer från konto i e-postkonversationer med organisationen       |  NoOfAccountContactsInvolved_Emails      | 
| Startdatum för engagemanget (första e-postmeddelandet eller mötet i dina data)                        |  EngagementStartDate                     | 
| Dagar sedan senaste e-post                                                             |  DaysSinceLastEmail                      | 
| Dagar sedan senaste möte                                                           |  DaysSinceLastMeeting                    | 
| Genomsnittlig varaktighet för möten                                                      |  AverageDuration_Of_Meetings             | 
| Genomsnittlig varaktighet för e-postsvar från konto                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Aggregeringens startdatum                                                            |  AggregationStartDate                    | 
| Aggregationsnivå (år, månad eller vecka)                                          |  AggregationLevel                        | 


Granska utökade data genom att välja **Visa mer** i avsnittet för förhandsgranskning. *Office*-entiteten öppnas. Du kan också hitta entiteten i listan i gruppen **Berikande** i **Data**  > **Entiteter**.  Du hittar också *Office_UserEntity* som innehåller Active Directory-ID:erna för de e-postadresser som valdes vid konfiguration av berikande 

## <a name="see-enrichment-data-on-the-customer-card"></a>Visa utökande data på kundkortet

Kontoengagemang kan också visas på enskilda kundkort. Gå till **kunder** och välj en kundprofil. På kundkorten hittar du kontots åtagandepoäng, totalt antal e-postmeddelanden och totalt antal möten under det senaste året. Du hittar även diagram som visar e-post- och möteshistorik.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kundkort med förbättrade data.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Skapa segment och mått baserat på utökade data

Med utökade data kan du skapa segment och mått enligt beskrivningen nedan. Ett segment som till exempel innehåller alla kunder som har ett värde över 60 för *dagar sedan senaste postmeddelandet* och *dagar sedan senaste möte*. Det här avsnittet innehåller inaktuella konton som du kan försöka återaktivera. 

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
