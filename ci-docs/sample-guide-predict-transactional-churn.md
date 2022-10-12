---
title: Tapahtuman vaihtuvuusennusteen näyteopas
description: Tämän näyteoppaan avulla voi kokeilla valmista tapahtuman vaihtuvuusennustemallia.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609680"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Tapahtuman vaihtuvuusennusteen näyteopas

Tässä oppaassa käsitellään kattavasti esimerkkiä tapahtuman vaihtuvuusennusteesta, jossa käytetään näytetietoja. Tätä ennustetta kannattaa kokeilla [uudessa ympäristössä](manage-environments.md).

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukkaita kahveja ja kahvikoneita. He myyvät tuotteita Contoso Coffeen verkkosivuston kautta. Yrityksen tavoitteena on saada tietää, ketkä asiakkaat tyypillisesti ostavat heidän tuotteitaan säännöllisesti, eivät ole enää asiakkaita seuraavan 60 päivän kuluttua. Sen tietäminen, ketkä asiakkaat **todennäköisesti vaihtuvat**, voi auttaa yritystä säästämään markkinointitoimia keskittymällä kyseisten asiakkaiden säilyttämiseen.

## <a name="prerequisites"></a>edellytykset

- Ainakin [osallistujan käyttöoikeudet](permissions.md).

## <a name="task-1---ingest-data"></a>Tehtävä 1 – Tietojen käsitteleminen

Tutustu [tietojen käsittelyä](data-sources.md) ja [tietolähteiden yhdistämistä Power Query -tietolähteeseen](connect-power-query.md) käsitteleviin artikkeleihin. Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä

1. Luo **eCommerce**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscontacts.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **DateOfBirth**: päivämäärä
   - **CreatedOn**: päivämäärä, aika ja aikavyöhyke

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuttaminen päivämääräksi.":::

1. Vaihda oikean ruudun **Nimi**-kenttään tietolähteen nimeksi **eCommerceContacts**

1. Tallenna tietolähde.

### <a name="ingest-online-purchase-data"></a>Verkko-ostostietojen käsitteleminen

1. Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen. Valitse **Text/CSV**-yhdistin uudelleen.

1. Anna verkko-ostojen tietojen URL-osoitteeksi https://aka.ms/ciadclassonline.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **PurchasedOn**: päivämäärä ja aika
   - **TotalPrice**: valuutta

1. Vaihda oikean ruudun **Nimi**-kenttään tietolähteen nimeksi **eCommercePurchases**.

1. Tallenna tietolähde.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Asiakastietojen käyttäminen kanta-asiakasrakenteesta

1. Luo **LoyaltyScheme**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/ciadclasscustomerloyalty.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **DateOfBirth**: päivämäärä
   - **RewardsPoints**: kokonaisluku
   - **CreatedOn**: päivämäärä, aika

1. Vaihda oikean ruudun **Nimi**-kentän tietolähteen nimeksi **loyCustomers**.

1. Tallenna tietolähde.

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

Tutustu [tietojen yhdistämistä](data-unification.md) käsittelevään artikkeliin. Seuraavissa tiedoissa oletetaan, että tietojen yhdistäminen on yleisesti ottaen tuttua.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tehtävä 3 – tapahtumahistorian aktiviteetin luominen

Tutustu [asiakkaan aktiviteetteja](activities.md) käsittelevään artikkeliin. Seuraavissa tiedoissa oletetaan, että aktiviteettien luominen on yleisesti ottaen tuttua.

1. Luo **eCommercePurchases**-niminen aktiviteetti, jossa on *eCommercePurchases:eCommerce*-entiteetti ja pääavain **PurchaseId**.

1. Luo kohteiden *eCommercePurchases:eCommerce* ja *eCommerceContacts:eCommerce* välille suhde siten, että **ContactID** on kaksi entiteettiä yhdistävä viiteavain.

1. Valitse **TotalPrice** **Aikaleima**-kohdan **EventActivity**- ja **PurchasedOn**-kohdissa.

1. Valitse **Aktiviteetin tyyppi** -kohdassa **SalesOrderLine** ja yhdistä aktiviteetin tiedot semanttisesti.

1. Suorita aktiviteetti.

## <a name="task-4---configure-transaction-churn-prediction"></a>Tehtävä 4 – tapahtuman vaihtuvuusennusteen määrittäminen

Yhdistettyjen asiakasprofiilien ja aktiviteetin avulla voidaan nyt suorittaa tapahtumien vaihtuvuusennuste.

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Asiakasvaihtuvuusmalli**-kohdassa **Käytä mallia**.

1. Valitse vaihtuvuuden tyypiksi **Tapahtuma** ja valitse sitten **Aloita**.

1. Valitse **Sähköisen OOB-kaupankäyntitapahtuman vaihtuvuusennuste** ja tuloste-entiteetti **OOBeCommerceChurnPrediction**.

1. Valitse **Seuraava**.

1. Malliasetusten määrittäminen:

   - **Ennusteikkuna**: **60** päivää määrittää, miten pitkälle tulevaisuuteen asiakasvaihtuvuus halutaan ennustaa.

   - **Vaihtuvuusmääritelmä**: **60** päivää ilmaisee keston ilman ostoksia, jonka jälkeen asiakas katsotaan vaihtuneeksi.

     :::image type="content" source="media/model-levers.PNG" alt-text="Malliasetusten ennusteikkunan ja vaihtuvuusmääritelmän valitseminen":::

1. Valitse **Seuraava**.

1. Valitse **Ostohistoria (pakollinen)** ja valitse ostohistorialle **Lisää tiedot** -arvo.

1. Valitse ensin **SalesOrderLine** ja eCommercePurchases-entiteetti sekä sitten **Seuraava**. Pakolliset tiedot täytetään automaattisesti aktiviteetista. Valitse ensin **Tallenna** ja sitten **Seuraava**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce-entiteetit.":::

1. Ohita **Lisätiedot (valinnainen)** -vaihe.

1. Määritä **Tietojen päivitykset** -vaiheessa mallin aikatauluksi **Kuukausittain**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.

## <a name="task-5---review-model-results-and-explanations"></a>Tehtävä 5 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Tarkastele vaihtuvuusmallin selityksiä. Lisätietoja on kohdassa [Ennusteen tulosten näyttäminen](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tehtävä 6 – Suuren vaihtuvuusriskin asiakkaiden segmentin luominen

Tuotantomallin suorittaminen luo uuden entiteetin, joka näkyy **Tieto** > **Entiteetit** -kohdassa. Voit luoda uuden segmentin mallin luoman entiteetin perusteella.

1. Valitse tulossivulla **Luo segmentti**.

1. Luo sääntö **OOBeCommerceChurnPrediction**-entiteetin avulla ja määritä segmentti:
   - **Kenttä**: ChurnScore
   - **Operaattori**: suurempi kuin
   - **Arvo**: 0,6

1. Valitse **Tallenna** ja **suorita** segmentti.

Nyt sinulla on dynaamisesti päivitetty segmentti, joka määrittää suuren vaihtuvuusriskin asiakkaat. Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

> [!TIP]
> Ennustemallin segmentti voidaan luoda myös **Segmentit**-sivulla valitsemalla ensin **Uusi** ja sitten **Luominen kohteesta** > **Älykäs toiminto**. Lisätietoja on kohdassa [Uuden segmenttien luominen pikasegmenttien avulla](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
