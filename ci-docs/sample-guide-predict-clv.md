---
title: Asiakkaan elinkaariarvoennuste (CLV) esimerkkioppaassa
description: Tämän esimerkkioppaan avulla voit kokeilla asiakkaan ennustearvoa.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051633"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Asiakkaan elinkaariarvoennuste (CLV) esimerkkioppaassa

Tässä oppaassa kerrotaan esimerkkidatan avulla asiakkaan elinkaariarvon (CLV) ennakoinnista Customer Insightsissa alusta loppuun asti.

## <a name="scenario"></a>Skenaario

Contoso on yritys, joka tuottaa laadukkaita kahveja ja kahvikoneita. He myyvät tuotteita Contoso Coffeen verkkosivuston kautta. Yritys haluaa ymmärtää arvon (tuoton), jonka asiakkaat voivat luoda seuraavien 12 kuukauden aikana. Tietäen asiakkaiden odotetun arvon seuraavien 12 kuukauden aikana auttavat heitä ohjaamaan markkinointia suuriarvoisiin asiakkaisiin.

## <a name="prerequisites"></a>edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.
- Seuraavat vaiheet on suositeltavaa toteuttaa [uudessa ympäristössä](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tehtävä 1 – Tietojen käsitteleminen

Tutustu artikkeleihin [tietojen käsittelystä](data-sources.md) ja [tietolähteiden tuomisesta Power Query -yhdistinten avulla](connect-power-query.md). Seuraavissa tiedoissa oletetaan, että tietojen käsittely on yleisesti ottaen tuttua.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Asiakas tietojen käsitteleminen sähköisen kaupankäynnin ympäristössä

1. Luo **eCommerce**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:
   - **DateOfBirth**: päivämäärä
   - **CreatedOn**: päivämäärä, aika ja aikavyöhyke

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Syntymäpäivän muuntaminen päivämääräksi.":::

1. Vaihda oikean ruudun Nimi-kentän tietolähteen nimi. Vanha nimi on **Query** ja uusi on **eCommerceContacts**

1. **Tallenna** tietolähde.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Sivustoarvioista saatujen asiakastietojen käsitteleminen

1. Luo **Website**-niminen tietolähde, valitse tuontivaihtoehto ja valitse sitten **Text/CSV**-yhdistin.

1. Anna sähköisen kaupankäynnin yhteyshenkilöiden URL-osoite https://aka.ms/CI-ILT/WebReviews.

1. Valitse tietoja muokatessa **Muunna** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.

1. Päivitä seuraavien sarakkeiden tietotyyppi:

   - **Arvosteluarvosana**: desimaaliluku
   - **ReviewDate**: päivämäärä

1. Nimeä tietolähteesi oikeanpuoleisen ruudun Nimi-kenttä **Kyselystä** **Arvosteluiksi**.

1. **Tallenna** tietolähde.

## <a name="task-2---data-unification"></a>Tehtävä 2 – tietojen yhtenäistäminen

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tehtävä 3 ‑ Määritä asiakkaan elinkaariarvon ennuste

Kun yhtenäiset asiakasprofiilit ovat käytössä, voidaan nyt suorittaa asiakkaan elinkaariarvon ennuste. Yksityiskohtaiset ohjeet ovat ohjeaiheessa [Asiakkaan elinkaariarvon ennuste](predict-customer-lifetime-value.md).

1. Siirry kohtaan **Älykäs toiminto**  > **Ennusteet** ja valitse **Asiakkaan elinkaariarvomalli**.

1. Käy sivuruudun tiedot läpi ja valitse **Aloitus**.

1. Anna mallille nimeksi **OOB eCommerce CLV-ennuste** ja tulosentiteetille **OOBeCommerceCLVPrediction**.

1. Määritä CLV-mallin malliasetukset:
   - **Ennusteajanjakso**: **12 kuukautta tai 1 vuosi**. Tämä asetus määrittää, miten paljon tulevaisuudessa voidaan ennustaa asiakkaan elinkaariarvoa.
   - **Aktiiviset asiakkaat**: määritä, mitä aktiiviset asiakkaat tarkoittavat liiketoiminnassa. Määritä historiallinen ajanjakso, jolloin asiakkaalla on oltava vähintään yksi tapahtuma, jotta häntä voidaan pitää aktiivisena. Malli ennustaa vain aktiivisten asiakkaiden asiakkaan elinkaaren arvon. Valitse, annetaanko mallin laskea ajanjakso historiallisten tapahtumien tietojen perusteella vai antaa aikaväli. Tässä esimerkkioppaassa **mallin avulla voi laskea ostovälin**, joka on oletusvaihtoehto.
   - **Erittäin arvokkaat asiakkaat**: Määritä arvokkaat asiakkaat prosenttipisteeksi eniten maksavista asiakkaista. Mallin avulla saadaan tuloksia, jotka sopivat yrityksen arvokkaisiin asiakkaisiin. Voit antaa mallin määrittää korkean arvon asiakkaat. Se käyttää heuristista sääntöä, joka johtaa prosenttipisteen. Voit myös määrittää arvokkaat asiakkaat prosenttipisteeksi eniten maksavista tulevista asiakkaista. Tässä esimerkkioppaassa määritetään manuaalisesti arvokkaat asiakkaat **ylimmäksi 30 prosentiksi aktiivisista maksavista asiakkaista** ja valitaan **Seuraava**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV-mallin ohjatun käyttökokemuksen asetukset-vaihe.":::

1. Valitse **Pakolliset tiedot** -vaiheessa **Lisää tietoja**, jotta saat tapahtumahistoriatiedot.

1. Lisää **eCommercePurchases : eCommerce** -entiteetti ja yhdistä mallin edellyttämät määritteet:
   - Tapahtuman tunnus: eCommerce.eCommercePurchases.PurchaseId
   - Tapahtuman päivämäärä: eCommerce.eCommercePurchases.PurchasedOn
   - Tapahtuman summa: eCommerce.eCommercePurchases.TotalPrice
   - Tuotetunnus: eCommerce.eCommercePurchases.ProductId

1. Valitse **Seuraava**.

1. Määritä **eCommercePurchases : eCommerce**-entiteetin ja **eCommerceContacts : eCommerce**-entiteetin välinen suhde.

1. **Lisätiedot (valinnainen)**-vaiheen avulla voit lisätä asiakasaktiviteettitietoja. Näiden tietojen avulla saat enemmän tietoja asiakkaan kanssakäynnistä yrityksesi kanssa, mikä voi auttaa CLV:ssä. Lisäämällä tärkeitä asiakasvuorovaikutuksia, kuten verkkolokeja, asiakaspalvelulokeja tai palkitsemisohjelmahistoriaa, voi parantaa ennusteiden tarkkuutta. Valitse **Lisää tietoja**, jos haluat lisätä asiakasaktiviteettitietoja.

1. Lisää asiakasaktiviteettientiteetti ja yhdistä sen kenttien nimet vastaaviin mallin edellyttämiin kenttiin:
   - Asiakasaktiviteettientiteetti: Arviot:Verkkosivusto
   - Perusavain: Website.Reviews.ReviewId
   - Aikaleima: Website.Reviews.ReviewDate
   - Tapahtuma (aktiviteetin nimi): Website.Reviews.ActivityTypeDisplay
   - Tiedot (summa tai arvo): Website.Reviews.ReviewRating

1. Valitse **Seuraava** ja määritä aktiviteetti sekä tapahtumatietojen ja asiakastietojen välinen suhde:  
   - Aktiviteetin tyyppi: Valitse olemassa oleva
   - Aktiviteetin selite: Arvostelu
   - Vastaava otsikko: Website.Reviews.UserId
   - Asiakasentiteetti: eCommerceContacts:eCommerce
   - Suhde: WebsiteReviews

1. Määritä mallin aikataulu valitsemalla **Seuraava**.

   Mallin täytyy opetella säännöllisesti oppiakseen uusia kaavoja, kun uusia tietoja on sisäistetty. Valitse tässä esimerkissä **Kuukausittain**.

1. Kun tiedot on tarkistettu, valitse **Tallenna ja suorita**.

## <a name="task-4---review-model-results-and-explanations"></a>Tehtävä 4 – mallin tulosten ja selitysten tarkistaminen

Anna mallin suorittaa tietojen kouluttaminen ja pisteyttäminen. Seuraavaksi voit tarkastella CLV-mallin tuloksia ja selityksiä. Lisätietoja on kohdassa [Ennusteen tilan ja tulosten tarkasteleminen](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tehtävä 5 ‑ Luo segmentti arvokkaista asiakkaista

Mallin käyttö luo uuden entiteetin, joka näkyy **Tieto** > **Entiteetit** -kohdassa. Voit luoda uuden asiakassegmentin mallin luoman entiteetin perusteella.

1. Valitse **Segmentit**. 

1. Valitse ensin **Uusi** ja sitten **Luominen kohteesta** > **Analytiikka**.

   ![Segmentin luominen mallin tulosteen avulla](media/segment-intelligence.png)

1. Valitse **OOBeCommerceCLVPrediction**-entiteetti ja määritä segmentti:
  - Kenttä: CLVScore
  - Operaattori: suurempi kuin
  - Arvo: 1500

1. Valitse **Tarkista** ja **Tallenna** segmentti.

Sinulla on nyt segmentti, joka tunnistaa asiakkaat, joiden ennustetaan tuottavan yli 1500 $:n tuloja seuraavan 12 kuukauden aikana. Tämä segmentti päivittyy dynaamisesti, jos enemmän tietoja on nautittu.

Saat lisätietoja ohjeartikkelista [Segmenttien luominen ja hallinta](segments.md).
