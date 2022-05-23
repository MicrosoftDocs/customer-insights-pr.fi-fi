---
title: Tilauksen vaihtuvuusennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tilauksen vaihtuvuusennustemallia.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741407"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Tilauksen vaihtuvuusennusteen näyteopas

Aiheessa käsitellään kattavasti tilauksen vaihtuvuusennuste-esimerkki käyttämällä alla olevia näytetietoja. 

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukasta kahvia ja laadukkaita kahvinkeittimiä. Se myy näitä tuotteita Contoso Coffee -sivustossa. Yritys aloitti äskettäin tilaustoiminnan asiakkaille, jotka hakevat kahvia säännöllisesti. Yrityksen tavoitteena on selvittää, ketkä tilauksen tehneet asiakkaat saattavat peruuttaa tilauksensa seuraavien kuukausien aikana. Sen tietäminen, ketkä asiakkaat **todennäköisesti vaihtuvat**, voi auttaa yritystä säästämään markkinointitoimia keskittymällä kyseisten asiakkaiden säilyttämiseen.

## <a name="prerequisites"></a>Edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.
- Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tehtävä 1 – Tietojen käsitteleminen

Tutustu artikkeleihin [tietojen käsittelystä](data-sources.md) ja [tietolähteiden tuomisesta Power Query -yhdistinten avulla](connect-power-query.md). Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä

1. Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscontacts.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **DateOfBirth**: päivämäärä
   - **CreatedOn**: päivämäärä, aika ja aikavyöhyke

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

1. Anna tietolähteelle uusi nimi määrittämällä oikeanpuoleisen ruudun **Nimi**-kenttään **Query**-arvon sijaan **eCommerceContacts**-arvo

1. Tallenna tietolähde.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Asiakastietojen käyttäminen kanta-asiakasrakenteesta

1. Luo **LoyaltyScheme**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscustomerloyalty.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **DateOfBirth**: päivämäärä
   - **RewardsPoints**: kokonaisluku
   - **CreatedOn**: päivämäärä, aika

1. Vaihda oikeanpuoleisen ruudun **Nimi**-kentässä tietolähteen nimi **Query** nimeksi **loyCustomers**.

1. Tallenna tietolähde.

### <a name="ingest-subscription-information"></a>Tilaustietojen käsitteleminen

1. Luo **SubscriptionHistory**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadchurnsubscriptionhistory.

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

1. Vaihda oikean ruudun **Nimi**-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **SubscriptionHistory**.

1. Tallenna tietolähde.

### <a name="ingest-customer-data-from-website-reviews"></a>Sivustoarvioista saatujen asiakastietojen käsitteleminen

1. Luo **Website**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasswebsite.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **ReviewRating**: kokonaisluku
   - **ReviewDate**: päivämäärä

1. Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **webReviews**.

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tehtävä 3 – tilauksen vaihtuvuusennusteen määrittäminen

Kun asiakasprofiilit on yhtenäistetty, tilauksen vaihtuvuusennusteet voidaan nyt suorittaa. Yksityiskohtaiset ohjeet ovat [Tilauspoistuman ennuste](predict-subscription-churn.md) -artikkelissa. 

1. Valitse **Analytiikka** > **Tutustu** ja valitse sitten **Asiakasvaihtuvuusmalli**.

1. Valitse ensin **Tilaus**-vaihtoehto ja sitten **Aloita**.

1. Valitse **OOB-tilauksen vaihtuvuusennuste** ja tuloste-entiteetti **OOBSubscriptionChurnPrediction**.

1. Määritä vaihtuvuusmallille kaksi ehtoa:

   * **Päiviä tilauksen päättymisestä**: **vähintään 60** päivää. Jos asiakas ei ole uusinut tilaustaan tänä aikana tilauksen päättymisen jälkeen, sitä pidetään vaihtuneena. 

   * **Vaihtuvuusmääritelmä**: **vähintään 93** päivää. Kesto, jonka malli ennustaa asiakkaiden vaihtuvuudelle. Mitä pidemmälle tulevaisuuteen tarkastelu ulottuu, sitä epätarkemmat tulokset ovat.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Mallin ennusteikkunan ja vaihtuvuusmääritelmän valitseminen":::

1. Valitse **Lisää pakolliset tiedot** ja valitse tilaushistorian osalta **Lisää tiedot**.

1. Lisää **Subscription : SubscriptionHistory** -entiteetti ja yhdistä eCommercen kentät vastaaviin mallin edellyttämiin kenttiin.

1. Liitä **Subscription : SubscriptionHistory** -entiteetti **eCommerceContacts : eCommerce** -entiteettiin ja anna suhteen nimeksi **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="eCommerce-entiteettien liittäminen":::

1. Lisää **webReviews : Website** -entiteetti asiakasaktiviteeteissa ja yhdistä webReviews-kentät vastaaviin mallin edellyttämiin kenttiin. 
   - Perusavain: ReviewId
   - Aikaleima: ReviewDate
   - Tapahtuma: ReviewRating

1. Määritä sivustoarvioaktiviteetti. Valitse **Arvio**-aktiviteetti ja liitä **webReviews : Website** -entiteetti ja **eCommerceContacts : eCommerce**.

1. Määritä mallin aikataulu valitsemalla **Seuraava**.

   Mallia on koulutettava säännöllisesti, jotta se oppii uusia malleja, kun uusia tietoja käsitellään. Valitse tässä esimerkissä **Kuukausittain**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.

## <a name="task-4---review-model-results-and-explanations"></a>Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Voit nyt tarkastella tilauksen vaihtuvuusmallin selityksiä. Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tehtävä 5 – Suuren vaihtuvuusriskin asiakkaiden segmentin luominen

Tuotantomallin suorittaminen luo uuden entiteetin, jonka saa näkyviin valitsemalla **Tiedot** > **Entiteetit**.   

Voit luoda uuden segmentin mallin luoman entiteetin perusteella.

1.  Valitse **Segmentit**. Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmentin luominen mallin tulosteen avulla":::

1. Valitse **OOBSubscriptionChurnPrediction**-päätepiste ja määritä segmentti: 
   - Kenttä: ChurnScore
   - Operaattori: suurempi kuin
   - Arvo: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Tilauksen vaihtuvuussegmentin määrittäminen":::

Käytössä on nyt dynaamisesti päivitettävä segmentti, joka määrittää tämän tilausliiketoiminnan suuren vaihtuvuusriskin asiakkaat.

Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]