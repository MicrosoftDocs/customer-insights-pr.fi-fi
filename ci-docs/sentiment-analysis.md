---
title: Asiakaspalautteen asenteen analysointi (esiversio)
description: Tietoja asenneanalyysimallin käyttämisestä Dynamics 365 Customer Insightsin asiakaspalautteessa.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610461"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Asiakaspalautteen asenteen analysointi (esiversio)

Asenneanalyysin avulla voidaan tehdä asiakkaan asennesynteesi ja määrittää liiketoiminnan osia parannusmahdollisuuksiksi. Tämä Customer Insights -ominaisuus auttaa hahmottamaan, mikä toimii ja mitä on kehitettävä. Se voi edistää liiketoimintoja, joihin perustuvat kokemukset voivat parantaa asiakastyytyväisyyttä ja -uskollisuutta.

## <a name="overview"></a>Yleiskuvaus

Asenneanalyysiominaisuus luo kaksi asiakastunnuskohtaista johdettua merkityksellistä tietoa. Asennepisteytys (-5...5) ja soveltuvat liiketoiminnan alueet parantavat yhdessä käytettyinä asiakaspalautteen hahmottamista.

Tämän analyysin avulla voidaan tehdä seuraavaa:
- Yleiskuvaus brändiä tai organisaatiota koskevista asiakkaiden asenteista
- Niiden asiakkaiden tunnistaminen, joilla on negatiivinen asenne, sekä kampanjoiden ja aktivoinnin keskittäminen ja tuoton optimointi niiden perusteella  
- Asiakkaiden osoittamien liiketoiminnan ongelma-alueiden määrittäminen  
- Asiakkaiden segmentointi asenteen perusteella sekä mukautettujen kampanjoiden suorittaminen näiden tietojen perusteella kohdistamalla myynti, markkinointi ja tuki
- Liiketoimintojen optimointi käsittelemällä asiakkaiden mainitsemat alueet, joihin liittyy ongelmia tai mahdollisuuksia
- Hyvin toimien liiketoiminta-alueiden tunnistaminen sekä tyytyväisten asiakkaiden palkitseminen kanta-asiakas- ja korotusongelmien avulla

Malli tuottaa luettelon sanoista, jotka vaikuttavat mallin päätökseen määrittää tietty asennepisteytys tai liiketoiminta-alue palautteen kommentteihin.  

Käytössä on kaksi **luonnollisen kielen käsittelymallia (NLP-mallia)**: Ensimmäinen malli määrittä kullekin palautekommentille asennepisteet. Toinen malli liittää kunkin palautteen kaikkiin soveltuviin liiketoiminnan alueeseen. Mallien koulutukseen käytetään julkisia, erilaisista lähteistä saatavia tietoja. Näitä lähteitä ovat yhteisöpalvelu sekä jälleenmyynti-, ravintola- ja kuluttajatuotealat sekä autoteollisuus.
  
Mallin palautetietoihin liitettäviä esimääritettyjä liiketoiminnan alueita ovat esimerkiksi seuraavat:
- Asiakashallinta
- Uloskuittaus ja maksu
- Asiakastuki
- Noudot myymälästä
- Pakkauksen toimitus ja nouto
- Ennakkotilaukset
- Hinta
- Tietoturva ja tietosuoja
- Kampanjat ja palkkiot
- Kuitti ja takuu
- Palautusten vaihto ja peruutus
- Täytäntöönpanojen tarkkuus
- Sivuston/sovelluksen laatu

> [!NOTE]
> Tällä hetkellä tuetaan vain englanninkielisen palautteen asenneanalyysia. Jatkossa tuetaan myös muita kieliä. Malli palauttaa tulokset myös silloin, jos ladataan muun kielistä palautetta. Nämä tulokset eivät kuitenkaan ole tarkkoja.

## <a name="prerequisites"></a>edellytykset

- Vähintään [osallistujan käyttöoikeudet](permissions.md)
- [Yhdistetyn](data-unification.md) tekstimuotoiset palautetiedot. On erittäin suositeltavaa, että [palautetietoentiteetit määritetään semanttistyyppisinä aktiviteettientiteetteinä](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (palautetyyppi).
- Tietojen yhtenäistämisestä saatu yhtenäistetty asiakastunnus (UCID), jonka avulla tekstimuotoiset palautetietotietueet voidaan kohdistaa yksittäiseen asiakkaaseen.
- Palautteen tunnus
- Palautteen aikaleima
- Palautteen teksti

Customer Insights voi käsitellä enintään 10 miljoonaa palautetietuetta yhtä mallia suoritettaessa. Malli voi analysoida enintään 128 sanaa sisältäviä palautekommentteja. Jos palautekommentti on tätä pidempi, analyysi ottaa huomioon vain ensimmäiset 128 sanaa.

> [!NOTE]
> Vain yksi palaute-entiteetti voidaan määrittää. Jos palaute-entiteettejä on useita, ne yhdistetään Power Queryssä ennen tietojen käsittelyn alkamista.

## <a name="configure-a-sentiment-analysis"></a>Asenneanalyysin määrittäminen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Luo**-välilehden **Asiakkaan asenneanalyysi (esiversio)** -ruudussa **Käytä mallia**.

1. Valitse **Aloita**.

1. Anna ensin analyysille **nimi** sekä sitten **Liiketoimintanäkökulman tulosentiteetin nimi** ja **Asennepisteytyksen tulosentiteetin nimi**.

1. Valitse **Seuraava**.

1. Valitse **Lisää tiedot** **Asiakaspalaute**-kohdassa.

1. Valitse semanttisen aktiviteetin tyypiksi palautetiedot sisältävä **Palaute**. Jos aktiviteettia ei ole määritetty, valitse **täällä** ja luo se.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Määrityksen asenneanalyysin palauteaktiviteettien valintavaihe":::

1. Valitse asenneanalyysissa käytettävät aktiviteetit ja valitse sitten **Seuraava**.

1. Yhdistä tietojen määritteet mallin määritteisiin. 

1. Valitse **Tallenna**.

1. Valitse **Seuraava**. **Tarkistus ja suoritus** -vaiheessa näkyy määritysten yhteenveto. Siinä on myös mahdollista tehdä muutoksia ennen analyysin luontia.

1. Tee tarkistukset ja tarvittavat muutokset valitsemalla **Muokkaa**.

1. Jos olet tyytyväinen valintoihin, aloita mallin suorittaminen valitsemalla **Tallenna ja suorita**. Valitse **Valmis**. **Omat ennusteet** -välilehti on näkyvissä, kun ennustetta luodaan. Prosessin valmistumiseen voi kulua useita tunteja ennusteessa käytettyjen tietojen määrästä riippuen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Analyysin tulosten näyttäminen

1. Siirry kohteeseen **Tiedustelu** > **Ennusteet**.

1. Valitse **Omat ennusteet** -välilehdessä tarkasteltava ennuste.

Tulosvälilehtiä on kaksi.

### <a name="sumary-tab"></a>Yhteenveto-välilehti

Tiedot jakaantuvat tulossivulla neljään pääosaan.

- **Keskimääräinen asennepisteytys**: asennepisteytys auttaa hahmottamaan kaikkien asiakkaiden yleisen asenteen.
  - **Kielteinen** (-5 > 2)
  - **Neutraali** (-1 > 1)
  - **Myönteinen** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Asiakkaiden yleisen asenteen visuaalinen esitys":::

- **Asiakasjakauma asennepisteytyksen mukaan**: Asiakkaat luokitellaan asennepisteytyksen mukaan kielteiseen, neutraaliin ja myönteiseen ryhmään. Asiakkaiden määrän ja keskimääräisen asennepisteytyksen saa näkyviin kussakin ryhmässä siirtämällä kohdistimen pylväiden päälle histogrammissa. Näiden tietojen avulla voidaan [luoda asiakassegmenttejä](prediction-based-segment.md) asennepisteytyksen perusteella.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Pylväskaavio ilmaisee asiakkaan asenteen kolmessa asenneryhmässä":::

- **Keskimääräinen asennepisteytys ajan kuluessa**: Asiakkaan asenne voi muuttua ajan kuluessa. Näkyvissä on asiakkaiden trendit tietojen aikaväliltä. Tämä näkymä auttaa mittaamaan kausikampanjoiden, tuotejulkistusten tai muiden aikasidonnaisten tapahtumien vaikutusta asiakkaan asenteeseen. Kaaviota voi katsoa valitsemalla vuoden avattavasta valikosta.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historiakaavio sekä viivana ilmaistu asennepisteytys ajan mittaan":::

- **Asenne liiketoiminnan alueilla**: Keskimääräinen asenne liiketoiminnan alueilla auttaa mittaamaan, mihin liiketoiminnan alueisiin asiakkaat ovat jo tyytyväisiä tai mihin on kiinnitettävä enemmän huomiota. Jos palautetietue ei sovi mihinkään tuettuun liiketoiminnan alueeseen, se sijoitetaan luokkaan **Muut**. Tiedot lajitellaan valitsemalla jokin sarake.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Luettelo liiketoiminnan alueista ja niihin liittyvästä asennearvosta sekä alueen mainitsevien asiakkaiden määrä":::

  Kun liiketoiminnan alueen nimi valitaan, näkyviin tulee tietoja siitä, miten malli määrittää liiketoiminnan alueen:

  - **Vaikuttavat sanat**: tärkeimmät sanat, jotka vaikuttivat siihen, miten tekoälymalli tunnistaa liiketoiminnan alueen asiakkaan palautteessa.
    **Näytä kirosanat**: Kirosanat voidaan sisällyttää luetteloon, joka saadaan alkuperäisistä asiakaspalautetiedoista. Se on oletusarvoisesti poistettu käytöstä.  Tekoälymalli toteuttaa kirosanojen peiton, eikä se ehkä havaitse kaikki kirosanoja. Odotusten vastaisesti havaittu kirosana kannattaa ilmoittaa Microsoftille.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Luettelo vaikuttavista sanoista sekä vaihtopainike, jolla kirosanat näytetään tai piilotetaan":::

  - **Palautenäytteet**: Tietojen varsinaiset palautetietueet. Sanat on värikoodattu sen mukaan, kuinka vaikuttavia ne ovat liiketoiminnan alueen tunnistamisessa.

### <a name="influential-words-analysis-tab"></a>Vaikuttavien sanojen analyysi -välilehti

Asennemallin toimintaa selittäviä lisätietoja on kolmessa osassa.
  
- **Myönteiseen asenteeseen eniten vaikuttavat sanat**: sanat, jotka vaikuttivat eniten siihen, että tekoälymalli tunnistaa myönteisen asenteen asiakaspalautteessa.  

- **Kielteiseen asenteeseen eniten vaikuttavat sanat**: sanat, jotka vaikuttivat eniten siihen, että tekoälymalli tunnistaa kielteisen asenteen asiakaspalautteessa.

- **Palautenäytteet**: varsinaiset palautetietueet, joissa yhdessä on kielteinen asenne ja toisessa myönteinen asenne. Sanat on korostettu palautetietueissa sen perusteella, miten ne vaikuttavat määritettyyn asennepisteytykseen. Myönteiseen pisteytykseen vaikuttavat sanat on korostettu vihreällä. Kielteiseen pisteytykseen vaikuttavat sanat on korostettu punaisella.
   Lisää palautenäytteitä voidaan ladata valitsemalla **Näytä enemmän**.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Esimerkkejä asiakaspalautteen asenneanalyysista":::

**Näytä kirosanat**: Kirosanat voidaan sisällyttää luetteloon, joka saadaan alkuperäisistä asiakaspalautetiedoista. Se on oletusarvoisesti poistettu käytöstä.  Tekoälymalli toteuttaa kirosanojen peiton, eikä se ehkä havaitse kaikki kirosanoja. Odotusten vastaisesti havaittu kirosana kannattaa ilmoittaa Microsoftille.

## <a name="act-on-analysis-results"></a>Analyysitulosten perusteella toimiminen

Asenneanalyysin tuloksista voi luoda uusia asiakassegmenttejä valitsemalla **Luo segmenttejä** mallin tulossivun yläosassa.

## <a name="potential-bias"></a>Mahdolliset ennakkokäsitykset

Samoin kuin muissa ennakoivaa tekoälyä käyttävissä ominaisuuksissa ne tiedot, joita käytetään asiakkaan asenteen ennustamiseen, voivat sisältää ennakkokäsityksiä. Jos palautetta esimerkiksi kerätään vain digitaalisesti, on mahdollista, että käytössä ei ole palautetta asiakkailta, jotka käyttävät henkilökohtaisia palveluja, ja tämä voi vaikuttaa ominaisuuden tulokseen.

Koska tämä ominaisuus sekä arvioi tietoja että tekee ennusteita näiden tietojen perusteella automaattisesti, sitä on mahdollista käyttää profilointiin siinä mielessä kuin profilointi on määritetty yleisessä tietosuoja-asetuksessa (GDPR-asetuksessa). Jos tätä ominaisuutta käytetään tietojen käsittelemiseen, siihen sovelletaan GDPR-määrityksiä tai muita lakeja ja säännöksiä. Käyttäjä on vastuussa siitä, että Dynamics 365 Customer Insightsia asenneanalyysi mukaan lukien käytetään kaikkien sovellettavien lakien ja määräysten mukaisesti. Tämä koskee myös tietosuojaan, henkilökohtaisiin tietoihin, biometrisiin tietoihin, tietoturvaan ja viestinnän luottamuksellisuuteen liittyviä lakeja.

[!INCLUDE [footer-include](includes/footer-banner.md)]

