---
title: Utöka kundprofiler med data från Microsoft Office 365 (förhandsversion)
description: Använd tillverkarspecifika data från Microsoft Office för att utöka dina kundprofiler med kontaktdata.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055696"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Utöka kundprofiler med data från Microsoft Office 365 (förhandsversion)

Använd data från Microsoft Office 365 för att utöka dina kundkontoprofiler med insikter om åtaganden via Office 365 appar. Kontaktdata består av e-post- och mötesaktiviteter som samlas in på kontonivån. Till exempel antalet e-postmeddelanden från ett affärskonto eller antalet möten med kontot. Inga data om enskilda användare görs tillgängliga.

## <a name="supported-countries-or-regions"></a>Länder eller regioner som stöds

Vi stöder för närvarande följande regioner: Storbritannien, Europa, Nordamerika.

## <a name="prerequisites"></a>Förutsättningar

- En aktiv Office 365 molnlicens.
- [Enhetliga kundprofiler](customer-profiles.md) baserad på [företagskonton](work-with-business-accounts.md).
- En [Microsoft Dataverse organisation bifogad](create-environment.md#step-3-connect-to-microsoft-dataverse) i din Customer Insights-miljöer.
- [Administratör](permissions.md#admin) behörighet.
- Godkännande från din Office 365 klientorganisationsadministratör för att använda Office 365 data för att ge **Insikter för organisation** inom Dynamics 365-appar.

## <a name="configure-the-enrichment"></a>Konfiguration av berikning

1. Gå till **Data** > **Berikning** och välj fliken **Upptäcka**.

1. Välj **Utöka mina data** på panelen **Kontoengagemang**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Panelen Kontoengagemang.":::

1. Gå igenom översikten och välj sedan **Nästa**.

1. Ange e-postadresser från organisationen där Office-data ska samlas in. Endast data från de angivna e-postadresserna bearbetas för relevant kommunikation. Det bästa är att använda e-postgrupper, till exempel *amerikanska säljteam*, som du kan hantera i Office 365. Antalet e-postadresser i grupperna matchas och visas. Totalt antal e-postadresser måste vara minst 2 och får inte överskrida 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-postadresser till kontoengagemang.":::

1. Granska och ge ditt samtycke till [Office 365 klientorganisationsadministratör](#office-365-tenant-administrator-consent) genom att välja **Jag godkänner**.

1. Välj **Nästa**.

1. Välj **Kontaktdatauppsättning** och välj den profil du vill berika. Välj **Nästa**.

1. Mappa fältet kontaktadress och välj **Nästa**.

1. Ange ett **Namn** för berikningen och **utgående enhet**.

1. Välj **Spara berikning** när du har granskat dina val.

1. Välj **Stäng** om du vill gå tillbaka till sidan **Berikande**.

### <a name="office-365-tenant-administrator-consent"></a>Medgivande från Office 365 klientorganisationsadministratör

Medgivande från en Office 365 klientorganisationsadministratör krävs för att aktivera berikande. Ett e-postmeddelande skickas till Office 365 klientorganisationens administratörer när berikande sparas vilket ber dem granska och ge samtycke till Dynamics 365 appar att använda ditt företags Office 365 data för att ge **Insikter till organisationen**. En Office 365 klientorganisations administratör kan också godkänna direkt i Office 365 administrationskonsolen genom att välja **Insikter för organisationen**.

## <a name="running-the-enrichment-for-the-first-time"></a>Köra berikande för första gången

När berikande startas för första gången, efter att Office 365 klientorganisationens administratör har gett sitt godkännande, börjar datahämtningen från Office 365. Den här processen kan ta lite tid. Den första berikande-körningen schemaläggs med en fördröjning på sex timmar. Du kan se hur många dagar informationen omfattar på översiktssidan för kontoengagemang när berikandet har avslutats. Med en stor datavolym kör du berikandet igen efter några dagar. Med den kan data alltid fyllas i under hela tidsfönstret, det vill vara ett år.

Beroende på Office-datas storlek kan det ta flera timmar innan en berikandekörning slutförs.

När du gör ett berikande behandlar Microsoft data inom Office 365 efterlevnadsgränsen för att skapa aggregerade insikter som sedan läggs till i din Customer Insights-miljö. Inga data på enskild nivå (till exempel brödtexten i någon e-post eller kalenderinbjudning) blir tillgängliga för användare av Customer Insights.

Välj **Kör** för att starta berikandeprocessen.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Visa resultat för berikande

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Det här är entiteten *Kontor*. *Office_UserEntity* innehåller Active Directory-ID:erna för de e-postadresser som valdes vid konfiguration av berikande

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Visa utökande data på kundkortet

Kontoengagemang kan också visas på enskilda kundkort. Gå till **kunder** och välj en kundprofil. På kundkorten hittar du kontots åtagandepoäng, totalt antal e-postmeddelanden och totalt antal möten under det senaste året. Du hittar även diagram som visar e-post- och möteshistorik.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kundkort med förbättrade data.":::

## <a name="next-steps"></a>Nästa steg

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Ett segment som till exempel innehåller alla kunder som har ett värde över 60 för *dagar sedan senaste postmeddelandet* och *dagar sedan senaste möte*. Det här avsnittet innehåller inaktuella konton som du kan försöka återaktivera.

[!INCLUDE [footer-include](includes/footer-banner.md)]
