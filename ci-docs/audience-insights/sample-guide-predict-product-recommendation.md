---
title: Tuotesuositusten ennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tuotesuosituksen ennustemallia.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b219935dfbd9f7acc1104d83e2ca281801a1a4251ae4c19fc03d4b1ce46f4613
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035181"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Tuotesuositusten ennusteen (esiversio) näyteopas

Aiheessa käsitellään kattavasti tuotesuosituksen ennusteen esimerkkiä käyttämällä alla olevia näytetietoja.

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukkaat kahvi- ja kahvikoneet, joita he myyvät Contoso Coffee -verkkosivustonsa kautta. Tavoitteena on ymmärtää, mitä tuotteita tulisi suositella toistuville asiakkaille. Jos tiedetään, mitä asiakkaat **todennäköisesti ostavat**, markkinointiponnisteluissa voidaan keskittyä näihin tiettyihin nimikkeisiin.

## <a name="prerequisites"></a>Edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.
- Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tehtävä 1 – Tietojen käsitteleminen

Tutustu etenkin artikkeleihin, joissa on [tietoja tietojen käsittelystä](data-sources.md) ja [tietolähteiden tuomisestä Power Query -yhdistimiä](connect-power-query.md). Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä

1. Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscontacts.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **CreatedOn**: päivämäärä, aika ja aikavyöhyke

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

5. Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommerceContacts**

6. **Tallenna** tietolähde.

### <a name="ingest-online-purchase-data"></a>Verkko-ostostietojen käsitteleminen

1. Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen. Valitse **Text/CSV**-yhdistin uudelleen.

1. Anna **Verkko-ostokset**-tietojen URL-osoite https://aka.ms/ciadclassonline.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **PurchasedOn**: päivämäärä ja aika
   - **TotalPrice**: valuutta

1. Vaihda sivuruudun **Nimi**-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommercePurchases**.

1. **Tallenna** tietolähde.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Asiakastietojen käyttäminen kanta-asiakasrakenteesta

1. Luo **LoyaltyScheme**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscustomerloyalty.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **RewardsPoints**: kokonaisluku
   - **CreatedOn**: päivämäärä, aika

1. Vaihda oikeanpuoleisen ruudun **Nimi**-kentässä tietolähteen nimi **Query** nimeksi **loyCustomers**.

1. **Tallenna** tietolähde.

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

Tietojen purkamisen jälkeen aloitetaan nyt tietojen yhdistäminen ja luodaan yhtenäinen asiakasprofiili. Lisätietoja on kohdassa [Tietojen yhtenäistäminen](data-unification.md).

### <a name="map"></a>Liitä

1. Kun tiedot on käsitelty, tee eCommerce- ja Loyalty-tietojen yhdistämismääritys yleisiin tietotyyppeihin. Valitse **Tiedot** > **Yhtenäistä** > **Määritä vastaavuus**.

2. Valitse asiakasprofiilin ilmaisevat entiteetit: **eCommerceContacts** ja **loyCustomers**.

   ![ecommerce- ja loyalty-tietolähteiden yhtenäistäminen](media/unify-ecommerce-loyalty.png)

3. Valitse **ContactId** **eCommerceContacts**-perusavaimeksi ja **LoyaltyID** **loyCustomers**-perusavaimeksi.

   ![Yhtenäistäminen LoyaltyId-perusavaimena](media/unify-loyaltyid.png)

### <a name="match"></a>Täsmäytä

1. Valitse **Täsmäytä**-välilehdessä **Määritä järjestys**.

2. Valitse avattavasta **Ensisijainen**-luettelosta ensisijaiseksi lähteeksi **eCommerceContacts: eCommerce** ja sisällytä kaikki tietueet.

3. Valitse avattavasta **Entiteetti 2** -luettelosta **loyCustomers: LoyaltyScheme** ja sisällytä kaikki tietueet.

   ![eCommerce- ja Loyalty-täsmäytyksen yhtenäistäminen](media/unify-match-order.png)

4. Valitse **Luo uusi sääntö**

5. Lisää ensimmäinen ehto FullName-kentässä.

   - Valitse eCommerceContacts-kohdassa avattavasta valikosta **FullName**.
   - Valitse loyCustomers-kohdassa avattavasta valikosta **FullName**.
   - Valitse avattava **Normalisoi**-luettelo ja valitse sitten **Tyyppi (puhelin, nimi, osoite...)**.
   - Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.

6. Anna uuden säännön **FullName, Email**.

   - Lisää sähköpostiosoitteen toinen ehto valitsemalla **Lisää ehto**
   - Valitse entity eCommerceContacts-kohdassa avattavasta valikosta **Sähköposti**.
   - Valitse entity loyCustomers-kohdassa avattavasta valikosta **Sähköposti**.
   - Jätä Normalisoi-kohta tyhjäksi.
   - Määritä **Tarkkuustaso**: **Perustaso** ja **Arvo**: **Suuri**.

   ![Nimen ja sähköpostin vastaavuussäännön yhtenäistäminen](media/unify-match-rule.png)

7. Valitse **Tallenna** ja **Suorita**.

### <a name="merge"></a>Yhdistä

1. Siirry **Yhdistä**-välilehteen.

1. Vaihda **loyCustomers**-entiteetin **ContactId**-kohdassa näyttönimeksi **ContactIdLOYALTY** erottamaan se muista käsitellyistä tunnuksista.

   ![kanta-asiakastunnuksen contactid-nimen vaihtaminen](media/unify-merge-contactid.png)

1. Aloita yhdistämisprosessi valitsemalla **Tallenna** ja **Suorita**.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tehtävä 3 – tuotesuositusennusteen määrittäminen

Kun asiakasprofiilit on yhtenäistetty, tilauksen vaihtuvuusennusteet voidaan nyt suorittaa.

1. Siirry kohtaan **Analytiikka** > **Ennuste** ja valitse sitten **Tuotesuositus**.

1. Valitse **Aloita**.

1. Anna mallille nimi **OOB - tuotesuositusmallin ennuste** ja tulosentiteetille nimi **OOBProductRecommendationModelPrediction**.

1. Määritä mallille kolme ehtoa seuraavasti:

   - **Tuotteiden määrä**: Määritä arvoksi **5**. Tämä asetus määrittää, miten montaa tuotetta haluat suositella asiakkaillesi.

   - **Toista odotetut ostot**: Valitse **Kyllä**, jos haluat sisällyttää tuotteet asiakkaiden aiemmin ostamaan suositukseen.

   - **Katso taaksepäin -ikkuna:** Valitse vähintään **365 päivää**. Tämä asetus määrittää, miten pitkälle menneisyyteen asiakkaan aktiviteetteja tarkastellaan, kun sitä käytetään suositusten syötteenä.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tuotesuositusmallin mallin määritykset.":::

1. Valitse **Pakolliset tiedot** ja valitse ostohistorian **Lisää tiedot** -kohta.

1. Lisää **eCommercePurchases : eCommerce** -entiteetti ja yhdistä eCommercen kentät vastaaviin mallin edellyttämiin kenttiin.

1. Liitä **eCommercePurchases : eCommerce** -entiteetti **eCommerceContacts : eCommerce** -entiteettiin.

   ![eCommerce-entiteetit.](media/model-purchase-join.png)

1. Määritä mallin aikataulu valitsemalla **Seuraava**.

   Mallia on koulutettava säännöllisesti, jotta se oppii uusia malleja, kun uusia tietoja käsitellään. Valitse tässä esimerkissä **Kuukausittain**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.


## <a name="task-4---review-model-results-and-explanations"></a>Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Voit nyt tarkastella tuotesuositusmallin selityksiä. Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tehtävä 5 – eniten ostettujen tuotteiden segmentin luominen

Tuotantomallin suorittaminen luo uuden entiteetin, jonka saa näkyviin valitsemalla **Tiedot** > **Entiteetit**.

Voit luoda uuden segmentin mallin luoman entiteetin perusteella.

1. Valitse **Segmentit**. Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**.

   ![Segmentin luominen mallin tulosteen avulla](media/segment-intelligence.png)

1. Valitse **OOBProductRecommendationModelPrediction**-päätepiste ja määritä segmentti:

   - Kenttä: ProductID
   - Operaattori: Arvo
   - Arvo: Valitse kolme suosituinta tuotetunnusta

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Luo segmentti mallin tuloksista.":::

Nyt sinulla on dynaamisesti päivitetty segmentti, joka määrittää asiakkaat, jotka ovat valmiita ostamaan kolme suositeltua tuotetta 

Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
