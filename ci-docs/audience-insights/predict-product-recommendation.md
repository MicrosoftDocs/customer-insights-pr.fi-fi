---
title: Tuotesuosituksen ennuste
description: Ennusta tuotteet, joita asiakas todennäköisesti ostaa tai joiden kanssa asiakas on tekemisissä.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: bcbafa513c2c61b0280c91aa7ed71e211c32c35c
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556120"
---
# <a name="product-recommendation-prediction-preview"></a>Tuotesuosituksen ennuste (esiversio)

Tuotesuositusmalli luo ennakoivia tuotesuositusjoukkoja. Suositukset perustuvat aiempaan ostokäyttäytymiseen ja asiakkaisiin, joilla on samanlaisia ostomalleja. Voit luoda uusia tuotesuosituksen ennusteita **Analytiikka** > **Ennusteet** -sivulla Valitse **Omat ennusteet**, kun haluat nähdä muita luomiasi ennusteita.

Tuotesuosituksiin saatetaan soveltaa paikallisia lakeja ja määräyksiä sekä asiakkaiden odotuksia. Mallia ei ole suunniteltu ottamaan huomioon näitä seikkoja.  Tämän ennakoivan ominaisuuden käyttäjänä **sinun on tarkistettava suositukset, ennen kuin toimitat ne asiakkaillesi**. Näin voit varmistaa, että noudatat soveltuvia lakeja tai säädöksiä sekä asiakkaan odotuksia sille, mitä suosittelet. 

Lisäksi tämän mallin tulos antaa suosituksia tuotetunnuksen perusteella. Toimitusmekanismin on yhdistettävä ennustetut tuotetunnukset asiakkaiden sopivaan sisältöön lokalisointia, kuvasisältöä ja muuta liiketoimintakohtaista sisältöä tai toiminnallisuutta varten.

## <a name="sample-guide"></a>Esimerkkiopas

Jos haluat kokeilla tätä ominaisuutta, mutta sinulla ei ole tietoja alla mainittujen vaatimusten täyttämiseksi, voit [luoda esimerkkitoteutuksen](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.

- Liiketoiminnan tietämystä, joka auttaa ymmärtämään liiketoiminnan tuotteiden erilaisia tyyppejä ja sitä, miten asiakkaat käyttävät niitä. Tuemme sellaisten tuotteiden suosittelemista, joita asiakkaat ovat ostaneet aiemmin, tai uusien tuotteiden suosittelemista.

- Tietoja tapahtumista ja ostoista sekä niiden historiasta:
    - Tapahtumatunnisteet erottavat ostot ja tapahtumat toisistaan.
    - Asiakastunnisteet, joilla tapahtumat yhdistetään asiakkaisiin.
    - Tapahtuman tapahtumapäivämäärät, jotka määrittävät tapahtuman tapahtumispäivämäärät.
    - Tapahtuman tuotetunnustiedot.
    - (Valinnainen) Tuoteluettelon tietoentiteetti, joka käyttää tuotesuodatinta.
    - (Valinnainen) Määrittää, onko tapahtuma palautus vai ei.
    - Semanttiseen tietorakenteeseen tarvitaan seuraavat tiedot:
        - **Tapahtuma tunnus:** oston tai tapahtuman yksilöivä tunnus.
        - **Tapahtuman päivämäärä:** oston tai tapahtuman päivämäärä.
        - **Tapahtuman arvo:** oston tai tapahtuman numeroarvoinen summa.
        - **Yksilöivä tuotetunnus:** ostetun tuotteen tai palvelun tunnus, jos tieto on rivitasolla.
        - (Valinnainen) **Osto tai palautus:** Totuusarvokenttä, jonka arvo *tosi* osoittaa, että tapahtuma oli palautus. Jos osto- tai palautustietoja ei ole annettu mallissa ja **Tapahtuman arvo** on negatiivinen, käytämme näitä tietoja palautuksen päättelyssä.
- Ehdotetut tietojen ominaisuudet:
    - Riittävät historiatiedot: Ainakin yksi vuosi liiketapahtumatietoja, mielellään 2–3 vuotta, joihin sisältyy kausivaihteluita.
    - Useita ostoja asiakasta kohden: vähintään kolme tapahtumaa asiakastunnusta kohden
    - Asiakkaiden määrä: vähintään 100 asiakasta, mielellään yli 10 000 asiakasta. Malli epäonnistuu, jos asiakkaita on alle 100.

> [!NOTE]
> - Malliin tarvitaan asiakkaiden tapahtumahistoria. Tapahtuman määritelmä on varsin joustava. Kaikki tiedot, jotka kuvaavat käyttäjän ja tuotteen välistä vuorovaikutusta, voivat toimia syötteenä. Esimerkiksi tuotteen ostaminen tai osallistuminen kurssille tai tapahtumaan.
> - Tällä hetkellä voi määrittää vain yhden tapahtumahistorian entiteetin. Jos ostoentiteettejä on useita, yhdistä ne Power Queryssä ennen tietojen käsittelyä.
> - Jos tilaus ja tilaustiedot ovat eri entiteettejä, yhdistä ne ennen mallin käyttöä. Malli ei toimi, jos käytössä on vain entiteetin tilaustunnus tai vastaanottotunnus.


## <a name="create-a-product-recommendation-prediction"></a>Tuotesuosituksen ennusteen luominen

1. Siirry Customer Insightsissa kohtaan **Älykäs toiminto** > **Ennusteet**.

1. Valitse **Tuotesuositusten malli (esiversio)** -ruudussa **Käytä tätä mallia**.
   > [!div class="mx-imgBorder"]
   > ![Tuotesuositusmalli-ruutu ja Käytä tätä mallia -painike.](media/product-recommendation-usethismodel.PNG "Tuotesuositusmalli-ruutu ja Käytä tätä mallia -painike")

1. Tutustu mallivaatimusten tietoihin. Jos sinulla on tarvittavat tiedot, valitse **Aloitus**.

### <a name="name-model"></a>Nimimalli

1. Anna mallille nimi, joka erottaa sen muista malleista.

1. Syötä tulosentiteetin nimi käyttämällä vain kirjaimia ja numeroita ilman välilyöntejä. Se on nimi, jota mallientiteetti käyttää. Valitse sitten **Seuraava**.

### <a name="define-product-recommendation-configuration"></a>Tuotesuositusmäärityksen määrittäminen

1. Määritä **Tuotteiden määrä**, jota haluat suositella asiakkaalle. Arvo riippuu siitä, miten toimitusmenetelmä täyttää tiedot. Jos voit suositella kolmea tuotetta, määritä tämä arvo vastaavasti.
   
   >[!TIP]
   > Voit valita **Tallenna ja sulje** milloin tahansa, jos haluat tallentaa ennusteen luonnokseksi. Ennusteluonnos on **Omat ennusteet** -välilehdessä.

1. Määritä, haluatko **ehdottaa tuotteita, jotka asiakkaat ovat äskettäin ostaneet**.

1. Jos olet määrittänyt, että äskettäin ostettuja tuotteita *ei* suositella, määritä arvoksi **Katso taaksepäin -ikkuna**. Tämä määritys määrittää aikavälin, jonka malli odottaa, ennen kuin suosittelee tuotetta käyttäjälle uudelleen. Ilmoita esimerkiksi, että asiakas ostaa kannettavan tietokoneen kahden vuoden välein. Tässä ikkunassa näkyy ostohistoria kahden viime vuoden ajalta. Jos nimike löytyy, se suodatetaan suosituksista.

1. Valitse **Seuraava**

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Lisää tiedot** **Asiakkaan tapahtumahistoria** -kohdassa ja valitse entiteetti, josta saadaan tapahtuma- tai ostohistorian tiedot [edellytyksissä](#prerequisites) kuvatulla tavalla.

1. Yhdistä semanttiset kentät määritteisiin ostohistoriaentiteetissä ja valitse **Seuraava**. Lisätietoja kentistä on [edellytyksissä](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Entiteettisuhteen määrittäminen.](media/product-recommendation-purchasehistorymapping.PNG "Ostohistoria-sivulla näkyvät semanttiset määritteet, jotka on yhdistetty valitun ostohistoriaentiteetin kenttiin")

1. Jos alla olevia kenttiä ei ole täytetty, määritä ostohistoriaentiteetin suhde *asiakasentiteettiin*.
    1. Valitse **Ostohistorian entiteetti**.
    1. Valitse **kenttä**, joka määrittää asiakkaan ostohistorian entiteetissä. Sen on liityttävä ensisijaisen asiakkaan tunnukseen *asiakasentiteetissä*.
    1. Valitse **Asiakasentiteetti**, joka vastaa ensisijaista asiakasentiteettiä.
    1. Anna suhdetta kuvaava nimi.
       > [!div class="mx-imgBorder"]
       > ![Ostohistoriasivu, jossa näkyy suhteen luonti asiakkaaseen](media/model-purchase-join.png "Ostohistoriasivu, jossa näkyy suhteen luominen asiakkaaseen")

1. Valitse **Tallenna**.

1. Valitse **Seuraava**.

### <a name="configure-product-filters"></a>Tuotesuodattimien määritys

Joskus vain tietyt tuotteet ovat ennusteen tyypille sopivia tai hyödyllisiä. Tuotesuodattimien avulla voit määrittää asiakkaille suositeltujen tuotteiden alijoukon, joilla on tietyt ominaisuudet. Malli käyttää kaikkia käytettävissä olevia tuotteita kaavojen oppimiseen, mutta käyttää vain tuotteita, jotka vastaavat tuotesuodattimen tuloksia.

1. Lisää **Tuotetietojen lisääminen** -vaiheessa tuoteluetteloon kunkin tuotteen tiedot. Yhdistä tarvittavat tiedot ja valitse **Seuraava**.

3. Valitse **Tuotesuodattimet**-vaiheessa jokin seuraavista vaihtoehdoista.

   * **Ei suodattimia**: käytä kaikkia tuotesuosituksen ennusteen tuotteita.

   * **Määritä tietyt tuotesuodattimet**: käytä tiettyjä tuotteita tuotesuosituksen ennusteessa.

1. Valitse **Seuraava**.

1. Jos päätät määrittää tuotesuodattimen, se on määritettävä nyt. Valitse **Tuoteluettelon määritteet** -ruudussa *tuoteluetteloentiteetin* määritteet, jotka haluat sisällyttää suodattimeen.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Sivuruutu, joka näyttää tuoteluettelon entiteetin määritteet tuotesuodattimia varten.":::

1. Valitse, käytetäänkö tuotesuodattimessa **ja**- tai **tai**-yhdistimiä yhdistämään loogisesti määritteiden valinnan tuoteluettelosta.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Tuotesuodattimien esimerkkimääritys yhdistettynä loogisiin JA-yhdistimiin.":::

1. Valitse **Seuraava**.

### <a name="set-update-schedule-and-review-configuration"></a>Päivitysaikataulun määrittäminen ja määritysten tarkistaminen

1. Määritä mallin uudelleenkouluttamistiheys. Tämä asetus on tärkeä ennusteiden tarkkuuden päivittämiseksi, kun Customer Insightsiin tuodaan uusia tietoja. Useimmat yritykset voivat uudelleenkouluttaa kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

1. Tarkista määritys. Voit palata mihin tahansa ennustemäärityksen osaan valitsemalla **Muokkaa** annetun arvon kohdassa. Voit myös valita määritysvaiheen edistymisen ilmaisimesta.

1. Jos kaikki arvot on määritetty oikein, aloita ennusteprosessi valitsemalla **Tallenna ja suorita**. **Omat ennusteet** -välilehdessä voit tarkastella ennusteiden tilaa. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

## <a name="review-a-prediction-status-and-results"></a>Ennusteen tilan ja tulosten tarkasteleminen

1. Siirry **Omat ennusteet** -välilehteen kohdassa **Älykäs toiminto** > **Ennusteet**.
   > [!div class="mx-imgBorder"]
   > ![Omat ennusteet -sivun tarkasteleminen.](media/product-recommendation-mypredictions.PNG "Omat ennusteet -sivun tarkasteleminen")

1. Valitse ennuste, jota haluat tarkastella.
   - **Ennusteen nimi:** Ennusteelle luomisen yhteydessä annettu nimi.
   - **Ennustetyyppi:** Ennusteessa käytetyn mallin tyyppi.
   - **Tulosentiteetti:** Sen entiteetin nimi, johon ennusteen tulos tallennetaan. Tämänniminen entiteetti löytyy kohdasta **Tiedot** > **Entiteetit**.    
      Tulosentiteetin *pistemäärä* on suosituksen kvantitatiivinen mittari. Malli suosittelee tuotteita, joiden pistemäärä on suurempi kuin tuotteita, joiden pistemäärä on pienempi.
   - **Ennustettu kenttä**: Tähän kenttään täytetään vain tietyntyyppiset ennusteet, eikä sitä käytetä tuotesuositusten ennusteessa.
   - **Tila:** Ennusteen suoritumisen nykyinen tila.
        - **Jonossa:** Ennuste odottaa parhaillaan muiden prosessien suorittamista.
        - **Päivitys:** Ennusteessa suoritetaan parhaillaan käsittelyn tulosvaihetta. Sen avulla saadaan tulokset, jotka siirretään tulosentiteettiin.
        - **Epäonnistui:** Ennuste on epäonnistunut. Jos haluat lisätietoja, valitse **Lokit**.
        - **Onnistui:** Ennuste on onnistunut. Valitse allekkaisten pisteiden alla oleva **Tarkastele**-kohta, jos haluat tarkastella ennustetta.
   - **Muokattu:** Ennusteen määrityksen muutospäivämäärä.
   - **Viimeinen päivitys:** Päivämäärä, jona ennuste päivitti tulokset tulosentiteettiin.

1. Valitse sen ennusteen vieressä olevat allekkaiset pisteet, jonka tuloksia haluat tarkastella, ja valitse **Näytä**.
   > [!div class="mx-imgBorder"]
   > ![Tarkastele allekkaisten pisteiden valikon vaihtoehtoja, esimerkiksi muokkausta, päivittämistä, tarkastelemista, lokeja ja poistamista.](media/product-recommendation-verticalellipses.PNG "Tarkastele allekkaisten pisteiden valikon vaihtoehtoja, esimerkiksi muokkausta, päivittämistä, tarkastelemista, lokeja ja poistamista")

1. Tulossivulla on viisi ensisijaista tieto-osaa:
    1. **Opetusmallin suorituskyky:** A, B ja C ovat mahdollisia pistemääriä. Tämä pistemäärä osoittaa ennusteen suorituskyvyn. Sen avulla voit tehdä päätöksen tulosentiteettiin tallennettujen tulosten käyttämisestä.
        - Pistemäärät määritetään seuraavien sääntöjen perusteella:
            - **A** Mallia pidetään **A**-laatuna, jos Menestys @ K -mittarin arvo on vähintään 10 % enemmän kuin perustaso. 
            - **B** Mallia pidetään **B**-laatuna, jos Menestys @ K -mittarin arvo on 0–10 % enemmän kuin perustaso.
            - **C** Mallia pidetään **C**-laatuna, jos Menestys @ K -mittarin arvo on vähemmän kuin perustaso.
               
               > [!div class="mx-imgBorder"]
               > ![Tarkastele mallin suorituskyvyn tulosta.](media/product-recommendation-modelperformance.PNG "Tarkastele mallin suorituskyvyn tulosta")
            - **Perustaso**: Malli käyttää kaikkien asiakkaiden ostomäärien mukaisia suositelluimpia tuotteita ja mallin määrittämiä opittuja sääntöjä asiakkaiden suositusjoukon luomisessa. Ennusteita vertaillaan sen jälkeen myydyimpiin tuotteisiin tuotteen ostaneiden asiakkaiden määrän mukaan laskettuna. Jos asiakkaan suositelluissa tuotteissa on vähintään yksi tuote, joka on myös myydyimpien tuotteiden joukossa, heitä pidetään perustason asiakkaina. Jos 10 asiakasta yhteensä 100 asiakkaasta on suositellut ostettua tuotetta, perustaso on 10 %.
            - **Menestys @ K**: Suositukset luodaan kaikille asiakkaille käyttämällä tapahtumien ajanjakson tarkistusjoukkoa. Tämän jälkeen niitä verrataan tapahtumien tarkistusjoukkoihin. Esimerkiksi 12 kuukauden jakson aikana kuukausi 12 voidaan jättää pois tietojen tarkistusjoukoksi. Jos malli ennustaa vähintään yhden oston kuukauden 12 aikana edellisten 11 kuukauden tietojen perusteella, asiakas kasvattaa Menestys @ K -mittarin arvoa.
    
    1. **Useimmin ehdotetut tuotteet (laskurin kanssa)**: viisi yleisintä asiakkaille ennustettua tuotetta.
       > [!div class="mx-imgBorder"]
       > ![Kaavio, jossa on 5 eniten suositeltua tuotetta.](media/product-recommendation-topproducts.PNG "Kaavio, jossa on 5 eniten suositeltua tuotetta")
    
    1. **Tärkeimmät suositustekijät:** malli antaa tuotesuosituksia asiakkaiden tapahtumahistorian perusteella. Se oppii aiemmin tehtyihin ostoihin perustuvia malleja ja löytää samankaltaisuuksia asiakkaiden ja tuotteiden välillä. Näiden samankaltaisuuksien avulla luodaan tuotesuosituksia.
    Seuraavassa on tekijöitä, jotka voivat vaikuttaa mallin tuottamaan tuotesuositukseen. 
        - **Aiemmat tapahtumat**: malli käyttää aiempien ostojen malleja tuotesuositusten luomiseen. Malli voi esimerkiksi suositella _Surfacen Arc Mouse_ -hiirtä, jos joku on äskettäin ostanut _Surface Book 3:n_ ja _Surface-kynän_. Malli on oppinut, että monet asiakkaat olivat hankkineet _Surface Arc Mousen_, kun ovat ostaneet _Surface Book 3:n_ ja _Surface-kynän_.
        - **Asiakkaiden samankaltaisuus**: Muut asiakkaat, joilla on samanlaiset ostomallit, ovat hankkineet suositellun tuotteen. Esimerkiksi Johnille suositellaan _Surface Headphones 2_ -kuulokkeita, koska Jennifer ja Brad ostivat hiljattain _Surface Headphones 2_ -kuulokkeet. Malli olettaa, että John muistuttaa Jenniferiä ja Bradiä, koska heillä on ollut samanlaisia ostomalleja.
        - **Tuotteen samankaltaisuus**: Suositeltava tuote muistuttaa muita tuotteita, jotka asiakas oli aiemmin ostanut. Malli katsoo, että kaksi tuotetta on samanlaisia, jos ne on ostettu yhdessä tai samankaltaisten asiakkaiden toimesta. esimerkiksi joku saa suosituksen _USB-tallennusasemasta_, koska he aiemmin ostivat _USB-C – USB -adapterin_ ja malli olettaa historiallisten ostokaavojen perusteella, että _USB-tallennusasema_ on samankaltainen kuin _USB-C – USB -adapteri_.

        Yksi tai useampi näistä tekijöistä vaikuttaa kaikkiin tuotesuosituksiin. Niiden suositusten prosenttiosuus, joissa jokaisella tekijällä on ollut rooli, visualisoidaan kaaviossa. Seuraavassa esimerkissä aiemmat tapahtumat vaikuttavat 100 prosenttiin suosituksista, asiakkaan samankaltaisuus 60 prosenttiin suosituksista ja tuotteiden samankaltaisuus 22 prosenttiin suosituksista. Vie osoitin kaavion palkkien päälle nähdäksesi, minkä tarkan prosenttiosuuden vaikuttavat tekijät ovat vaikuttaneet.

        > [!div class="mx-imgBorder"]
        > ![Tärkeimmät suosittelukriteerit.](media/product-recommendation-keyrecommendationfactors.png "Tärkeimmät suositustekijät, joita malli oppi tuotesuositusten tuottamiseksi")
       
     
   1. **Tietotilastot**: Antaa yleiskuvan käytettävän mallin tapahtumien, asiakkaiden ja tuotteiden lukumäärästä. Se perustuu syötetietoihin, joita käytettiin kaavojen oppimiseen ja tuotesuositusten luomiseen.

      > [!div class="mx-imgBorder"]
      > ![Tietotilastot.](media/product-recommendation-datastatistics.png "Mallin käyttämät syöte-/tulostietojen tilastot, joita käytetään mallissa kaavojen oppimiseen")

      Tässä osassa on esitetty tilastot arvopisteistä, joita malli käyttää kaavojen opettelemiseen ja tuotesuositusten luomiseen. Mallimäärityksessä määritetty suodatus koskee mallin luomaa tulosta. Malli käyttää kuitenkin kaikkia käytettävissä olevia tietoja kaavojen oppimiseen. Jos siis käytät tuotesuodatusta mallimäärityksessä, tässä osassa näkyy mallin analysoimien tuotteiden kokonaismäärä mallien oppimiseksi, mikä voi poiketa määritettyjä suodatusehtoja vastaavien tuotteiden lukumäärästä.

   1. **Erittäin luotettavat tuotesuositukset:** Asiakkaille annettujen suositusten esimerkki tuotteista, joita malli olettaa asiakkaan ostavan.    
      Jos tuoteluettelo on lisätty, tuotetunnukset korvataan tuotenimillä. Tuotteiden nimet antavat käyttökelpoisempia ja intuitiivisempia tietoja ennusteista.
       > [!div class="mx-imgBorder"]
       > ![Luettelo, jossa näkyvät erittäin luotettavat suositukset valitulle yksittäisten asiakkaiden joukolle.](media/product-recommendation-highconfidence.PNG "Luettelo, jossa näkyvät erittäin luotettavat suositukset valitulle yksittäisten asiakkaiden joukolle")

## <a name="manage-predictions"></a>Hallitse ennusteita

Voit optimoida, tehdä vianmäärityksen, päivittää tai poistaa ennusteita. Käytettävyysraportissa on tietoja siitä, miten tehdä ennusteista nopeampia ja luotettavampia. Lisätietoja on kohdassa [Ennusteiden hallinta](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
