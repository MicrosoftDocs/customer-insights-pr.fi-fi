---
title: Tietojen yhtenäistäminen entiteettien vastaavuuden avulla
description: Yhtenäisten asiakasprofiilien luominen entiteettien vastaavuuden avulla.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405620"
---
# <a name="match-entities"></a>Entiteettien vastaavuus

Kun olet tehnyt yhdistämisvaiheen, voit täsmäyttää entiteetit. Täsmäytysvaihe määrittää, miten tietojoukot yhdistetään yhdistetyksi asiakasprofiilin tietojoukoksi. Täsmäytysvaihe edellyttää vähintään [kahta yhdistettyä entiteettiä](map-entities.md).

## <a name="specify-the-match-order"></a>Määritä täsmäytysjärjestys.

Siirry kohtaan **Yhdistä** > **Täsmäytä** ja valitse **Määritä järjestys**. Täsmäytysvaihe alkaa.

Kukin täsmäytys yhdistää kaksi entiteettiä tai useampia entiteettejä yhdeksi entiteetiksi. Samalla säilytetään kukin yksittäinen asiakastietue. Seuraavassa esimerkissä valitaan seuraavat kolme entiteettiä: **ContactCSV: TestData** **ensisijaiseksi** entiteetiksi, **WebAccountCSV: TestData** **entiteetiksi 2** ja **CallRecordSmall: TestData** **entiteetiksi 3**. Valintojen alla olevassa kaaviossa on kuva siitä, miten täsmäytysjärjestys suoritetaan.

> [!div class="mx-imgBorder"]
> ![Muokkaa tietojen täsmäytysjärjestystä](media/configure-data-match-order-edit-page.png "Muokkaa tietojen täsmäytysjärjestystä")
  
**Ensisijainen** entiteetti täsmäytetään **entiteetin 2** kanssa. Tietojoukko, joka saadaan ensimmäisen täsmäytyksen tuloksena, täsmäytetään **entiteetin 3** kanssa.
Tässä esimerkissä valittiin vain kaksi täsmäytystä. Järjestelmä tukee kuitenkin useampia täsmäytyksiä.

> [!IMPORTANT]
> Entiteetti, jonka valitset **ensisijaiseksi** entiteetiksi, toimii yhdistetyn päätietojoukon perustana. Täsmäytysvaiheen aikana valitut lisäentiteetit lisätään tähän entiteettiin. Tämä ei kuitenkaan tarkoita sitä, että yhdistetty entiteetti sisältää *kaikki* tähän entiteettiin sisältyvät tiedot.
>
> Seuraavat kaksi seikkaa auttavat entiteettihierarkian valinnassa:
>
> - Missä entiteetissä on täydellisimmät ja luotettavimmat asiakastiedot?
> - Onko juuri määrittämälläsi entiteetillä määritteitä, jotka on jaettu muiden entiteettien kanssa (esimerkiksi nimi, puhelinnumero tai sähköpostiosoite)? Jos näin ei ole, valitse seuraavaksi luotettavin entiteetti.

Valitse **Valmis**, kun haluat tallentaa täsmäytysjärjestyksen.

## <a name="define-rules-for-your-first-match-pair"></a>Ensimmäisen täsmäytysparin sääntöjen määrittäminen

Kun olet määrittänyt täsmäytysjärjestyksen, määritetyt täsmäytykset näkyvät **Täsmäytys**-sivulla. Näytön yläreunassa olevat ruudut ovat tyhjiä, kunnes olet suorittanut täsmäytysjärjestyksen.

> [!div class="mx-imgBorder"]
> ![Määritä säännöt](media/configure-data-match-need-rules.png "Määritä säännöt")

**Tarvitsee säännöt** -varoitus tarkoittaa sitä, että täsmäytysparille ei ole määritetty täsmäytyssääntöä. Täsmäytyssäännöt määrittävät logiikan, jonka avulla määritetty entiteettipari täsmäytetään.

1. Jos haluat määrittää ensimmäisen säännön, avaa **Säännön määritys** -ruutu valitsemalla vastaava täsmäytysrivi täsmäytystaulukossa (1) ja valitsemalla sitten **Luo uusi sääntö** (2).

   > [!div class="mx-imgBorder"]
   > ![Luo uusi sääntö](media/configure-data-match-new-rule2.png "Luo uusi sääntö")

2. Määritä **Muokkaa sääntöä** -ruudussa säännön ehdot. Kutakin ehtoa vastaa kaksi riviä, jotka sisältävät pakolliset valinnat.

   > [!div class="mx-imgBorder"]
   > ![Uusi sääntö -ruutu](media/configure-data-match-new-rule-condition.png "Uusi sääntö -ruutu")

   Entiteetti/kenttä (ensimmäinen) - määrite, jota käytetään ensimmäisen täsmäytysparientiteetin täsmäytyksessä. Esimerkkejä ovat puhelinnumero ja sähköpostiosoite. Valitse määrite, joka on todennäköisesti asiakkaan yksilöllinen määrite.

   > [!TIP]
   > Vältä täsmäyttämistä aktiviteettityyppisten määritteiden perusteella. Eli jos määrite näyttää olevan aktiviteetti, sitä ei ehkä kannata käyttää täsmäytyksen ehtona.  

   Entiteetti/kenttä (toinen) - määrite, jota käytetään toisen täsmäytysparientiteetin täsmäytyksessä.

   Normalisoi - **normalisointimenetelmä**: Valituille määritteille on käytettävissä useita normalisointivaihtoehtoja. Esimerkiksi välimerkkien tai välilyöntien poistaminen

   Organisaation nimen normalisoimista (esikatselua) varten voit valita myös **Tyyppi (puhelin, nimi, organisaatio)** -kohdan

   > [!div class="mx-imgBorder"]
   > ![Normalisointi - yritysten välinen](media/match-normalization-b2b.png "Normalisointi - yritysten välinen")

   Tarkkuustaso - tässä ehdossa käytettävän tarkkuuden taso. Täsmäytysehdon tarkkuustason määrityksessä voi käyttää seuraavia kahta tyyppiä: **Perus** ja **Mukautettu**.  
   - Perus: Sisältää neljä vaihtoehtoa: matala, keskitaso, korkea ja tarkka. Valitse **Tarkka** vain, jos haluat täsmäyttää tietueita, joiden täsmäävyys on 100 prosenttia. Valitse jokin toinen taso, jos haluat täsmäyttää tietueita, jotka eivät ole täysin identtisiä.
   - Mukautettu: Määritä niille tietueille mukautettu prosenttiosuus liukusäätimellä, jotka on täsmäytettävä, tai anna arvo **Mukautettu**-kenttään. Järjestelmä täsmäyttää vain tietueet, jotka läpäisevät tämän raja-arvon yhdistettyinä täsmäytyspareina. Liukusäätimen arvot ovat välillä 0–1. Eli 0,64 tarkoittaa 64 prosenttia.

3. Tallenna sääntö valitsemalla **Valmis**.

### <a name="add-multiple-conditions"></a>Useiden ehtojen lisääminen

Jos haluat täsmäyttää entiteetit vain, jos useat ehdot täyttyvät, lisää ehtoja, jotka on linkitetty JA-operaattorin avulla.

1. Valitse **Muokkaa sääntöä** -ruudussa **Lisää ehto**. Voit myös poistaa ehtoja valitsemalla olemassa olevan ehdon vieressä olevan Poista-painikkeen.

2. Tallenna sääntö valitsemalla **Valmis**.

## <a name="add-multiple-rules"></a>Useiden sääntöjen lisääminen

Kukin ehto koskee yhtä määriteparia. Sääntö taas edustaa ehtojoukkoja. Jos haluat, että entiteetit täsmäytetään eri määritejoukkojen avulla, voit lisätä sääntöjä.

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Yhtenäistä** > **Täsmäytä**.

2. Valitse päivitettävä entiteetti ja valitse sitten **Lisää säännöt**.

3. Noudata kohdassa [Ensimmäisen täsmäytysparin sääntöjen määrittäminen](#define-rules-for-your-first-match-pair) olevia ohjeita.

> [!NOTE]
> Sääntöjen järjestys on tärkeä. Täsmäytysalgoritmi yrittää täsmäyttää ensimmäisen säännön perusteella ja jatkaa toiseen sääntöön vain, jos ensimmäisen säännön avulla ei löytynyt vastaavuuksia.

## <a name="define-deduplication-on-a-match-entity"></a>Vastaavan entiteetin kaksoiskappaleiden poistaminen

Sen lisäksi että entiteettien väliset vastaavuussäännöt määritetään edellä kuvatuilla tavoilla, myös kaksoiskappaleiden poistosäännöt voidaan määrittää. *Kaksoiskappaleiden poisto* on prosessi. Se määrittää tietueiden kaksoiskappaleet, yhdistää ne yhdeksi tietueeksi ja linkittää kaikki lähdetietueet kyseiseen yhdistettyyn tietueeseen käyttämällä vaihtoehtoisia tunnuksia yhdistettyyn tietueeseen.

Kun kaksoiskappaleiden poistotietue on määritetty, kyseistä tietuetta käytetään entiteettien välisessä vastaavuusprosessissa. Kaksoiskappaleiden poisto toteutetaan entiteettitasolla, ja sitä voidaan käyttää jokaisessa vastaavuusprosessissa käytetyssä entiteetissä.

### <a name="add-deduplication-rules"></a>Kaksoiskappaleiden poistosääntöjen lisääminen

1. Valitse käyttäjäryhmän merkityksellisissä tiedoissa **Tiedot** > **Yhtenäistä** > **Täsmäytä**.

1. Valitse **Yhdistetyt kaksoiskappaleet** -osassa **Määritä entiteetit**.

1. Valitse **Yhdistä asetukset** -osassa entiteetit, joissa käytetään kaksoiskappaleiden poistoa.

1. Määritä, miten kaksoiskappaletietueet yhdistetään, ja valitse jokin kolmesta yhdistämisvaihtoehdosta:
   - *Useimmat täytetyt*: Määrittää voittavaksi tietueeksi tietueen, jossa on eniten täytettyjä tietueita. Tämä on yhdistämisen oletusasetus.
   - *Uusin*: Määrittää voittajatietueeksi uusimman tietueen. Viimeaikaisuuden määrittämiseen tarvitaan päivämäärä- tai numerokenttä.
   - *Vähiten viimeaikaiset*: Määrittää voittajatietueeksi vähiten viimeaikaisimman tietueen. Viimeaikaisuuden määrittämiseen tarvitaan päivämäärä- tai numerokenttä.
 
   > [!div class="mx-imgBorder"]
   > ![Kaksoiskappaleiden poistosääntöjen vaihe 1](media/match-selfconflation.png "Kaksoiskappaleiden poistosääntöjen vaihe 1")
 
1. Kun entiteetit on valittu ja niiden yhdistämisasetus on määritetty, määritä kaksoiskappaleiden poistosäännöt entiteettitasoalla valitsemalla **Luo uusi sääntö**.
   - **Valitse kenttä** sisältää luettelon kaikista sen entiteetin käytettävissä olevista kentistä, jonka lähdetietojen kaksoiskappaleet halutaan poistaa.
   - Määritä normalisointi- ja tarkkuusasetukset samoin kuin ne määritetään entiteettien välisessä vastaavuudessa.
   - Lisäehtoja voi määrittää valitsemalla **Lisää ehto**.
 
   > [!div class="mx-imgBorder"]
   > ![Kaksoiskappaleiden poistosääntöjen vaihe 2](media/match-selfconflation-rules.png "Kaksoiskappaleiden poistosääntöjen vaihe 2")

  Voit luoda entiteetille useita kaksoiskappaleiden poistosääntöjä. 

1. Vastaavuusprosessin suorittaminen ryhmittelee nyt tietueet kaksoiskappaleiden poistosäännöissä määritettyjen ehtojen perusteella. Kun tietueet on ryhmitelty, voittajatietue määritetään käyttämällä vastaavuuskäytäntöä.

1. Voittajatietue siirretään sitten entiteettien väliseen vastaavuuden etsimiseen.

1. Mahdolliset mukautetut aina vastattava- ja ei koskaan vastaa -säännöille ohittavat kaksoiskappaleiden poistosäännöt. Jos kaksoiskappaleiden poistosääntö määrittää vastaavia tietueita ja mukautetuksi vastaavuussääntönä on, etteivät tietueet saa koskaan vastata toisiin, näille kahdelle tietueelle ei etsitä vastaavuutta.

1. Kun vastaavuusprosessi on suoritettu, kaksoiskappaleiden poistotilastot ovat näkyvissä.
   
> [!NOTE]
> Kaksoiskappaleiden poistosääntöjen määrittäminen ei ole pakollista. Jos kyseisiä sääntöjä ei ole määritetty, järjestelmän määrittämiä sääntöjä käytetään. Ne kutistavat kaikki tietueet, jotka jakavat saman arvoyhdistelmän (tarkka vastine) perusavaimesta ja vastaavuussääntöjen kentät, yhdeksi tietueeksi ennen entiteettitietojen siirtämistä entiteettien väliseen vastaavuuksien etsimiseen. Tämä parantaa suorituskykyä ja järjestelmän toimintaa.

## <a name="run-your-match-order"></a>Täsmäytysjärjestyksen suorittaminen

Kun vastaavuussäännöt, mukaan lukien entiteettien välinen vastaavuuksien etsiminen ja kaksoiskappaleiden poistosäännöt, on määritetty, voit suorittaa täsmäytysjärjestyksen. Valitse **Täsmäytys**-sivulla **Suorita**, kun haluat aloittaa prosessin. Täsmäytysalgoritmin suorittamiseen voi mennä aikaa. Ominaisuuksia voi muuttaa **Täsmäytys**-sivulla vasta, kun täsmäytysprosessi on valmis. Löydät yhdistetyn asiakasprofiilientiteetin, joka luotiin **Entiteetit**-sivulla. Yhdistettyä asiakasentiteettiä kutsutaan nimellä **ConflationMatchPairs : CustomerInsights**.

Jos haluat tehdä lisää muutoksia ja suorittaa vaiheen uudelleen, voit peruuttaa meneillään olevan vastaavuuden. Valitse **Pävitetään...**-teksti ja valitse sitten **Peruuta työ** näkyviin tulevan reunaruudun alaosasta.

Kun vastaavuusprosessi on valmis, **Päivitetään...** teksti muuttuu tekstiksi **Onnistui** ja voit käyttää kaikkia sivun toimintoja uudelleen.

Ensimmäisen täsmäytysprosessin tuloksena luodaan yhdistetty pääentiteetti. Kaikkien seuraavien täsmäytysten suoritusten tuloksena on tämän entiteetin laajennus.

> [!TIP]
> Tehtävillä ja prosesseilla on [kuusi tilatyyppiä](system.md#status-types). Lisäksi useimmat prosessit [riippuvat muista loppupään prosesseista](system.md#refresh-policies). Voit valita prosessin tilan, jos haluat tarkastella koko työn edistymistä koskevia tietoja. Kun työn jossakin tehtävissä on valittu **Näytä tiedot**, saat lisätietoja: käsittelyajan, viimeisimmän käsittelypäivämäärän sekä kaikki tehtävään liitetyt virheet ja varoitukset.

## <a name="review-and-validate-your-matches"></a>Täsmäytysten tarkistaminen ja vahvistaminen

Arvioi täsmäytysparien laatu ja tarkenna sitä seuraavasti:

- **Täsmäytys**-sivulla on kaksi ruutua, joissa on alkuperäiset tiedot.

  - **Yksittäiset asiakkaat**: Näyttää järjestelmän määrittämien yksittäisten profiilien määrän.
  - **Täsmäytetyt tietueet**: Näyttää kaikkien täsmäytysparien täsmäytysten määrän.

- **Täsmäytysjärjestys**-taulukossa voi käyttää kunkin täsmäytysparin tuloksia vertailemalla niiden tietueiden määrää, jotka saatiin tästä täsmäytysparientiteetin ja onnistuneesti täsmäytettyjen tietueiden prosenttiosuuden vertailusta.

- Entiteetin **Säännöt**-osassa **Täsmäytysjärjestys**-taulukossa on sääntötasolla onnistuneesti täsmäytettyjen tietueiden prosenttiosuus. Kun valitset säännön vieressä olevan taulukkosymbolin, voit tarkastella kaikkia näitä sääntöjä sääntötasolla. Tietueiden osajoukko kannattaa tarkistaa ja näin varmistaa, että tietueet on täsmäytetty oikein.

- Kokeilemalla ehdoille erilaisia tarkkuusrajoja voit määrittää optimaalisen arvon.

  1. Valitse sen täsmäytysparin kolme pistettä (...), jota haluat kokeilla, ja valitse sitten **Muokkaa**.

  2. Valitse ehto, jota haluat kokeilla. Jokaista ehtoa edustaa yksi rivi **Täsmäytyssääntö**-ruudussa.

  3. **Ehtojen esikatselu** -sivun näkymän sisältö riippuu ehdolle valitusta tarkkuustasosta. Etsi valitun ehdon täsmättyjen ja ei-täsmättyjen tietueiden määrä.

     Tutustu eri raja-arvotasojen vaikutuksiin. Voit verrata eri raja-arvotasoilla täsmättävien tietueiden määrää ja tarkastella kunkin vaihtoehdon tietueita. Valitse kaikki ruudut ja tarkista taulukko-osan tiedot.

## <a name="optimize-your-matches"></a>Täsmäytysten optimoiminen

Paranna laatua määrittämällä joitakin täsmäytysparametreja uudelleen seuraavasti:

- **Vaihda täsmäytysjärjestystä** valitsemalla **Muokkaa** ja muuttamalla täsmäytysjärjestyksen kenttiä.

  > [!div class="mx-imgBorder"]
  > ![Muokkaa tietojen täsmäytysjärjestystä](media/configure-data-match-order-edit.png "Muokkaa tietojen täsmäytysjärjestystä")

- **Muuta sääntöjen järjestystä**, jos määritit useita sääntöjä. Voit järjestää täsmäytyssäännöt uudelleen valitsemalla **Siirrä ylös**- ja **Siirrä alas** -vaihtoehdon täsmäytyssääntöjen ruudukossa.

  > [!div class="mx-imgBorder"]
  > ![Muuta sääntöjärjestystä](media/configure-data-change-rule-order.png "Muuta sääntöjärjestystä")

- **Monista säännöt**, jos olet määrittänyt täsmäytyssäännön ja haluat luoda samanlaisen säännön, jota muokkaat. Voit tehdä niin valitsemalla **Monista**.

  > [!div class="mx-imgBorder"]
  > ![Monista sääntö](media/configure-data-duplicate-rule.png "Monista sääntö")

- **Muokkaa sääntöjä** valitsemalla **Muokkaa**-symboli. Voit ottaa käyttöön myös seuraavat muutokset:

  - Muuta ehdon määritteitä: Valitse uudet määritteet tietyltä ehtoriviltä.
  - Muuta ehdon raja-arvoa: Muokkaa tarkkuuden liukusäädintä.
  - Muuta ehdon normalisointimenetelmää: Päivitä normalisointimenetelmä.

## <a name="specify-your-custom-match-records"></a>Mukautettujen täsmäytystietueiden määrittäminen

Voit määrittää ehdot, joita tiettyjen tietueiden on aina vastattava tai joita ne eivät voi koskaan vastata. Nämä säännöt voidaan joukkoladata täsmäytysprosessissa.

1. Valitse **Mukauta täsmäytys** -vaihtoehto **Täsmäytysjärjestys**-näytössä.

   > [!div class="mx-imgBorder"]
   > ![Luo mukautettu täsmäytys](media/custom-match-create.png "Luo mukautettu täsmäytys")

2. Jos sinulla ei ole ladattuja entiteettejä, näkyvissä on uusi **Mukautettu täsmäytys** -valintaikkuna, johon on annettava tietoja. Jos olet antanut nämä tiedot aiemmin, siirry vaiheeseen 8.

   > [!div class="mx-imgBorder"]
   > ![Uusi mukautettu täsmäytys -valintaikkuna](media/custom-match-new-dialog-box.png "Uusi mukautettu täsmäytys -valintaikkuna")

3. Valitse **Täytä malli**, jos haluat hakea mallitiedoston, joka voi määrittää entiteetit ja niiden tietueet, joiden on aina vastattava toisiaan tai jotka eivät koskaan saa vastata toisiaan. Täytä vastaa aina- ja ei vastaa koskaan -tietueet erikseen kahdessa eri tiedostossa.

4. Malli sisältää kenttiä, jotka määrittävät entiteetin ja entiteetin ensisijaisen avaimen arvot. Niitä käytetään mukautetussa täsmäytyksessä. Jos haluat esimerkiksi, että myyntientiteetin ensisijainen avain 12345 vastaa aina yhteyshenkilöentiteetin ensisijaista avainta 34567, määritä seuraavat arvot:
    - Entiteetti1: Myynti
    - Entiteetti1Avain: 12345
    - Entiteetti2: Yhteyshenkilö
    - Entiteetti2avain: 34567

   Sama mallitiedosto voi määrittää mukautetut täsmäytystietueet useista entiteeteistä.

5. Kun olet lisännyt kaikki haluamasi korvaukset, tallenna mallitiedosto.

6.Valitse **Tiedot** > **Tietolähteet** ja käsittele mallitiedostot uusina entiteetteinä. Kun ne on käsitelty, voit käyttää niitä täsmäytyskokoonpanon määrityksessä.

7. Kun tiedostot on ladattu ja entiteetit ovat käytettävissä, valitse uudelleen **Mukautettu täsmäytys** -vaihtoehto. Näkyviin tulee vaihtoehtoja, joilla määritetään sisällytettävät kohteet. Valitse vaaditut entiteetit avattavasta valikosta.

   > [!div class="mx-imgBorder"]
   > ![Mukautetun täsmäytyksen korvaukset](media/custom-match-overrides.png "Mukautetun täsmäytyksen korvaukset")

8. Valitse entiteetit, joita haluat käyttää **Täsmäytä aina**- ja **Älä täsmäytä koskaan** -kohdissa. Valitse sitten **Valmis**.

9. Valitse **Tallenna** juuri määritetyn mukautetun täsmäytyskokoonpanon **Täsmäytä**-sivulla.

10. Aloita täsmäytysprosessi valitsemalla **Suorita** **Täsmäytys**-sivulla. Mukautettu täsmäytyskokoonpano tulee voimaan. Järjestelmän täsmäyttämät säännöt korvataan määritetyllä kokoonpanolla.

11. Kun täsmäytys on tehty, voit tarkistaa **ConflationMatchPair**-entiteetin ja vahvistaa, että korvaukset on otettu käyttöön yhdistämisen täsmäytyksissä.

## <a name="next-step"></a>Seuraava vaihe

Kun olet suorittanyt vähintään yhden täsmäytysparin täsmäytysprosessin, voit ratkaista mahdolliset tietojen ristiriidat siirtymällä [**Täsmäytys**](merge-entities.md)-ohjeaiheeseen.
