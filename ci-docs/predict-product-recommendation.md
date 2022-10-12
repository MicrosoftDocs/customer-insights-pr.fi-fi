---
title: Tuotesuositusten ennustaminen
description: Ennusta tuotteet, joita asiakas todennäköisesti ostaa tai joiden kanssa asiakas on tekemisissä.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610278"
---
# <a name="predict-product-recommendations"></a>Tuotesuositusten ennustaminen

Tuotesuositusmalli luo ennakoivia tuotesuositusjoukkoja. Suositukset perustuvat aiempaan ostokäyttäytymiseen ja asiakkaisiin, joilla on samanlaisia ostomalleja. Tämä malli on tarkoitettu yksittäisille kuluttajille (kuluttajakauppa).

Tarvitaan liiketoiminnan tietämystä liiketoiminnassa käytettävien tuotteiden eri tyypeistä ja tavasta, jolla asiakkaat käyttävät niitä. Tuemme sellaisten tuotteiden suosittelemista, joita asiakkaat ovat ostaneet aiemmin, tai uusien tuotteiden suosittelemista.

Tuotesuosituksiin saatetaan soveltaa paikallisia lakeja ja määräyksiä sekä asiakkaiden odotuksia. Mallia ei ole suunniteltu ottamaan huomioon näitä seikkoja. Tämän vuoksi **suositukset on tarkistettava ennen toimitusta asiakkaille**. Näin voidaan varmistaa, että soveltuvia lakeja tai säädöksiä noudetaan sekä asiakkaan odotuksiin vastataan suositusten osalta.

Tämän mallin tulos antaa suosituksia tuotetunnuksen perusteella. Toimitusmekanismin on yhdistettävä ennustetut tuotetunnukset asiakkaiden sopivaan sisältöön lokalisointia, kuvasisältöä ja muuta liiketoimintakohtaista sisältöä tai toiminnallisuutta varten.

> [!TIP]
> Tuotesuositusten ennustamista voi kokeilla näytetietojen avulla: [Tuotesuositusten ennusteen näyteopas](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>edellytykset

- Vähintään [osallistujan käyttöoikeudet](permissions.md)
- Vähintään 100 asiakasta, mielellään yli 10 000 asiakasta.
- Asiakkaan tunnus on yksilöivä tunnus, joka yhdistää tapahtumat yksittäiseen asiakkaaseen
- Vähintään yhden vuoden, mielellään 2–3 vuoden liiketapahtumatiedot, joihin sisältyy kausivaihteluita. Parhaan tuloksen saa, kun kullakin asiakastunnuksella on vähintään kolme tapahtumaa. Tapahtumahistorian on sisällettävä seuraavat tiedot:
  - **Tapahtuman tunnus**: oston tai tapahtuman yksilöivä tunnus.
  - **Tapahtuman päivämäärä**: oston tai tapahtuman päivämäärä.
  - **Tapahtuman arvo**: oston tai tapahtuman numeroarvoinen summa.
  - **Yksilöivä tuotetunnus**: ostetun tuotteen tai palvelun tunnus, jos tieto on rivitasolla.
  - **Osto tai palautus**: totuusarvo, jonka arvo *tosi* osoittaa, että tapahtuma oli palautus. Jos osto- tai palautustietoja ei ole annettu mallissa ja **Tapahtuman arvo** on negatiivinen, palautus johdetaan.
- Tuoteluettelon tietoentiteetti, jota käytetään tuotesuodattimena.

> [!NOTE]
> - Mallia varten tarvitaan asiakkaiden tapahtumahistoria, jossa tapahtumalla tarkoitetaan mitä tahansa käyttäjätuotteen käyttöä koskevaa tietoa. Esimerkiksi tuotteen ostaminen tai osallistuminen kurssille tai tapahtumaan.
> - Vain yksi tapahtumahistorian entiteetti voidaan määrittää. Jos ostoentiteettejä on useita, ne yhdistetään Power Queryssä ennen tietojen käsittelyn alkamista.
> - Jos tilaus ja tilaustiedot ovat eri entiteettejä, yhdistä ne ennen mallin käyttöä. Malli ei toimi, jos käytössä on vain entiteetin tilaustunnus tai vastaanottotunnus.

## <a name="create-a-product-recommendation-prediction"></a>Tuotesuosituksen ennusteen luominen

Ennuste voidaan tallentaa koska tahansa luonnoksena valitsemalla **Tallenna luonnos**. Ennusteluonnos näkyy **Omat ennusteet** -välilehdessä.

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Tuotesuositukset (esiversio)** -ruudussa **Käytä mallia**.

1. Valitse **Aloita**.

1. **Anna tälle mallille** ja **tulosentiteetille nimi**, jotta ne voidaan erottaa muista malleista tai entiteeteistä.

1. Valitse **Seuraava**.

### <a name="define-product-recommendation-preferences"></a>Tuotesuositusmääritysten määrittäminen

1. Määritä asiakkaille suositeltavien **tuotteiden määrä**. Arvo riippuu siitä, miten toimitusmenetelmä täyttää tiedot.

1. Valitse, sisällytetäänkö **Toistuvia ostoja odotetaan** -kenttään tuotteet, joita asiakkaat ovat aiemmin ostaneet.

1. Määritä **Katso taaksepäin -ikkuna** -kohtaan aikaväli, jonka malli odottaa, ennen kuin tuotetta suositellaan käyttäjälle uudelleen. Ilmoita esimerkiksi, että asiakas ostaa kannettavan tietokoneen kahden vuoden välein. Malli tarkastelee ostohistoriaa kahden viime vuoden ajalta. Jos nimike löytyy, se suodatetaan suosituksista.

1. Valitse **Seuraava**

### <a name="add-purchase-history"></a>Lisää ostohistoria

1. Valitse **Lisää tiedot** **Asiakkaan tapahtumahistoria** -kohdassa.

1. Valitse semanttinen aktiviteettityyppi **SalesOrderLine**, joka sisältää tarvittavat tapahtuma- tai ostohistoriatiedot. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty semanttisesti aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos semanttista yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Sivuruutu, jossa näkyy tiettyjen aktiviteettien valitseminen semanttisen tyypin perusteella.":::

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Valitse **Seuraava**.

### <a name="add-product-information-and-filters"></a>Tuotetietojen ja suodattimien lisääminen

Joskus vain tietyt tuotteet ovat ennusteen tyypille sopivia tai hyödyllisiä. Tuotesuodattimien avulla asiakkaille voidaan määrittää suositeltujen tuotteiden alijoukko, jolla on tietyt ominaisuudet. Malli käyttää kaikkia käytettävissä olevia tuotteita kaavojen oppimiseen, mutta käyttää vain tuotteita, jotka vastaavat tuotesuodattimen tuloksia.

1. Lisää kunkin tuotteen tiedot sisältävä tuoteluetteloentiteetti. Yhdistä tarvittavat tiedot ja valitse **Tallenna**.

1. Valitse **Seuraava**.

1. Valitse **Tuotesuodattimet**:

   - **Ei suodattimia**: käytä kaikkia tuotesuosituksen ennusteen tuotteita.

   - **Määritä tietyt tuotesuodattimet**: käytä tiettyjä tuotteita tuotesuosituksen ennusteessa. Valitse **Tuoteluettelon määritteet** -ruudussa tuoteluetteloentiteetin määritteet, jotka haluat sisällyttää suodattimeen.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Sivuruutu, joka näyttää tuoteluettelon entiteetin määritteet tuotesuodattimia varten.":::

1. Valitse, käytetäänkö tuotesuodattimessa **ja**- tai **tai**-yhdistimiä yhdistämään loogisesti määritteiden valinta tuoteluettelosta.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Tuotesuodattimien esimerkkimääritys yhdistettynä loogisiin JA-yhdistimiin.":::

1. Valitse **Seuraava**.

### <a name="set-update-schedule"></a>Päivitysaikataulun määrittäminen

1. Valitse mallin uudelleenkouluttamistiheys. Tämä asetus on tärkeä ennusteiden tarkkuuden päivittämiseksi, kun Customer Insightsissa käsitellään uusia tietoja. Useimmat yritykset voivat kouluttaa uudelleen kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

### <a name="review-and-run-the-model-configuration"></a>Mallimäärityksen tarkasteleminen ja suorittaminen

**Tarkistus ja suoritus** -vaiheessa näkyy määritysten yhteenveto. Siinä on myös mahdollista tehdä muutoksia ennen ennusteen luontia.

1. Tee tarkistukset ja tarvittavat muutokset valitsemalla **Muokkaa**.

1. Jos olet tyytyväinen valintoihin, aloita mallin suorittaminen valitsemalla **Tallenna ja suorita**. Valitse **Valmis**. **Omat ennusteet** -välilehti on näkyvissä, kun ennustetta luodaan. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ennusteen tulosten näyttäminen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Omat ennusteet** -välilehdessä tarkasteltava ennuste.

Tulossivulla on viisi ensisijaista tieto-osaa.

- **Mallin suorituskyky**: Luokka A, B tai C osoittaa ennusteen suorituskyvyn. Sen avulla voit päättää, käytetäänkö tulosentiteettiin tallennettuja tuloksia.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Kuva mallin suorituskyvystä, kun tuloksena on luokka A":::

  Luokat määritetään seuraavien sääntöjen perusteella:
  - **A**, kun Onnistui @ K -mittari ylittää vähintään 10 % perustason.
  - **B**, kun Onnistui @ K -mittari ylittää vähintään 0–10 % perustason.
  - **C**, kun Onnistui @ K -mittari on alle perustason.
  - **Perustaso**: Kaikkien asiakkaiden ostomäärien mukaiset suositelluimmat tuotteet + mallin määrittämät opitut säännöt = joukko suosituksia asiakkaille. Ennusteita vertaillaan sen jälkeen myydyimpiin tuotteisiin tuotteen ostaneiden asiakkaiden määrän mukaan laskettuna. Jos asiakkaan suositelluissa tuotteissa on vähintään yksi tuote, joka on myös myydyimpien tuotteiden joukossa, heitä pidetään perustason asiakkaina. Jos esimerkiksi 10 asiakasta yhteensä 100 asiakkaasta on suositellut ostettua tuotetta, perustaso on 10 %.
  - **Onnistui @ K**: Suositukset luodaan kaikille asiakkaille käyttämällä, ja niitä verrataan tapahtumien ajanjakson tarkistusjoukkoon. Esimerkiksi 12 kuukauden jakson aikana kuukausi 12 voidaan jättää tietojen tarkistusjoukoksi. Jos malli ennustaa vähintään yhden oston kuukauden 12 aikana edellisten 11 kuukauden tietojen perusteella, asiakas kasvattaa Menestys @ K -mittarin arvoa.

- **Useimmin ehdotetut tuotteet (laskurin kanssa)**: viisi yleisintä asiakkaille ennustettua tuotetta.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Kaavio, jossa on 5 eniten suositeltua tuotetta.":::

- **Tärkeimmät suositustekijät:** malli antaa tuotesuosituksia asiakkaiden tapahtumahistorian perusteella. Se oppii aiemmin tehtyihin ostoihin perustuvia malleja ja löytää samankaltaisuuksia asiakkaiden ja tuotteiden välillä. Näiden samankaltaisuuksien avulla luodaan tuotesuosituksia.
  Seuraavat tekijät voivat vaikuttaa mallin tuottamaan tuotesuositukseen.
  - **Aiemmat tapahtumat**: Suositeltu tuote perustui aiempiin ostomalleihin. Malli voi esimerkiksi suositella *Surfacen Arc Mouse* -hiirtä, jos joku on äskettäin ostanut *Surface Book 3:n* ja *Surface-kynän*. Malli on oppinut, että monet asiakkaat olivat hankkineet *Surface Arc Mousen*, kun ovat ostaneet *Surface Book 3:n* ja *Surface-kynän*.
  - **Asiakkaiden samankaltaisuus**: Muut asiakkaat, joilla on samanlaiset ostomallit, ovat hankkineet suositellun tuotteen. Esimerkiksi Johnille suositellaan *Surface Headphones 2* -kuulokkeita, koska Jennifer ja Brad ostivat hiljattain *Surface Headphones 2* -kuulokkeet. Malli olettaa, että John muistuttaa Jenniferiä ja Bradiä, koska heillä on ollut samanlaisia ostomalleja.
  - **Tuotteen samankaltaisuus**: Suositeltava tuote muistuttaa muita tuotteita, jotka asiakas oli aiemmin ostanut. Malli katsoo, että kaksi tuotetta on samanlaisia, jos ne on ostettu yhdessä tai samankaltaisten asiakkaiden toimesta. esimerkiksi joku saa suosituksen *USB-tallennusasemasta*, koska he aiemmin ostivat *USB-C – USB -adapterin* ja malli olettaa historiallisten ostokaavojen perusteella, että *USB-tallennusasema* on samankaltainen kuin *USB-C – USB -adapteri*.

  Yksi tai useampi näistä tekijöistä vaikuttaa kaikkiin tuotesuosituksiin. Niiden suositusten prosenttiosuus, joissa jokaisella tekijällä on ollut rooli, visualisoidaan kaaviossa. Seuraavassa esimerkissä aiemmat tapahtumat vaikuttavat 100 prosenttiin suosituksista, asiakkaan samankaltaisuus 60 prosenttiin suosituksista ja tuotteiden samankaltaisuus 22 prosenttiin suosituksista. Vie osoitin kaavion palkkien päälle nähdäksesi, minkä tarkan prosenttiosuuden vaikuttavat tekijät ovat vaikuttaneet.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Tärkeimmät suositustekijät, jotka malli on oppinut tuotesuositusten luontia varten":::

- **Tietotilastot**: Yleiskuvan käytettävän mallin tapahtumien, asiakkaiden ja tuotteiden lukumäärästä. Se perustuu syötetietoihin, joita käytettiin kaavojen oppimiseen ja tuotesuositusten luomiseen.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Mallin käyttämät syötetietojen tilastot, joita malli käyttää kaavojen oppimiseen":::
  
  Malli käyttää kaikkia käytettävissä olevia tietoja kaavojen oppimiseen. Jos tuotesuodatusta siis käytetään mallimäärityksessä, tässä osassa näkyy mallin kaavojen oppimista varten analysoimien tuotteiden kokonaismäärä, mikä voi poiketa määritettyjä suodatusehtoja vastaavien tuotteiden lukumäärästä. Suodatus koskee mallin luomaa tulosta.

- **Näytetuotesuositukset:** Näyte tuotesuosituksista, joita malli olettaa asiakkaan ostavan. Jos tuoteluettelo on lisätty, tuotetunnukset korvataan tuotenimillä.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Luettelo, jossa näkyvät erittäin luotettavat suositukset valitulle yksittäisten asiakkaiden joukolle.":::

> [!NOTE]
> Tämä mallin tulosentiteetissä *pistemäärä* osoittaa suosituksen kvantitatiivisen mittarin. Malli suosittelee tuotteita, joiden pistemäärä on suurempi kuin tuotteita, joiden pistemäärä on pienempi. Pistemäärää voi tarkastella valitsemalla **Tiedot** > **Entiteetit** ja tarkastelemalla malliin määritetyn tulosentiteetin tietovälilehteä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
