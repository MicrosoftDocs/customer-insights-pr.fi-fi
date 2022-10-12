---
title: Tilauksen vaihtuvuusennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tilauksen vaihtuvuusennustemallia.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610002"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Tilauksen vaihtuvuusennusteen näyteopas

Tässä oppaassa käsitellään kattavasti tilauksen vaihtuvuusennuste-esimerkkiä, jossa käytetään näytetietoja. Tätä ennustetta kannattaa kokeilla [uudessa ympäristössä](manage-environments.md).

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukkaita kahveja ja kahvikoneita. He myyvät tuotteita Contoso Coffeen verkkosivuston kautta. Yritys aloitti äskettäin tilaustoiminnan asiakkaille, jotka hakevat kahvia säännöllisesti. Yrityksen tavoitteena on selvittää, ketkä tilauksen tehneet asiakkaat saattavat peruuttaa tilauksensa seuraavien kuukausien aikana. Sen tietäminen, ketkä asiakkaat **todennäköisesti vaihtuvat**, voi auttaa yritystä säästämään markkinointitoimia keskittymällä kyseisten asiakkaiden säilyttämiseen.

## <a name="prerequisites"></a>edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.

## <a name="task-1---ingest-data"></a>Tehtävä 1 – Tietojen käsitteleminen

Tutustu [tietojen käsittelyä](data-sources.md) ja [tietolähteiden yhdistämistä Power Query -tietolähteeseen](connect-power-query.md) käsitteleviin artikkeleihin. Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä

1. Luo **eCommerce**-niminen Power Query -tietolähde ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscontacts.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **CreatedOn**: päivämäärä, aika ja aikavyöhyke

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

1. Vaihda oikean ruudun **Nimi**-kenttään tietolähteen nimeksi **eCommerceContacts**

1. Tallenna tietolähde.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Asiakastietojen käyttäminen kanta-asiakasrakenteesta

1. Luo **LoyaltyScheme**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Anna kanta-asiakkaiden URL-osoitteeksi https://aka.ms/ciadclasscustomerloyalty.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **RewardsPoints**: kokonaisluku
   - **CreatedOn**: päivämäärä, aika

1. Vaihda oikean ruudun **Nimi**-kentän tietolähteen nimeksi **loyCustomers**.

1. Tallenna tietolähde.

### <a name="ingest-subscription-information"></a>Tilaustietojen käsitteleminen

1. Luo **SubscriptionHistory**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Anna tilauksille URL-osoite https://aka.ms/ciadchurnsubscriptionhistory.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **SubscriptioID**: kokonaisluku
   - **SubscriptionAmount**: valuutta
   - **SubscriptionEndDate**: päivämäärä, aika
   - **SubscriptionStartDate**: päivämäärä, aika
   - **TransactionDate**: päivämäärä, aika
   - **IsRecurring**: tosi, epätosi
   - **Is_auto_renew**: tosi, epätosi
   - **RecurringFrequencyInMonths**: kokonaisluku

1. Vaihda oikeassa ruudussa **Nimi**-kenttään tietolähteen nimeksi **SubscriptionHistory**.

1. Tallenna tietolähde.

### <a name="ingest-customer-data-from-website-reviews"></a>Sivustoarvioista saatujen asiakastietojen käsitteleminen

1. Luo **Website**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Anna sivuston arvioille URL-osoite https://aka.ms/ciadclasswebsite.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **ReviewRating**: kokonaisluku
   - **ReviewDate**: päivämäärä

1. Vaihda oikean ruudun **Nimi**-kentässä tietolähteen nimeksi **webReviews**.

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

Tutustu [tietojen yhdistämistä](data-unification.md) käsittelevään artikkeliin. Seuraavissa tiedoissa oletetaan, että tietojen yhdistäminen on yleisesti ottaen tuttua.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tehtävä 3 – tapahtumahistorian aktiviteetin luominen

Tutustu [asiakkaan aktiviteetteja](activities.md) käsittelevään artikkeliin. Seuraavissa tiedoissa oletetaan, että aktiviteettien luominen on yleisesti ottaen tuttua.

1. Luo **SubscriptionHistory**-niminen aktiviteetti, jossa on *Tilaus*-entiteetti ja pääavain **CustomerId**.

1. Luo kohteiden *SubscriptionHistory:Subscription* ja *eCommerceContacts:eCommerce* välille suhde siten, että **CustomerID** on kaksi entiteettiä yhdistävä viiteavain.

1. Valitse **SubscriptionType** **Aikaleima**-kohdan **EventActivity**- ja **SubscriptionEndDate**-kohdissa.

1. Valitse **Aktiviteetin tyyppi** -kohdassa **Tilaus** ja yhdistä aktiviteetin tiedot semanttisesti.

1. Suorita aktiviteetti.

1. Lisää toinen aktiviteetti ja yhdistä sen kenttien nimet vastaaviin kenttiin:
   - Asiakasaktiviteettientiteetti: Arviot:Verkkosivusto
   - Perusavain: Website.Reviews.ReviewId
   - Aikaleima: Website.Reviews.ReviewDate
   - Tapahtuma (aktiviteetin nimi): Website.Reviews.ActivityTypeDisplay
   - Tiedot (summa tai arvo): Website.Reviews.ReviewRating

1. Suorita aktiviteetti.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tehtävä 4 – tilauksen vaihtuvuusennusteen määrittäminen

Kun asiakasprofiilit on yhtenäistetty ja aktiviteetti luotu, suorita tilauksen vaihtuvuusennuste. Lisätietoja on kohdassa [Tilauksen vaihtuvuusennuste](predict-subscription-churn.md).

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Asiakasvaihtuvuusmalli**-ruudussa **Käytä mallia**.

1. Valitse vaihtuvuuden tyypiksi **Tilaus** ja valitse sitten **Aloita**.

1. Valitse **OOB-tilauksen vaihtuvuusennuste** ja tuloste-entiteetti **OOBSubscriptionChurnPrediction**.

1. Malliasetusten määrittäminen:
   - **Päiviä tilauksen päättymisestä**: **60** päivää ilmaisee, että asiakas katsotaan vaihtuneeksi, jos tilausta ei uusita tänä aikana tilauksen päättymisen jälkeen.
   - **Päivät, joista tulevaisuuteen ennustetaan vaihtuvuus**: **93** päivää ilmaisee keston, jonka aikana malli ennustaa tietyn asiakkaan mahdollisen vaihtuvuuden. Mitä pidemmälle tulevaisuuteen tarkastelu ulottuu, sitä epätarkemmat tulokset ovat.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Mallin asetusten ja vaihtuvuusmääritelmän valitseminen":::

1. Valitse **Seuraava**.

1. Anna tilaushistoria valitsemalla **Pakolliset tiedot** -vaiheessa **Lisää tietoja**.

1. Valitse ensin **Tilaus** ja SubscriptionHistory-entiteetti ja sitten **Seuraava**. Pakolliset tiedot täytetään automaattisesti aktiviteetista. Valitse **Tallenna**.

1. Valitse Asiakasaktiviteetit-kohdassa **Lisää tiedot**.

1. Tässä esimerkissä lisätään verkkoarviointiaktiviteetti.

1. Valitse **Seuraava**.

1. Määritä **Tietojen päivitykset** -vaiheessa mallin aikatauluksi **Kuukausittain**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.

## <a name="task-5---review-model-results-and-explanations"></a>Tehtävä 5 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Tarkastele tilauksen vaihtuvuusmallin selityksiä. Lisätietoja on kohdassa [Ennusteen tulosten näyttäminen](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tehtävä 6 – Suuren vaihtuvuusriskin asiakkaiden segmentin luominen

Mallin käyttö luo uuden entiteetin, joka näkyy **Tieto** > **Entiteetit** -kohdassa. Voit luoda uuden segmentin mallin luoman entiteetin perusteella.

1. Valitse tulossivulla **Luo segmentti**.

1. Luo sääntö **OOBSubscriptionChurnPrediction**-entiteetin avulla ja määritä segmentti:
   - **Kenttä**: ChurnScore
   - **Operaattori**: suurempi kuin
   - **Arvo**: 0,6

1. Valitse **Tallenna** ja **suorita** segmentti.

Käytössä on nyt dynaamisesti päivitettävä segmentti, joka määrittää tämän tilausliiketoiminnan suuren vaihtuvuusriskin asiakkaat. Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

> [!TIP]
> Ennustemallin segmentti voidaan luoda myös **Segmentit**-sivulla valitsemalla ensin **Uusi** ja sitten **Luominen kohteesta** > **Älykäs toiminto**. Lisätietoja on kohdassa [Uuden segmenttien luominen pikasegmenttien avulla](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
