---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755566"
---
När data har förts in startar du dataprocessen för att skapa Unified customer profile. Mer information finns i [Dataförening](../data-unification.md).

### <a name="select-source-fields"></a>Välj källfält

1. Efter inmatande av data mappar du kontakter från e-handels- och lojalitetsdata till vanliga datatyper. Gå till **Data** > **Förena**.

1. Välj de entiteter som representerar kundprofilen – **eCommerceContacts** och **loyCustomers**.

   ![förena e-handels- och lojalitetsdatakällor.](../media/unify-ecommerce-loyalty.png)

1. Välj **ContactId** som primärnyckel för **eCommerceContacts** och **LoyaltyID** som primärnyckel för **loyCustomers**.

1. Välj **Nästa**. Hoppa över dubblettposter och välj **Nästa**.

### <a name="match-conditions"></a>Matchningsvillkor

1. Välj **eCommerceContacts : eCommerce** som den primära entiteten och ta med alla poster.

1. Välj **loyCustomers : LoyaltyScheme** och ta med alla poster.

1. Lägga till en regel:
   - Välj **FullName** för både eCommerceContacts och loyCustomers.
   - Välj **Typ (Telefon, Namn, Adress, ...)** för **Normalisering**.
   - Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.
   - Ange **FullName, Email** för namn.

1. Lägg till ett andra villkor för e-postadressen:
   - Välj **Email** för både eCommerceContacts och loyCustomers.
   - Lämna Normalisera tomt.
   - Ange **Precisionsnivå**: **Basic** och **Värde**: **Hög**.

   ![Förena matchningsregel för namn och e-post.](../media/unify-match-rule.png)

1. Välj **Utfört**.

1. Välj **Nästa**.

### <a name="unify-fields"></a>Förenade fält

1. Byt namn på **ContactId** för entiteten **loyCustomers** till **ContactIdLOYALTY** för att skilja det från det andra ID:t som inte finns.

1. Välj **Nästa** att granska och välj sedan **Skapa kundprofiler**.
