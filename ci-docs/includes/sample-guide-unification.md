---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755540"
---
Kun olet saanut tiedot käyttöön, aloita tietojen yhdistäminen ja luo unified customer profile. Lisätietoja on kohdassa [Tietojen yhtenäistäminen](../data-unification.md).

### <a name="select-source-fields"></a>Valitse lähdekentät

1. Kun tiedot on käsitelty, tee eCommerce- ja Loyalty-tietojen yhdistämismääritys yleisiin tietotyyppeihin. Siirry kohtaan **Tiedot** > **Yhdistä**.

1. Valitse asiakasprofiilin ilmaisevat entiteetit: **eCommerceContacts** ja **loyCustomers**.

   ![ecommerce- ja loyalty-tietolähteiden yhtenäistäminen](../media/unify-ecommerce-loyalty.png)

1. Valitse **ContactId** **eCommerceContacts**-perusavaimeksi ja **LoyaltyID** **loyCustomers**-perusavaimeksi.

1. Valitse **Seuraava**. Ohita tietueiden kaksoiskappaleet ja valitse **Seuraava**.

### <a name="match-conditions"></a>Yhdistämisehdot

1. Valitse **eCommerceContacts : eCommerce** ensisijaiseksi entiteetiksi ja sisällytä kaikki tietueet.

1. Valitse **loyCustomers : LoyaltyScheme** ja liitä mukaan kaikki tietueet.

1. Säännön lisääminen:
   - Valitse **FullName** sekä eCommerceContacts- että  loyCustomers-arvolle.
   - Valitse **Tyyppi (Puhelin, Nimi, Osoite, ...)** kohtaan **Normalisoi**.
   - Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.
   - Syötä nimeksi **FullName, Email**.

1. Lisää sähköpostiosoitteeseen toinen ehto:
   - Valitse **Sähköposti** sekä eCommerceContacts-että loyCustomers-arvoksi.
   - Jätä Normalisoi-kohta tyhjäksi.
   - Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.

   ![Nimen ja sähköpostin vastaavuussäännön yhtenäistäminen](../media/unify-match-rule.png)

1. Valitse **Valmis**.

1. Valitse **Seuraava**.

### <a name="unify-fields"></a>Yhdenmukaista kentät

1. Nimeä **ContactId** **loyCustomers**-entiteetille arvoksi **ContactIdLOYALTY** erottaaksesi sen muista sisällytetyistä tunnuksista.

1. Valitse **Seuraava** tarkistaaksesi ja valitse sitten **Luo asiakasprofiilit**.
