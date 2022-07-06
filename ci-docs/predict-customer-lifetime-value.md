---
title: Asiakkaan elinkaaren arvon (CLV) ennuste
description: Ennakoi aktiivisten asiakkaiden myyntituoton potentiaali tulevaisuudessa.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: ea7acd1ddbb0eb8d66fb82018637a85b6ffb369b
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055210"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Asiakkaan elinkaaren arvon (CLV) ennuste

Ennusta mahdollinen arvo (myyntituotto), jonka yksittäiset aktiiviset asiakkaat tuovat yritykselle tiettynä tulevana ajanjaksona. Tämän ominaisuuden avulla voit saavuttaa esimerkiksi seuraavat tavoitteet:
- Korkean lisäarvon asiakkaiden tunnistaminen ja näiden merkityksellisten tietojen käsitteleminen
- Strategisten asiakassegmenttien luominen niiden mahdollisen arvon perusteella mukautettujen kampanjoiden ja kohdistetun myynnin, markkinoinnin ja tukitoimintojen suorittamiseksi
- Tuotekehityksen opastaminen keskittymällä asiakkaan arvoa lisääviin ominaisuuksiin
- Myynti- tai markkinointistrategian optimoiminen ja budjetin kohdistaminen aiempaa tarkemmin asiakkaiden tavoittamiseksi
- Korkean lisäarvon asiakkaiden tunnistaminen ja palkitseminen kanta-asiakas- ja palkkio-ohjelmien avulla 

## <a name="prerequisites"></a>Edellytykset

Mieti ennen käytön aloittamista, mitä asiakkaan elinkaaren arvo merkitsee yrityksellesi. Tällä hetkellä tuemme tapahtumiin perustuvia asiakkaan elinkaaren arvon ennusteita. Asiakkaan ennustettu arvo perustuu liiketoimintatapahtumahistoriaan. Jos haluat luoda ennusteen, tarvitset vähintään [osallistujan](permissions.md) käyttöoikeudet.

Koska asiakkaan elinkaaren arvon mallin määrittäminen ja käyttäminen ei vie paljon aikaa, kannattaa luoda useita malleja erilaisilla syöttömäärityksillä ja vertailla mallien tuloksia. Näin näet, mikää malliskenaario vastaa parhaiten liiketoiminnan tarpeita.

###  <a name="data-requirements"></a>Tietojen vaatimukset

Seuraavat tiedot ovat pakollisia. Valinnaisia tietoja suositellaan mallin suorituskyvyn parantamiseksi. Mitä enemmän tietoja malli voi käsitellä, sitä tarkempi ennuste on. Siksi suosittelemme asiakasaktiviteettitietojen lisäämistä, jos niitä on käytettävissä.

- Asiakkaan tunnus: Yksilöllinen tunnus, joka yhdistää tapahtumat yksittäiseen asiakkaaseen

- Tapahtumahistoria: Historiallisten tapahtumien loki ja semanttinen tietorakenne alapuolella
    - **Tapahtuman tunnus**: Kunkin tapahtuman yksilöivä tunnus
    - **Tapahtuman päivämäärä**: Päivämäärä, mieluiten kunkin tapahtuman aikaleima
    - **Tapahtuman summa**: Kunkin tapahtuman rahasumma (esimerkiksi myyntituotto tai katetuotto)
    - **Palautuksille määritetty otsikko** (valinnainen): Totuusarvo, joka osoittaa, onko tapahtuma palautus 
    - **Tuotetunnus** (valinnainen): Tapahtumaan osallistuvan tuotteen tuotetunnus

- Lisätiedot (valinnainen), esimerkiksi
    - Verkkoaktiviteetit: Sivuston vierailuhistoria, sähköpostihistoria
    - Kanta-asiakasaktiviteetit: Kanta-asiakkuuden palkkiopisteiden kertymä- ja lunastushistoria
    - Asiakaspalveluloki-, huoltokäynti-, valitus- tai palautushistoria
- Tietoja asiakkaan aktiviteeteista (valinnainen):
    - Aktiviteetin tunnisteet, joiden avulla saman tyypin aktiviteetit erotetaan toisistaan
    - Asiakastunnisteet, joiden avulla aktiviteetit yhdistetään asiakkaisiin
    - Aktiviteetin tiedot, jotka sisältävät aktiviteetin nimen ja päivämäärän
    - Aktiviteettien semanttinen tietorakenne sisältää seuraavat tiedot: 
        - **Perusavain:** Aktiviteetin yksilöivä tunnus
        - **Aikaleima**: Perusavaimen tunnistaman tapahtuman päivämäärä ja aika
        - **Tapahtuma (aktiviteetin nimi)**: Sen tapahtuman nimi, jota haluat käyttää
        - **Tiedot (summa tai arvo)**: Tietoja asiakasaktiviteettista

- Ehdotetut tietojen ominaisuudet:
    - Riittävät historiatiedot: Tapahtumatiedot vähintään vuoden ajalta. Mieluiten 2–3 vuoden transaktiotiedot CLV:n ennustamiseksi vuodeksi.
    - Useita ostoksia asiakasta kohti: Mieluiten vähintään 2–3 tapahtumaa asiakastunnusta kohden, mieluiten useana päivämääränä.
    - Asiakkaiden määrä: Vähintään 100 eri asiakasta, mielellään yli 10 000 asiakasta. Malli epäonnistuu, jos asiakkaita on alle 100 ja historiatiedot ovat puutteellisia
    - Tietojen täydellisyys: Vähemmän kuin 20 % arvoista puutuu syötetietojen pakollisissa kentissä   

> [!NOTE]
> - Malliin tarvitaan asiakkaiden tapahtumahistoria. Tällä hetkellä voi määrittää vain yhden tapahtumahistorian entiteetin. Jos osto-/tapahtumaentiteettejä on useita, ne voidaan yhdistää Power Queryssä ennen tietojen käsittelyä.
> - Jos haluat lisää asiakkaan aktiviteettitietoja (valinnaisia), voit kuitenkin lisätä mallin käsiteltäväksi niin monta asiakasaktiviteettientiteettiä kuin haluat.

## <a name="create-a-customer-lifetime-value-prediction"></a>Asiakkaan elinkaaren arvon ennusteen luominen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Asiakkaan elinkaaren arvo** -ruutu ja valitse sitten **Käytä mallia**. 

1. Valitse **Asiakkaan elinkaaren arvo** -ruudussa **Aloita käyttö**.

1. **Anna tälle mallille** ja **tulosentiteetille nimi**, jotta ne voidaan erottaa muista malleista tai entiteeteistä.

1. Valitse **Seuraava**.

### <a name="define-model-preferences"></a>Malliasetusten määrittäminen

1. Määritä, milloin haluat ennustaa asiakkaan elinkaaren arvon, antamalla **Ennusteen ajanjakso** -kohdalle arvo.    
   Oletusarvoisesti arvoksi määritetään kuukausia. Voit muuttaa arvoksi vuodet, jos haluat tarkastella tilannetta tulevaisuudessa.

   > [!TIP]
   > Jotta asiakkaan elinkaaren arvo voidaan ennustaa määrittämällesi ajanjaksolle, tarvitset historiallisten tietojen vertailtavissa olevan kauden. Jos esimerkiksi haluat ennustaa asiakkaan elinkaaren arvon seuraavien 12 kuukauden jaksolle, on suositeltavaa, että sinulla on vähintään 18–24 kuukauden historiatiedot.

1. Määritä, mitä **aktiiviset asiakkaat** tarkoittavat liiketoiminnassa. Määritä aikaväli, jonka aikana asiakkaalla on oltava vähintään yksi tapahtuma, jotta asiakasta pidetään aktiivisena. Malli ennustaa vain aktiivisten asiakkaiden asiakkaan elinkaaren arvon. 
   - **Salli mallin laskea ostoväli (suositus)**: Malli analysoi tiedot ja määrittää ajanjakson ostohistorian perusteella.
   - **Määritä väli manuaalisesti**: Jos aktiivisella asiakkaalla on tietty liiketoiminnan määritys, valitse tämä vaihtoehto ja määritä ajanjakso vastaavasti.

1. Määritä **korkean lisäarvon asiakkaan** prosenttipiste, jotta malli voi antaa liiketoiminnan määritystä vastaavat tulokset.
    - **Mallin laskenta (suositus)**: Malli analysoi tiedot ja määrittää, mikä korkean lisäarvon asiakas voi olla liiketoiminnassasi asiakkaiden tapahtumahistorian perusteella. Malli käyttää heuristiikkasääntöä (80/20-säännön tai pareto-käytännön mukaan) korkean lisäarvon asiakkaiden osuuden etsimisessä. Niiden asiakkaiden prosenttiosuus, jotka ovat vaikuttaneet 80 prosenttiin yrityksen kumulatiivisesta myyntituotosta aiemman kauden aikana, pidetään korkean lisäarvon asiakkaina. Yleensä alle 30–40 prosenttia asiakkaista tuo 80 prosentin kumulatiivisen myyntituoton. Luku voi kuitenkin vaihdella yrityksen ja toimialan mukaan.    
    - **Aktiivisten asiakkaiden prosenttiosuus**: Määritä yrityksen korkean lisäarvon asiakkaat aktiivisimpien maksavien asiakkaiden prosenttipisteenä. Voit käyttää tätä vaihtoehtoa esimerkiksi määrittäessäsi ne 20 prosenttia korkean lisäarvon asiakkaista, jotka maksavat tulevaisuudessa eniten.

    Jos yrityksesi määrittää korkean lisäarvon asiakkaat eri tavalla, [kerro siitä meille](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Siirry seuraavaan vaiheeseen valitsemalla **Seuraava**.

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Pakolliset tiedot** -vaiheessa **Lisää tiedot** **Asiakkaan tapahtumahistoria** -kohtaan ja valitse entiteetti, joka sisältää tapahtuman historiatiedot [edellytyksissä](#prerequisites) kuvatulla tavalla.

1. Yhdistä semanttiset kentät määritteisiin ostohistoriaentiteetissä ja valitse **Seuraava**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Kuva määritysvaiheesta, jossa tietomääritteet yhdistetään pakollisiin tietoihin.":::
 
1. Jos alla olevia kenttiä ei ole täytetty, määritä ostohistoriaentiteetin suhde *asiakasentiteettiin* ja valitse **Tallenna**.
    1. Valitse tapahtumahistorian entiteetti.
    1. Valitse kenttä, joka määrittää asiakkaan ostohistorian entiteetissä. Sen on liityttävä ensisijaisen asiakkaan tunnukseen asiakasentiteetissä.
    1. Valitse entiteetti, joka vastaa ensisijaista asiakasentiteettiä.
    1. Anna suhdetta kuvaava nimi.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Kuva määritysvaiheesta, jossa määritetään suhde asiakasentiteettiin.":::

1. Valitse **Seuraava**.

### <a name="add-optional-data"></a>Lisää valinnaisia tietoja

Tärkeisiin asiakastapahtumiin (kuten verkko-, asiakaspalvelu- ja tapahtumalokitapahtumat) liittyvät tiedot lisäävät tapahtumatietueisiin kontekstia. Mallien lisääminen asiakkaiden aktiivisuustietoihin voi parantaa ennusteiden tarkkuutta. 

1. Valitse **Lisätiedot (valinnainen)** -vaiheessa **Lisää tietoja**. Valitse asiakasaktiviteettientiteetti, jossa on asiakasaktiviteetin tiedot [edellytyksissä](#prerequisites) kuvatulla tavalla.

1. Yhdistä semanttiset kentät määritteisiin asiakasaktiviteettientiteetissä ja valitse **Seuraava**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Kuva määritysvaiheesta, jossa kentät yhdistetään lisätietoihin.":::

1. Valitse aktiviteettityyppi, joka vastaa lisättävän asiakasaktiviteetin tyyppiä. Valitse aiemmin luodut aktiviteettityypit tai lisää uusi aktiviteettityyppi.

1. Määritä asiakasaktiviteettientiteetin suhde *asiakasentiteettiin*.
    
    1. Valitse kenttä, joka määrittää asiakkaan asiakasaktiviteettitaulukossa. Se voi liittyä suoraan *asiakasentiteetin* ensisijaiseen asiakastunnukseen.
    1. Valitse *asiakasentiteetti*, joka vastaa ensisijaista *asiakasentiteettiä*.
    1. Anna suhdetta kuvaava nimi.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Kuva määritystyönkulun siitä vaiheesta, jossa lisätään tietoja ja määritetään aktiviteetti täytetyillä esimerkeillä.":::

1. Valitse **Tallenna**.    
    Lisää tietoja, jos haluat sisällyttää muita asiakasaktiviteetteja.

1. Valitse **Seuraava**.

### <a name="set-update-schedule"></a>Päivitysaikataulun määrittäminen

1. Valitse **Tietojen päivitysaikataulu** -vaiheessa aikaväli, jonka mukaan mallia koulutetaan uudelleen uusimpien tietojen perusteella. Tämä asetus on tärkeä, jotta ennusteiden tarkkuus voidaan päivittää, kun uusia tietoja päivitetään Customer Insightsissa. Useimmat yritykset voivat uudelleenkouluttaa kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

### <a name="review-and-run-the-model-configuration"></a>Mallimäärityksen tarkasteleminen ja suoritaminen

1. Voit tarkastella ennusteen määritystä **Tarkastele mallin tietoja** -vaiheessa. Voit palata mihin tahansa ennustemäärityksen osaan valitsemalla **Muokkaa** annetun arvon kohdassa. Voit myös valita määritysvaiheen edistymisen ilmaisimessa.

1. Jos kaikki arvot on määritetty oikein, aloita mallin suorittaminen valitsemalla **Tallenna ja suorita**. **Omat ennusteet** -välilehdessä näet ennusteprosessin tilan. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

## <a name="review-prediction-status-and-results"></a>Tilan ennusteen ja tulosten tarkasteleminen

### <a name="review-prediction-status"></a>Tilan ennusteen tarkasteleminen

1.  Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.
2.  Valitse ennuste, jota haluat tarkastella.

- **Ennusteen nimi**: Ennusteelle luonnin yhteydessä annettu nimi.
- **Ennustetyyppi**: Ennusteessa käytetyn mallin tyyppi
- **Tulosentiteetti**: Sen entiteetin nimi, johon ennusteen tulos tallennetaan. Siirry kohtaan **Tiedot** > **Entiteetit**, jos haluat löytää tämännimisen entiteetin.
- **Ennustettu kenttä**: Tämä kenttä täytetään vain tietyissä ennustetyypeissä eikä sitä käytetä asiakkaan elinkaaren arvon ennusteessa.
- **Tila**: Ennusten suorituksen tila.
    - **Jonossa**: Ennuste odottaa muiden prosessien valmistumista.
    - **Päivittyy**: Ennustetta suoritetaan parhaillaan, jotta luodaan tulosentiteettiin siirrettävät tulokset.
    - **Epäonnistui**: Ennusteen suorittaminen epäonnistui. Lisätietoja saa [lokeja tarkastelemalla](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Onnistui**: Ennuste onnistui. Valitse kolmen pystysuuntaisen pisteen alapuolella oleva **Näytä**-kohta, jos haluat tarkastella ennusteen tuloksia.
- **Muokattu**: Ennusteen määrityksen muutospäivämäärä.
- **Viimeinen päivitys**: Päivämäärä, jona ennuste päivitti tulokset tulosentiteettiin.

### <a name="review-prediction-results"></a>Ennusteen tulosten tarkasteleminen

1. Valitse ensin **Analytiikka** > **Ennusteet** ja sitten **Omat ennusteet** -välilehti.

1. Valitse ennuste, jonka tuloksia haluat tarkastella.

Tulossivulla on kolme ensisijaista tieto-osaa.

- **Opetusmallin suorituskyky**: Valittavissa olevat luokat ovat A, B ja C. Luokka osoittaa ennusteen suorituskyvyn. Sen avulla voit päättää, käytetäänkö tulosentiteettiin tallennettuja tuloksia. Valitse **Lisätietoja tästä pisteytyksestä**, jos haluat lisätietoja perustana olevan mallin suorituskykymittareista ja siitä, miten lopullinen mallin suorituskykyluokka johdettiin.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Kuva mallin pisteiden tietoruudusta, jossa luokka on A.":::

  Jos korkean lisäarvon asiakkaiden määritystä käytetään ennusteen määrittämisessä, järjestelmä arvioi, miten tekoälymalli suoriutui korkean lisäarvon asiakkaiden ennustamisessa perusmalliin verrattuna.    

  Luokat määritetään seuraavien sääntöjen perusteella:
  - **A**, kun malli ennusti tarkasti vähintään 5 % enemmän korkean lisäarvon asiakkaita kuin perusmalli.
  - **B**, kun malli ennusti tarkasti 0-5 % enemmän korkean lisäarvon asiakkaita kuin perusmalli.
  - **C**, kun malli ennusti tarkasti vähemmän korkean lisäarvon asiakkaita kuin perusmalli.

  **Malliluokitus**-ruudussa näkyvät tekoälymallin suorituskyvyn ja perusmallin lisätiedot. Perusmallissa käytetään muuta kuin tekoälyyn perustuvaa tapaa laskea asiakkaan elinkaaren arvo ensisijaisesti asiakkaiden tekemien aiempien ostojen perusteella.     
  Vakiokaava, jonka avulla asiakkaan elinkaaren arvo lasketaan perusmallin mukaan:    

  _**Asiakkaan elinkaaren arvo kullekin asiakkaalle** = Asiakkaan kuukauden keskimääräiset ostot aktiivisessa asiakasikkunassa * Asiakkaan elinkaaren arvon ennustejakson kuukausien määrä * Kaikkien asiakkaiden yleinen uskollisuusprosentti*_

  Tekoälymallia verrataan perusmalliin kahden mallin suorituskykymittareiden perusteella.
  
  - **Korkean lisäarvon asiakkaiden ennustamisen onnistumisaste**

    Katso ero ennustettaessa korkean lisäarvon asiakkaat tekoälymallin ja perusmallin avulla. Esimerkiksi 84 prosentin onnistumisaste tarkoittaa sitä, että opetusmallin kaikista korkean lisäarvon asiakkaista tekoälymalli löysi 84 %. Tämän jälkeen onnistumisastetta verrataan perusmallin onnistumisasteeseen ja suhteellinen muutos raportoidaan. Tätä arvoa käytetään määritettäessä mallille luokka.

  - **Virhemittarit**
    
    Toisen mittarin avulla voit tarkastella malin yleistä suorituskykyä tulevien arvojen ennustamisen virheiden perusteella. Tämän virheen arvioinnissa käytetään neliöllistä keskiarvoa (root mean squared error, RMSE). RMSE on kvantitatiivisten tietojen mallin virheen mittauksen vakiomenetelmä. Tekoälymallin RMSE-arvoa verrataan perusmallin RMSE-arvoon. Lopuksi raportoidaan suhteellinen ero.

  Tekoälymalli priorisoi asiakkaiden tarkan luokittelun sen mukaan, millaista lisäarvoa he tuovat yritykselle. Korkean lisäarvon asiakkaiden ennustamisessa käytetään siis vain onnistumisastetta. Sen avulla johdetaan mallin lopullinen luokka. RMSE-mittari on herkkä poikkeaville arvoille. Skenaarioissa, joissa pieni prosenttiosuus erittäin korkean ostoarvon omaavia asiakkaita, yleinen RMSE-mittari ei ehkä annan todellista kuvaa mallin suorituskyvystä.   

- **Asiakkaiden arvo prosenttipisteen mukaan**: Asiakkaan ryhmitellään korkean lisäarvon asiakkaiden määrityksen mukaan alhaisen lisäarvon ja korkean lisäarvon luokkiin asiakkaan elinkaaren arvon ennusteiden perusteeella. Tiedot näytetään kaaviossa. Jos viet hiiren osoittimen histogrammin pakkien kohdalle, näet kunkin ryhmän asiakkaiden määrän ja kyseisen ryhmän keskimääräisen asiakkaan elinkaaren arvon. Tiedoista on apua, jos haluat [luoda asiakassegmenttejä](segments.md) asiakkaan elinkaaren arvon ennusteiden perusteella.

- **Vaikuttavimmat tekijät**: Huomioon otetaan eri tekijöitä, kun asiakkaan elinkaaren arvon ennuste luodaan tekoälymallille annettujen syötetietojen perusteella. Kunkin tekijän tärkeys on laskettu mallin luomille yhdistellyille ennusteille. Näiden tekijöiden avulla voit tarkistaa ennusteen tulokset. Nämä tekijät antavat myös enemmän tietoja tekijöistä, jotka vaikuttivat eniten kaikkien asiakkaiden asiakkaan elinkaaren arvon ennustamiseen.

## <a name="manage-predictions"></a>Hallitse ennusteita

Voit optimoida, tehdä vianmäärityksen, päivittää tai poistaa ennusteita. Käytettävyysraportissa on tietoja siitä, miten tehdä ennusteista nopeampia ja luotettavampia. Lisätietoja on kohdassa [Ennusteiden hallinta](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
