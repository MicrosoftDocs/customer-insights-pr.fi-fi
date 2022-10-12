---
title: Asiakkaan elinkaaren arvon ennustaminen
description: Ennakoi aktiivisten asiakkaiden myyntituoton potentiaali tulevaisuudessa.
ms.date: 09/30/2022
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
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610370"
---
# <a name="predict-customer-lifetime-value-clv"></a>Asiakkaan elinkaaren arvon ennustaminen

Ennusta mahdollinen arvo (myyntituotto), jonka yksittäiset aktiiviset asiakkaat tuovat yritykselle tiettynä tulevana ajanjaksona. Tämän ennusteen avulla voidaan

- tunnistaa korkean lisäarvon asiakkaita ja käsitellä näitä merkityksellisiä tietoja
- luoda strategisia asiakassegmenttejä niiden mahdollisen arvon perusteella mukautettujen kampanjoiden ja kohdistetun myynnin, markkinoinnin ja tukitoimintojen suorittamista varten
- opastaa tuotekehitystä keskittymällä asiakkaan arvoa lisääviin ominaisuuksiin
- optimoida myynti- tai markkinointistrategian ja kohdistaa budjetti aiempaa tarkemmin asiakkaiden tavoittamiseksi
- tunnistaa ja palkita korkean lisäarvon asiakkaat kanta-asiakas- ja palkkio-ohjelmien avulla

määrittää, mitä asiakkaan elinkaaren arvo tarkoittaa liiketoiminnassa. Tapahtumiin perustuvia asiakkaan elinkaaren arvon ennusteita tuetaan. Asiakkaan ennustettu arvo perustuu liiketoimintatapahtumahistoriaan. Useita sellaisten mallien luontia kannattaa harkita, joissa on erilaisia syöttömäärityksiä. Mallien tuloksia vertailemalla nähdään, mikä malliskenaario vastaa parhaiten liiketoiminnan tarpeita.

> [!TIP]
> Asiakkaan elinkaaren arvoennustetta voi kokeilla näytetietojen avulla: [Asiakkaan elinkaariarvoennuste (CLV) esimerkkioppaassa](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>edellytykset

- Vähintään [osallistujan](permissions.md) käyttöoikeudet
- Vähintään 100 yksilöityä asiakasta, mielellään yli 10 000 asiakasta
- Asiakkaan tunnus on yksilöivä tunnus, joka yhdistää tapahtumat yksittäiseen asiakkaaseen
- Vähintään 1 ja mielellään 2–3 vuoden tapahtumahistoria. Mieluiten vähintään 2–3 tapahtumaa asiakastunnusta kohden, mielellään usealta päivältä. Tapahtumahistorian on sisällettävä seuraavat tiedot:
  - **Tapahtuman tunnus**: Kunkin tapahtuman yksilöivä tunnus
  - **Tapahtuman päivämäärä**: kunkin tapahtuman päivämäärä- tai aikaleima
  - **Tapahtuman summa**: Kunkin tapahtuman rahasumma (esimerkiksi myyntituotto tai katetuotto)
  - **Palautuksille määritetty otsikko**: totuusarvo, joka osoittaa, onko tapahtuma palautus
  - **Tuotetunnus**: tapahtumaan osallistuvan tuotteen tuotetunnus
- Tietoja asiakasaktiviteeteista:
  - **Perusavain**: aktiviteetin yksilöivä tunnus
  - **Aikaleima**: perusavaimen tunnistaman tapahtuman päivämäärä ja aika
  - **Tapahtuma (aktiviteetin nimi)**: käytettävän tapahtuman nimi
  - **Tiedot (summa tai arvo)**: Tietoja asiakasaktiviteettista
- Lisätiedot, kuten seuraavat:
  - Verkkoaktiviteetit: sivuston vierailuhistoria tai sähköpostihistoria
  - Kanta-asiakasaktiviteetit: kanta-asiakkuuden palkkiopisteiden kertymä- ja lunastushistoria
  - Asiakaspalveluloki: huoltokäynti-, valitus- tai palautushistoria
  - Asiakkaan profiilitiedot
- Vähintään 20 % arvoista puuttuu pakollisissa kentissä

> [!NOTE]
> Vain yksi tapahtumahistorian entiteetti voidaan määrittää. Jos osto- tai tapahtumaentiteettejä on useita, ne voidaan yhdistää Power Queryssä ennen tietojen käsittelyä.

## <a name="create-a-customer-lifetime-value-prediction"></a>Asiakkaan elinkaaren arvon ennusteen luominen

Ennuste voidaan tallentaa koska tahansa luonnoksena valitsemalla **Tallenna luonnos**. Ennusteluonnos näkyy **Omat ennusteet** -välilehdessä.

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Asiakkaan elinkaaren arvo** -ruudussa **Käytä mallia**.

1. Valitse **Aloita**.

1. **Anna tälle mallille** ja **tulosentiteetille nimi**, jotta ne voidaan erottaa muista malleista tai entiteeteistä.

1. Valitse **Seuraava**.

### <a name="define-model-preferences"></a>Malliasetusten määrittäminen

1. Määritä, milloin haluat ennustaa asiakkaan elinkaaren arvon, antamalla **Ennusteen ajanjakso** -kohdalle arvo. Oletusarvoisesti arvoksi määritetään kuukausia.

   > [!TIP]
   > Jotta asiakkaan elinkaaren arvo voidaan ennustaa määritetylle ajanjaksolle, vertailukauden historialliset tiedot ovat pakollisia. Jos esimerkiksi halutaan ennustaa asiakkaan elinkaaren arvon seuraavien 12 kuukauden jaksolle, tarvitaan 18–24 kuukauden historiatiedot.

1. Määritä aikaväli, jonka aikana asiakkaalla on oltava vähintään yksi tapahtuma, jotta asiakasta pidetään aktiivisena. Malli ennustaa vain **aktiivisten asiakkaiden** asiakkaan elinkaaren arvon.
   - **Salli mallin laskea ostoväli (suositus)**: malli analysoi tiedot ja määrittää ajanjakson ostohistorian perusteella.
   - **Määritä väli manuaalisesti**: Aktiivisen asiakkaan aikavälin määritys.

1. **Korkean arvon asiakkaan** prosenttipisteen määritys.
    - **Mallin laskenta (suositus)**: Mallissa käytetään 80/20-sääntöä. Niiden asiakkaiden prosenttiosuus, jotka ovat vaikuttaneet 80 prosenttiin yrityksen kumulatiivisesta myyntituotosta aiemman kauden aikana, pidetään korkean lisäarvon asiakkaina. Yleensä alle 30–40 prosenttia asiakkaista tuo 80 prosentin kumulatiivisen myyntituoton. Luku voi kuitenkin vaihdella yrityksen ja toimialan mukaan.
    - **Prosenttia aktiivisista asiakkaista**: Korkean arvon asiakkaan prosenttipiste. Esimerkiksi **25** määrittää ne 25 prosenttia korkean lisäarvon asiakkaista, jotka maksavat tulevaisuudessa eniten.

    Jos yrityksesi määrittää korkean lisäarvon asiakkaat eri tavalla, [kerro siitä meille](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Valitse **Seuraava**.

### <a name="add-required-data"></a>Lisää pakolliset tiedot

1. Valitse **Lisää tiedot** **Asiakkaan tapahtumahistoria** -kohdassa.

1. Valitse semanttinen aktiviteettityyppi **SalesOrder** tai **SalesOrderLine**, joka sisältää tapahtumahistorian. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty semanttisesti aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos semanttista yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Asiakkaan elinkaaren arvomalliin tarvittavien tietojen lisääminen":::

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Lisää enemmän aktiviteetteja ja valitse **Seuraava**.

### <a name="add-optional-activity-data"></a>Lisää valinnaiset aktiviteettitiedot

Tärkeisiin asiakastapahtumiin (kuten verkko-, asiakaspalvelu- ja tapahtumalokitapahtumat) liittyvät tiedot lisäävät tapahtumatietueisiin kontekstia. Mallien lisääminen asiakkaiden aktiivisuustietoihin voi parantaa ennusteiden tarkkuutta.

1. Valitsee **Lisää tiedot** **Paranna mallien merkityksellisiä tietoja lisätiedoilla aktiviteeteissa** -kohdassa.

1. Valitse aktiviteettityyppi, joka vastaa lisättävän asiakasaktiviteetin tyyppiä. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

1. Jos aktiviteetin määritteet on yhdistetty aktiviteettia luotaessa, valitse **Aktiviteetit**- kohdassa määritteet tai entiteetti, joihin laskelma keskittyy. Jos yhdistämismääritystä ei tehty, valitse **Muokkaa** ja yhdistä tiedot.

1. Valitse **Seuraava** ja tarkista mallissa tarvittavat määritteet.

1. Valitse **Tallenna**.

1. Valitse **Seuraava**.

1. [Lisää valinnaiset asiakastiedot](#add-optional-customer-data) tai valitse ensin **Seuraava** ja sitten [Päivitysaikataulun määrittäminen](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Valinnaisten asiakastietojen lisääminen

Valitse 18:sta yleisesti käytetystä asiakasprofiilimääritteestä, jotka sisällytetään mallin syötteenä. Nämä määritteet voivat johtaa yrityksen tarkoituksiin soveltuviin mukautettuihin, olennaisiin ja toimintaan sopiviin mallituloksiin.

Esimerkki: Contoso Coffee haluaa ennustaa asiakkaan elinkaariarvon kohdistaakseen tärkeille asiakkaille mukautetun tarjouksen, joka liittyy uuden espressokoneen lanseeraukseen. Contoso käyttää CLV-mallia ja lisää kaikki 18 asiakasprofiilimääritettä nähdäkseen, mitkä tekijät vaikuttavat sen tärkeimpiin asiakkaisiin. Contoso havaitsee asiakkaiden sijainnin olevan vaikuttavin tekijä näille asiakkaille.
Näiden tietojen avulla Contoso järjestää paikallisen tapahtuman, joka järjestetään espressokoneen lanseerausta varten, ja tekee yhteistyötä paikallisten toimittajien kanssa erikoistarjouksien ja erikoiskokemuksien tarjoamiseksi tapahtumassa. Ilman näitä tietoja Contoso on ehkä lähettänyt vain yleisiä markkinointisähköposteja eikä ole voinut mukauttaa näitä paikallisia asiakassegmenttejä tärkeimmille asiakkailleen.

1. Valitse **Lisää tiedot** **Paranna mallien merkityksellisiä tietoja lisätiedoilla asiakkaista** -kohdassa.

1. Valitse asiakkaan määritetietoihin yhdistävä yhdistetty asiakasprofiili valitsemalla **Entiteetti**-kohdassa **Asiakas: CustomerInsights**. Valitse **asiakastunnukseksi** **System.Customer.CustomerId**.

1. Yhdistä lisää kenttiä, jos tiedot ovat yhtenäisten asiakasprofiilien käytettävissä.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Esimerkki asiakasprofiilin tietojen yhdistetyistä kentistä.":::

1. Valitse **Tallenna**.

1. Valitse **Seuraava**.

### <a name="set-update-schedule"></a>Päivitysaikataulun määrittäminen

1. Valitse aikaväli, jonka mukaan mallia koulutetaan uudelleen uusimpien tietojen perusteella. Tämä asetus on tärkeä ennusteiden tarkkuuden päivittämiseksi, kun Customer Insightsissa käsitellään uusia tietoja. Useimmat yritykset voivat kouluttaa uudelleen kerran kuukaudessa ja saada hyvän tarkkuuden ennusteille.

1. Valitse **Seuraava**.

### <a name="review-and-run-the-model-configuration"></a>Mallimäärityksen tarkasteleminen ja suorittaminen

**Tarkistus ja suoritus** -vaiheessa näkyy määritysten yhteenveto. Siinä on myös mahdollista tehdä muutoksia ennen ennusteen luontia.

1. Tee tarkistukset ja tarvittavat muutokset valitsemalla **Muokkaa**.

1. Jos olet tyytyväinen valintoihin, aloita mallin suorittaminen valitsemalla **Tallenna ja suorita**. Valitse **Valmis**. **Omat ennusteet** -välilehti on näkyvissä, kun ennustetta luodaan. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ennusteen tulosten näyttäminen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Omat ennusteet** -välilehdessä tarkasteltava ennuste.

Tulossivulla on kolme ensisijaista tieto-osaa.

- **Koulutusmallin suorituskyky**: Luokka A, B tai C osoittaa ennusteen suorituskyvyn. Sen avulla voit päättää, käytetäänkö tulosentiteettiin tallennettuja tuloksia.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Kuva mallin pisteiden tietoruudusta, jossa luokka on A.":::

  Customer Insights arvioi, miten hyvin tekoälymalli ennusti suuren arvon asiakkaat perusmalliin verrattuna.

  Luokat määritetään seuraavien sääntöjen perusteella:
  - **A**, kun malli ennusti tarkasti vähintään 5 % enemmän korkean lisäarvon asiakkaita kuin perusmalli.
  - **B**, kun malli ennusti tarkasti 0-5 % enemmän korkean lisäarvon asiakkaita kuin perusmalli.
  - **C**, kun malli ennusti tarkasti vähemmän korkean lisäarvon asiakkaita kuin perusmalli.
  
  Avaa **Malliluokitus**-ruutu valitsemalla [**Lisätietoja tästä pisteytyksestä**](#learn-about-the-score). Tässä ruudussa on lisätietoja tekoälymallin suorituskyvystä ja perusmallista. Se antaa lisätietoja perustana olevan mallin suorituskykymittareista ja siitä, miten lopullinen mallin suorituskykyluokka johdettiin. Perusmallissa käytetään muuta kuin tekoälyyn perustuvaa tapaa laskea asiakkaan elinkaaren arvo ensisijaisesti asiakkaiden tekemien aiempien ostojen perusteella.

- **Asiakkaiden arvo prosenttiosuuden mukaan**: Pienen ja korkean arvon asiakkaat näytetään kaaviossa. Kun hiiren osoite on histogrammin palkkien päällä, näkyviin tulee kunkin ryhmän asiakkaiden määrä ja kyseisen ryhmän keskimääräinen asiakkaan elinkaaren arvo. Valinnaisesti voidaan [luoda asiakassegmenttejä](prediction-based-segment.md) asiakkaan elinkaaren arvon ennusteiden perusteella.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Asiakkaan elinkaaren arvomallin asiakkaiden arvo prosenttipisteen mukaan":::

- **Vaikuttavimmat tekijät**: Huomioon otetaan eri tekijöitä, kun asiakkaan elinkaaren arvon ennuste luodaan tekoälymallille annettujen syötetietojen perusteella. Kunkin tekijän tärkeys on laskettu mallin luomille yhdistellyille ennusteille. Näiden tekijöiden avulla voidaan tarkistaa ennusteen tulokset. Nämä tekijät antavat myös enemmän tietoja tekijöistä, jotka vaikuttivat eniten kaikkien asiakkaiden asiakkaan elinkaaren arvon ennustamiseen.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Asiakkaan elinkaaren arvomallin vaikuttavimmat tekijät":::

### <a name="learn-about-the-score"></a>Lisätietoja pistemäärästä

Vakiokaava, jonka avulla asiakkaan elinkaaren arvo lasketaan perusmallin mukaan:

 _**Asiakkaan elinkaaren arvo kullekin asiakkaalle** = Asiakkaan kuukauden keskimääräiset ostot aktiivisessa asiakasikkunassa * Asiakkaan elinkaaren arvon ennustejakson kuukausien määrä * Kaikkien asiakkaiden yleinen uskollisuusprosentti_

Tekoälymallia verrataan perusmalliin kahden mallin suorituskykymittareiden perusteella.
  
- **Korkean lisäarvon asiakkaiden ennustamisen onnistumisaste**

  Katso ero ennustettaessa korkean lisäarvon asiakkaat tekoälymallin ja perusmallin avulla. Esimerkiksi 84 prosentin onnistumisaste tarkoittaa sitä, että opetusmallin kaikista korkean lisäarvon asiakkaista tekoälymalli löysi 84 %. Tämän jälkeen onnistumisastetta verrataan perusmallin onnistumisasteeseen ja suhteellinen muutos raportoidaan. Tätä arvoa käytetään määritettäessä mallille luokka.

- **Virhemittarit**

  Mallin yleistä suorituskykyä voidaan tarkastella tulevien arvojen ennustamisen virheiden perusteella. Tämän virheen arvioinnissa käytetään neliöllistä keskiarvoa (root mean squared error, RMSE). RMSE on kvantitatiivisten tietojen mallin virheen mittauksen vakiomenetelmä. Tekoälymallin RMSE-arvoa verrataan perusmallin RMSE-arvoon. Lopuksi raportoidaan suhteellinen ero.

Tekoälymalli priorisoi asiakkaiden tarkan luokittelun sen mukaan, millaista lisäarvoa he tuovat yritykselle. Korkean lisäarvon asiakkaiden ennustamisessa käytetään siis vain onnistumisastetta. Sen avulla johdetaan mallin lopullinen luokka. RMSE-mittari on herkkä poikkeaville arvoille. Skenaarioissa, joissa pieni prosenttiosuus erittäin korkean ostoarvon omaavia asiakkaita, yleinen RMSE-mittari ei ehkä annan todellista kuvaa mallin suorituskyvystä.

[!INCLUDE [footer-include](includes/footer-banner.md)]
