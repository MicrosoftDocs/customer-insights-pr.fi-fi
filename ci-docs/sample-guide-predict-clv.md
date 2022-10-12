---
title: Asiakkaan elinkaariarvoennuste (CLV) esimerkkioppaassa
description: Tämän esimerkkioppaan avulla voit kokeilla asiakkaan ennustearvoa.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609634"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Asiakkaan elinkaariarvoennuste (CLV) esimerkkioppaassa

Tässä oppaassa käsitellään näytetietojen ja kattavan esimerkiksi avulla asiakkaan elinkaaren arvon (CLV) ennustamista Customer Insightsissa. Tätä ennustetta kannattaa kokeilla [uudessa ympäristössä](manage-environments.md).

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukkaita kahveja ja kahvikoneita. He myyvät tuotteita Contoso Coffeen verkkosivuston kautta. Yritys haluaa ymmärtää arvon (tuoton), jonka asiakkaat voivat luoda seuraavien 12 kuukauden aikana. Tietäen asiakkaiden odotetun arvon seuraavien 12 kuukauden aikana auttavat heitä ohjaamaan markkinointia suuriarvoisiin asiakkaisiin.

## <a name="prerequisites"></a>edellytykset

- Ainakin [osallistujan käyttöoikeudet](permissions.md).

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

1. **Tallenna** tietolähde.

### <a name="ingest-online-purchase-data"></a>Verkko-ostostietojen käsitteleminen

1. Lisää toinen tietojoukko samaan **eCommerce**-tietolähteeseen. Valitse **Text/CSV**-yhdistin uudelleen.

1. Anna **Verkko-ostokset**-tietojen URL-osoite https://aka.ms/ciadclassonline.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **PurchasedOn**: päivämäärä ja aika
   - **TotalPrice**: valuutta

1. Vaihda sivuruudun **Nimi**-kenttään tietolähteen nimeksi **eCommercePurchases**.

1. **Tallenna** tietolähde.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Asiakastietojen käyttäminen kanta-asiakasrakenteesta

1. Luo **LoyaltyScheme**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Anna kanta-asiakkaiden URL-osoitteeksi https://aka.ms/ciadclasscustomerloyalty.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **RewardsPoints**: kokonaisluku
   - **CreatedOn**: päivämäärä, aika

1. Vaihda oikean ruudun **Nimi**-kentän tietolähteen nimeksi **loyCustomers**.

1. **Tallenna** tietolähde.

### <a name="ingest-customer-data-from-website-reviews"></a>Sivustoarvioista saatujen asiakastietojen käsitteleminen

1. Luo **Website**-niminen tietolähde ja valitse **Text/CSV**-yhdistin.

1. Anna sivuston arvioille URL-osoite https://aka.ms/CI-ILT/WebReviews.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **Arvosteluarvosana**: desimaaliluku
   - **ReviewDate**: päivämäärä

1. Vaihda oikean ruudun **Nimi**-kentässä tietolähteen nimeksi **Reviews**.

1. **Tallenna** tietolähde.

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

1. Lisää toinen aktiviteetti ja yhdistä sen kenttien nimet vastaaviin kenttiin:
   - **Aktiviteettientiteetti**: Reviews:Website
   - **Perusavain**: ReviewId
   - **Aikaleima**: ReviewDate
   - **Tapahtuma-aktiviteetti**: ActivityTypeDisplay
   - **Lisätiedot**: ReviewRating
   - **Aktiviteetin tyyppi**: Review

1. Suorita aktiviteetti.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tehtävä 4 ‑ Määritä asiakkaan elinkaariarvon ennuste

Kun yhtenäiset asiakasprofiilit ovat käytössä ja aktiviteetti luotu, asiakkaan elinkaaren arvon (CLV) ennuste voidaan suorittaa. Yksityiskohtaiset ohjeet ovat ohjeaiheessa [Asiakkaan elinkaariarvon ennuste](predict-customer-lifetime-value.md).

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Asiakkaan elinkaaren arvo** -ruudussa **Käytä mallia**.

1. Valitse **Aloita**.

1. Anna mallille nimeksi **OOB eCommerce CLV-ennuste** ja tulosentiteetille **OOBeCommerceCLVPrediction**.

1. Malliasetusten määrittäminen:
   - **Ennusteen ajanjakso**: **12 kuukautta tai 1 vuosi** määrittää, miten paljon tulevaisuudessa voidaan ennustaa asiakkaan elinkaariarvoa.
   - **Aktiiviset asiakkaat**: **Salli mallin laskea ostoväli** on aikaväli, jonka aikana asiakkaalla on oltava vähintään yksi tapahtuma, jotta asiakasta pidetään aktiivisena.
   - **Korkean lisäarvon asiakkaat**: määritetään manuaalisesti korkean lisäarvon asiakkaat **ylimmäksi 30 prosentiksi aktiivisista asiakkaista**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV-mallin ohjatun käyttökokemuksen asetukset-vaihe.":::

1. Valitse **Seuraava**.

1. Valitse **Pakolliset tiedot** -vaiheessa **Lisää tietoja**, jotta saat tapahtumahistoriatiedot.

    :::image type="content" source="media/clv-model-required.png" alt-text="Pakollisen tietovaiheen lisääminen CLV-mallin ohjatussa kokemuksessa":::

1. Valitse ensin **SalesOrderLine** ja eCommercePurchases-entiteetti sekä sitten **Seuraava**. Pakolliset tiedot täytetään automaattisesti aktiviteetista. Valitse ensin **Tallenna** ja sitten **Seuraava**.

1. **Lisätiedot (valinnainen)**-vaiheen avulla voidaan lisätä asiakkaan aktiviteettitietoja, joilla saadaan lisää merkityksellisiä tietoja asiakasvuorovaikutusta varten. Valitse tässä esimerkissä **Lisää tiedot** ja lisää sivustoarvioaktiviteetti.

1. Valitse **Seuraava**.

1. Määritä **Tietojen päivitykset** -vaiheessa mallin aikatauluksi **Kuukausittain**.

1. Valitse **Seuraava**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.

## <a name="task-5---review-model-results-and-explanations"></a>Tehtävä 5 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Tutustuminen [CLV-mallin tuloksiin ja selityksiin](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tehtävä 6 ‑ Luo segmentti arvokkaista asiakkaista

Mallin käyttö luo uuden entiteetin, joka näkyy **Tieto** > **Entiteetit** -kohdassa. Voit luoda uuden asiakassegmentin mallin luoman entiteetin perusteella.

1. Valitse tulossivulla **Luo segmentti**.

1. Luo sääntö **OOBeCommerceCLVPrediction**-entiteetin avulla ja määritä segmentti:
   - **Kenttä**: CLVScore
   - **Operaattori**: suurempi kuin
   - **Arvo**: 1500

1. Valitse **Tallenna** ja **suorita** segmentti.

Sinulla on nyt segmentti, joka tunnistaa asiakkaat, joiden ennustetaan tuottavan yli 1500 $:n tuloja seuraavan 12 kuukauden aikana. Tämä segmentti päivittyy dynaamisesti, jos enemmän tietoja on nautittu. Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).

> [!TIP]
> Ennustemallin segmentti voidaan luoda myös **Segmentit**-sivulla valitsemalla ensin **Uusi** ja sitten **Luominen kohteesta** > **Älykäs toiminto**. Lisätietoja on kohdassa [Uuden segmenttien luominen pikasegmenttien avulla](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
