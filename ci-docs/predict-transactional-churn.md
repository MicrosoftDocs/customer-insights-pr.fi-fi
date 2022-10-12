---
title: Tapahtumien vaihtuvuusennuste (sisältää video)
description: Sen riskin ennustaminen, että asiakas ei enää osta yrityksen tuotteita tai palveluja.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610508"
---
# <a name="predict-transaction-churn"></a>Tapahtuman vaihtuvuuden ennustaminen

Tapahtuman vaihtuvuusennuste auttaa ennustamaan, ostaako asiakas vielä tuotteita tai palveluja annetulla ajanjaksolla.

Liiketoiminnan tietämystä tarvitaan, jotta voidaan hahmottaa, mitä vaihtuvuus merkitsee yritykselle. Aikaperusteista vaihtuvuusmääritelmiä tuetaan, joten asiakkaan katsotaan vaihtuneen tietyn ostamattoman ajanjakson jälkeen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Yritystileihin perustuvissa ympäristöissä voidaan ennustaa tilin tapahtumien vaihtuvuus ja myös tilin ja toisen tietotason, kuten tuoteluokan, yhdistelmän vaihtuvuus. Esimerkiksi dimension lisääminen voi auttaa määrittämään, kuinka todennäköistä on, että asiakas Contoso lopettaa tuoteluokan toimistotarvikkeet ostamisen. Lisäksi yritystilien osalta voimme käyttää tekoälyä muodostamaan luettelon syistä, miksi on todennäköistä, että asiakas vaihtaa toissijaisen tason tietoluokkaan.

> [!TIP]
> Tapahtuman vaihtuvuusennustetta voi kokeilla käyttämällä näytetietoja: [Tapahtuman vaihtuvuusennusteen näyteopas](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>edellytykset

- Ainakin [osallistujan käyttöoikeudet](permissions.md).
- Vähintään 10 asiakasprofiilia, mielellään yli 1 000 yksilöllistä asiakasta.
- Asiakastunniste on yksilöivä asiakkaiden tapahtumia vastaava tunniste.
- Tapahtumatiedot vähintään kaksinkertaisena valittuun aikaikkunaan verrattuna, kuten 2–3 vuoden tapahtumahistoria. Mieluiten vähintään kaksi asiakaskohtaista tapahtumaa. Tapahtumahistorian on sisällettävä seuraavat tiedot:
  - **Tapahtuman tunnus**: oston tai tapahtuman yksilöivä tunnus.
  - **Tapahtuman päivämäärä**: oston tai tapahtuman päivämäärä.
  - **Tapahtuman arvo**: tapahtuman valuutta tai numeroarvoinen summa.
  - **Yksilöivä tuotetunnus**: ostetun tuotteen tai palvelun tunnus, jos tieto on rivitasolla.
  - **Tieto siitä, oliko tämä tapahtuma palautus**: Tosi/epätosi-kenttä ilmaisee, oliko tapahtuma palautus vai ei. Jos **Tapahtuman arvo** on negatiivinen, viittaus palautukseen johdetaan.
- Asiakasaktiviteetin tiedot:
  - Asiakastunniste on yksilöivä tunniste aktiviteettien yhdistämiseen asiakkaisiin.
  - **Perusavain:** Aktiviteetin yksilöivä tunnus. Esimerkiksi sivustovierailu tai käyttötietue, joka osoittaa, että asiakas kokeile tuotenäytettä.
  - **Aikaleima:** perusavaimen tunnistaman tapahtuman päivämäärä ja aika.
  - **Tapahtuma:** Käytettävän tapahtuman nimi. Esimerkiksi elintarvikemyymälän UserAction-kenttä voisi olla asiakkaan käyttämä kuponki.
  - **Tiedot:** Tapahtuman yksityiskohtaiset tiedot. Esimerkiksi elintarvikemyymälän CouponValue-kenttä voisi olla kupongin valuutta-arvo.
- Puuttuvia arvoja alle 20 % annetun entiteetin tietokentässä

Yritystenvälisissä tileissä asiakastiedot lisätään staattisiin määritteisin painottuen, sillä näin varmistetaan mallin paras suorituskyky:
- **CustomerID:** asiakkaan yksilöivä tunnus.
- **Luontipäivämäärä:** päivämäärä, jona asiakas alun perin lisättiin.
- **Osavaltio tai provinssi:** asiakkaan osavaltio- tai provinssisijainti.
- **Maa:** asiakkaan maa.
- **Toimiala:** asiakkaan toimialatyyppi. Esimerkiksi ”Toimiala”-niminen kenttä kahvipaahtimon kohdalla voi ilmaista, onko asiakas vähittäismyyjä.
- **Luokitus:** asiakkaan luokitteleminen yrityksen tarpeiden mukaan. Esimerkiksi ”ValueSegment”-niminen kenttä kahvipaahtimon kohdalla voi olla asiakkaan kokoon perustuva asiakastaso.

> [!NOTE]
> Jos asiakkaan ostoväli on suuri (muutaman viikon välein), on suositeltavaa valita lyhyempi ennusteen aikaväli ja vaihtuvuusmääritys. Jos ostoväli on alhainen (muutaman kuukauden välein tai kerran vuodessa), valitse pitkä ennusteen aikaväli ja vaihtuvuusmääritys.

## <a name="create-a-transaction-churn-prediction"></a>Tapahtuman vaihtuvuusennusteen luominen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Asiakasvaihtuvuusmalli**-ruudussa **Käytä mallia**.

1. Valitse vaihtuvuuden tyypiksi **Tapahtuma** ja valitse sitten **Aloita**.

1. **Anna tälle mallille** ja **tulosentiteetille nimi**, jotta ne voidaan erottaa muista malleista tai entiteeteistä.

1. Valitse **Seuraava**.

### <a name="define-customer-churn"></a>Määritä asiakasvaihtuma

Ennuste voidaan tallentaa koska tahansa luonnoksena valitsemalla **Tallenna luonnos**. Ennusteluonnos näkyy **Omat ennusteet** -välilehdessä.

1. Määritä **Ennusteikkuna**. Ennustetaan esimerkiksi asiakkaiden vaihtuvuusriski seuraavan 90 päivän aikana siten, että se on linjassa markkinoinnin säilyttämispyrkimysten kanssa. Vaihtuvuusriskin ennusteen pituus voi hankaloittaa vaihtuvuusriskiprofiilissa olevien seikkojen huomioon ottamista; tämä kuitenkin määräytyy liiketoimintakohtaisten tarpeiden mukaan.

1. Määritä vaihtuvuus **Vaihtuvuusmääritelmä** -kentässä antamalla päivien määrä. Jos asiakas ei ole esimerkiksi tehnyt ostoja 30 päivän aikana, heidän voidaan katsoa vaihtuneen liiketoiminnassa.

1. Valitse **Seuraava**.

### <a name="add-purchase-history"></a>Lisää ostohistoria

1. Valitse **Lisää tiedot** **Asiakkaan tapahtumahistoria** -kohdassa.

1. Valitse semanttinen aktiviteettityyppi **SalesOrder** tai **SalesOrderLine**, joka sisältää tapahtumahistorian tiedot. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty semanttisesti aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos semanttista yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Sivuruutu, jossa näkyy tiettyjen aktiviteettien valitseminen semanttisen tyypin perusteella.":::

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Lisää enemmän aktiviteetteja ja valitse **Seuraava**.

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Lisätietojen lisääminen (valinnainen)

1. Valitse **Lisää tiedot** **Asiakasaktiviteetit**-kohdassa.

1. Valitse käytettävät tiedot sisältävä semanttinen aktiviteettityyppi. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty semanttisesti aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos semanttista yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Valitse **Seuraava**

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

### <a name="select-prediction-level"></a>Valitse ennusteen taso

Useimmat ennusteet luodaan asiakastasolla. Joissakin tilanteissa ne eivät ehkä ole riittävän tarkkoja yrityksen tarpeisiin. Tämän ominaisuuden avulla voidaan ennustaa vaihtuvuus esimerkiksi asiakashaaran osalta koko asiakkaan asemesta.

1. Valitse **Valitse toissijaisen tason entiteetti**. Jos vaihtoehto ei ole käytettävissä, varmista, että olet suorittanut edellisen osan.

1. Laajenna entiteetit, joista haluat valita toissijaisen tason, tai käytä hakusuodatinruutua suodattaaksesi valitut vaihtoehdot.

1. Valitse määrite, jota haluat käyttää toissijaisena tasona, ja valitse sitten **Lisää**.

1. Valitse **Seuraava**.

> [!NOTE]
> Tässä osassa käytettävissä olevat entiteetit näkyvät, koska niillä on suhde edellisessä osassa valitsemaasi entiteettiin. Jos lisättävää entiteettiä ei näy, varmista, että sillä on kelvollinen suhde kohdassa **Suhteet**. Vain yksi yhteen- ja monta yhteen -suhteet kelpaavat tässä kokoonpanossa.

### <a name="add-additional-data-optional"></a>Lisätietojen lisääminen (valinnainen)

1. Valitse **Lisää tiedot** **Asiakasaktiviteetit**-kohdassa.

1. Valitse käytettävät tiedot sisältävä semanttinen aktiviteettityyppi. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty semanttisesti aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos semanttista yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Valitse **Seuraava**

1. Voit myös valita **Lisää tietoja** kohteelle **Asiakastiedot**.

1. Yhdistä semanttiset määritteet omien asiakastietojesi kenttiin tunnistettuiksi. Käytetyissä kentissä olevien tietojen ei tulisi muuttua usein, jotta mallin suorituskyky olisi paras. Esimerkiksi jos valitaan kenttä “Luokittelu”, joka on muuttunut joka kuukausi, ennusteessa käytetään vain viimeistä arvoa, vaikka asiakashistoriassa sama arvo ei soveltuisi asiakkaaseen, kun ennustemalleja tehdään.

1. Valitse **Seuraava**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Valinnaisen luettelon muodostaminen vertailuasiakkaista

Lisää luettelo yritysasiakkaistasi ja asiakkaistasi, joita haluat käyttää vertailukohtana. [Näiden vertailuasiakkaiden tiedot](#view-prediction-results) sisältävät niiden vaihtuvuuspisteytyksen ja ominaisuudet, jotka vaikuttivat eniten niiden vaihtuvuusennusteeseen.

1. Valitse **+ Lisää asiakkaita**.

1. Valitse asiakkaat, jotka toimivat vertailukohtina.

1. Valitse **Seuraava**.

---

### <a name="set-update-schedule"></a>Päivitysaikataulun määrittäminen

1. Valitse **Päivitä tiedot** -vaiheessa mallin uudelleenkoulutuksen tiheys. Tämä asetus on tärkeä ennusteiden tarkkuuden päivittämiseksi, kun Customer Insightsissa käsitellään uusia tietoja. Useimmat yritykset voivat kouluttaa uudelleen kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

### <a name="review-and-run-the-model-configuration"></a>Mallimäärityksen tarkasteleminen ja suorittaminen

**Tarkistus ja suoritus** -vaiheessa näkyy määritysten yhteenveto. Siinä on myös mahdollista tehdä muutoksia ennen ennusteen luontia.

1. Tee tarkistukset ja tarvittavat muutokset valitsemalla **Muokkaa**.

1. Jos olet tyytyväinen valintoihin, aloita mallin suorittaminen valitsemalla **Tallenna ja suorita**. Valitse **Valmis**. **Omat ennusteet** -välilehti on näkyvissä, kun ennustetta luodaan. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ennusteen tulosten näyttäminen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Omat ennusteet** -välilehdessä tarkasteltava ennuste.

# <a name="individual-consumers-b-to-c"></a>[Yksittäiset kuluttajat (kuluttajakauppa)](#tab/b2c)

Tulossivulla on seuraavat kolme ensisijaista tieto-osaa:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Yritystilit (yritysten väliset)](#tab/b2b)

Tulossivulla on seuraavat kolme ensisijaista tieto-osaa:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

**Vaikuttavan ominaisuuden analyysi** -tietosivulla on tietoja neljässä osassa:

- Tee oikeassa ruudussa valinta **Parhaat asiakkaat**- tai **Vertailuasiakkaat**-kohdassa. Molemmat luettelot on järjestetty laskevasti vaihtuvuuspisteiden mukaan riippumatta siitä, onko kyseessä asiakkaan pisteytys vai asiakkaiden ja toissijaisen tason, kuten tuoteluokan, yhteispisteytys. Valittu vaihtoehto määrittää tämän sivun sisällön.

  - **Parhaat asiakkaat**: Luettelo 10 asiakkaasta, joilla on suurin vaihtuvuusriski ja matalin vaihtuvuusriski asiakkaiden vaihtuvuuspisteiden perusteella.
  - **Vertailuasiakkaat**: Luettelo 10 asiakkaasta, jotka valittiin tätä mallia määritettäessä.

- **Vaihtuvuuspisteet:** Näyttää valitun kohteen vaihtuvuuspisteet oikeanpuoleisessa ruudussa.

- **Vaihtuvuusriskin jakautuminen:** Näyttää asiakkaiden vaihtuvuusriskin jakautumisen ja prosenttipisteen, jossa valittu asiakas on.

- **Eniten vaihtuvuusriskin suurenemiseen ja pienenemiseen vaikuttavat ominaisuudet:** Luettelossa on viisi ominaisuutta, jotka suurensivat ja pienensivät vaihtuvuusriskiä eniten oikeassa ruudussa valittuna olevan kohteen osalta. Näyttää jokaisen vaikuttavan ominaisuuden arvon kyseiselle kohteelle ja ominaisuuden vaikutuksen vaihtuvuuspisteisiin. Näytetään myös ominaisuuksien keskimääräinen arvo pienien, keskisuurien ja suurien vaihtuvuusasiakkaiden segmenteissä. Sen avulla on helpompaa ymmärtää vaikuttavimpien ominaisuuksien arvot kyseiselle kohteelle ja tehdä vertailuja pienien, keskisuurien ja suurien vaihtuvuusasiakkaiden segmentteihin.

  - Pieni: tilit sekä tilien ja toissijaisen tason yhdistelmät, joiden vaihtuvuuspisteet ovat 0–0,33.
  - Keskisuuri: tilit sekä tilien ja toissijaisten tasojen yhdistelmät, joiden vaihtuvuuspisteet ovat 0,33–0,66.
  - Suuri: tilit sekä tilien ja toissijaisten tasojen yhdistelmät, joiden vaihtuvuuspisteet ovat suuremmat kuin 0,66.

  Kun ennustat vaihtuvuutta asiakastasolla, kaikki asiakkaat otetaan huomioon, kun keskimääräisiä ominaisuusarvoja johdetaan vaihtuvuussegmenteille. Jokaisen asiakkaan toissijaisen tason vaihtuvuusennusteissa vaihtuvuussegmenttien johtaminen riippuu sivuruudussa valitun kohteen toissijaisesta tasosta. Jos kohteella on esimerkiksi tuoteluokan toissijainen taso (toimistotarvikkeet), otetaan huomioon vain kohteet, joissa toimistotarvikkeet ovat tuoteluokkana, kun keskimääräisiä ominaisuusarvoja johdetaan vaihtuvuussegmenteille. Logiikkaa käytetään, jotta kohteen ominaisuusarvojen ja pienien, keskisuurien ja suurien vaihtuvuussegmenttien keskimääräisten arvojen vertailu olisi tasapuolista.

  Joissain tapauksissa pienien, keskisuurien ja suurien vaihtuvuussegmenttien keskimääräinen arvo on tyhjä tai se ei ole käytettävissä, koska ei ole kohteita, jotka kuuluvat yllä olevaan määritelmään perustuviin, vastaaviin vaihtuvuussegmentteihin.

  Keskimäärin pienen, keskitason ja suuren sarakkeen arvojen tulkinta poikkeaa luokitteluominaisuuksista, kuten maa tai toimiala. Koska ominaisuuden keskimääräinen arvo ei ole käytössä luokitteluominaisuuksissa, näiden sarakkeiden arvo on niiden asiakkaiden osuus pienen, keskitason tai suuren vaihtuvuuden segmenteissä, joiden luokitteluominaisuuden arvo on sama sivupaneelissa valittuun kohteeseen verrattuna.

---

 > [!NOTE]
 > Tämän mallin tulosentiteetissä *ChurnScore* näyttää poistuman ennustetun todennäköisyyden ja *IsChurn* on *ChurnScore*-raja-arvoon 0,5 perustuva binaarinen selite. Jos tämä oletusraja-arvo ei toimi omassa skenaariossa, ensisijaisen raja-arvon sisältävä [uusi segmentti voidaan luoda](segments.md#create-a-segment). Kaikki asiakkaat eivät ole välttämättä aktiivisia asiakkaita. Joillakin niistä ei ehkä ole ollut pitkään aikaan mitään aktiviteettia, ja niitä pidetään jo poistuneina perustuen vaihtuvuusmääritykseen. Vaihtuvuusriskin ennustaminen asiakkaille, jotka jo vaihtuivat, ei ole hyödyllistä, koska ne eivät kuulu kiinnostavaan käyttäjäryhmään.
>
> Vaihtuvuuden pistemäärää voi tarkastella valitsemalla **Tiedot** > **Entiteetit** ja tarkastelemalla malliin määritetyn tulosentiteetin tietovälilehteä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
