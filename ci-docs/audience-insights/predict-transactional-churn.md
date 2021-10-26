---
title: Tapahtuman vaihtuvuuden ennustaminen
description: Sen riskin ennustaminen, että asiakas ei enää osta yrityksen tuotteita tai palveluja.
ms.date: 10/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ac484f74e388aa23422a89e25dabb555f2ad4118
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643373"
---
# <a name="transaction-churn-prediction-preview"></a>Tapahtuman vaihtuvuuden ennustaminen (esiversio)

Tapahtuman vaihtuvuusennuste auttaa ennustamaan, ostaako asiakas vielä tuotteita tai palveluja annetulla ajanjaksolla. Voit luoda uusia vaihtuvuusennusteita valitsemalla **Analytiikka** > **Ennusteet**. Valitse **Omat ennusteet**, kun haluat nähdä muita luomiasi ennusteita. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Yritystileihin perustuvissa ympäristöissä voidaan ennustaa tilin tapahtumien vaihtuvuus ja myös tilin ja toisen tietotason, kuten tuoteluokan, yhdistelmän vaihtuvuus. Dimension lisääminen voi auttaa saamaan selville, kuinka todennäköistä on, että asiakas ”Contoso” lopettaa tuoteluokan ”toimistotarvikkeet” ostamisen. Lisäksi yritystilien osalta voimme käyttää tekoälyä muodostamaan luettelon syistä, miksi on todennäköistä, että asiakas vaihtaa toissijaisen tason tietoluokkaan.

> [!TIP]
> Kokeile tapahtuman vaihtuvuusennustetta opasohjelmaa ja mallitietoja käyttäen: [Tapahtuman vaihtuvuuden ennustamisen (esiversio) esimerkkiopas](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>edellytykset

- Vähintään [osallistujan oikeudet](permissions.md) Customer Insightsissa.
- Liiketoiminnan tietämys, jonka avulla tiedät, mitä vaihtuvuus merkitsee yrityksellesi. Aikaperusteista vaihtuvuusmääritelmiä tuetaan, joten asiakkaan katsotaan vaihtuneen tietyn ostamattoman ajanjakson jälkeen.
- Tietoja tapahtumista ja ostoista sekä niiden historiasta:
    - Tapahtumatunnisteet erottavat ostot ja tapahtumat toisistaan.
    - Asiakastunnisteet, joilla tapahtumat yhdistetään asiakkaisiin.
    - Tapahtuman tapahtumapäivämäärät, jotka määrittävät tapahtuman tapahtumispäivämäärät.
    - Ostojen ja tapahtumien semanttiseen tietorakenteeseen tarvitaan seuraavat tiedot:
        - **Tapahtuman tunnus**: oston tai tapahtuman yksilöivä tunnus.
        - **Tapahtuman päivämäärä**: oston tai tapahtuman päivämäärä.
        - **Tapahtuman arvo**: tapahtuman tai nimikkeen valuutta tai numeroarvoinen summa.
        - (Valinnainen) **Yksilöivä tuotetunnus**: ostetun tuotteen tai palvelun tunnus, jos tieto on rivitasolla.
        - (Valinnainen) **Tieto siitä, oliko tämä tapahtuma palautus**: Tosi/epätosi-kenttä ilmaisee, oliko tapahtuma palautus vai ei. Jos **Tapahtuman arvo** on negatiivinen, myös tällä tiedolla viitataan palautukseen.
- (Valinnainen) Tietoja asiakkaan aktiviteeteista:
    - Aktiviteetin tunnisteet, joiden avulla saman tyypin aktiviteetit erotetaan toisistaan.
    - Asiakastunnisteet, joiden avulla aktiviteetit yhdistetään asiakkaisiin.
    - Aktiviteetin tiedot, jotka sisältävät aktiviteetin nimen ja päivämäärän.
    - Asiakasaktiviteettien semanttinen tietorakenne sisältää seuraavat tiedot:
        - **Perusavain:** Aktiviteetin yksilöllinen tunniste. Esimerkiksi sivustovierailu tai käyttötietue, joka osoittaa, että asiakas kokeile tuotenäytettä.
        - **Aikaleima:** Ensisijaisen avaimen tunnistaman tapahtuman päivämäärä ja aika.
        - **Tapahtuma:** Sen tapahtuman nimi, jota haluat käyttää. Esimerkiksi elintarvikemyymälän UserAction-kenttä voisi olla asiakkaan käyttämä kuponki.
        - **Tiedot:** Tapahtuman yksityiskohtaiset tiedot. Esimerkiksi elintarvikemyymälän CouponValue-kenttä voisi olla kupongin valuutta-arvo.
- (Valinnainen) Tietoja asiakkaistasi:
    - Nämä tiedot tulisi kohdistaa staattisempiin määritteisiin, jotta malli toimisi parhaalla mahdollisella tavalla.
    - Asiakastietojen semanttinen tietorakenne sisältää seuraavat tiedot:
        - **CustomerID:** Asiakkaan yksilöivä tunnus.
        - **Luontipäivämäärä:** Päivämäärä, jona asiakas alun perin lisättiin.
        - **Osavaltio tai provinssi:** Asiakkaan osavaltio- tai provinssisijainti.
        - **Maa:** asiakkaan maa.
        - **Toimiala:** asiakkaan toimialatyyppi. Esimerkiksi "Toimiala"-niminen kenttä kahvipaahtimon kohdalla voi ilmaista, onko asiakas vähittäismyyjä.
        - **Luokitus:** asiakkaan luokitteleminen yrityksesi tarpeiden mukaan. Esimerkiksi "ValueSegment"-niminen kenttä kahvipaahtimon kohdalla voi olla asiakkaan kokoon perustuva asiakastaso.
- Ehdotetut tietojen ominaisuudet:
    - Riittävät historiatiedot: Tapahtumatiedot vähintään kaksinkertainen määrä valittuun aikaikkunaan verrattuna. Mieluiten 2-3 vuoden tapahtumahistoria. 
    - Useita ostoja asiakasta kohden: Parhaimmillaan vähintään kaksi tapahtumaa asiakasta kohden
    - Asiakkaiden määrä: vähintään 10 asiakasprofiilia, mielellään yli 1 000 yksilöllistä asiakasta. Malli epäonnistuu, jos asiakkaita on alle 10 ja historiatiedot ovat puutteellisia.
    - Tietojen täydellisyys: Puuttuvia arvoja alle 20 % määritetyn entiteetin tietokentässä.

> [!NOTE]
> Jos asiakkaan ostoväli on suuri (muutaman viikon välein), on suositeltavaa valita lyhyempi ennusteen aikaväli ja vaihtuvuusmääritys. Jos ostoväli on alhainen (muutaman kuukauden välein tai kerran vuodessa), valitse pitkä ennusteen aikaväli ja vaihtuvuusmääritys.

## <a name="create-a-transaction-churn-prediction"></a>Tapahtuman vaihtuvuusennusteen luominen

1. Siirry Customer Insightsissa kohtaan **Älykäs toiminto** > **Ennusteet**.

1. Valitse **Asiakasvaihtuvuusmalli (esiversio)** -ruudussa **Käytä tätä mallia**.

1. Valitse **Asiakasvaihtuvuuden malli** -ruudussa **Tapahtuma** ja valitse **Aloita**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Näyttökuvassa valittu tapahtumavaihtoehto Asiakasvaihtuvuuden malli -ruudussa.":::

### <a name="name-model"></a>Nimimalli

1. Anna mallille nimi, joka erottaa sen muista malleista.

1. Anna tulosentiteetille nimi käyttämällä vain kirjaimia ja numeroita. Välilyöntejä ei voi käyttää. Se on nimi, jota mallientiteetti käyttää. 

1. Valitse **Seuraava**.

### <a name="define-customer-churn"></a>Määritä asiakasvaihtuma

1. Määritä vaihtuvuusennusteen aikaikkuna **Tunnista asiakkaat, jotka saattavat vaihtaa tilauksen seuraavassa** -kentässä. Ennustetaan esimerkiksi asiakkaiden vaihtuvuusriski seuraavan 90 päivän aikana siten, että se on linjassa markkinoinnin säilyttämispyrkimysten kanssa. Vaihtuvuusriskin ennusteen pituus voi hankaloittaa vaihtuvuusriskiprofiilissa olevien seikkojen huomioon ottamista; tämä kuitenkin määräytyy liiketoimintakohtaisten tarpeiden mukaan.
   >[!TIP]
   > Voit valita **Tallenna ja sulje** milloin tahansa, jos haluat tallentaa ennusteen luonnokseksi. Näkyviin tulee ennusteluonnos **Omat ennusteet** -välilehdessä.

1. Anna vaihtuvuuden määrittävän päivien määrä **Asiakkaan katsotaan vaihtuneen, jos hän ei ole tehnyt ostoksia:** -kentässä. Jos asiakas ei ole esimerkiksi tehnyt ostoja 30 päivän aikana, heidän voidaan katsoa vaihtuneen liiketoiminnassa. 

1. Jatka valitsemalla **Seuraava**.

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Lisää tiedot** ja valitse sitten sivuruudusta aktiviteetin tyyppi, joka sisältää tarvittavat tapahtuma- tai ostohistoriatiedot.

1. Valitse **Valitse aktiviteetit** -kohdassa aktiviteetit, jotka haluat kohdistaa laskutoimitukseen valitusta aktiviteetista.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Sivuruutu, jossa näkyy tiettyjen aktiviteettien valitseminen semanttisen tyypin perusteella.":::

1. Jos et ole vielä yhdistänyt aktiviteettia semanttiseen tyyppiin, valitse **Muokkaa**. Ohjattu kokemus semanttisten aktiviteettien yhdistämiseksi avautuu. Yhdistä tietosi valitun toimintotyypin vastaaviin kenttiin.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Sivun asetusaktiviteetin tyyppi.":::

1. Kun aktiviteetti on yhdistetty vastaavaan semanttiseen tyyppiin, jatka valitsemalla **Seuraava**

1. Yhdistä semanttiset määritteet kenttiin, jotka tarvitaan mallin suorittamiseen. Jos alla olevia kenttiä ei ole täytetty, määritä ostohistoriaentiteetin suhde *Asiakas*-entiteettiin.

1. Valitse **Seuraava**.

### <a name="select-prediction-level"></a>Valitse ennusteen taso

Useimmat ennusteet luodaan asiakastasolla. Joissakin tilanteissa ne eivät ehkä ole riittävän tarkkoja yrityksen tarpeisiin. Tämän ominaisuuden avulla voit ennustaa vaihtuvuuden esimerkiksi asiakashaaran osalta kokonaisen asiakkaan asemesta.

1. Jos haluat luoda ennusteen asiakasta tarkemmalla tasolla, valitse **Valitse entiteetti toissijaiselle tasolle**. Jos vaihtoehto ei ole käytettävissä, varmista, että olet suorittanut edellisen osan.

1. Laajenna entiteetit, joista haluat valita toissijaisen tason, tai käytä hakusuodatinruutua suodattaaksesi valitut vaihtoehdot.

1. Valitse määrite, jota haluat käyttää toissijaisena tasona, ja valitse sitten **Lisää**

1. Valitse **Seuraava**

> [!NOTE]
> Tässä osassa käytettävissä olevat entiteetit näkyvät, koska niillä on suhde edellisessä osassa valitsemaasi entiteettiin. Jos lisättävää entiteettiä ei näy, varmista, että sillä on kelvollinen suhde kohdassa **Suhteet**. Vain yksi yhteen- ja monta yhteen -suhteet kelpaavat tässä kokoonpanossa.

### <a name="add-additional-data-optional"></a>Lisätietojen lisääminen (valinnainen)

Määritä asiakasaktiviteettientiteetin suhde *asiakasentiteettiin*.

1. Valitse kenttä, joka määrittää asiakkaan asiakasaktiviteettitaulukossa. Se voi liittyä suoraan *asiakasentiteetin* ensisijaiseen asiakastunnukseen.

1. Valitse entiteetti, joka on ensisijainen *Asiakas*-entiteettisi.

1. Anna suhdetta kuvaava nimi.

#### <a name="customer-activities"></a>Asiakasaktiviteetit

1. Vaihtoehtoisesti voit valita **Lisää tiedot** **Asiakasaktiviteetit**-kohdassa.

1. Valitse semanttinen aktiviteettityyppi, joka sisältää haluamasi tiedot, ja valitse sitten yksi tai useampi aktiviteetti **Aktiviteetit**-osasta.

1. Valitse aktiviteettityyppi, joka vastaa määrittämiesi asiakkaan aktiviteetin tyyppiä. Valitse **Luo uusi** ja valitse käytettävissä oleva aktiviteettityyppi tai luo uusi tyyppi.

1. Valitse **Seuraava**, sitten **Tallenna**.

1. Jos haluat sisällyttää muita asiakasaktiviteetteja, toista edellä olevat vaiheet.

#### <a name="customers-data"></a>Asiakkaiden tiedot

1. Voit myös valita **Lisää tietoja** kohteelle **Asiakastiedot**.

1. Yhdistä semanttiset määritteet omien asiakastietojesi kenttiin tunnistettuiksi. Käytetyissä kentissä olevien tietojen ei tulisi muuttua usein, jotta mallin suorituskyky olisi paras. Esimerkiksi jos valitaan kenttä “Luokittelu”, joka on muuttunut joka kuukausi, ennusteessa käytetään vain viimeistä arvoa, vaikka asiakashistoriassa sama arvo ei soveltuisi asiakkaaseen, kun ennustemalleja tehdään.

1. Valitse **Seuraava**.

### <a name="provide-an-optional-list-of-benchmark-accounts-business-accounts-only"></a>Valinnaisen luettelon tarjoaminen vertailuasiakkaista (vain yritystilit)

Lisää luettelo yritysasiakkaistasi ja asiakkaistasi, joita haluat käyttää vertailukohtana. Saat [tietoja näistä vertailuasiakkaista](#review-a-prediction-status-and-results) mukaan lukien niiden vaihtuvuuspisteytyksen ja vaikuttavimmat ominaisuudet, jotka vaikuttivat niiden vaihtuvuusennusteeseen.

1. Valitse **+ Lisää asiakkaita**.

1. Valitse asiakkaat, jotka toimivat vertailukohtina.

1. Jatka valitsemalla **Seuraava**.

### <a name="set-schedule-and-review-configuration"></a>Määritä aikataulu ja tarkista määritys

1. Määritä mallin uudelleenkouluttamistiheys. Tämä asetus on tärkeä ennusteiden tarkkuuden päivityksessä uusia tietoja käsiteltäessä. Useimmat yritykset voivat uudelleenkouluttaa kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

1. Tarkista ennusteen määritys. Voit palata edellisiin vaiheisiin valitsemalla **Muokkaa** näytetyssä arvossa. Voit myös valita määritysvaiheen edistymisen ilmaisimesta.

1. Jos kaikki arvot on määritetty oikein, aloita ennusteprosessi valitsemalla **Tallenna ja suorita**. **Omat ennusteet** -välilehdessä voit tarkastella ennusteiden tilaa. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

## <a name="review-a-prediction-status-and-results"></a>Ennusteen tilan ja tulosten tarkasteleminen

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse ennuste, jota haluat tarkastella.
   - **Ennusteen nimi**: Ennusteelle luonnin yhteydessä annettu nimi.
   - **Ennustetyyppi**: Ennusteessa käytetyn mallin tyyppi
   - **Tulosentiteetti**: Sen entiteetin nimi, johon ennusteen tulos tallennetaan. Tämänniminen entiteetti löytyy kohdasta **Tiedot** > **Entiteetit**.
     Tulosentiteetissä *ChurnScore* on poistuman ennustettu todennäköisyys ja *IsChurn* on *ChurnScore*-raja-arvoon 0,5 perustuva binaarinen otsikko. Oletusraja-arvo ei ehkä toimi skenaariossasi. [Luo uusi segmentti](segments.md#create-a-new-segment), jolla on haluamasi raja-arvo.
     Kaikki asiakkaat eivät ole välttämättä aktiivisia asiakkaita. Joillakin niistä ei ehkä ole ollut pitkään aikaan mitään aktiviteettia, ja niitä pidetään jo poistuneina perustuen vaihtuvuusmääritykseen. Vaihtuvuusriskin ennustaminen asiakkaille, jotka jo vaihtuivat, ei ole hyödyllistä, koska ne eivät kuulu kiinnostavaan käyttäjäryhmään.
   - **Ennustettu kenttä**: tämä kenttä täytetään vain tietyissä ennustetyypeissä eikä sitä käytetä vaihtuvuusennusteessa.
   - **Tila**: Ennusten suorituksen tila.
        - **Jonossa**: ennuste odottaa muiden prosessien suorittamista.
        - **Päivittyy**: suoritettavan ennusteen tulokset siirretään tuloste-entiteettiin.
        - **Epäonnistui**: Ennusteen suorittaminen epäonnistui. Lisätietoja saa [lokeja tarkastelemalla](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Onnistui**: Ennuste onnistui. Valitse allekkaisten pisteiden alla oleva **Tarkastele**-kohta, jos haluat tarkastella ennustetta.
   - **Muokattu**: Ennusteen määrityksen muutospäivämäärä.
   - **Viimeinen päivitys**: Päivämäärä, jona ennuste päivitti tulokset tulosentiteettiin.

1. Valitse sen ennusteen vieressä olevat allekkaiset pisteet, jonka tuloksia haluat tarkastella, ja valitse **Näytä**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Ennusteen tulosten näyttäminen näkymän ohjausobjektilla":::

1. Tulossivulla on seuraavat kolme ensisijaista tieto-osaa:
   - **Opetusmallin suorituskyky**: A, B ja C ovat mahdollisia pistemääriä. Tämä pistemäärä osoittaa ennusteen suorituskyvyn, ja sen avulla voit tehdä päätöksen tulosentiteettiin tallennettujen tulosten käyttämisestä. Pistemäärät määritetään seuraavien sääntöjen perusteella: 
        - **A**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on ainakin 10 % suurempi kuin lähtöarvo.
            
        - **B**, kun mallin tarkkuudeksi on ennustettu vähintään 50 % ennusteesta yhteensä ja kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on enintään 10 % suurempi kuin lähtöarvo.
            
        - **C**, kun mallin tarkkuudeksi on ennustettu alle 50 % ennusteesta yhteensä tai kun vaihtuvuusasiakkaiden tarkka ennusteprosentti on pienempi kuin lähtöarvo.
               
        - **Lähtöarvo** käyttää mallin ennusteen aikaikkunan (kuten yhden vuoden), ja malli luo eri aikajakoja jakamalla sen kahdella, kunnes tuloksena on yksi kuukausi tai sitä lyhyempi jakso. Se luo liiketoimintasäännön näiden osien avulla asiakkaille, jotka eivät ole tehneet ostona kyseisellä aikavälillä. Näiden asiakkaiden katsotaan vaihtuneen. Lähtöarvomalliksi valitaan aikaperusteinen liiketoimintasääntö, joka ennustaa parhaiten todennäköisen vaihtuvuuden.
            
    - **Vaihtuvuuden todennäköisyys (asiakkaiden määrä)**: Asiakasryhmät ennustetun vaihtuvuusriskin perusteella. Nämä tiedot auttavat myöhemmin, jos haluat luoda asiakassegmentin, jolla on suuri vaihtuvuusriski. Tällaiset segmentit auttavat ymmärtämään, missä segmentin jäsenyyden rajan on oltava.
       
    - **Tärkeimmät tekijät**: Ennusteen luomisessa otetaan huomioon useita tekijöitä. Kunkin tekijän tärkeys lasketaan mallin luomille kooste-ennusteille. Voit käyttää näitä tekijöitä apuna ennusteen tuloksien vahvistamisessa tai voit käyttää tätä tietoa myöhemmin [luodessasi segmenttejä](segments.md), joista voi olla apua asiakkaiden vaihtuvuusriskiin vaikuttamisessa.


1. Yritystileille on käytettävissä **Vaikuttavien ominaisuuksien analyysi** -tietosivu. Se sisältää neljä tieto-osaa:

    - Oikeanpuoleisessa ruudussa valittu kohde määrittää tämän sivun sisällön. Valitse kohde **Parhaat asiakkaat**- tai **Vertailuasiakkaat**-kohdasta. Molemmat luettelot on järjestetty laskevasti vaihtuvuuspisteiden mukaan riippumatta siitä, onko kyseessä asiakkaan pisteytys vai asiakkaiden ja toissijaisen tason, kuten tuoteluokan, yhteispisteytys.
        
        - **Parhaat asiakkaat**: Luettelo 10 asiakkaasta, joilla on suurin vaihtuvuusriski ja matalin vaihtuvuusriski asiakkaiden vaihtuvuuspisteiden perusteella. 
        - **Vertailuasiakkaat**: Luettelo 10 asiakkaasta, jotka valittiin tätä mallia määritettäessä.
 
    - **Vaihtuvuuspisteet:** Näyttää valitun kohteen vaihtuvuuspisteet oikeanpuoleisessa ruudussa.
    
    - **Vaihtuvuusriskin jakautuminen:** Näyttää asiakkaiden vaihtuvuusriskin jakautumisen ja prosenttipisteen, jossa valittu asiakas on. 
    
    - **Eniten vaihtuvuusriskin suurenemiseen ja pienenmiseen vaikuttavat ominaisuudet:** Luettelossa näkyvät viisi ominaisuutta, jotka suurensivat ja pienensivät vaihtuvuusriskiä eniten kohteelle, joka on valittuna oikeanpuoleisessa ruudussa. Löydät jokaisen vaikuttavan ominaisuuden arvon kyseiselle kohteelle ja ominaisuuden vaikutuksen vaihtuvuuspisteisiin. Näytetään myös ominaisuuksien keskimääräinen arvo pienien, keskisuurien ja suurien vaihtuvuusasiakkaiden segmenteissä. Sen avulla on helpompaa ymmärtää vaikuttavimpien ominaisuuksien arvot kyseiselle kohteelle ja tehdä vertailuja pienien, keskisuurien ja suurien vaihtuvuusasiakkaiden segmentteihin.

       - Pieni: tilit sekä tilien ja toissijaisen tason yhdistelmät, joiden vaihtuvuuspisteet ovat 0–0,33
       - Keskisuuri: tilit sekä tilien ja toissijaisten tasojen yhdistelmät, joiden vaihtuvuuspisteet ovat 0,33–0,66
       - Suuri: tilit sekä tilien ja toissijaisten tasojen yhdistelmät, joiden vaihtuvuuspisteet ovat suuremmat kuin 0,66
    
       Kun ennustat vaihtuvuutta asiakastasolla, kaikki asiakkaat otetaan huomioon, kun keskimääräisiä ominaisuusarvoja johdetaan vaihtuvuussegmenteille. Jokaisen asiakkaan toissijaisen tason vaihtuvuusennusteissa vaihtuvuussegmenttien johtaminen riippuu sivuruudussa valitun kohteen toissijaisesta tasosta. Esimerkiksi jos kohteella on tuoteluokan toissijainen taso = toimistotarvikkeet, otetaan huomioon vain kohteet, joissa on toimistotarvikkeet tuoteluokkana, kun keskimääräisiä ominaisuusarvoja johdetaan vaihtuvuussegmenteille. Logiikkaa käytetään, jotta kohteen ominaisuusarvojen ja pienien, keskisuurien ja suurien vaihtuvuussegmenttien keskimääräisten arvojen vertailu olisi tasapuolista.

       Joissain tapauksissa pienien, keskisuurien ja suurien vaihtuvuussegmenttien keskimääräinen arvo on tyhjä tai se ei ole käytettävissä, koska ei ole kohteita, jotka kuuluvat yllä olevaan määritelmään perustuviin, vastaaviin vaihtuvuussegmentteihin.

## <a name="manage-predictions"></a>Hallitse ennusteita

Voit optimoida, tehdä vianmäärityksen, päivittää tai poistaa ennusteita. Käytettävyysraportissa on tietoja siitä, miten tehdä ennusteista nopeampia ja luotettavampia. Jos haluat lisätietoja, siirry kohtaan [Ennusteiden hallinta](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
