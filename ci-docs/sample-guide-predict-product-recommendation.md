---
title: Tuotesuositusten ennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tuotesuosituksen ennustemallia.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762682"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Tuotesuositusten ennusteen näyteopas

Aiheessa käsitellään kattavasti tuotesuosituksen ennusteen esimerkkiä käyttämällä alla olevia näytetietoja.

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukasta kahvia ja laadukkaita kahvinkeittimiä. Se myy näitä tuotteita Contoso Coffee -sivustossa. Tavoitteena on ymmärtää, mitä tuotteita tulisi suositella toistuville asiakkaille. Jos tiedetään, mitä asiakkaat **todennäköisesti ostavat**, markkinointiponnisteluissa voidaan keskittyä näihin tiettyihin nimikkeisiin.

## <a name="prerequisites"></a>Edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.
- Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tehtävä 1 – Tietojen käsitteleminen

Tutustu artikkeleihin [tietojen käsittelystä](data-sources.md) ja [tietolähteiden tuomisesta Power Query -yhdistinten avulla](connect-power-query.md). Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä

1. Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna eCommerce-yhteyshenkilöiden URL-osoite: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **CreatedOn**: päivämäärä, aika ja aikavyöhyke

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

1. Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommerceContacts**

1. **Tallenna** tietolähde.

### <a name="ingest-online-purchase-data"></a>Verkko-ostostietojen käsitteleminen

1. Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen. Valitse **Text/CSV**-yhdistin uudelleen.

1. Syötä **Verkko-ostojen** tietojen URL-osoite [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **PurchasedOn**: päivämäärä ja aika
   - **TotalPrice**: valuutta

1. Vaihda sivuruudun **Nimi**-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommercePurchases**.

1. **Tallenna** tietolähde.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Asiakastietojen käyttäminen kanta-asiakasrakenteesta

1. Luo **LoyaltyScheme**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna eCommerce-yhteyshenkilöiden URL-osoite [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **RewardsPoints**: kokonaisluku
   - **CreatedOn**: päivämäärä, aika

1. Vaihda oikeanpuoleisen ruudun **Nimi**-kentässä tietolähteen nimi **Query** nimeksi **loyCustomers**.

1. **Tallenna** tietolähde.

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tehtävä 3 – tuotesuositusennusteen määrittäminen

Unified customer profiles -profiilien avulla voidaan nyt suorittaa tuotesuositusennuste.

1. Siirry kohtaan **Analytiikka** > **Ennuste** ja valitse sitten **Tuotesuositus**.

1. Valitse **Aloita**.

1. Anna mallille nimi **OOB - tuotesuositusmallin ennuste** ja tulosentiteetille nimi **OOBProductRecommendationModelPrediction**.

1. Määritä mallille kolme ehtoa seuraavasti:

   - **Tuotteiden määrä**: Määritä arvoksi **5**. Tämä asetus määrittää, miten montaa tuotetta haluat suositella asiakkaillesi.

   - **Toista odotetut ostot**: Valitse **Kyllä**, jos haluat sisällyttää tuotteet asiakkaiden aiemmin ostamaan suositukseen.

   - **Katso taaksepäin -ikkuna:** Valitse vähintään **365 päivää**. Tämä asetus määrittää, miten pitkälle menneisyyteen asiakkaan aktiviteetteja tarkastellaan, kun sitä käytetään suositusten syötteenä.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tuotesuositusmallin mallin määritykset.":::

1. Valitse **Lisää pakolliset tiedot** -vaiheessa **Lisää tiedot**.

1. Valitse **Lisää tiedot** - ruudussa **SalesOrderLine** ostohistoriaentiteetiksi. Tässä vaiheessa sitä ei todennäköisesti ole vielä määritetty. Avaa ruudussa linkki, jolla voit luoda aktiviteetin seuraavien vaiheiden mukaisesti:
   1. Syötä **Aktiviteetin nimi** ja valitse *eCommercePurchases:eCommerce* **Aktiviteetin entiteetiksi**. **Perusavain** on *PurchaseId*.
   1. Määritä ja anna nimi suhteelle *eCommerceContacts:eCommerce entity* ja valitse **ContactId** viiteavaimeksi.
   1. Määritä Aktiviteetin yhdistämiselle **Tapahtuman aktiviteetiksi** *TotalPrice* ja aikaleimaksi *PurchasedOn*. Voit määrittää lisää kenttiä [Asiakas-aktiviteettien](activities.md) mukaisesti.
   1. Valitse **Aktiviteettityypiksi** *SalesOrderLine*. Yhdistä seuraavat aktiviteettikentät:
      - Tilausrivin tunnus: PurchaseId
      - Tilauksen tunnus: PurchaseId
      - Tilaustiedot: PurchasedOn
      - Tuotetunnus: ProductId
      - Summa: TotalPrice
   1. Tarkista aktiviteetti ja viimeistele se, ennen kuin palaat mallimääritykseen.

1. Valitse uudelleen **Valitse aktiviteetit** -vaiheessa uusi luotu aktiviteetti **Aktiviteetit**-osassa. Valitse **Seuraava**, jossa määritteen yhdistämismääritys on jo täytetty. Valitse **Tallenna**.

1. Tässä esimerkkioppaassa ohitetaan **Tuotetietojen lisääminen** ja **Tuotesuodattimet** -tietojoukko, koska tuotetietoja ei ole.

1. Määritä **Tietojen päivitykset** - vaiheessa mallin aikataulu.

   Mallia on koulutettava säännöllisesti, jotta se oppii uusia malleja, kun uusia tietoja käsitellään. Valitse tässä esimerkissä **Kuukausittain**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**. Mallin ensimmäinen suoritus kestää muutaman minuutin.

## <a name="task-4---review-model-results-and-explanations"></a>Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Voit nyt tarkastella tuotesuositusmallin selityksiä. Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tehtävä 5 – eniten ostettujen tuotteiden segmentin luominen

Tuotantomallin suorittaminen luo uuden entiteetin, jonka saa näkyviin valitsemalla **Tiedot** > **Entiteetit**.

Voit luoda uuden segmentin mallin luoman entiteetin perusteella.

1. Valitse **Segmentit**. Valitse **Uusi** ja sitten **Luo kohteesta Analytiikka**.

   ![Segmentin luominen mallin tulosteen avulla](media/segment-intelligence.png)

1. Valitse **OOBProductRecommendationModelPrediction**-päätepiste ja määritä segmentti:

   - Kenttä: ProductID
   - Arvo: Valitse kolme suosituinta tuotetunnusta

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Luo segmentti mallin tuloksista.":::

Nyt sinulla on dynaamisesti päivitetty segmentti, joka määrittää asiakkaat, jotka saattaisivat olla kiinnostuneita ostamaan kolme suositeltua tuotetta.

Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
