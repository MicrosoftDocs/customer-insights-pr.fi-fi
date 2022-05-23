---
title: Tapahtuman vaihtuvuusennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tapahtuman vaihtuvuusennustemallia.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741315"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Tapahtuman vaihtuvuusennusteen näyteopas

Oppaassa käsitellään kattavasti tapahtuman vaihtuvuusennuste-esimerkki Customer Insightsissa käyttämällä alla olevia tietoja. Mitkään tässä oppaassa käytetyt tiedot eivät ole todellisia asiakastietoja. Ne ovat osa Contoso-tietojoukkoa, joka sijaitsee Customer Insights -tilauksen *Esittely*-ympäristössä.

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukasta kahvia ja laadukkaita kahvinkeittimiä. Se myy näitä tuotteita Contoso Coffee -sivustossa. Yrityksen tavoitteena on saada tietää, ketkä asiakkaat tyypillisesti ostavat heidän tuotteitaan säännöllisesti, eivät ole enää asiakkaita seuraavan 60 päivän kuluttua. Sen tietäminen, ketkä asiakkaat **todennäköisesti vaihtuvat**, voi auttaa yritystä säästämään markkinointitoimia keskittymällä kyseisten asiakkaiden säilyttämiseen.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuttaminen päivämääräksi.":::

1. Anna tietolähteelle uusi nimi määrittämällä oikeanpuoleisen ruudun **Nimi**-kenttään **Query**-arvon sijaan **eCommerceContacts**-arvo

1. Tallenna tietolähde.

### <a name="ingest-online-purchase-data"></a>Verkko-ostostietojen käsitteleminen

1. Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen. Valitse **Text/CSV**-yhdistin uudelleen.

1. Anna **Verkko-ostokset**-tietojen URL-osoite https://aka.ms/ciadclassonline.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **PurchasedOn**: päivämäärä ja aika
   - **TotalPrice**: valuutta
   
1. Anna tietolähteelle uusi nimi määrittämällä oikeanpuoleisen ruudun **Nimi**-kenttään **Query**-arvon sijaan **eCommercePurchases**-arvo.

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

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Tehtävä 3 – tapahtuman vaihtuvuusennusteen määrittäminen

Unified customer profiles -profiilien avulla voidaan nyt suorittaa tapahtumien vaihtuvuusennuste. Yksityiskohtaiset ohjeet ovat [Tapahtumien vaihtuvuusennuste](predict-transactional-churn.md) -artikkelissa. 

1. Valitse **Analytiikka** > **Tutustu** ja valitse sitten **Asiakasvaihtuvuusmalli**.

1. Valitse ensin **Tapahtuma**-vaihtoehto ja sitten **Aloita**.

1. Valitse **Sähköisen OOB-kaupankäyntitapahtuman vaihtuvuusennuste** ja tuloste-entiteetti **OOBeCommerceChurnPrediction**.

1. Määritä vaihtuvuusmallille kaksi ehtoa:

   * **Ennusteikkuna**: **vähintään 60** päivää. Tämä asetus määrittää, miten pitkälle tulevaisuuteen asiakasvaihtuvuus halutaan ennustaa.

   * **Vaihtuvuusmääritelmä**: **vähintään 60** päivää. Kesto ilman ostoksia, jonka jälkeen asiakas katsotaan vaihtuneeksi.

     :::image type="content" source="media/model-levers.PNG" alt-text="Mallin ennusteikkunan ja vaihtuvuusmääritelmän valitseminen":::

1. Valitse **Ostohistoria (pakollinen)** ja valitse ostohistorialle **Lisää tiedot** -arvo.

1. Lisää **eCommercePurchases : eCommerce** -entiteetti ja yhdistä eCommercen kentät vastaaviin mallin edellyttämiin kenttiin.

1. Liitä **eCommercePurchases : eCommerce** -entiteetti **eCommerceContacts : eCommerce** -entiteettiin.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce-entiteetit.":::

1. Määritä mallin aikataulu valitsemalla **Seuraava**.

   Mallia on koulutettava säännöllisesti, jotta se oppii uusia malleja, kun uusia tietoja käsitellään. Valitse tässä esimerkissä **Kuukausittain**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.

## <a name="task-4---review-model-results-and-explanations"></a>Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Nyt voit tarkastella vaihtuvuusmallin selityksiä. Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tehtävä 5 – Suuren vaihtuvuusriskin asiakkaiden segmentin luominen

Tuotantomallin suorittaminen luo uuden entiteetin, jonka saa näkyviin valitsemalla **Tiedot** > **Entiteetit**.   

Voit luoda uuden segmentin mallin luoman entiteetin perusteella.

1.  Valitse **Segmentit**. Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmentin luominen mallin tulosteen avulla":::

1. Valitse **OOBeCommerceChurnPrediction**-päätepiste ja määritä segmentti: 
   - Kenttä: ChurnScore
   - Operaattori: suurempi kuin
   - Arvo: 0,6

Nyt sinulla on dynaamisesti päivitetty segmentti, joka määrittää suuren vaihtuvuusriskin asiakkaat.

Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
